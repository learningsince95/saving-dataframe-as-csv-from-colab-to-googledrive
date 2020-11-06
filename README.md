# saving-dataframe-as-csv-from-colab-to-googledrive


Steps to create dataframe in google colab and saving it as csv in google drive

import pandas as pd

import gspread

#import df2gspread as d2g

#import pygsheets


import pandas as pd


x=[]

y=[]

z=[]

a=[]


for i in range(1,40001):

  x.append(i)
  
  y.append(str(i))
  
  z.append('=char(')
  
  a.append(')')
  


  
import pandas as pd

df=pd.DataFrame(x,y)

df = pd.DataFrame(list(zip(x,z,y,a)), columns =['Name','c', 'val','b']) 

df['val']=df['c']+df['val']+df['b']


df_symbol=df[['Name','val']]

df_symbol.shape


from google.colab import drive

drive.mount('drive')


df_symbol.to_csv('data_symbol.csv')

!cp data_symbol.csv "drive/My Drive/"


print('done')
