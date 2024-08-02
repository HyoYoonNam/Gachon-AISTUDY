# Table of contents
[Introduction](#introduction)  
[Object dtype](#object-dtype)  
[Category dtype](#category-dtype)  
[How to convert dtype of pandas.dataframe](#how-to-convert-dtype-of-pandas-dataframe)

# Introdction
In pandas, `object` and `category` are bothe data types that can be used to store **categorical data**, but they have significant differences in how they are represented and used. 
Understanding these differences is crucial for optimizing performance and memory usage in your data analysis tasks.  


# Object dtype
**Representation:**  
* The `object` dtype in pandas is a **general-purpose type that can hold any kind of Python object**. This is commonly used for text(string) data.

**Memory Usage:**  
* Since each element in an `object` column can be any Python object, it often requires more memory. Each value is stored as a separate Python object.

**Performance:**  
* Operations on `object` columns are generally slower compared to other dtypes due to the overhead of Python objects.

**Flexibility:**  
* Very flexible as it can hold any data type. However, this flexibility comes at the cost of increased memory usage and slower performance.


# Category dtype
**Representation:**  
* The `category` dtype is **specifically designed for categorical data**. It stores data as a fixed set of categories, **each of which is represented by an integer**.
  The actual data is stored as an integer array and a mapping of the integers to the categories.

**Memory Usage:**  
* More memory efficient than `object`. Only the categories are stored as objects, and **the acutal data is stored as integers**.

**Performance:**  
* Operations on `category` columns are typically faster than on `object` columns because comparisons are done on integer codes rather than objects.


# How to convert dtype of pandas.dataframe
csv나 excel 등의 dataset을 pandas.dataframe으로 불러왔을 때 기본적으로 numerical하지 않은 categorical data는 `object` dtype을 사용하게 된다.  
dataset의 features나 label이 numerical하지 않으면 이후에 많은 제약이 발생하기 때문에 이를 numerical하게 변경해야 한다.  

```python
import pandas as pd

df = pd.read_csv('https://raw.githubusercontent.com/gilbutITbook/080289/main/chap02/data/car_evaluation.csv')
```
