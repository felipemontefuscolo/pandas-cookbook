# pandas-cookbook

Good references:
* https://www.tutorialspoint.com/python_pandas/index.htm

## daily aggregations
```python
index=[pd.Timestamp('2016-06-06 01:01:01'),
       pd.Timestamp('2016-06-06 05:05:05'),
       pd.Timestamp('2016-06-07 02:02:02'),
       pd.Timestamp('2016-06-07 06:06:06')]
a = pd.DataFrame({'A': [1. , 2., 3., 4.]}, index=index)
# sum method 1:
a.groupby(lambda x: x.date()).agg(lambda x: x.sum())
# sum method 2:
a.resample('D').sum()
```
result:
```
              A
2016-06-06  3.0
2016-06-07  7.0
```
