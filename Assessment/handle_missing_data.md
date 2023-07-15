## Handle missing data in a given dataset and provide a code snippet 

There can be several approaches to handle missing data. I’ll be explaining two of them below.

- **Dropping rows and columns containing missing data**: 
If the missing data is limited to a few rows in the dataset, we can drop those rows. Similarly, If an entire column contains a significant amount of missing data and is not critical for our analysis, we can drop that column.However, this should be done cautiously to ensure that you are not losing too much valuable information.
```
import pandas as pd
#Drop rows containing null values
data_dropped_rows = data.dropna(axis=0)
#Drop columns containing null values
data_dropped_columns = data.dropna(axis=1)
```
- **Missing value Imputation**:
Imputation involves filling in the missing values with estimated or substituted values. This can be done using various techniques such as mean, median, mode imputation, or more advanced approaches like regression imputation or K-nearest neighbors imputation. The Impute module in Sklearn can be used to achieve the same.


```	
import numpy as np
import pandas as pd
from sklearn.impute import SimpleImputer

# Create a DataFrame with missing values
df = pd.DataFrame({
    "Name": ["Viraj Sharma", "Sharma", np.nan, "Viraj"],
    "Age": [30, 25, np.nan, 40],
    "Country": ["India", "Canada", "UK", np.nan]
})

# Create a SimpleImputer instance
imputer = SimpleImputer(strategy="mean")

# Impute the missing values
df = imputer.fit_transform(df.values)

# Print the DataFrame with the imputed values
print(df)
```		