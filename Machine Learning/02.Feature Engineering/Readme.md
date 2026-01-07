- Feature Engineering
  - 1.feature transformation
    - 1.1 feature Encoding

      - Label Encoding -> ordinal data (order) like ordered integers ex: 1,2,3 on categories
      - One Hot Encoding   -> nominal data (doesn't have order)
      - Frequency Encoding -> when we have many features (high cardinality) replaced with the count of its appearance.
      - Target Encoding -> replaces each category with mean of target variable(only for classification)
    - 1.2 Feature scaling

      - Normalization
      - Standardization



## 1.1 Feature Encoding

we convert raw data into numerical format so that machine learning algorithms can understand it.

example: converting categorical variables (like gender Male/Female)-> (0,1) into numerical values.



### Types of Feature Encoding
#### 1. Label Encoding:
 Assigns each unique category an integer value. Suitable for ordinal data(order matters) where order matters.

 example:
| Size   | Encoded |  
|--------|---------|
| Small  | 0       |
| Medium | 1       |
| Large  | 2       |
| Large  | 2       |
| Small  | 0       |




#### 2. One-Hot Encoding:
 It transforms categories into individual binary columns for each category. Suitable for nominal data(doesn't have order) where no order exists.
Example:
| Color  | Red | Blue | Green |
|--------|-----|------|-------| 
| Red    | 1   | 0    | 0     |
| Blue   | 0   | 1    | 0     | 
| Green  | 0   | 0    | 1     |


#### 3. Frequency Encoding: 
Replaces categories with their frequency counts. Useful for high-cardinality features.  
Example:
| City      | Frequency |
|-----------|-----------|
| New York  | 3         |
| Los Angeles| 2         |
| Chicago   | 1         |
| New York  | 3         |
| Los Angeles| 2         |
| New York  | 3         |


#### 4. Target Encoding: 

Replaces categories with the mean of the target variable. Useful for classification tasks but can lead to overfitting if not handled properly.


```
Encoded value for category X = Sum of target values for X /Count of rows with X

```
So the denominator is always the number of rows for that category, not the total dataset size.


Example:
| Category | Target | Encoded |
|----------|--------|---------|
| A        | 1      | 0.67    |
| B        | 0      | 0.33    |
| A        | 1      | 0.67    |
| C        | 0      | 0.00    |
| A        | 0      | 0.67    |

Example in Python:

Here we have A as 2/3 = 0.67, B as 1/3 = 0.33, C as 0/1 = 0.00







```python
import pandas as pd
from sklearn.preprocessing import LabelEncoder, OneHotEncoder


# Sample Data

data = {'Size': ['Small', 'Medium', 'Large', 'Large', 'Small'],
        'Color': ['Red', 'Blue', 'Green', 'Blue', 'Red']}
df = pd.DataFrame(data)

# Label Encoding

label_encoder = LabelEncoder()
df['Size_Encoded'] = label_encoder.fit_transform(df['Size'])

# One-Hot Encoding

one_hot_encoder = OneHotEncoder(sparse=False)
color_encoded = one_hot_encoder.fit_transform(df[['Color']])
color_df = pd.DataFrame(color_encoded, columns=one_hot_encoder.get_feature_names_out(['
Color']))
df = pd.concat([df, color_df], axis=1)

# frequency encoding
frequency = df['Color'].value_counts().to_dict()
df['Color_Frequency'] = df['Color'].map(frequency)

# Target Encoding
# Assuming a target variable for demonstration
target = [1, 0, 1, 0, 1]
df['Target'] = target
target_mean = df.groupby('Color')['Target'].mean().to_dict()
df['Color_Target_Encoded'] = df['Color'].map(target_mean)
print(df)


```



## 1.2 Feature Scaling
Feature scaling is a technique used to standardize the range of independent variables or features of data. In data processing, it is also known as data normalization and is generally performed during the data preprocessing step.


### Difference Between Scaling and Normalization

- In machine learning preprocessing, scaling and normalization are related but distinct techniques used to adjust feature values so models perform optimally.

Normalization transforms feature values to a specific range, typically [0, 1] or [-1, 1], often using Min-Max scaling:

```
X_norm = (X - X_min) / (X_max - X_min)
```

- It preserves the shape of the original distribution but can be sensitive to outliers. Variants include Max-Abs normalization, mean normalization, z-score normalization (when used loosely), and log scaling for skewed data. Normalization is especially useful for distance-based algorithms like KNN or SVM, where feature magnitude directly impacts distance calculations.
- Scaling is a broader concept that adjusts the spread or variability of data without necessarily constraining it to a fixed range. The most common form is standardization (z-score scaling):

```
X_scaled = (X - μ) / σ
```

- This centers data at mean 0 with standard deviation 1, making it less sensitive to outliers than min-max normalization. Other scaling methods include robust scaling (using median and IQR), feature scaling to custom ranges, and categorical scaling for encoded variables.

### Key Differences:

- Purpose: Normalization → Fit values into a bounded range. Scaling → Adjust distribution to a standard form (often mean=0, std=1).
- Outlier Sensitivity: Normalization → High sensitivity (min/max affected). Scaling → More robust (especially robust scaling).
- Algorithm Fit: Normalization → Best for algorithms relying on magnitude/distance. Scaling → Best for algorithms assuming zero-centered data (e.g., PCA, gradient descent models).
- Distribution Impact: Normalization → Preserves original shape. Scaling → May alter shape slightly.

#### Example in Python:

```python
from sklearn.preprocessing import MinMaxScaler, StandardScaler
import numpy as np

data = np.array([[18], [22], [30], [45], [80]])

# Normalization (Min-Max)
norm = MinMaxScaler()
data_norm = norm.fit_transform(data)

# Scaling (Standardization)
scaler = StandardScaler()
data_scaled = scaler.fit_transform(data)

print("Normalized:\n", data_norm)
print("Scaled:\n", data_scaled)
```

### Best Practice:

- Use normalization when feature ranges differ greatly and the algorithm is distance-based.
- Use scaling/standardization when algorithms assume normally distributed, zero-centered data. Always fit transformations on training data only to avoid data leakage.
