```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
ver_python = !python --version
ver_numpy = np.__version__
ver_pandas = pd.__version__
```


```python
print(f'Python: Version {ver_python} \nNumpy: Version {ver_numpy} \nPandas: Version {ver_numpy}')
```

    Python: Version ['Python 3.9.19'] 
    Numpy: Version 1.26.4 
    Pandas: Version 1.26.4
    


```python
df = pd.read_csv('./dataset/car_evaluation.csv')
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
      <th>price</th>
      <th>maint</th>
      <th>doors</th>
      <th>persons</th>
      <th>lug_capacity</th>
      <th>safety</th>
      <th>output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>small</td>
      <td>low</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>1</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>small</td>
      <td>med</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>2</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>small</td>
      <td>high</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>3</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>med</td>
      <td>low</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>4</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>med</td>
      <td>med</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1723</th>
      <td>low</td>
      <td>low</td>
      <td>5more</td>
      <td>more</td>
      <td>med</td>
      <td>med</td>
      <td>good</td>
    </tr>
    <tr>
      <th>1724</th>
      <td>low</td>
      <td>low</td>
      <td>5more</td>
      <td>more</td>
      <td>med</td>
      <td>high</td>
      <td>vgood</td>
    </tr>
    <tr>
      <th>1725</th>
      <td>low</td>
      <td>low</td>
      <td>5more</td>
      <td>more</td>
      <td>big</td>
      <td>low</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>1726</th>
      <td>low</td>
      <td>low</td>
      <td>5more</td>
      <td>more</td>
      <td>big</td>
      <td>med</td>
      <td>good</td>
    </tr>
    <tr>
      <th>1727</th>
      <td>low</td>
      <td>low</td>
      <td>5more</td>
      <td>more</td>
      <td>big</td>
      <td>high</td>
      <td>vgood</td>
    </tr>
  </tbody>
</table>
<p>1728 rows × 7 columns</p>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1728 entries, 0 to 1727
    Data columns (total 7 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   price         1728 non-null   object
     1   maint         1728 non-null   object
     2   doors         1728 non-null   object
     3   persons       1728 non-null   object
     4   lug_capacity  1728 non-null   object
     5   safety        1728 non-null   object
     6   output        1728 non-null   object
    dtypes: object(7)
    memory usage: 94.6+ KB
    


```python
df.describe()
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
      <th>price</th>
      <th>maint</th>
      <th>doors</th>
      <th>persons</th>
      <th>lug_capacity</th>
      <th>safety</th>
      <th>output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1728</td>
      <td>1728</td>
      <td>1728</td>
      <td>1728</td>
      <td>1728</td>
      <td>1728</td>
      <td>1728</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>4</td>
      <td>4</td>
      <td>4</td>
      <td>3</td>
      <td>3</td>
      <td>3</td>
      <td>4</td>
    </tr>
    <tr>
      <th>top</th>
      <td>vhigh</td>
      <td>vhigh</td>
      <td>2</td>
      <td>2</td>
      <td>small</td>
      <td>low</td>
      <td>unacc</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>432</td>
      <td>432</td>
      <td>432</td>
      <td>576</td>
      <td>576</td>
      <td>576</td>
      <td>1210</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns
```




    Index(['price', 'maint', 'doors', 'persons', 'lug_capacity', 'safety',
           'output'],
          dtype='object')




```python
'''
| price        | 가격
| maint        | 유지비 maintenance costs 
| doors        | 문 개수
| persons      | 탑승 가능 인원
| lug_capacity | 수화물 적재 용량 luggage capacity
| safety       | 안정성
| output       | 차 상태
'''
```




    '\n| price        | 가격\n| maint        | 유지비 maintenance costs \n| doors        | 문 개수\n| persons      | 탑승 가능 인원\n| lug_capacity | 수화물 적재 용량 luggage capacity\n| safety       | 안정성\n| output       | 차 상태\n'




```python
# missing value 확인
df.isnull().sum()
```




    price           0
    maint           0
    doors           0
    persons         0
    lug_capacity    0
    safety          0
    output          0
    dtype: int64




```python
pd.unique(df['output'])

# unacceptable, acceptable, verygood, good
```




    array(['unacc', 'acc', 'vgood', 'good'], dtype=object)




```python
# label count 확인 by graph
sns.countplot(data=df, x='output')
plt.xlabel('outputs')
plt.ylabel('count')
plt.title('label')
plt.show()
```


    
![png](output_10_0.png)
    



```python
# label count 확인 by numeric
df['output'].value_counts()
```




    output
    unacc    1210
    acc       384
    good       69
    vgood      65
    Name: count, dtype: int64




```python
# correlation 확인 <- dtype이 object일 때는 불가능 함
df_corr = df.corr()
plt.figure(figsize=(10, 10))
sns.set(font_scale=0.8)
sns.heatmap(df_corr, annot=True, cbar=False)
plt.show()
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[29], line 2
          1 # correlation 확인
    ----> 2 df_corr = df.corr()
          3 plt.figure(figsize=(10, 10))
          4 sns.set(font_scale=0.8)
    

    File ~\miniconda3\envs\gc_ml_scratch\lib\site-packages\pandas\core\frame.py:11049, in DataFrame.corr(self, method, min_periods, numeric_only)
      11047 cols = data.columns
      11048 idx = cols.copy()
    > 11049 mat = data.to_numpy(dtype=float, na_value=np.nan, copy=False)
      11051 if method == "pearson":
      11052     correl = libalgos.nancorr(mat, minp=min_periods)
    

    File ~\miniconda3\envs\gc_ml_scratch\lib\site-packages\pandas\core\frame.py:1993, in DataFrame.to_numpy(self, dtype, copy, na_value)
       1991 if dtype is not None:
       1992     dtype = np.dtype(dtype)
    -> 1993 result = self._mgr.as_array(dtype=dtype, copy=copy, na_value=na_value)
       1994 if result.dtype is not dtype:
       1995     result = np.asarray(result, dtype=dtype)
    

    File ~\miniconda3\envs\gc_ml_scratch\lib\site-packages\pandas\core\internals\managers.py:1688, in BlockManager.as_array(self, dtype, copy, na_value)
       1686     arr = np.asarray(blk.values, dtype=dtype)
       1687 else:
    -> 1688     arr = np.array(blk.values, dtype=dtype, copy=copy)
       1690 if using_copy_on_write() and not copy:
       1691     arr = arr.view()
    

    ValueError: could not convert string to float: 'vhigh'



```python
for feature in df.columns[:-1]: # 마지막 column인 'output'은 제외
    # 각 feature의 unique 출력
    print(f'{feature}({df[feature].dtype}): {pd.unique(df[feature])}')

# 6개의 features 모두 nominal type이다.
# cf. category가 2개만 있을 때는 binary type이라고 한다
```

    price(object): ['vhigh' 'high' 'med' 'low']
    maint(object): ['vhigh' 'high' 'med' 'low']
    doors(object): ['2' '3' '4' '5more']
    persons(object): ['2' '4' 'more']
    lug_capacity(object): ['small' 'med' 'big']
    safety(object): ['low' 'med' 'high']
    


```python
df['price'].astype('category')
```




    0       vhigh
    1       vhigh
    2       vhigh
    3       vhigh
    4       vhigh
            ...  
    1723      low
    1724      low
    1725      low
    1726      low
    1727      low
    Name: price, Length: 1728, dtype: category
    Categories (4, object): ['high', 'low', 'med', 'vhigh']


