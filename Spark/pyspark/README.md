* [PySpark split() Column into Multiple Columns](https://sparkbyexamples.com/pyspark/pyspark-split-dataframe-column-into-multiple-columns/)
* [Sum a column in dataframe and return results as int](https://stackoverflow.com/questions/47812526/pyspark-sum-a-column-in-dataframe-and-return-results-as-int)
* [Extracting, transforming and selecting features](https://spark.apache.org/docs/latest/ml-features)
* [Feature Engineering in pyspark](https://dhiraj-p-rai.medium.com/essentials-of-feature-engineering-in-pyspark-part-i-76a57680a85)
* [Get specific row from PySpark dataframe](https://www.geeksforgeeks.org/get-specific-row-from-pyspark-dataframe/)

drop column by name
```python
df.drop(col("firstname"))
```

list of unique values from column:
```python
unique_list = [i.variable for i in df.select('variable').distinct().collect()]
```


filter df with elements of dict:
```python
filtered_df = df.filter(F.col('col_name').isin(dict_name['dict_element_name']))
```

filter df with elements of list:
```python
filtered_df = df.filter(F.col('col_name').isin(list_name))
```
or
```python
filtered_df.where((filtered_df.col_name).isin(list_name))
```


Join 2 df's:
```python
df_joined = df_orig.join(df_to_join, on=join_cols, how='left')
```


renaming a column:
```python
df = df.withColumnRenamed(column_name, new_column_name)
```

copy a column:
```python
df = df.withColumn("new_column_name", df["column_name"])
```

change columns data type:
```python
df = df.withColumn("column_name", df["column_name"].cast(IntegerType()))
```

select columns:
```python
df_selected_cols = df_original.select('cols_to_select')
```

get columns data types:
```python
df.dtypes
```

get elements type on list:
```python
from collections import Counter

Counter([type(value) for value in lista])
```

delete NoneType element from list:
```python
res = list(filter(None, lista))
```

convert pyspark DF to Pandas DF:
```python
pandas_df = pyspark_df.toPandas()
```

convert Pandas DF to Pyspark DF:
```python
sparkDF=spark.createDataFrame(pandasDF) 
```

add a column with value depending of whether the value is in list or not

```python
prueba = (
    df
    .withColumn("new_col_name",sf.when(sf.col(col_name).isin(list_name),"value to assign").otherwise("value if not true") )
) 
```

or

```python
prueba = (
    df
    .withColumn("new_col_name",sf.when(sf.col(col_name).isin(list_name),"value to assign").otherwise(sf.col(col_name) )
) 
```

Filter by column value
```python
df.filter(sf.col('column_name')==value_looking_for)
```

from [stackoverflow](https://stackoverflow.com/questions/40421845/pyspark-dataframe-filter-or-include-based-on-list)
```python
def filter_spark_dataframe_by_list(df, column_name, filter_list):
    """ Returns subset of df where df[column_name] is in filter_list """
    spark = SparkSession.builder.getOrCreate()
    filter_df = spark.createDataFrame(filter_list, df.schema[column_name].dataType)
    return df.join(filter_df, df[column_name] == filter_df["value"])
```

get table with unique count elements
from [stackoverflow](https://stackoverflow.com/questions/40888946/spark-dataframe-count-distinct-values-of-every-column)
```python
from pyspark.sql.functions import col, countDistinct

df.agg(*(countDistinct(col(c)).alias(c) for c in df.columns))
```

get Dummies on pyspark
from [stackoverflow](https://stackoverflow.com/questions/42805663/e-num-get-dummies-in-pySpark)
```python
pivot_cols = ['TYPE','CODE']
keys = ['ID','TYPE','CODE']

before = sc.parallelize([(1,'A','X1'),
                         (2,'B','X2'),
                         (3,'B','X3'),
                         (1,'B','X3'),
                         (2,'C','X2'),
                         (3,'C','X2'),
                         (1,'C','X1'),
                         (1,'B','X1')]).toDF(['ID','TYPE','CODE'])                         

#Helper function to recursively join a list of dataframes
#Can be simplified if you only need two columns
def join_all(dfs,keys):
    if len(dfs) > 1:
        return dfs[0].join(join_all(dfs[1:],keys), on = keys, how = 'inner')
    else:
        return dfs[0]

dfs = []
combined = []
for pivot_col in pivot_cols:
    pivotDF = before.groupBy(keys).pivot(pivot_col).count()
    new_names = pivotDF.columns[:len(keys)] +  ["e_{0}_{1}".format(pivot_col, c) for c in pivotDF.columns[len(keys):]]        
    df = pivotDF.toDF(*new_names).fillna(0)    
    combined.append(df)

join_all(combined,keys).show()
```

Split Time Series pySpark data frame into test & train without using random split
from [stackoverflow](https://stackoverflow.com/questions/51772908/split-time-series-pyspark-data-frame-into-test-train-without-using-random-spli)
```python
from pyspark.sql.functions import percent_rank
from pyspark.sql import Window

df = df.withColumn("rank", percent_rank().over(Window.partitionBy().orderBy("date")))
```


Count every element of unique values on pyspark column:
```python
df.groupBy('col_name').count().show()
```
[good guide](https://www.analyticsvidhya.com/blog/2019/11/build-machine-learning-pipelines-pyspark/)
[categ_guide](https://www.analyticsvidhya.com/blog/2015/11/easy-methods-deal-categorical-variables-predictive-modeling/?utm_source=blog&utm_medium=build-machine-learning-pipelines-pyspark)


Get dummies for pyspark:
```python
def get_dummies(dataframe, column_name):

    import pyspark.sql.functions as F
    
    list_values = [dataframe.select(column_name).distinct().collect()[i][0] for i in range(0, dataframe.select(column_name).distinct().count())]
    dummies_col = [F.when(F.col(column_name) == value, 1).otherwise(0).alias("{}_{}".format(column_name, value)) for value in list_values]
    
    return dataframe.select(column_name, *dummies_col)
```


Get dummies for pyspark **my version**:
```python
def pyspark_get_dummies(dataframe, columns_to_one_hot_encode):
    
    for pivot_col in columns_to_one_hot_encode:
        keys = dataframe.columns
        keys.remove(pivot_col)
        pivotDF = dataframe.groupBy(keys).pivot(pivot_col).count()
        pivoted_columns = pivotDF.columns
        added_columns = [i for i in pivoted_columns if i not in keys]
        added_columns

        pivotDF = pivotDF.fillna(0, subset=added_columns)

        for added_col in added_columns:
            pivotDF = pivotDF.withColumnRenamed(added_col,(pivot_col+"_"+added_col))
    
    return pivotDF
```

fill na for specific columns:
```python
df = df.fillna(0, subset=['colname_a', 'colname_b'])
```

Add column with count of zeros by row
```python
df.withColumn(
    "count",
    sum([
            F.when(F.col(cl) != 0, 1).otherwise(0) for cl in df.columns[1:]
    ])
).show()
```

Split a vector/list in a pyspark DataFrame into columns
```python
import pyspark.sql.functions as F

df2 = df.select([F.col("Col_name")[i] for i in df.columns])
df2.show()
```

Ways to get the max value of a column:
```python
# Method 1: Use describe()
float(df.describe("A").filter("summary = 'max'").select("A").collect()[0].asDict()['A'])

# Method 2: Use SQL
df.registerTempTable("df_table")
spark.sql("SELECT MAX(A) as maxval FROM df_table").collect()[0].asDict()['maxval']

# Method 3: Use groupby()
df.groupby().max('A').collect()[0].asDict()['max(A)']

# Method 4: Convert to RDD
df.select("A").rdd.max()[0]
```
