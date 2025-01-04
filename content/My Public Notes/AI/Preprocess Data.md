## How to preprocess data before training a machine learning model?

### 1. Handle Missing Data
- Identify and handle missing values using techniques like imputation
- Drop irrelevant rows or columns with excessive missing values
- Use advanced imputation methods like KNN or domain-specific approaches
- Ensure imputation consistency across datasets
- Visualize missing data patterns for better understanding

### 2. Encode Categorical Data
- Apply one-hot or label encoding for categorical features
- Use target encoding for high cardinality features
- Avoid over-encoding nominal variables
- Ensure consistent encoding across training and test sets
- Use appropriate libraries like pandas or sklearn for encoding

### 3. Feature Selection
- Use correlation matrices to remove highly correlated features
- Apply techniques like recursive feature alemination (RFE) or Lasso
- Utilize domain knowledge to discard irrelevant features
- Try wrapper methods to select features that improve model performance
- Perform feature selection on the full dataset before splitting

### 4. Handle Imbalanced Data
- Apply oversampling or undersampling techniques
- Use class weighting in models sensitive to imbalance
- Apply SMOTE to generate synthetic samples for minority classes
- Monitor the impact of balancing techniques on model performance
- Use metrics like F1-score or ROC-AUC to evaluate imbalanced datasets

### 5. Dimensionality Reduction
- Identify redundant or irrelevant features
- Scale data to standardize features
- Apply techniques like PCA, t-SNA, or UMAP for feature extraction
- Use feature selection methods like RFE or Lasso Regression to keep essential features
- Monitor the impact of reduction on model performance
- Use visualization and metrics to ensure data qulity is maintained

### 6. Split Data
- Perform an 80/20 split using train_test_split() or stratified sampling
- Ensure repproducibility with a set random seed
- Create a validation set if needed for hyperparameter tuning
- Perform splitting after data preprocessing (except for scalling and reduction)
- Check for any data leakage to ensure integrity during training/testing

### 7. Scale and Normalize Data
- Normalize or standardize features as required
- Use log transformations for skewed data
- Apply robust scaling in the presence of outliers
- Always scale data after splitting to avoid data leakage
- Check if scaling improves model performance during cross-validation

Notes to self: There are so many things i dont know *cry in the corner* gskcjck gut luck bruh

#AI #MachineLearning
[[My Sillly AI Roadmap]]
