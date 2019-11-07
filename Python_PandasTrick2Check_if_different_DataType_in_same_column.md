
# How to check if same column has different data types


```python
import pandas as pd
```


```python
df = pd.DataFrame({ 'Customer': ['A','B','C','D'],
                    'Sales':['3',4,'5',200.15]},
                    index=[0,1,2,3]) # if you don't pass an index, pandas will assign default index
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Customer</th>
      <th>Sales</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>4</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>D</td>
      <td>200.15</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.Sales.apply(type)
```




    0      <class 'str'>
    1      <class 'int'>
    2      <class 'str'>
    3    <class 'float'>
    Name: Sales, dtype: object




```python
df.Sales.apply(type).value_counts() # THis is important as you cannot keep a check if DataFrame is huge
```




    <class 'str'>      2
    <class 'int'>      1
    <class 'float'>    1
    Name: Sales, dtype: int64


