# Heart_Disease_Prediction

## Loading the dataset
* This line of code loads a CSV file named 'heart_disease.csv' into a Pandas DataFrame named heart_disease.

Exploring the dataset
The subsequent lines of code perform various exploratory tasks:

1. heart_disease.shape
* Returns a tuple representing the number of rows and columns in the dataset.
2. heart_disease.columns
* Provides an object containing all the column headers in the dataset.
3. heart_disease.dtypes
* Displays the data types of each column (e.g., float, int, string, bool).
4. heart_disease.head()
* Shows the first 5 rows of the dataset to provide a quick glimpse of the data.
5. heart_disease.tail()
* Displays the last 5 rows of the dataset, offering a view of the end of the data.
6. heart_disease.isnull().any()
* Checks for missing values in each column. Returns True if any null values are present in a column; otherwise, returns False.
7. heart_disease.info()
* Provides basic information about the dataset, including the data types, number of non-null values, and memory usage.
8. heart_disease.describe().T
* Generates basic statistics (like count, mean, min, max, and quartiles) for numeric columns in the dataset. The.T transposes the output for better readability.

The loaded dataset gives insights into its size, structure, column names, data types, summary statistics, and the presence of missing values.


## Data Visualization
1. Importing Libraries
* matplotlib.pyplot and seaborn are imported for data visualization. %matplotlib inline is a magic command in Jupyter Notebook to display plots inline.

2. Plotting Histogram for the Entire Dataset
* This code creates a figure and axis, then generates histograms for all numeric columns in the heart_disease dataset.

3. Visualizing Dataset Balance
* Uses Seaborn's countplot() to visualize the distribution of the 'target' variable, which seems to indicate whether a patient has heart disease or not.


## Feature Engineering
1. Feature Selection Using Correlation

### Get Correlation of Features:
* Calculates the correlation matrix for all features in the dataset and stores the index (column names) of the top correlated features.

