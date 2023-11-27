# Heart_Disease_Prediction

## Loading the dataset
heart_disease = pd.read_csv('/heart_disease.csv')
This line of code loads a CSV file named 'heart_disease.csv' into a Pandas DataFrame named heart_disease.

Exploring the dataset
The subsequent lines of code perform various exploratory tasks:

1. heart_disease.shape
Returns a tuple representing the number of rows and columns in the dataset.
2. heart_disease.columns
Provides an object containing all the column headers in the dataset.
3. heart_disease.dtypes
Displays the data types of each column (e.g., float, int, string, bool).
4. heart_disease.head()
Shows the first 5 rows of the dataset to provide a quick glimpse of the data.
5. heart_disease.tail()
Displays the last 5 rows of the dataset, offering a view of the end of the data.
6. heart_disease.isnull().any()
Checks for missing values in each column. Returns True if any null values are present in a column; otherwise, returns False.
7. heart_disease.info()
Provides basic information about the dataset, including the data types, number of non-null values, and memory usage.
8. heart_disease.describe().T
Generates basic statistics (like count, mean, min, max, quartiles) for numeric columns in the dataset. The .T transposes the output for better readability.

The loaded dataset, giving insights into its size, structure, column names, data types, summary statistics, and the presence of missing values.

