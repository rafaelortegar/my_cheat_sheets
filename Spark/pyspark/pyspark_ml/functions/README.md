## Converting a DenseVector column to an array_column
There is a function to convert a Dense Vector to an array after doing a pyspark.ml transformation:
```python
from pyspark.ml.functions import vector_to_array

df1 = df.select(vector_to_array("vec_column").alias("vec_column"),
                vector_to_array("array_column").alias("array_column"))
```
This could be used when getting the following error: `IllegalArgumentException: Column must be of type struct<type:tinyint,size:int,indices:array<int>,values:array<double>> but was actually double.'`
