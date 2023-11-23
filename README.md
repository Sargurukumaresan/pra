https://github.com/JoyceBeulah/ODD2023-Datascience-Ex01
https://github.com/gururamu08/ODD2023-Datascience-Ex-04
https://github.com/JoyceBeulah/ODD2023---Datascience---Ex-02
https://github.com/gururamu08/ODD2023-DataScience-Ex-03
https://github.com/gururamu08/ODD2023-Datascience-Ex-05
https://github.com/gururamu08/ODD2023-Datascience-Ex06
https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-07
https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-08
https://github.com/JoyceBeulah/ODD2023-Datascience-Ex-09


#PDF
1.[Ex no 2.pdf](https://github.com/Sargurukumaresan/pra/files/13451343/Ex.no.2.pdf)

2.[U3-FEATURE SELECTION EXAMPLE.pdf](https://github.com/Sargurukumaresan/pra/files/13451820/U3-FEATURE.SELECTION.EXAMPLE.pdf)

#IQR
```
import pandas as pd
import seaborn as sns

age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df

sns.boxplot(data=df)
sns.scatterplot(data=df)

q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr

low=q1-1.5*iqr
low

high=q3+1.5*iqr
high

aq=df[((df>=low)&(df<=high))]
aq.dropna()

df=df[((df>=low)&(df<=high))]
df.dropna()

sns.boxplot(data=df)
sns.scatterplot(data=df)
```

#Z score
```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats

data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df

sns.boxplot(data=df)
sns.scatterplot(data=df)

z=np.abs(stats.zscore(df))
print(df[z['weight']>3])

val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]

out=[]
def d_o(val):
  ts=3
  m=np.mean(val)
  sd=np.std(val)
  for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out
op=d_o(val)
op

 ir=pd.read_csv('iris.csv')
 ir
ir.describe()
sns.boxplot(x='sepal_width',data=ir)

c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid

sns.boxplot(x='sepal_width',data=delid)
```
#UNIVIRETE
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/iris (1).csv")
df.head()
df.tail()
```
```
df.nunique()
df.iloc[:,4].value_counts()
for i in range(0,df.shape[1]):
  print("-----------",df.columns[i],"------------")
  print(df.iloc[:,i].value_counts())
  print("---------------------------------------")
sns.countplot(x='species',data=df)
```
```
dfv=df.loc[df['species']=='virginica']
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'*')
plt.xlabel('sepal length')
plt.show()
dfs=df.loc[df['species']=='setosa']
dfc=df.loc[df['species']=='versicolor']
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'*')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'X')
plt.plot(dfv['sepal_length'],np.zeros_like(dfv['sepal_length']),'o')
plt.plot(dfs['sepal_length'],np.zeros_like(dfs['sepal_length']),'+')
plt.plot(dfc['sepal_length'],np.zeros_like(dfc['sepal_length']),'-')
plt.xlabel('SEPALLENGTH')
plt.show()
```
#MULTIVIRATE
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt=pd.read_csv("titanic_dataset.csv")
dt
dt.info()
dt.set_index("PassengerId",inplace=True)
dt.shape
dt.nunique()
dt["Survived"].value_counts()

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per

dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

fig,ax1=plt.subplots(figsize=(8,5))
graph=sns.countplot(ax=ax1,data=dt,x="Survived",hue="Pclass",palette="rainbow")
graph.set_xticklabels(graph.get_xticklabels())
for p in graph.patches:
  height=p.get_height()
  graph.text(p.get_x()+p.get_width()/2,height+20.8,height,ha="left")

dt.boxplot(column="Age",by="Survived")
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
sns.jointplot(x="Age",y="Fare",data=dt)
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

g=sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count",legend=True)
g.fig.set_size_inches(8,5)
g.fig.subplots_adjust(top=0.81,right=0.86)
ax=g.facet_axis(0,0)
for p in ax.patches:
  ax.text(p.get_x()-0.01,p.get_height()*1.02,'{0:.1f}'.
  format(p.get_height()),color='red',rotation='horizontal',size='small')

corr=dt.corr()
sns.heatmap(corr,annot=True)

sns.pairplot(dt)
```
