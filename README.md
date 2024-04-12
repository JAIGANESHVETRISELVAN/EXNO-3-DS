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
     ![316296378-eca0e23d-6ea3-4685-ad3e-3a3c688afce4](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/c76675dd-0efc-4878-b9b4-6fc7b9e4ab96)
```
  from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
  pm=['Hot','Warm','Cold']
  e1=OrdinalEncoder(categories=[pm])
  e1.fit_transform(df[["ord_2"]])

  ![316296336-6f0fce59-7852-489d-a76f-db5988a45a3b](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/9323e3d4-dc14-4402-ab8b-c4d59d845cc7)

    df['bo2']=e1.fit_transform(df[["ord_2"]])
    df
    ![316295056-84e9360b-9728-444d-bbe3-f7480e9633f6](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/57714ba6-9382-4036-8ecf-cf74843082c5)
    df['bo2']=e1.fit_transform(df[["ord_2"]])
    df
    ![316295116-addbdb92-ff8a-41f3-af9e-bd97ac6800a2](https://github.com/JAIGANESHVETRISELVAN/EXNO-3-DS/assets/133752156/e658ae02-7841-4e7f-836f-e7f4f61b1466)

```


# RESULT:
       # INCLUDE YOUR RESULT HERE

       
