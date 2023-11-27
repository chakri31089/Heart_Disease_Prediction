# Heart_Disease_Prediction

## Loading the dataset
* This line of code loads a CSV file named 'heart_disease.csv' into a Pandas DataFrame named heart_disease.

Exploring the dataset
The subsequent lines of code perform various exploratory tasks:

#### 1. heart_disease.shape
* Returns a tuple representing the number of rows and columns in the dataset.

#### 2. heart_disease.columns
* Provides an object containing all the column headers in the dataset.
#### 3. heart_disease.dtypes
* Displays the data types of each column (e.g., float, int, string, bool).

#### 4. heart_disease.head()
* Shows the first 5 rows of the dataset to provide a quick glimpse of the data.

#### 5. heart_disease.tail()
* Displays the last 5 rows of the dataset, offering a view of the end of the data.

#### 6. heart_disease.isnull().any()
* Checks for missing values in each column. Returns True if any null values are present in a column; otherwise, returns False.

#### 7. heart_disease.info()
* Provides basic information about the dataset, including the data types, number of non-null values, and memory usage.

#### 8. heart_disease.describe().T
* Generates basic statistics (like count, mean, min, max, and quartiles) for numeric columns in the dataset. The.T transposes the output for better readability.

The loaded dataset gives insights into its size, structure, column names, data types, summary statistics, and the presence of missing values.


# I.Data Visualization
#### 1. Importing Libraries
* matplotlib.pyplot and seaborn are imported for data visualization. %matplotlib inline is a magic command in Jupyter Notebook to display plots inline.

#### 2. Plotting Histogram for the Entire Dataset
* This code creates a figure and axis, then generates histograms for all numeric columns in the heart_disease dataset.

#### 3. Visualizing Dataset Balance
* Uses Seaborn's countplot() to visualize the distribution of the 'target' variable, which seems to indicate whether a patient has heart disease or not.


## Feature Engineering
#### 1. Feature Selection Using Correlation

#### Get Correlation of Features:
* Calculates the correlation matrix for all features in the dataset and stores the index (column names) of the top correlated features.

#### Plotting Heatmap for Correlation:
* Generates a heatmap to visualize the correlations among the top features identified earlier. The annot=True argument displays the correlation values on the heatmap.

# II.Data Preprocessing
## Handling Categorical Features
#### 1. Converting Categorical Variables to Dummy Variables
* Uses pd.get_dummies() to convert categorical variables ('sex', 'cp', 'fbs', 'restecg', 'exang', 'slope', 'ca', 'thal') into dummy variables. Even if the original dataset doesn't contain string values, this step ensures that the categorical columns are encoded properly for model interpretation.

### Feature Scaling
#### 2. Standardizing Numeric Features
* mports StandardScaler from sklearn.preprocessing to standardize numerical features ('age', 'trestbps', 'chol', 'thalach', 'oldpeak') to have a mean of 0 and a standard deviation of 1.
* fit_transform() applies this scaling to the selected columns in the heart_dataset.

#### 3. Splitting the Dataset
* Separates the dataset into independent features (X) and the target variable (y), where X contains all columns except the 'target' column, and y contains only the 'target' column.


# **Model Building**
I will be experimenting with 3 algorithms:
#### 1. KNeighbors Classifier
#### 2. Decision Tree Classifier
#### 3. Random Forest Classifier


## K-Neighbors Classifier Model
This code performs K-Nearest Neighbors (KNN) classification on a dataset. Here's a breakdown of the steps:
#### 1. Importing Libraries

* Imports necessary libraries from Scikit-learn for KNN classification and cross-validation.

#### 2. Finding the Best K Value
* Iterates through different values of n_neighbors (from 1 to 20) to find the optimal K value for the KNN algorithm using 10-fold cross-validation.
* cross_val_score() computes the accuracy for each value of K, and the mean of these scores is stored in knn_scores.

#### 3. Plotting KNN Scores
* Plots the accuracy scores for different values of K to visualize the best K value based on the highest accuracy.

#### 4. Training the KNN Classifier with Optimal K Value
* Trains the KNN classifier using the optimal K value (K=12) obtained from the previous step.
* Evaluates the model's accuracy using cross-validation and prints the average accuracy score.


## Decision Tree Classifier
Decision Tree Classifier and searches for the best accuracy based on different depth values. Here's a breakdown of the steps:
#### 1. Importing Libraries
Imports the necessary library for Decision Tree Classifier from Scikit-learn.

#### 2. Finding the Best Depth Value
* Iterates through different depth values (from 1 to 10) to find the optimal depth for the Decision Tree algorithm using 10-fold cross-validation.
* cross_val_score() computes the accuracy for each depth, and the mean of these scores is stored in decision_scores.

#### 3. Plotting Decision Tree Scores
* Plots the accuracy scores for different depth values to visualize the best depth based on the highest accuracy.

#### 4. Training the Decision Tree Classifier with Optimal Depth
* Trains the Decision Tree classifier using the optimal depth value (max_depth=3) obtained from the previous step.
* Evaluates the model's accuracy using cross-validation and prints the average accuracy score.

## Random Forest Classifier
Random Forest Classifier and finding the optimal number of estimators (trees) for achieving the best accuracy. Here's a step-by-step explanation:

#### 1. Importing Libraries
* Imports the necessary library for the Random Forest Classifier from Scikit-learn.

#### 2. Finding the Best Number of Estimators
* Iterates through different numbers of estimators (from 10 to 100 in steps of 10) to find the optimal number of trees for the Random Forest using 5-fold cross-validation.
* cross_val_score() computes the accuracy for each number of estimators, and the mean of these scores is stored in forest_scores.

#### 3. Plotting Random Forest Scores
* Plots the accuracy scores for different numbers of estimators to visualize the best number of trees based on the highest accuracy.

#### 4. Training the Random Forest Classifier with Optimal Number of Estimators
* Trains the Random Forest classifier using the optimal number of estimators (n_estimators=90) obtained from the previous step.
* Evaluates the model's accuracy using 5-fold cross-validation and prints the average accuracy score.


# CONCLUSION
## 1.K-Neighbors Classifier
* K-Neighbors Classifier Accuracy with K=12: Around 84.47%
### Conclusion: 
* The K-Neighbors Classifier achieved its highest accuracy of approximately 84.47% when using K=12.
* Beyond this value, the accuracy tends to decrease slightly, indicating that with a moderate number of neighbors, the model performed well on the dataset.

## 2.Decision Tree Classifier
* Decision Tree Classifier Accuracy with max_depth=3: Approximately 82.48%
### Conclusion: 
* The Decision Tree Classifier obtained its highest accuracy, around 82.48%, when utilizing a max_depth of 3.
* As the depth increases, the accuracy might decrease due to overfitting; hence, a depth of 3 is optimal for this dataset.

## 3. Random Forest Classifier
* Random Forest Classifier Accuracy with n_estimators=90: Approximately 85.39%
### Conclusion: 
* The Random Forest Classifier achieved its peak accuracy, about 85.39%, when employing n_estimators=90. 
* The accuracy increases with the number of estimators up to this point, suggesting that utilizing a larger number of trees enhances the model's predictive power.
