
import pandas as pd
import numpy as np
data=pd.read_table(r'D:\EURUSD.txt',sep=',')


data.info()
data.head(5)
data.describe()


data['high']=data['<HIGH>']
data['low1']=data['<LOW>']
data['range']= data['high'] - data['low1']
data.head()
data['range'].describe()
import matplotlib.pyplot as plt
import matplotlib.pyplot as plt
#plt.figure(figsize=(16,8))
#plt.plot(data['range'])
  

df1=data[data['range'].isin([0.0000])] 
df2=data[~data['range'].isin([0.0000])]
#df2


Hdata = list(df2["high"])
Ldata = list(df2["low1"])
plt.figure(figsize=(300,10))
plt.plot(Hdata[0:])
plt.plot(Ldata[0:])
plt.title("1 min H-L Range")
plt.xlim(0,4168612 )
plt.ylim(1.1,1.4 )
plt.legend()

