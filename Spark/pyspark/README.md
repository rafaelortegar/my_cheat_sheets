* [PySpark split() Column into Multiple Columns](https://sparkbyexamples.com/pyspark/pyspark-split-dataframe-column-into-multiple-columns/)
* [Sum a column in dataframe and return results as int](https://stackoverflow.com/questions/47812526/pyspark-sum-a-column-in-dataframe-and-return-results-as-int)


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
