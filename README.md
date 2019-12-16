# -
import pandas

df = pandas.read_csv('C:/Users/Gram/Desktop/학교/2학년/2-2수업/오픈소스/doit_pandas-master/notebook/cat_info.csv', sep='\t')

import pandas as pd

df = pd.read_csv('C:/Users/Gram/Desktop/학교/2학년/2-2수업/오픈소스/doit_pandas-master/notebook/cat_info.csv', sep='\t')

print(df.head())
print(type(df))
print(df.shape)
print(df.columns)
print(df.dtypes)
print(df.info())

cat = pd.read_csv('C:/Users/Gram/Desktop/학교/2학년/2-2수업/오픈소스/doit_pandas-master/notebook/cat_info.csv')

cat_long = pd.melt(cat, id_vars=['animal_id', 'breed', 'color', 'sex', 'Cat/Kitten'], var_name='range',value_name='days')
print(cat_long.shape)
print(cat_long.head())

cat_sub=cat_long[['animal_id', 'breed', 'color', 'sex', 'Cat/Kitten']]
print(cat_sub.shape)
print(cat_long.groupby('breed')['days'].mean())

%matplotlib inline
import matplotlib.pyplot as plt

cat_breed_days=cat_long.groupby('breed')['days'].mean()
print(cat_breed_days)
cat_breed_days.plot()

cat_sex_days=cat_long.groupby('sex')['days'].mean()
print(cat_sex_days)
cat_sex_days.plot()

cat_CK_days=cat_long.groupby('Cat/Kitten')['days'].mean()
print(cat_CK_days)
cat_CK_days.plot()
