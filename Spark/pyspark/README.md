* [PySpark split() Column into Multiple Columns](https://sparkbyexamples.com/pyspark/pyspark-split-dataframe-column-into-multiple-columns/)
* [Sum a column in dataframe and return results as int](https://stackoverflow.com/questions/47812526/pyspark-sum-a-column-in-dataframe-and-return-results-as-int)


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
