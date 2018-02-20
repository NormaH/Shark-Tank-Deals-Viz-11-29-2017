# Shark-Tank-Deals-Viz-11-29-2017
Valuation of Deals  (made and no made) 

# coding: utf-8

# In[2]:


import pandas as pd
from pandas import Series, DataFrame
import numpy as np


# In[1]:


import matplotlib.pyplot as plt
import seaborn as sns
sns.set_style('whitegrid')
get_ipython().magic('matplotlib inline')
from scipy import stats


# In[3]:


from __future__ import division


# In[7]:


path = r"C:\Users\t\.spyder-py3\Shark_tank_companies.csv"
shark = pd.read_csv(r"C:\Users\t\.spyder-py3\Shark_tank_companies.csv", low_memory=False)


shark.head()


# In[8]:


# bug fix for display formats to avoid run time errors
pd.set_option('display.float_format', lambda x: '%f' %x)


# In[9]:


print(len(shark))            # Number of observations (rows)
print(len(shark.columns)) #Number of Variables (columns)

 # Setting variables to work as numeric


# In[6]:


shark.info()


# In[10]:


# bug fix for display formats to avoid run time errors
pd.set_option('display.float_format', lambda x: '%f' %x)


# In[11]:


shark['valuation'].mean()


# In[12]:


shark['askedfor'].max()


# In[11]:


shark[shark['valuation'] == shark['valuation'].max()]['valuation']


# In[13]:


avg= pd.DataFrame (shark.mean())


# In[14]:


import statistics


# In[40]:


print (avg)


# In[25]:


print (std)


# In[16]:


path = r"C:\Users\t\.spyder-py3\Shark_tank_companies.csv"
shark = pd.read_csv(r"C:\Users\t\.spyder-py3\Shark_tank_companies.csv", low_memory=False) 


# In[23]:


sns.lmplot(x='askedfor', y='valuation', data=shark, hue= 'deal', markers=['o', 'v'], scatter_kws={'s':80})
plt.xlabel ('Dollars $ asked for')
plt.ylabel ('Valuation in US $')


# In[24]:


sns.lmplot(x='exchangeforstake', y='valuation', data=shark, hue= 'deal', markers=['o', 'v'], scatter_kws={'s':80})
plt.xlabel ('Percentage of exchange stake')
plt.ylabel ('Valuation in US $')


# In[25]:


sns.lmplot(x= 'askedfor', y='exchangeforstake', data=shark, hue= 'deal', markers=['o', 'v'], scatter_kws={'s':80})
plt.xlabel ('Dollars $ asked for')
plt.ylabel ('Percentage of exchange stake')

