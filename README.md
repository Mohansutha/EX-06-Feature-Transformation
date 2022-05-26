# EX-06-Feature-Transformation

## AIM
To Perform the various feature transformation techniques on a dataset and save the data to a file. 

# Explanation
Feature Transformation is a mathematical transformation in which we apply a mathematical formula to a particular column(feature) and transform the values which are useful for our further analysis.

 
# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Transformation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
~~~
import numpy as np
import pandas as pd
import seaborn as sns
import statsmodels.api as sm
import scipy.stats as stats
import matplotlib.pyplot as plt
df=pd.read_csv("Data_to_Transform.csv")
df
df1=df.copy()
log_ModPositive = np.log1p(df1["Moderate Positive Skew"])
log_HighPositive = np.log1p(df1["Highly Positive Skew"])
log_ModNegative = np.log1p(df1["Moderate Negative Skew"])
log_HighNegative = np.log1p(df1["Highly Negative Skew"])
df1.insert(1,"log_ModPositive",log_ModPositive)
df1.insert(3,"log_HighPositive",log_HighPositive)
df1.insert(5,"log_ModNegative",log_ModNegative)
df1.insert(7,"log_HighNegative",log_HighNegative)
df1
df1["Moderate Positive Skew"].plot(kind = 'hist')
df1["log_ModPositive"].plot(kind = 'hist')
df1["Highly Positive Skew"].plot(kind = 'hist')
df1["log_HighPositive"].plot(kind = 'hist')
df1["Moderate Negative Skew"].plot(kind = 'hist')
df1["log_ModNegative"].plot(kind = 'hist')
df1["Highly Negative Skew"].plot(kind = 'hist')
df1["log_HighNegative"].plot(kind = 'hist')
df2=df.copy()
sqrt_ModPositive = df["Moderate Positive Skew"]**(1/2)
sqrt_HighPositive = df["Highly Positive Skew"]**(1/2)
sqrt_ModNegative = df["Moderate Negative Skew"]**(1/2)
sqrt_HighNegative = df["Highly Negative Skew"]**(1/2)
df2.insert(1,"sqrt_ModPositive",sqrt_ModPositive)
df2.insert(3,"sqrt_HighPositive",sqrt_HighPositive)
df2.insert(5,"sqrt_ModNegative",sqrt_ModNegative)
df2.insert(7,"sqrt_HighNegative",sqrt_HighNegative)
df2
df2["Moderate Positive Skew"].plot(kind = 'hist')
df2["sqrt_ModPositive"].plot(kind = 'hist')
df2["Highly Positive Skew"].plot(kind = 'hist')
df2["sqrt_HighPositive"].plot(kind = 'hist')
df2["Moderate Negative Skew"].plot(kind = 'hist')
df2["sqrt_ModNegative"].plot(kind = 'hist')
df2["Highly Negative Skew"].plot(kind = 'hist')
df2["sqrt_HighNegative"].plot(kind = 'hist')
df3=df.copy()
reciprocal_ModPositive = 1/df["Moderate Positive Skew"]
reciprocal_HighPositive = 1/df["Highly Positive Skew"]
reciprocal_ModNegative = 1/df["Moderate Negative Skew"]
reciprocal_HighNegative = 1/df["Highly Negative Skew"]
df3.insert(1,"reciprocal_ModPositive",reciprocal_ModPositive)
df3.insert(3,"reciprocal_HighPositive",reciprocal_HighPositive)
df3.insert(5,"reciprocal_ModNegative",reciprocal_ModNegative)
df3.insert(7,"reciprocal_HighNegative",reciprocal_HighNegative)
df3
df3["reciprocal_ModPositive"].plot(kind = 'hist')
df3["reciprocal_HighPositive"].plot(kind = 'hist')
df3["reciprocal_ModNegative"].plot(kind = 'hist')
df3["reciprocal_HighNegative"].plot(kind = 'hist')
from scipy.stats import boxcox
df4=df.copy()
bcx_ModPositive, lam = boxcox(df["Moderate Positive Skew"])
bcx_HighPositive, lam = boxcox(df["Highly Positive Skew"])
df4.insert(1,"bcx_ModPositive",bcx_ModPositive)
df4.insert(3,"bcx_HighPositive",bcx_HighPositive)
df4
df4["bcx_ModPositive"].plot(kind = 'hist')
df4["bcx_HighPositive"].plot(kind = 'hist')
from scipy.stats import yeojohnson
df5=df.copy()
yf_ModPositive, lam = yeojohnson(df["Moderate Positive Skew"])
yf_HighPositive, lam = yeojohnson(df["Highly Negative Skew"])
yf_ModNegative, lam = yeojohnson(df["Moderate Negative Skew"])
yf_HighNegative, lam = yeojohnson(df["Highly Negative Skew"])
df5.insert(1,"yf_ModPositive",yf_ModPositive)
df5.insert(3,"yf_HighPositive",yf_HighPositive)
df5.insert(5,"yf_ModNegative",yf_ModNegative)
df5.insert(7,"yf_HighNegative",yf_HighNegative)
df5
df5["yf_ModPositive"].plot(kind = 'hist')
df5["yf_HighPositive"].plot(kind = 'hist')
df5["yf_ModNegative"].plot(kind = 'hist')
df5["yf_HighNegative"].plot(kind = 'hist')
~~~

# OUPUT

![Ex 6 ds1](https://user-images.githubusercontent.com/94828335/170413697-a6d43dcf-4c8c-4f1d-ad4b-19588c505481.png)

![Ex 6 ds2](https://user-images.githubusercontent.com/94828335/170413736-82f7217e-0c12-46db-9528-8048435b8b1f.png)

![Ex 6 ds3](https://user-images.githubusercontent.com/94828335/170413754-31a7e624-2c99-467d-a4c7-6d5b047714a8.png)

![Ex 6 ds4](https://user-images.githubusercontent.com/94828335/170413778-6deee049-83c0-482a-bd19-9dc4a459563d.png)

![Ex 6 ds5](https://user-images.githubusercontent.com/94828335/170413803-d7e66259-97da-4e2b-89bc-302f82efdb6b.png)

![Ex 6 ds6](https://user-images.githubusercontent.com/94828335/170413827-b2b8843d-285e-4edc-8204-6dd80c273f67.png)

![Ex 6 ds7](https://user-images.githubusercontent.com/94828335/170413897-a3083609-7cb0-4b00-933b-22a58883102c.png)

![Ex 6 ds8](https://user-images.githubusercontent.com/94828335/170413934-1ab10464-214f-4231-9376-d95acaf9b61d.png)

![Ex 6 ds9](https://user-images.githubusercontent.com/94828335/170413944-0892e073-0e30-4b9a-a280-68562a211f96.png)

![Ex 6 ds10](https://user-images.githubusercontent.com/94828335/170413958-2144bca0-a91d-4757-822c-faa62c9c354c.png)

![Ex 6 ds11](https://user-images.githubusercontent.com/94828335/170413970-3386c7d7-b707-45df-bbd6-fba184cf5e9b.png)

![Ex 6 ds12](https://user-images.githubusercontent.com/94828335/170413983-e6654cf7-bcca-40a0-8dd4-230bf657ecbf.png)

![Ex 6 ds13](https://user-images.githubusercontent.com/94828335/170414002-d3cf487c-1f6c-465e-ba23-9c6fe99adc8b.png)

![Ex 6 ds14](https://user-images.githubusercontent.com/94828335/170414020-1a6a0aa1-b7e0-4a4b-8ee2-15e4b29a73b7.png)

![Ex 6 ds15](https://user-images.githubusercontent.com/94828335/170414036-84bed841-2fcc-40e2-91a9-294366758a08.png)

![Ex 6 ds16](https://user-images.githubusercontent.com/94828335/170414046-19ce87c4-232d-48f0-925e-754f6adf8122.png)

![Ex 6 ds17](https://user-images.githubusercontent.com/94828335/170414061-2a8001cd-997a-41da-9a04-c1188b32249f.png)

![Ex 6 ds18](https://user-images.githubusercontent.com/94828335/170414072-659f8454-56c7-4307-a0ac-05cec2628737.png)

![Ex 6 ds19](https://user-images.githubusercontent.com/94828335/170414089-c83aa0b3-7a63-4c4c-b499-c22ce3583e92.png)

![Ex 6 ds20](https://user-images.githubusercontent.com/94828335/170414115-9344cd2a-3c3c-44ba-83f8-eae4c1fa1aac.png)

![Ex 6 ds21](https://user-images.githubusercontent.com/94828335/170414154-dca58433-580e-482d-9f8a-a1b772e7a913.png)

![Ex 6 ds22](https://user-images.githubusercontent.com/94828335/170414163-e6fdaa7b-0e3d-4202-ac6f-f427574d82be.png)

![Ex 6 ds23](https://user-images.githubusercontent.com/94828335/170414175-038ebc9e-ffa3-461d-92be-75aa1d464535.png)

![Ex 6 ds25](https://user-images.githubusercontent.com/94828335/170414209-b55c02c6-425e-4841-984a-5d72bd6b4b0b.png)

![Ex 6 ds26](https://user-images.githubusercontent.com/94828335/170414243-d99bdf48-1ef3-41f5-8973-e79d75bb23de.png)

![Ex 6 ds27](https://user-images.githubusercontent.com/94828335/170414270-e9163891-5c47-4ef0-b9c9-747939a1fcf8.png)

![Ex 6 ds28](https://user-images.githubusercontent.com/94828335/170414297-60baf669-57e8-402f-8e67-623dd63a6aea.png)

![Ex 6 ds29](https://user-images.githubusercontent.com/94828335/170414315-c63031c0-2811-4ab8-adad-a29a2182b6f8.png)

![Ex 6 ds30](https://user-images.githubusercontent.com/94828335/170414335-f5aa3189-e853-4ece-8e90-07f8910f9ff3.png)

![Ex 6 ds31](https://user-images.githubusercontent.com/94828335/170414353-9c165112-4804-41a5-abf6-6299fcc7b02f.png)

![Ex 6 ds33](https://user-images.githubusercontent.com/94828335/170414383-531a9d94-30bc-414c-b92a-bc3095dfbc28.png)

![Ex 6 ds32](https://user-images.githubusercontent.com/94828335/170414363-baed3f2e-a28f-460b-800e-e843a92ae9d5.png)

##RESULT:

The various feature transformation techniques has been performed on the given datasets and the data are saved to a file.





