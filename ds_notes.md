# My notes for the Codeup Data Science course

## Foundational Knowledge
- AI vs ML vs DL: Machine Learning is a model adjustment tool that observes data, makes predictions using a model, and adjusts the model to make better predictions. The code to set this up is written by humans. Machine Learning is not entirely separate from AI- AI is an umbrella term for the automated handling of conditionals. Deep Learning is a specific application of Machine Learning that involves three or more layers of hidden (not human-designed) neural network nodes- the flexibility of Deep Learning allows systems to adjust to input in ways that humans can’t precisely code themselves.
- Parameters, hyperparameters, features, targets: A feature is an input, a parameter is a machine- or human-set portion of a model, and a target is the output. Hyperparameters are human adjustments to a model in order to help it better reach the correct target.

## CLI:
- Access the MySQL database (-p prompts for password): -u username -p -h IP-address
- code filename.filetype 
- - opens VS Code with specified file (creates new one if not exist)
- JupyterNB issues... You can use Command + T to open tabs in Terminal so you don't have to stop JupyterNB processes

## SQL
### Basic Syntax
- show databases;
- use database_name;
- show tables;
- describe table_name;
- select column_name from table_name;
- - you can select * from table_name, or specify multiple columns
- - you can filter to an entry using WHERE, select * from table_name where condition_statment
- - you can also create aliases for columns, select column_name AS Column from table_name;
### Functions
- SUBSTR(string, index, step_number)
- - index starts before the position is read (first character is at index 1), step_number = 1 reads one character from index
### WHERE
- Used to filter the database with conditional statements before the data is pulled down
- Great for simple conditionals and also allows subqueries
### ORDER BY
- Used to order the output column by ASC or DESC order
- - DESC is reverse-alphabetical (Z is first)
- - DESC is highest-to-lowest number
### GROUP BY
- Analyze records (rows) based on specified column
- Used to run aggregate functions on multiple records based on similar value in the column 
- - aggregate functions: avg(), min(), max(), std(), etc
- - avg(numbers_column) would return average of all values
- - select numbers_column, avg(numbers_column) from numbers GROUP BY numbers_column would return nothing very useful, it would return each unique number's average (average of 5 is 5)
### JOIN
- Used to temporarily merge tables on a similar column
- INNER uses AND logic, LEFT / RIGHT use OR logic and prepend/append, the FROM table is indicated LEFT or RIGHT
- ON vs USING() - ON preserves the linked key while USING() merges the linked keys into one column
- - use the USING() function to merge same-name columns, but this will throw an error if two tables have more than one similar column name
### SUBQUERIES
- Flexible tool to return a query's results to a query
- Often used in WHERE clause, example: WHERE emp_no IN (SELECT emp_no FROM employees WHERE to_date > curdate())
### CASE 
- Used to temporarily create a column from scratch with conditional assignment of records
- uses WHEN condition THEN append new info ELSE append new info END AS new column name
- use CASE in SELECT statement
### HAVING
- Used to filter after records are extracted/sliced
- - Example: With GROUP BY colname, only show a few of the rows
- to filter results to a specific THEN. example: HAVING item_type = 'Specialty Item'
### Temporary Tables
#### Overview
- Used to create a new table, very flexible
- Great for pulling read-only tables into write-enabled databases
#### Syntax
- CREATE TEMPORARY TABLE database.table as (stuff);
- DROP TABLE table;
- INSERT INTO table(column) VALUES (value), (value), (value), ...;
- UPDATE table SET column = value + 25;
- DELETE FROM table WHERE ...; (this works without WHERE clause, deletes entire table's contents)
- ALTER TABLE table DROP COLUMN column;
- ALTER TABLE table ADD column (value type);

## Python lessons
- Data types: bool, str, int, float, list, dict, NoneType
- - bool(0) returns False, bool(1) returns True
### Cool things
- "a" in "banana" returns True
- print(string, int) converts the int to str and adds a space between string and int. Don't need to print("string " + str(int))
- {} performs simple operations in distressed conditions, great with formatted strings. Formatted string example: print(f"here is my string that takes {number} and multiplies it by two which is {number * 2}")
- Slice: [0:3], [2:], [:-1] (works with str and list)
- list[0][0] returns first char of first string in list
- string[0] returns first char of string
- the char _ is a trash variable, [num for _ in range(1, 5)]
### String methods
- JupyterNB: can use TAB to check available methods
- - Example: string.lower() can be found with string. + TAB
- string.count("a") returns number of "a" in string
- "b a n a n a".split(" ") returns list of each letter using the " " delimiter
- delimiter.join(list) returns a string from the list with the delimiter spacer
- string.strip() deletes left/right whitespace, new lines, and tabs
- string.isnumeric() checks for a string comprised of numbers
### Lists
- A grouping of values, created with []
- Can hold any data type including list and dict
- - list containing list is two-dimensional data (a spreadsheet)
- JupyterNB: use TAB to check available methods, list. + TAB
- List comprehensions and operations: return [n + 1 for n in numbers], return [n + 10 for n % 2 == 0 in numbers]
- - List comprehension only returns affected items; to preserve original list's unaffected items in return use [output if condition else output for item in list]
### Dictionaries
- A labeled list, created with {}, uses key:value pairs (each pair should be considered its own variable)
- JupyterNB: can use TAB to check available methods, dictionary. + TAB
- dict.keys() returns keys, dict.values() returns values
- dict[0] returns first entry in the dictionary, dict[0][key] returns the value for the key in the first entry
### Tuples
- A list that can't change (a constant variable for a grouping), uses () instead of []
- Often returned from functions
- - return sum(numbers), avg ----- returns tuple (sum, avg)
- tuple[0] returns first item in tuple like normal
- enumerate() works with tuples
- - for x in enumerate(four_values): print(x) ---- (0, value1) (1, value2) (2, value3) (3, value4)
### Output formatting
- Use .format() to make a table like in the following example
- - print(" stuff | stuff | stuff ")
- - print("-------|-------|-------")
- - print(f"|{:<8}|{:<8}|{:<8}|".format(stuff, stuff, stuff)
- lambda: list.sort(key=lambda x: len(item)) ----- sorts based on length of each item
### Functions
- Parameters and Arguments: Parameter is the shell, Argument is the value put in the shell.
### Importing
#### Basic info
- Import from Python Standard Library, packages/libraries installed from pip/conda, or our own .py files
- docs.python.org/3/library
#### Import syntax
- import math ----- imports the Python Standard Library math library, use math. + TAB to see list of functions
- - import math as m ----- alias math as m
- - math.function(argument, argument)
- from math import function, function, function ----- imports specific functions from math
- - from math import tan
- - tan(argument, argument)
- from math import tan as alias ----- alias the function
#### Importing self-created files
- create file util.py, then in new .py, import util
- - from util import function, function, function
- - function(argument, argument)
### key= usage
- key= is used to change the default output
- - max(list, key=list.method) ----- chooses highest based on the method (doesn't need parentheses)
- - list.sort(key=lambda x:function) ----- sorts using x (an anonymous function declaration)
### lambda
- lambda is on-the-fly creation of a return
- Used to avoid creating a function for one or two uses
- - fun_name = lambda a, b: a + b ----- creates function that pulls in a and b, returns a + b
- - fun_name(1, 3) ----- returns 4
- - lambda x: try_me ----- calls the try_me function with x argument and returns try_me output
- - key=lambda x: try_me ----- uses the return of the try_me function (called with x argument) for the key
- - max(list, key=lambda x: try_me) ----- returns the biggest item of the list determined by the try_me function
### Sorting through a .json (a list of dictionaries)
- Can easily find highest or lowest value of a key in a list of dicts
- - max_dict = max(list_of_dicts, key=lambda x:dict["key"]) ----- stores as max_dict the dict in the list with the highest dict["key"]
- - print(max_dict["key"]) ----- quick solution to printing the max_value of a key shared across a list of dicts
- - understanding the key= in max() can yield very quick and clean results

## NumPy
- A staple library of the scientific community and the foothold of Python in science
- NumPy arrays (and the array functions) are excellent
- - Boolean masks used to filter arrays; mask = array conditions, a[mask]
### NumPy tools
- array.size ----- returns number of values in array
- (a > 1).sum() ----- returns sum of values in a that are greater than 1
- array_test = numpy.array(list) ----- set array_test to numpy array of the list
- array_test = numpy.random.randn(5) ----- set array_test to numpy array of 5 random numbers
- - numpy.random.randn(2, 2) ----- creates 2x2 array of random numbers
- numpy.arange(start, stop, step) ----- creates one-row array of range start,stop with step gaps
- numpy.linspace(start, stop, num) ----- creates one-row array of range start,stop with num columns
- sum, min, max, std, mean, product, and more for basic math on arrays
- - sum(array, axis=1) ----- sum each row's contents, do not sum the rows together
#### NumPy Array Examples
- do element-wise arithmetic and comparison, such as array_test + 1, array_test == list, array_test * array_test_2, etc
- - a = numpy.array([0,1,2,3,4,5])
- - a == 2 returns array of bool results
- - a[a == 2] returns the indexed elements of a with True values (masks)
- use [row, column] indexing
- - m[0,2] of 3x3 array ----- [row_index, column_index]
- - m[0:1, 0:1] of 3x3 array ----- returns columns 0 and 1 from row 0 and 1, preserves formatting
- - m[:,1] of 3x3 array ----- returns column 1 from all rows

## Pandas
- Another excellent staple of the Python science community
- Built on Numpy and Matplotlib
- Dataframes (df) are extremely powerful data representation tools
- - df.attribute is easily modified
- - 2D array with labeled axes (labeled rows, labeled columns), array is a NumPy array
- Series Methods v Series Attributes: Series Attributes return valuable information about the Series object (series.dtype, series.size, series.shape), they do not perform calculations or require parentheses. Series Methods perform calculations or operations on a copy of a series and return the copy (series.head(n=5), series.tail(n=5), series.value_counts())
- - dtype: Python type str is Pandas dtype object (object = str or mixed, int64 is int, float64 is float, bool is bool, datetime64 is datetime...)
- Vectorized Operations: Call default Python methods on Pandas Series, for example: series_name.str.capitalize() will capitalize all values in the series.
- Method Chaining: using multiple methods at once - ex: series_name[str.method()].str.method()
### Pandas tools
- df['column_name'].head(10) ----- returns rows 0 to 9 of the column (this avoids issues with spaces in column names or reserved words as column names)
- df.first_name.head(10) ----- also returns rows 0 to 9 of the column
- - first_name is NOT a variable, it is a named column that exists in df. 
- pd.Series(list_name) ----- creates a column (first index 0) of row-separated values from list_name
- pd.Series(dict_name) ----- creates label column and value column for dict_name keys and values, respectfully
- series.size ----- returns length of series
- df.index returns list of indices for dataframe, df.values returns list of values
- df.sample(num) ----- returns a random sample of num amount of values
- series.astype(object) ----- returns a copy of a series with its dtype changed to object
- series.value_counts(normalize=False, sort=True, ascending=False, bins=None, dropna=True)
- series_or_df.describe() ----- summary statistics of a series or dataframe 
- - for series type object: row count, unique values, most frequent value, how many times most frequent value occurs
- - for series type int64: count_uniques, mean, std, min, 25%, 50%, 75%, max
- (bool_mask).any() ----- returns True if any bool_mask value is True
- (bool_mask).all() ----- returns True if all bool_mask values are True, otherwise return False
- series_name[boolean_mask] ----- returns values of series_name that return True in boolean mask
- series.apply(function) ----- applies function to each element in the series, function can be user-defined, built-in, lambda, etc
- series_name.isin(series_name_2) ----- returns array of bool values where series_name is in series_name_2
- - series_name[series_name.isin(series_name)] ----- uses bool array as boolean mask
- dict_series["key1":"key2"] ----- returns rows between and including "key1" and "key2"
- dict_series[["key1", "key5", "key9"]] ----- return rows with index "key1", "key5", "key9"
- bin_assignment_array = pd.cut(series, [start, cut, cut, cut, stop]) ----- bin values from series into 4 different bins, stored as (start, cut], (cut, cut], (cut, cut], (cut, stop]
- - pd.cut(df, bin=bin_edges , labels=[bin_label, bin_label, bin_label]).value_counts().sort_index() ----- displays count of each bin, ordered by index (not highest count to lowest count)
### DataFrames
- 2-Dimensional data with a lot of functionality
- Made from pandas Series
- pd.DataFrame(list_of_dicts) ----- Make a dataframe from a list of dictionaries
- - Dictionary keys should be the same between all dictionaries in the list
#### DataFrame Syntax
- list_of_dicts_dataframe.key.sum() ----- sum all values of key in list_of_dicts_dataframe
- - .max(), .mean(), etc all work
- df[value].argmax() ----- gives index of df where max value exists
- df[df.index == 0] ----- give the entire row of first index of df
- df[df.key == value] ----- return entire row where key is set to value
- df.key.idxmax() ----- return index for the key's highest value in df
- - df[df.index == df.key.idxmax()] ----- return entire row of index with max value of key
- df[[key1, key2]] ----- returns dataframe with column key1 and key2
- - keys = [key1, key2]
- - df[keys]
- df.colname > 100 ----- returns bool mask
- - df[(df.colname > 100) & ((df.colname < 400) | (df.colname == 500))] ----- use & and | operators for AND and OR, needs parentheses because bool array is created in parentheses *then* bool arrays are compared
- df[condition1 & condition2] ----- no need for parentheses
- df_copy = df.copy() ----- makes a copy, can't assign df_copy to df or else they'll point to same dataframe
- df_copy.drop(columns=[colname], inplace=True) ----- permanently alters df_copy, drops colname
- df_copy.rename(columns={colname1: colname2, colname5: colname6}) ----- permanently alters df_copy, changes colname1 to colname2, changes colname5 to colname6
- df_copy[new_column] = df_copy.colname > 100 ----- returns bool array in new_column for each row that is > 100 in colname
- - can use the new column as a bool mask!!
- df_copy.assign(new_colname=df.colname > 100) ----- same as previous
- df.sort_values(by=col_name, ascending=False) ----- sort df by col_name in descending order
### "Advanced" Dataframes
- Produce dataframe from dictionary: pd.Dataframe({'A': [1,2,3], 'B': [0,1,2])
- Produce dataframe from list: pd.Dataframe([[1,2,3], [4,5,6]])
- Labeled dataframe from list: pd.Dataframe(numpy_array, columns=['a', 'b', 'c'])
- Use specific columns from dataframe: df[['col1', 'col2, 'col5']]
- Slice row and column at once using names/bools: df.loc[row_indexer, col3:col4] ----- returns rows of row_indexer (can be bool mask!) and one column within the bounds (INCLUSIVE)
- Slice row and column at once using index: df.iloc[1:3, :]
- Run multiple aggregate functions on a dataframe: df[['col1', 'col2', 'col5']].agg(['mean', 'min']) ----- returns new dataframe with agg functions ran on all columns specified in df
- Group By in pandas: df.groupby('col_want_to_group_by').col_want_to_do_func_on.mean()
- - df.groupby('col_want_to_group_by').col_want_to_do_func_on.agg(['mean', 'median', 'count'])
- - can do multiple columns in groupby
- - can rename aggregate function columns: df.columns = ['name1', 'name2']
- Programatically insert values in new column: df['new_col'] = np.where(df.col > 100, 'me_true', 'me_false')
- Create new column on dataframe using agg functions: df.assign(new_col=df.groupby('show_me_col').calc_me_col.transform('mean')) ----- transform keeps index intact
- Join dataframes together: pd.concat([df1, df2], axis=0, ignore_index=True)
- - .concat here is very raw, may create nulls and not line up exactly
- SQL join in python: df1.merge(df2, left_on='df1_col', right_on='df2_col', how='outer', indicator=True) 
- - _x, _y, _merge in colnames help out, so does .drop and .rename
- - use .merge when columns in common between two dataframes, helps keeps things together
- Crosstabulation (count occurences of one column per another): pd.crosstab(df.col1, df.col2, margins=True, normalize=True) ----- margins show total of each column or each row, normalize shows percentage of value compared to entire table
- Create pivot table: df.pivot_table(index='col1', columns='col2', values='col3') ----- each row that matches x1, y1 gets col3's values put together and default agg function mean... then x2, y1... then x1, y2... then x2, y2... and so on for all unique combos of col1 and col2
- Init a map and use map to fill a column based on another column: create dict with input: output, then df['new_column'] = df.col1.map(dict_map) ----- the .map function returns the value, so you can perform regular arithmetic and other stuff on it like normal
- Rotate a table (transpose): df.T

## Matplotlib
- Visualizations for dataframes
- import matplotlib.pyplot as plt
- Once .plot() is run, can do plt.method_here
- can run multiple .plot() in a single visual before plt.show()
- can use tuple as first argument in ex: hist() to do side-by-side
- - plt.hist((series1, series2), ...)
### Matplotlib Syntax
- df.plot() ----- put dataframe to a plot
- df.plot.barh() ----- put dataframe to a bar plot
- x = list(range(150)) -- plt.plot(x) -- plt.show()
- - JupyterNB will automatically show a plot without plt.show(), but .py scripts ran from Terminal require plt.show()
### Matplotlib Methods
- plot
- - defaults to line plot. plt.plot(x, y, c='color')
- - scatter(), bar(), barh(), hist(), and more
- - c= ----- color, can use alpha= to do transparency (0.0 - 1.0)
- - s= ----- size of dots on scatterplot
- - ls= ----- line type for line chart, ':' is dotted, '--' is dashed, etc
- - bins=[list_of_cuts]
- - align='left' ----- aligns to left
- - edgecolor= ----- sets edge for the data (ex: border on bars in chart)
- show()
- title('title'), xlabel('clabel'), ylabel('ylabel')
- xlim(bounds), ylim(bounds)
- xticks(list_of_int_ticks, list_of_str_tick_names), yticks(list, list)
- - rotation=num ----- rotate each tick num degrees
- text(left_boundary_coords_for_txt, txt_to_place, fontsize=num, color='color')
- annotate('text', xy=(coords_for_tip), xytext=(coords_for_left_bound), arrowprops={'key':'value'})
- figure(figsize=(num_width, num_height))
- legend(loc='upper right') ----- puts legend in upper right
- savefig('name_of_my_new_figure') ----- generates .png of your figure
- plt.subplot
- - subplot(num_of_rows, num_of_cols, index_start_at_1)
- - plt.plot(list, list)
- - plt.title('title1')
- - subplot(num_of_rows, num_of_cols, index_start_at_1)
- - plt.plot(list, list)
- - plt.title('title2')
- - plt.tight_layout() ----- fixes spacing
- - plt.suptitle('title') ----- super (wrapper) title for subplots
- - plt.show() ----- gens 2 subplots, then plt.show() puts them next to each other


## JupyterNB
### Basic usage
- Kernel > Restart and Clear Output to restart the shell without any cells having yet ran; Stop shell then start again for troubleshooting
- Option+Clickdrag to create vertical multi-cursor
- Command Mode uses Z for undo-cell operations, Edit Mode uses Command + Z.
- ESC from Edit mode into Command mode; RETURN from Command mode into Edit mode
- Shift+RETURN to run a cell
- Other Command mode shortcuts: dd to delete cell; y to change cell to Code; m to change cell to Markdown
- Shift+TAB to check information at cursor location (like the default parameters of a method), very powerful tool

## Statistics Notes
- Centering is important to take a pile of data purely as its distance away from the mean in positive/negative direction
- - Centering is also known as de-meaning a vector
- Z-Score is like centering but it's the distance from the mean in terms of standard deviation
- - zscore = (value - population_mean) / standard_deviation
- - zscore = (value - avg(value_list)) / std(value_list)
- - from scipy import stats, stats.zscore(value_list) ----- returns Z-Score of value_list

## Bringing it all together
- from env import user, password, host
- def get_connection(db, user=user, host=host, password=password): url = f'protocol://[user[:password]@]hostname/database_name'
- - url = mysql+pymysql://codeup:p@assw0rd@123.123.123.123/some_db ----- Notice some_db? Same as USE DATABASE;
- - pd.read_sql('SELECT * FROM employees LIMIT 10', url)
- - query = '''
- - SELECT
- -     emp_no,
- -     to_date
- - FROM employees
- - WHERE to_date > curdate()
- - LIMIT 100
- - '''
- - cur_emps = pd.read_sql(query, url)
- set df to file pulled from the MySQL database
- df.head() and df.tail() to return the data first 5 rows and last 5 rows
- - series attributes to check for more information
- series methods to perform necessary calculations