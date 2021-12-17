* [PySpark split() Column into Multiple Columns](https://sparkbyexamples.com/pyspark/pyspark-split-dataframe-column-into-multiple-columns/)
* [Sum a column in dataframe and return results as int](https://stackoverflow.com/questions/47812526/pyspark-sum-a-column-in-dataframe-and-return-results-as-int)


list of unique values from column:
```python
unique_list = [i.variable for i in df.select('variable').distinct().collect()]
```


filter df with elements of dict:
```python
filtered_df = df.filter(sf.col('col_name').isin(dict_name['dict_element_name']))
```


Join 2 df's:
```python
df_joined = df_orig.join(df_to_join, on=join_cols, how='left')
```


renaming a column:
```python
df = df.withColumnRenamed(column_name, new_column_name)
```
