## Code Overview

### 1. Importing Required Libraries
The code starts by importing necessary libraries including `pandas` for data manipulation, `LabelEncoder` from `sklearn.preprocessing` for encoding categorical variables, and various model training libraries from `sklearn`.

### 2. Loading Datasets
- The training dataset is loaded into a DataFrame called `train_dataset` from the `train.csv` file.
- The test dataset is loaded into a DataFrame called `test_dataset` from the `test.csv` file.
- The target results for the test set are loaded into a DataFrame called `y_test` from the `sample_submission.csv` file, excluding the `Id` column.

### 3. Splitting Data into Features and Labels
- The target variable `SalePrice` is separated from the training data into `y_train`.
- The remaining features in the training data are stored in `x_train`, excluding the `SalePrice` and `Id` columns.
- The test data features are stored in `x_test`, excluding the `Id` column.

### 4. Encoding Categorical Features
- A `LabelEncoder` is used to encode categorical features in both `x_train` and `x_test`. For each column, if the type is `str` or if the column contains missing values, it is encoded.

### 5. Training a Decision Tree Classifier
- A `DecisionTreeClassifier` is trained on the encoded `x_train` data using the `SalePrice` as the target.
- The classifier is then used to predict the `SalePrice` for the test data.
- The predicted values are stored and saved as `decisionTree.csv` with columns `Id` and `SalePrice`.

### 6. Training a Linear Regression Model with GridSearchCV
- A `LinearRegression` model is instantiated and hyperparameters are tuned using `GridSearchCV` to find the best model configuration.
- The model is trained on the encoded `x_train` data, and predictions are made for the test data.
- The predicted values are stored and saved as `linearRegression.csv` with columns `Id` and `SalePrice`.
