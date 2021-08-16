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
- select datediff(curdate(), colname) as alias ----- return column with days between curdate() and colname (great for renure calculation)
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
- df.columns = ['col1', 'col2', 'col3'] ----- rename 0, 1, 2 columns to 'col1' 'col2' 'col3'
- np.repeat(df.col1.iloc[0], df.col2.iloc[0]) ----- create 1-D array of rows where # is df.col2.iloc[0] and value is df.col1.iloc[0]
- df.loc[df.index.repeat(df.col_with_aggregated_count)].reset_index(drop=True) ----- repeat in-order each index the number of times specified by df.col_with_aggregated_count, keeping the dataframe, reassigning the index to the new rows
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
- df.nunique(axis=1) < ncols ----- setting ncols at start, then see if there are duplicates in a row. By setting this result to a new column, you can run this check for all rows in a dataframe and store the result in the column.
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
- Join dataframes together: pd.concat([df1, df2], axis=0, ignore_index=True) ----- adds rows, use axis=1 to add columns
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

## Seaborn
- Library that builds on matplotlib and integrates well with pandas
- Powerful in its defaults!
### Seaborn Syntax, Methods
- import seaborn as sns
- df = sns.load_dataset('dataset') ----- does same as pydataset
- sns.relplot(x='col1', y='col2', data=df) ----- returns scatterplot for df using col1 for x axis and col2 for y axis
- - once plotted, can use plt.title, plt.xlabel, etc as normal
- sns.histplot(df.col_name, kde=True) ----- histogram (bar chart of frequency count) of col_name, with kernel density estimator
- sns.boxplot(data=df) ----- box and whisker plot (inter-quartile range, quartiles, median, and outliers all on a plot)
- sns.catplot(x=, y=, col=, col_wrap=, hue=, data=, kind=) ----- categorical plot (default is silo'd dot plot, can kind='count')
- sns.heatmap(data, annot=True, cmap=plt.cm.Greens) ----- heatmap with annotations using the Greens color palette
- - https://seaborn.pydata.org/tutorial/color_palettes.html
- sns.set_palette("colorblind") ----- makes your stuff colorblind-friendly
- sns.pairplot(df) ----- quickie for combinations of data in df
- sns.jointplot(data=df, x=, y=) ----- attaches a histogram per axis for a scatterplot
### Seaborn Arguments
- col='col1' ----- chart for each unique value in col1
- hue='col1' ----- separate color for each unique value in col1
- style='col1' ----- changes style of plot point for each unique value in col1
- kind='line' ----- draws a line to each plot point

## JupyterNB
### Basic usage
- Kernel > Restart and Clear Output to restart the shell without any cells having yet ran; Stop shell then start again for troubleshooting
- Option+Clickdrag to create vertical multi-cursor
- Command Mode uses Z for undo-cell operations, Edit Mode uses Command + Z.
- ESC from Edit mode into Command mode; RETURN from Command mode into Edit mode
- Shift+RETURN to run a cell
- Other Command mode shortcuts: dd to delete cell; y to change cell to Code; m to change cell to Markdown
- Shift+TAB to check information at cursor location (like the default parameters of a method), very powerful tool
- Split cell at cursor: Control + Shift + -

## Spreadsheets / Excel
- Two-dimensional data
- Less functional than Seaborn/Matplotlib for plotting data
- Less capable than Numpy/Pandas for processing data
- Basically only use it when the situation requires Excel/Google Sheets, like handing a spreadsheet to someone
- =FUNCTION() ----- calls a function at a cell
- - all functions start with =
- - point function at another cell to run function on the other and return the value in the current cell
- - bottom-right of cell has a button... double-clicking it allows you to run the function for all rows... ex: extract year from a date
- - values will update for all connected cells if the looked-at cell changes... VLOOKUP works nice with this
- Conditional Formatting and Alternating Colors for readability
- fn + f4 is the absolute reference to a cell or cell range
- Pivot Table: Select All (the entire table, for convenience), Insert, Create Pivot Table (make a new sheet), add rows and columns using interface
- - Insert, Chart... ----- Produces chart, can customize
- Splitting text: Select data, Data, Split Data *OR* =SPLIT(cell, delimiter)
- =CONCATENATE(cell, delimiter_if_desire, cell, cell, delimiter, cell...)
### Spreadsheets Functions
- =YEAR(B2), =MONTH(B2)... ----- use existing functions against cell B2
- =B2-B3 ----- subtract B3 from B2 in cell
- Filtering ----- Select all, Data, Create Filter, hover over column you want to filter, apply a filter to it
- - Filter Views allows you to view the filtered version while the shared view for others is unchanged. Can save the view and share it with others if you want, it appears listed under the Filter Views tab in Google Sheets.
- =IF(condition, value_if_true, value_if_false)
- - =IF(AND(B2 > 100, B3 < 50), True, False)
- =SUM(value1, value2), =SUMIF(range, condition) =AVERAGE(A1:A100), =COUNT(A1:A100), =COUNTIF(range, condition), =MIN(B1:B100), =MAX(C42:C999)
- - Conditions (criterion) can be a pointer towards a cell with logic in it, so a cell that generates a list under it can be referenced as the criterion for =COUNTIF() to find the count of each value in the list from the whole table
- - Summary statistics can be initiated from any cell for any cell range... convention is to put a small table in the Sheet next to the values to show the statistics
- =VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE) ----- vertically searches range_to_search for key, if it finds it, returns col_to_return, if it's not exact match, ignores it (due to FALSE)
- - VLOOKUP looks at first column specified... be careful
- =LEFT(cell, char_count), =MID(cell, start_position, steps)
- IFERROR(try, except)
- =SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc}) ----- creates a red in-cell bar chart of data from range with maxed bar when reaching max value of range

## Tableau
- Visualization tool, can be used for presentations
- Public is free but cannot privately save your work (publishes everything)
- - Save with each new sheet as a standard... Nothing is autosaved so if it crashes you're donezo
- Faith's Tableau Public: https://public.tableau.com/app/profile/faith.kane
- Sean Oslin's Tableau Public: https://public.tableau.com/app/profile/sean.oslin
- A lot of people use the superstore CSV to learn and demo Tableau, you should consider using it to learn Tableau too
### Tableau Usage
- Consider exploring your data in Google Sheets first
- - Tableau is a bit slow for *exploration* compared to pivot tables in Google Sheets
- - Once you've discovered what you want, switch to Tableau for presentation and visualization creation
- CSV files are Text Files when ingesting data into Tableau
- Hide unnecessary columns using drop-downs in each column
- - Can unhide columns
- Filter results at top-right (intuitive)
- Put results to charts via button in bottom-left "Sheet 1"
- - Can rename tabs (will rename table [results])
- - Can add extra to name in the table and leave tab simplified
- Leftmost options (columns) - can adjust if needed
- - Can switch between Data tab and Analytics tab
- - Drag options up into Rows or Columns to add to table
- - Drag options into Marks, onto Label or Color to append certain data to table, right-click on existing Label/Color things and make changes to the appended data (very cool!), each drag is an added feature - move Legend to under Marks as a preference
- - Change number to currency - right click option, default properties, number format...
- Can click on leftmost options to display them
- - Rightmost tables are choices for displaying your data
- Semi-leftmost options (Measure Values) - change aggregations for any measure values
- Table - Right click on table things, change alias or other things about it
- - Change view width/height in dropdown at top of window (apparently Entire View is good for displaying later on)
- Transpose: Drag rows into column field, columns into row field (really simple)
- Change table format: select entire window, use MacOS File/Data/Etc bar (context menu), Format, Lines (change lines on table)
### Dashboard
- View multiple sheets in one dashboard
- - Drag sheets into playspace
- - "Entire View" option for sheets fills the box in the playspace
- Edit/hide titles, add "supertitle", etc in here
- Great for interactive deliverable for stakeholders that want to play with filters
### Story
- Essentially a slide deck/presentation for sheets/dashboards
- - Slides for one table in a slide... dashboard for multiple tables in a slide
- Captions are basically named slides
- Can drag text window from bottom left into slide and right click-edit it

## Storytelling
- Data requires velocity to be useful
### Visualization Considerations
- Expert-level visualizations != presentation-level visualization
- - The pivot tables are more appropriate for Appendix
- - If the audience has to read it, don't include it
- Serve the "why" first, then follow with the specifics
- - Leading with specifics will lose your audience
- Give the "why" some amplifying, relative information to help seat your audience
- - Avoid cluttering the "why" with too much amplification
- Design the velocity with your audience in mind
- Prepare to Create; Talk and Listen; Sketch; Prototype
- - Clear physical and mental room; Know your data; Understand your audience and Big Idea
- - Determine which framework to use (persuasive, man-in-hole, story), determine context, challenge, and solution
- - Understand your audience and use an appropriate approach
- - A topic isn't a big idea... use your chances to express the big idea
- - Explain out loud what your project is, take notes of feedback, make corrections [I'm working on... I'm trying to show... Why...]
- - Use everything so far to sketch out your ideas (brainstorm)
- - Refine the sketches into presentation material
- A non-correlation can be more important than a correlation
- Start with overview in presentation, dissect the focus later (start with churn v not churned, then dive into churn data)
- Relate the problem to the audience's interests and focus for maximum effect

## Statistics Notes
### Distributions
- Uniform - equal likelihood of all outcomes (coin)
- - stats.randint(low, high_not_including)
- Binomial - two outcomes (success/failure)
- - stats.binom(rolls, probability_of_one_outcome)
- Normal - continuous random variable (bell curve)
- - stats.norm(mean, standard_deviation)
- Poisson - events per time interval
- - stats.poisson(number)
- Lots more distributions... check scipy documentation for stats module
### Order of ops for scipy.stats distribution objects
- Consider which distribution to use
- Create the distribution using scipy.stats
- "What info do I have, what info do I need"
- Call the appropriate distribution (there's a nice diagram that helps you use the right call)
- Use rvs method to use dummy data instead of default
#### Diagram
- rvs --- pmf / pdf --- cdf / ppf --- sf / isf
- probability of specific (or list of) outcomes: pmf(outcome) or pdf(outcome) (continuous or discrete, respectively)
- probability of threshold and below: cdf(threshold)
- values at specified probability or below: ppf(probability)
- probability of all above threshold: sf(threshold)
- values of above probability: isf(probability)
#### Examples
- die_distribution = stats.randint(1,7) ----- set die_distribution to a recipe for random numbers between 1 and 7 (not including 7)
- die_distribution.rvs() ----- give me one random number from die_distribution
- die_distribution(5) ----- give me five random numbers from die_distribution
- die_distribution((3,5)) ----- give me a 3 x 5 numpy array of random numbers from die_distribution
- x = die_distribution.rvs(10_000) ----- roll die_distribution 10,000 times and store results to x
- plt.hist(x, bins=, align=, width=, edgecolor=) ----- plot results
- plt.title(f'Outcome of {n:,} Dice Rolls;') ----- add title
###
- Working inside a dataframe is standard for the industry
- - Can take shortcuts, it's not standard practice but you can do this and explain what's going on
- Centering is important to take a pile of data purely as its distance away from the mean in positive/negative direction
- - Centering is also known as de-meaning a vector
- Z-Score is like centering but it's the distance from the mean in terms of standard deviation
- - zscore = (value - population_mean) / standard_deviation
- - zscore = (value - avg(value_list)) / std(value_list)
- - from scipy import stats, stats.zscore(value_list) ----- returns Z-Score of value_list
### Python/NumPy/Pandas
- Figure out a way to represent our data (ex: dice_outcomes = [1,2,3,4,5,6])
- Create a matrix of random data, rows = simulations, columns = trial
- - For example, rolling 2 dice 10,000 times means rows=10,000 and columns = 2 because we roll 2 dice each time
- Apply an aggregate function, row-wise to get the results of the simulation
- Apply a final aggregate to get our probability
#### Deeper on Python/np/pd
- setting rows as variable and columns as variable helps with dataframe formatting
- - nrows, ncols... df.reshape(nrows, ncols)
- .mean() against a boolean list will give count_of_trues / length_of_list
- Rolling two dice at once: to sum an iteration of rolling two die, use axis=1 as the argument for .sum()
- np.random.choice(outcomes, size=(simulations, trials))
- - rolls = np.random.choice([1,2,3,4,5,6], 1_000_000)
- - rolls[0:10] ----- shows first 10 rolls
- - (rolls == 5).mean() ----- times_rolled_5 / total_rolls, or the calculated probability (not theoretical)
- - ((rolls == 5) & (rolls == 6)).mean()
- - size=(experiments, number_of_dice per experiment)
- weigh outcomes: np.random.choice(outcomes, size=, p=[0.55, 0.45])
### Hypothesis Testing
- Taking sample data and generalizing for a larger population... Comparing, testing, predicting future outcomes... Final result is probability scores
- Often takes the form of distributions
- Null hypothesis: all cases that are NOT the alternative hypothesis, as $H_{0}$ -- H with subscript 0
- - Do those who churn spend more per month than those who don't? Null hypothesis: No, they spend less or equal to
- Alternative hypothesis: The hypothesis you decide, as $H_{a}$ -- H subscript a
- - Do those who churn spend more per month than those who don't? Alternative hypothesis: Yes, they spend more
#### Steps
1. ID the question
2. state the hypotheses
3. validate the assumptions
4. run our test, set our significance level (alpha)
- - industry standards are 5% or 1%, but other values are fine
5. get results: test statistic and p-value
- - p-value: probability that we observed this result due to chance... if it's less than our alpha, we reject the null hypothesis... there IS a difference, or a relationship.
6. evaluate results and draw conclusions
- - "We reject the alternative hypothesis" or "We reject the null hypothesis" is formalspeak
- - False Negative Rate: Probability of a false negative, or the probability of a type 2 error... P(FN) = P(Type II Error)... failure to reject the null hypothesis... exceeding alpha
- - False Positive Rate: Probability of a false positive, or the probability of a type 1 error... P(FP) = P(Type I Error)... said there was a difference or relationship, when there wasn't one... within alpha
#### Test Types
- Comparison of Means (t-test) ----- bool v continuous/numeric, the mean is calculated from the cont/num variable
- Comparison of Proportions/Relationships (chi-square) ----- bool v bool or bool v categorical
- Linear correlation (does one cont value affect another cont value) ----- numeric v numeric, continuous v continuous
- Check variances for equality: stats.levene(sample1, sample2)
- - the threshold for significant inequality is pvalue < .05 or .01
- Finding *linear* corr: corr, p = stats.pearsonr(x, y) ----- Pearson correlation coefficient calculation
- - Finding r using dataframe: df.corr() --- df[['col1', 'col2']].corr() ----- find r for col1 and col2
- Finding *non-linear* corr: stats.spearmanr()
- Chi2 Test (for Independence) ----- Compare two categorical variables, ex: gender v phone_manufacturer_choice, to see if they are independent of one another or not
- - pd.crosstab against two *categorical* columns, then stats.chi2_contingency of that dataframe (returns chi2, pvalue, degf, expected_values_array)
- - Degree of Freedom: (num_cols - 1) * (num_rows - 1)
- - Check df for potential categorical columns: df.nunique() ----- returns count of unique values for each column, if column has low count then good chance it's categorical
### Comparing Means
- "(x)-tail, (x)-sample t-test"
- mu is population mean, subscript is the population
- if t-statistic is proper and p-value is significant (less than 0.05), then we reject the null hypothesis
- - Null: sample <= theoretical, then if t-statistic > 0 and p-value < 0.05, we reject the null hypothesis. If not, we can't reject it.
- - Null: sample == theoretical, then we only care about p-value being 0.05 / 2
- Steps: Plot distributions (ex: histogram); Establish hypothesis; Set significance level alpha to .05; Verify assumptions (normal distribution, or at least 30 observations with normal-looking distribution [more observations = less needed to look like normal distribution]); Compute test statistic and probability using scipy.stats.ttest_1samp(); Decide. 
- .sf() * 2 is your friend... be careful though!
- Compare an observed mu to the theoretical mu (sample vs whole): One sample t-test, normally distributed
- - t, p = scipy.stats.ttest_1samp(array_of_sample, array_of_overall)
- Compare two observed mu (sample against sample): Independent t-test, normally distributed, equal variances
- - t,p = scipy.stats.ttest_ind(sample1, sample2, equal_var=False)
- Compare multiple observed mu: ANOVA, normally distributed, independent variables, equal variances
- - scipy.stats.f_oneway(sample1, sample2, sample3, ....,equal_var=False)


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


## Methodologies
- Classification: Is this new observation A or B (or C, D....)
- Regression: How many of something
- Clustering: What groupings already exist in the data?
- Time Series Analysis: What happens next????
- Anomaly Detection: Is this weird??

## Classification
- Assigning observations to existing classifications
- Supervised learning... training on data with answers/labels
- Produces: Rules
- - Data + Answers, with ML, creates rules
- - Traditional programming doesn't seek to create rules, it creates answers
### Vocab
- Classifier: Algorithm that maps input data to specific category
- Classification Model: A series of steps that takes the patterns of input variables, generalizes, then applies generalizations to new data
- Feature: An input/independent variable
- Binary Classification: Two possible outcomes
- Multiclass Classification: More than two, where samples are assigned to exactly one target label (ex: students in grades 1-12)
### Algorithms
- Data Science is heavily based on decision trees
- These are designed to create rules from data/labels:
- **Logistic Regression** - Predict binary outcomes for inputs
- - Interpretable, Flexible, Easily-Implemented, Efficient
- - Need to remove unrelated attributes, not a top-performing algorithm
- **Decision Tree** - Sequence of rules to classify two or more classes via one-input-binary-output nodes
- - Simple to Understand/Visualize/Explain, Low-Prep, Handle numerical and categorical data, performs well
- - Overfitting risk, unstable
- Naive Bayes - contingent probabilities - low # of observations (in the hundreds)
- **K-Nearest Neighbors (KNN)** - Predictions based on how close new data is to known data (top-5 closest known datapoints are 'votes')
- - Simple, Robust to noise, just-in-time calculation, can be updated over time
- - Need to determine K, high computational cost, curse of dimensionality (distances can break down in high-dimensional space)
- **Random Forest** - Lots of decision trees
- - Less risk of overfitting than one decision tree, more accurate than decision tree (due to moar trees)
- - High computational demand, difficult to implement, hard to explain (black-box factor)
- Many more

## Data Acquisition
- pd.read_clipboard ----- VERY COOL store data from your clipboard
- pd.read_excel, pd.read_csv, pd.read_sql
- can pull from Google Sheets from within Python using following sample code:
- - sheet_url = 'https://docs.google.com/spreadsheets/d/1Uhtml8KY19LILuZsrDtlsHHDC9wuDGUSe8LTEwvdI5g/edit#gid=341089357'    
- - csv_export_url = sheet_url.replace('/edit#gid=', '/export?format=csv&gid=')
- can pull from ANY online document using following sample code (only public-facing documents work):
- - df_s3 = pd.read_csv('https://s3.amazonaws.com/irs-form-990/index_2011.csv', encoding='unicode_escape')
### Data Caching
- Can save money and time (doesn't use Cloud services)
- df.to_csv("file.csv") ----- writes dataframe to a cached file.csv (not saved to disk)
- df.to_file(filename) ----- writes dataframe to disk

## Data Preparation
- **DOCUMENT YOUR DATA PREP**
- Categorical/Discrete features need to become numbers
- - Pclass 1,2,3 are ordinal/discrete, but can be treated as categorical if converted
- - Pname is categorical even though each value is unique
- If algorithm relies on *distance*, Continuous features may need to be scaled
- - Just look it up if you don't remember
- df.colname.map(dict_with_map_logic) ----- replace colname values identified in dict_with_map_logic keys with the associated value of the key:value pair
- pointers v assignments... careful when assigning dataframes to dataframes!!!!!
- - df2 = df1.copy() ----- disconnects df1 from df2, where without .copy(), changes in df2 would reflect in df2
- df = df.drop_duplicates() ----- drop duplicate rows in df
- df = df.drop(columns=['colname', 'colname2', ...]) ----- drop columns
- df = df.colname.fillna(value='value_want_to_fill_nulls_with') ----- fill nulls
### Encoding
- Associate each unique value with a number (label encoding)
- - Use label encoding when categories have an inherit order
- One-hot encoding: 1 or 0 in new column if row is or isn't that value
- - Use one-hot when there's no order
- pd.get_dummies(df['col1', 'col2'], drop_first=[True, True]) ----- automagically does one-hot encoding for unique values in col1 and col2
- - creates a new column for each unique value in col1 and col2 with 0 or 1 representing False and True respectively, drops first new column for col1 and col2 (less dimensionality)
### Tidying Data
- Great link: https://vita.had.co.nz/papers/tidy-data.pdf
- One cell for one value, no repeat cells or multi-value cells
- df[['newcol1', 'newcol2']] = df.col.str.split(':', expand = True) ----- creates new dataframe with columns for the split items, columns are newcol1 and newcol2
- df.pivot_table(index = ['col1', 'col2', ...], columns = 'colx', values = 'coly', aggfunc='mean').reset_index() ----- creates pivot table, aggregates duplicate rows, resets it from sub-dataframe format
### Train-Test Split
- Randomize entire dataset *before* splitting to remove potential bias (dataset potentially sorted)
- Make sure all splits include all options (stratify target)
- sklearn does randomization/stratification for you!
### Data Prep Tips
- pd.melt(df, id_vars='colname') ----- creates 'variable' and 'value' columns from columns not specified and their values
- - melt has multiple useful arguments to help make this better
- Use for loop to iterate through columns in dataframe and nest plt methods to push out different graphs for each column
- - numeric: 
- - object columns: df['colname'].value_counts(), df['colname'].value_counts(normalize=True, dropna=False)
- - df.isnull().sum() ----- prints all columns of df with number of null values in each column
- Curse of dimensionality: try to limit columns
- - df_dummy ----- new dimension-limited dataframe of "dummy data" from full dataframe
#### Example takeaways for titanic data (classification exercises)
- embarked == embark_town, so remove embarked & keep embark_town
- class == pclass, so remove class & keep pclass (already numeric)
- drop deck...way too many missing values
- fill embark_town with most common value ('Southampton')
- drop age column
- encode or create dummy vars for sex & embark_town.

## sklearn
- Python library for machine learning applications
- sklearn objects share methods like fit_transform and transform, can be called against variables like imputer (which stores SimpleImputer(strategy='most_frequent'))
### Modules
- from sklearn.model_selection import train_test_split ----- splits data in two sets
- - train, test = train_test_split(df, test_size=0.2, random_state=123, stratify=df.colname) ----- create train and test dataframes, test dataframe is 20% of rows, randomization seed is 123, stratifies df.colname
- - train, validate = train_test_split(train, test_size=.25, random_state=123, stratify=train.survived) ----- modifies train, sets validate dataframe using new parameters
- from sklearn.impute import SimpleImputer ----- fills values by inference
- - fill with: 0, average, median, subgroup mean, most frequent value, build model to predict missing values, etc
- - strategy='average' ----- fills with average
- - will need to modify dataframes with impute results
### Syntax
- imputer = SimpleImputer(strategy='most_frequent')
- imputer = imputer.fit(train[['embark_town']])
- train[['embark_town']] = imputer.transform(train[['embark_town']])
- do same for validate and test datasets
- - imputer = SimpleImputer(strategy='most_frequent')
- - train[['embark_town']] = imputer.fit_transform(train[['embark_town']])
- - validate[['embark_town']] = imputer.transform(validate[['embark_town']])
- - test[['embark_town']] = imputer.transform(test[['embark_town']])
- - return train, validate, test

## Stakeholders
- Move functions and analysis to separate .ipynb as required for stakeholders
- - Stakeholders want just the end product: give them it
- - Stakeholders want the models and end product: give them it
- - Stakeholders want everything: give them everything