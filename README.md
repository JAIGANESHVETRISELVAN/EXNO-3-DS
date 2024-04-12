## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:
```
NAME :JAIGANESH V
REG NO : 212221040063
```
```
     import pandas as pd
     df=pd.read_csv("/content/Encoding Data.csv")
     df
```
![316296378-eca0e23d-6ea3-4685-ad3e-3a3c688afce4](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/67f4b2e3-8071-40d4-9762-8af62d6d6bc6)
```
  from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
  pm=['Hot','Warm','Cold']
  e1=OrdinalEncoder(categories=[pm])
  e1.fit_transform(df[["ord_2"]])
```
![316296336-6f0fce59-7852-489d-a76f-db5988a45a3b](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/ac580d98-5609-44bf-90aa-855a2f98d29b)
```
    df['bo2']=e1.fit_transform(df[["ord_2"]])
    df
```
![316295056-84e9360b-9728-444d-bbe3-f7480e9633f6](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/2b436247-891b-4a4d-b734-c30388031459)
```
        le=LabelEncoder()
    dfc=df.copy()
    dfc['ord_2']=le.fit_transform(dfc['ord_2'])
    dfc
```
![316295165-1c7de496-371e-4a21-a189-7ed70ecc2900](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/0ab3cedb-b51e-4b95-920f-8d490da113dd)
```
  from sklearn.preprocessing import OneHotEncoder
  ohe=OneHotEncoder(sparse=False)
  df2=df.copy()
  enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
  df2=pd.concat([df2,enc],axis=1)
  df2
```
![316295256-a8c5038b-2814-4b1d-8f85-c27b292c04d4](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/bf397c84-7da6-4edd-9566-28aca310310d)
```
  pd.get_dummies(df2,columns=["nom_0"])
```
![316295310-797cb3cf-cc31-4c39-ba12-af1d740bbbed](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/54acaab0-881f-4a3a-8d75-81e8ff8ad428)
```
  pip install --upgrade category_encoders
```

![316295375-eba5c171-3e23-483f-b4ed-6f4c47b5e89b](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/7aaa85fa-5ddf-4b27-ab6c-8d4d1e33dd0e)
```
    from category_encoders import BinaryEncoder
    df=pd.read_csv("/content/data.csv")
    be=BinaryEncoder()
    nd=be.fit_transform(df['Ord_2'])
    fb=pd.concat([df,nd],axis=1)
    dfb1=df.copy()
    dfb

```
![316295450-9b983cb5-c712-49d8-bcd8-817ca7f56947](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/5380c816-a490-43d5-8479-9e3d029b4e61)
```
   from category_encoders import TargetEncoder
   te=TargetEncoder()
   cc=df.copy()
   new=te.fit_transform(X=cc["City"],y=cc["Target"])
   cc=pd.concat([cc,new],axis=1)
   cc
```
![316295534-0d2e7e51-9cb4-4530-a56d-39d1435d0249](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/57a18d55-4433-4b74-8533-632fbb935f51)
```
    import pandas as pd
    from scipy import stats
    import numpy as np
    df=pd.read_csv("/content/Data_to_Transform.csv")
    df
```
![316295585-f71a4dd5-6389-4fb9-a209-81064b1d878f](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/451860ac-0a39-4bca-82d1-2ae85a58f070)
```
    df.skew()
```
![316295623-3e30db2a-11cd-4980-a53d-87e495cdba2d](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/ef5352b6-fe3f-4b22-96fd-cfe3544d4bfb)
```
    np.log(df["Highly Positive Skew"])
```
![316295660-ea34c360-81a5-4760-bc9e-2c6a9d07be6c](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/1b5605ca-dccd-4816-a592-94189d4e5e99)
```
    np.reciprocal(df["Moderate Positive Skew"])
```
![316295703-790eadf6-e770-4874-943c-ddfb7bca5113](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/2c0bf8a5-98bb-4950-ac99-e6eb0c776b5b)
```
    np.sqrt(df["Highly Positive Skew"])
```
![316295749-7e2ab48c-7321-477e-81e4-ba3d6b132bf5](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/3552e56a-824b-43a5-b55b-509eef240428)
```
   df["Highly Positive Skew_boxcox"],parameters=stats.boxcox(df["Highly Positive Skew"])
   df
```
![316295883-7632047a-430d-4b18-8bab-abc86a475a5a](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/d9d9f392-a0f1-410b-a6d4-b0c49c8f7b6b)

```
    df["Moderate Negative Skew_yeojohnson"],parameters=stats.yeojohnson(df["Moderate Negative Skew"])
    df.skew()
```
![316295945-90edf1a6-0480-49e3-9fe6-7ac276d2acf3](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/fe0437e3-99be-4813-a1df-c479289ae0f1)


```
   import matplotlib.pyplot as plt
   import seaborn as sns
   import statsmodels.api as sm
   import scipy.stats as stats

   sm.qqplot(df["Moderate Negative Skew"],line='45')

   plt.show()
```
![316296082-b72a5319-b492-4c91-981e-15bf8d38c539](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/5e892cde-8b09-4dc4-bee1-7ca97afa5e90)
```
    sm.qqplot(np.reciprocal(df["Moderate Negative Skew"]),line='45')
```
![316296150-9c011486-2fd5-4752-b434-702ecc5bebdc](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/500ea8cf-6064-410b-a67a-6b88ec94457f)
```
    from sklearn.preprocessing import QuantileTransformer
    qt=QuantileTransformer(output_distribution='normal',n_quantiles=891)

    df["Moderate Negative Skew"]=qt.fit_transform(df[["Moderate Negative Skew"]])

    sm.qqplot(df["Moderate Negative Skew"],line='45')
    plt.show()

```
![316296228-880ace95-7dd1-4732-941d-e007439a6fc5](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/de083f40-c35b-4135-b795-ffc8188bade9)

# RESULT:
       Hence performing Feature Encoding and Transformation process is Successful.

       
