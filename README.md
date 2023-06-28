# My Netflix EDA project by BigBlueAcademy
To clean and analyze a movie dataset, the following procedures were carried out in the provided code:

1. Reading the dataset: The code starts by reading the movie dataset into a Pandas DataFrame called 'df' from a CSV file called 'n_movies.csv'.


   Validating the dataset The DataFrame's column names, data types, and the amount of non-null values in each column are all displayed with the command df.info().

2. Cleaning procedures: On the DataFrame, several cleaning procedures are carried out:

   a. Rearranging columns:

      The non-numeric characters are removed from the 'duration' column before it is transformed to a float.
      The commas are removed from the 'votes' column, and it is changed to float.
      Using regular expressions, the 'year' column is extracted to reveal the start year for each movie.

   b.  The 'pd.to_datetime()' function is used to convert the 'StartYear' column to datetime format.
       The 'year' column has been removed from the DataFrame.
       
3. Renaming columns: To provide the columns more descriptive titles, the column names are changed using the df.rename() method.

4. Taking care of missing values

  a.  For missing values, the 'Certificate' column has the value 'Not Rated'.
  b.  For missing entries, the 'Genre' column is set to the value 'Unknown'.
  c.  For missing values, the 'Duration(mins)' column is set to the integer data type and filled with the value 'Unknown'.
  
5. Establishing a "Protagonist" column

  a. To identify the first actor or actress in the list, the 'Stars' column is divided by commas.
  b. The 'Protagonist' values are cleaned using regular expressions and string substitutions.
  c. The DataFrame removes rows with empty 'Protagonist' values.


6. Calculating weighted average
   The 'Votes' and 'Rating' columns are used to produce a weighted average for each film using the provided algorithm. A new column called "WeightedAverage" now contains the outcome.

7. Sorting and dropping duplicates:
    Sorting the DataFrame and removing duplicates: The DataFrame is sorted in descending order using the 'WeightedAverage' column. Only the first instance of a row with the same 'Title' is 
   kept when there are several instances.

8. Further data cleaning:
   Rows with missing values in the "WeightedAverage," "Protagonist," and "Genre" columns are removed from the DataFrame as part of the data cleaning process. 'df_cleaned' contains the 
   cleaned-up DataFrame.

9. Visualization:
   Various visualizations are created using Matplotlib to analyze the cleaned data. The code generates bar plots for the top 10 genres by count and by weighted average, a bar plot for the 
   top 10 most frequently appearing protagonists, and a line plot showing the average rating by year.

 
These cleaning and analysis steps were performed to prepare and explore the movie dataset. The code and visualizations can be used as a starting point for further analysis or as an example 
 for working with similar datasets.


