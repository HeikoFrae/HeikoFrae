# Day 12 10.09.2024
Protocol writer: Heiko

## __Schedule__ 

|Time|Notes|
|---|---|
|09:00 - 9:30     |Daily review|
|09:30 - 10:30    |Finishing of "Pandas -  filtering rows and columns" Exercise no.2|
|10:30 - 12:30    |Start with lecture and exercise of "Pandas - methods, functions and attributes"|
|12:30 - 13:30    |Lunch Break| 
|13:30 - 14:00    |Review and correction of exercise|
|14:00 - open end |Start with lecture and exercise of "Pandas - Data cleansing"| 


---

## __Daily Review__ 

* Recap of Mondays lecture and exercise "Pandas - selecting rows and columns" and
  "Pandas - filtering rows and columns "

## __Pandas - filtering rows and columns Exercise no.2__ 
* Possible dictionary solutions for the exercise:
  ```
  species_list = iris.Species.unique()
  iris_dict = {}

  for iris_name in species_list:
    iris_dict[f'{iris_name}'] = iris[iris.Species == f'{iris_name}']

  iris_dict['Iris-setosa'].describe()
  ```

  
  * Instead of the for loop and the assignments above, you can also use a cool dict comprehension, and/or even get rid of the assignment of the species_list before - so it's a nice one-liner:
  ```
  iris_dict = {iris_name: iris[iris.Species == f'{iris_name}'] for iris_name in iris.Species.unique()}
  ``` 
* For issues or errors with pandas you can post and ask the neuefische-community for help:
   
## __Pandas - methods, functions and attributes__ 

- **Methods**: These are actions you can perform on pandas objects (like DataFrames and Series). Methods are invoked using dot notation and can perform operations such as filtering, grouping, and transforming data. Examples include `.groupby()`, `.merge()`, and `.sort_values()`.

- **Functions**: In the context of pandas, functions are standalone procedures called by their name and can take one or more arguments, including pandas objects. Functions perform specific tasks on the data and return a result. Common pandas functions include `pd.read_csv()` for reading data into a DataFrame and `pd.to_datetime()` for converting a column to datetime format.

- **Attributes**: Attributes are properties of pandas objects that you can access to gain information about the data's structure or content without modifying the data itself. They are accessed using dot notation. For instance, `DataFrame.shape` returns the dimensions of the DataFrame, and `Series.dtype` gives the data type of the Series. 

### Key Pandas Functions

- **DataFrame Creation (`pd.DataFrame(...)`):** The `DataFrame` is a two-dimensional, size-mutable, and potentially heterogeneous tabular data structure with labeled axes (rows and columns). Creating a `DataFrame` involves structuring your data into this format, allowing for more complex data manipulations.

- **Series Creation (`pd.Series(...)`):** A `Series` is a one-dimensional array with labels. It can hold data of any type (integer, string, float, python objects, etc.). The `Series` creation function is fundamental for working with single-dimensional data, providing a simple yet powerful tool for data analysis.

- **Reading CSV Files (`pd.read_csv(file)`):** This function is used to read a table from a CSV file into a DataFrame. It's one of the most common methods for importing data into pandas for further processing and analysis.

- **Finding Unique Values (`pd.unique(values)`):** `pd.unique` returns the unique values from a one-dimensional array-like object, helping identify distinct values within a dataset. This function is crucial for data cleaning and exploration, allowing analysts to quickly understand the variety of data they are dealing with.

- **Combining Data (`pd.concat([df1, df2])`):** This function is used to concatenate pandas objects along a particular axis. `pd.concat` can be used to combine Series, DataFrame, or Panel objects, providing a flexible way to add new rows or columns to your dataset.

#### You can find find other built-in functionshere:  https://docs.python.org/3/library/functions.html









## __Pandas - Cleansing data__ 
Data is often very disorganized. Messy data can hinder data exploration and other steps in your analysis. Data cleansing is about identifying incorrect, incomplete, inaccurate, or irrelevant data, fixing the problems, and making sure that all such issues will be fixed automatically in the future. In pandas missing data is represented by the values NA or NaN. As data comes in many shapes and forms, pandas aims to be flexible with regard to handling missing data.

### Dealing with missing data
If upon inspecting data, missing values are evident how to handle them becomes of the utmost importance. This will always depend upon the situation. Above all the introduction of any bias into the dataset must be avoided. Therefore one option would be to leave it as is, yet that may also hinder the use of some valuable data analysis tools. Here are some options as to how to deal with missing data:

- drop the observations with missing values
- insert mode/mean/median depending on data type
- insert the next or last known value using pandas.DataFrame.fillna()
- insert the mean/median dependent on another column
- for time series data: interpolate using pandas.Series.interpolate


| Command              | Description                                            |
|----------------------|--------------------------------------------------------|
| df.info()            | prints concise summary of dataframe                    |
| df.rename()          | alter row or column axes labels                        |
| df.dropna()          | removes rows or columns that contain missing values     |
| df.set_index()       | assign a column to be the row index of the table       |
| df.reset_index()     | replace the current row index with a default           |
| df["col_name"].isna()| identify missing values in a column                    |
| df["col_name"].replace()| replace values in a Series                           |
| df["col_name"].fillna()| fill NaN values using the specified method           |


  



