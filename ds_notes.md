# My notes for the Codeup Data Science course

## Foundational Knowledge
- AI vs ML vs DL: Machine Learning is a model adjustment tool that observes data, makes predictions using a model, and adjusts the model to make better predictions. The code to set this up is written by humans. Machine Learning is not entirely separate from AI- AI is an umbrella term for the automated handling of conditionals. Deep Learning is a specific application of Machine Learning that involves three or more layers of hidden (not human-designed) neural network nodes- the flexibility of Deep Learning allows systems to adjust to input in ways that humans can’t precisely code themselves.
- Parameters, hyperparameters, features, targets: A feature is an input, a parameter is a machine- or human-set portion of a model, and a target is the output. Hyperparameters are human adjustments to a model in order to help it better reach the correct target.

## CLI:
- Access the MySQL database (-p prompts for password): -u username -p -h IP-address
- code filename.filetype 
    * opens VS Code with specified file (creates new one if not exist)
- JupyterNB issues... You can use Command + T to open tabs in Terminal so you don't have to stop JupyterNB processes
- Multi-line cursor: Hold command, clickdrag

## SQL
### Basic Syntax
- show databases;
- use database_name;
- show tables;
- describe table_name;
- select column_name from table_name;
    * you can select * from table_name, or specify multiple columns
    * you can filter to an entry using WHERE, select * from table_name where condition_statment
    * you can also create aliases for columns, select column_name AS Column from table_name;
### Functions
- SUBSTR(string, index, step_number)
    * index starts before the position is read (first character is at index 1), step_number = 1 reads one character from index
- select datediff(curdate(), colname) as alias ----- return column with days between curdate() and colname (great for renure calculation)
### WHERE
- Used to filter the database with conditional statements before the data is pulled down
- Great for simple conditionals and also allows subqueries
### ORDER BY
- Used to order the output column by ASC or DESC order
    * DESC is reverse-alphabetical (Z is first)
    * DESC is highest-to-lowest number
### GROUP BY
- Analyze records (rows) based on specified column
- Used to run aggregate functions on multiple records based on similar value in the column 
    * aggregate functions: avg(), min(), max(), std(), etc
    * avg(numbers_column) would return average of all values
    * select numbers_column, avg(numbers_column) from numbers GROUP BY numbers_column would return nothing very useful, it would return each unique number's average (average of 5 is 5)
### JOIN
- Used to temporarily merge tables on a similar column
- INNER uses AND logic, LEFT / RIGHT use OR logic and prepend/append, the FROM table is indicated LEFT or RIGHT
- ON vs USING() - ON preserves the linked key while USING() merges the linked keys into one column
    * use the USING() function to merge same-name columns, but this will throw an error if two tables have more than one similar column name
### SUBQUERIES
- Flexible tool to return a query's results to a query
- Often used in WHERE clause, example: WHERE emp_no IN (SELECT emp_no FROM employees WHERE to_date > curdate())
### CASE 
- Used to temporarily create a column from scratch with conditional assignment of records
- uses WHEN condition THEN append new info ELSE append new info END AS new column name
- use CASE in SELECT statement
### HAVING
- Used to filter after records are extracted/sliced
    * Example: With GROUP BY colname, only show a few of the rows
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
    * bool(0) returns False, bool(1) returns True
### Cool things
- "a" in "banana" returns True
- print(string, int) converts the int to str and adds a space between string and int. Don't need to print("string " + str(int))
- {} performs simple operations in distressed conditions, great with formatted strings. Formatted string example: print(f"here is my string that takes {number} and multiplies it by two which is {number * 2}")
- Slice: [0:3], [2:], [:-1] (works with str and list)
- list[0][0] returns first char of first string in list
- string[0] returns first char of string
- the char _ is a trash variable, [num for _ in range(1, 5)]
- for col in enumerate(cols): ----- i, col gen'd for you, no need to initialize i before the loop (cleaner code)
### String methods
- JupyterNB: can use TAB to check available methods
    * Example: string.lower() can be found with string. + TAB
- string.count("a") returns number of "a" in string
- "b a n a n a".split(" ") returns list of each letter using the " " delimiter
- delimiter.join(list) returns a string from the list with the delimiter spacer
- string.strip() deletes left/right whitespace, new lines, and tabs
- string.isnumeric() checks for a string comprised of numbers
### Lists
- A grouping of values, created with []
- Can hold any data type including list and dict
    * list containing list is two-dimensional data (a spreadsheet)
- JupyterNB: use TAB to check available methods, list. + TAB
- List comprehensions and operations: return [n + 1 for n in numbers], return [n + 10 for n % 2 == 0 in numbers]
    * List comprehension only returns affected items; to preserve original list's unaffected items in return use [output if condition else output for item in list]
### Dictionaries
- A labeled list, created with {}, uses key:value pairs (each pair should be considered its own variable)
- JupyterNB: can use TAB to check available methods, dictionary. + TAB
- dict.keys() returns keys, dict.values() returns values
- dict[0] returns first entry in the dictionary, dict[0][key] returns the value for the key in the first entry
### Tuples
- A list that can't change (a constant variable for a grouping), uses () instead of []
- Often returned from functions
    * return sum(numbers), avg ----- returns tuple (sum, avg)
- tuple[0] returns first item in tuple like normal
- enumerate() works with tuples
    * for x in enumerate(four_values): print(x) ---- (0, value1) (1, value2) (2, value3) (3, value4)
### Output formatting
- Use .format() to make a table like in the following example
    * print(" stuff | stuff | stuff ")
    * print("-------|-------|-------")
    * print(f"|{:<8}|{:<8}|{:<8}|".format(stuff, stuff, stuff)
- lambda: list.sort(key=lambda x: len(item)) ----- sorts based on length of each item
### Functions
- Parameters and Arguments: Parameter is the shell, Argument is the value put in the shell.
### Importing
#### Basic info
- Import from Python Standard Library, packages/libraries installed from pip/conda, or our own .py files
- docs.python.org/3/library
#### Import syntax
- import math ----- imports the Python Standard Library math library, use math. + TAB to see list of functions
    * import math as m ----- alias math as m
    * math.function(argument, argument)
- from math import function, function, function ----- imports specific functions from math
    * from math import tan
    * tan(argument, argument)
- from math import tan as alias ----- alias the function
#### Importing self-created files
- create file util.py, then in new .py, import util
    * from util import function, function, function
    * function(argument, argument)
### key= usage
- key= is used to change the default output
    * max(list, key=list.method) ----- chooses highest based on the method (doesn't need parentheses)
    * list.sort(key=lambda x:function) ----- sorts using x (an anonymous function declaration)
### lambda
- lambda is on-the-fly creation of a return
- Used to avoid creating a function for one or two uses
    * fun_name = lambda a, b: a + b ----- creates function that pulls in a and b, returns a + b
    * fun_name(1, 3) ----- returns 4
    * lambda x: try_me ----- calls the try_me function with x argument and returns try_me output
    * key=lambda x: try_me ----- uses the return of the try_me function (called with x argument) for the key
    * max(list, key=lambda x: try_me) ----- returns the biggest item of the list determined by the try_me function
### Sorting through a .json (a list of dictionaries)
- Can easily find highest or lowest value of a key in a list of dicts
    * max_dict = max(list_of_dicts, key=lambda x:dict["key"]) ----- stores as max_dict the dict in the list with the highest dict["key"]
    * print(max_dict["key"]) ----- quick solution to printing the max_value of a key shared across a list of dicts
    * understanding the key= in max() can yield very quick and clean results

## NumPy
- A staple library of the scientific community and the foothold of Python in science
- NumPy arrays (and the array functions) are excellent
    * Boolean masks used to filter arrays; mask = array conditions, a[mask]
### NumPy tools
- array.size ----- returns number of values in array
- (a > 1).sum() ----- returns sum of values in a that are greater than 1
- array_test = numpy.array(list) ----- set array_test to numpy array of the list
- array_test = numpy.random.randn(5) ----- set array_test to numpy array of 5 random numbers
    * numpy.random.randn(2, 2) ----- creates 2x2 array of random numbers
- numpy.arange(start, stop, step) ----- creates one-row array of range start,stop with step gaps
- numpy.linspace(start, stop, num) ----- creates one-row array of range start,stop with num columns
- sum, min, max, std, mean, product, and more for basic math on arrays
    * sum(array, axis=1) ----- sum each row's contents, do not sum the rows together
#### NumPy Array Examples
- do element-wise arithmetic and comparison, such as array_test + 1, array_test == list, array_test * array_test_2, etc
    * a = numpy.array([0,1,2,3,4,5])
    * a == 2 returns array of bool results
    * a[a == 2] returns the indexed elements of a with True values (masks)
- use [row, column] indexing
    * m[0,2] of 3x3 array ----- [row_index, column_index]
    * m[0:1, 0:1] of 3x3 array ----- returns columns 0 and 1 from row 0 and 1, preserves formatting
    * m[:,1] of 3x3 array ----- returns column 1 from all rows

## Pandas
- Another excellent staple of the Python science community
- Built on Numpy and Matplotlib
- Dataframes (df) are extremely powerful data representation tools
    * df.attribute is easily modified
    * 2D array with labeled axes (labeled rows, labeled columns), array is a NumPy array
- Series Methods v Series Attributes: Series Attributes return valuable information about the Series object (series.dtype, series.size, series.shape), they do not perform calculations or require parentheses. Series Methods perform calculations or operations on a copy of a series and return the copy (series.head(n=5), series.tail(n=5), series.value_counts())
    * dtype: Python type str is Pandas dtype object (object = str or mixed, int64 is int, float64 is float, bool is bool, datetime64 is datetime...)
- Vectorized Operations: Call default Python methods on Pandas Series, for example: series_name.str.capitalize() will capitalize all values in the series.
- Method Chaining: using multiple methods at once - ex: series_name[str.method()].str.method()
### Working with Dates in Pandas
- pd.to_datetime(date_value, format='%b:%d:%Y') ----- highly-flexible date reader, throw something in get a better format back, in this case you specify format of a date_value having colon separation so that to_datetime can convert it
- pd.to_datetime(df.date) ----- element-wise converts date column's values, casts column as datetime64 dtype
    * with datetime64 column, can use df.date.dt.day to element-wise change date to day
    * .month, .year, .quarter, .day_name() etc all available in place of day
- number of observations per month: df.date.dt.month.value_counts().sort_index()
    *value_counts() orders on count, not month, so use sort_index()
- df['month'].value_counts() after casting df.date.dt.month to df['month']
- df.loc[date_start:date_end] ----- inclusive slicing of dataframe
- df['rolling_weekly_average'] = df.colname.rolling(7).mean() - first 6 values will be null, 7th will show first calculation
    * can also use .asfreq('W').transform('mean')
    * can also do rolling sums (.sum()) and change the roll iteration (.rolling(30))
- df['weekday'] = df.col_cast_as_datetime64.day_name() ----- create new column with name of day using another date column
- Create a data range from scratch: pd.date_range('starting_date', freq='D', periods=num_days_starting_with_starting_date)
- Create data from scratch: np.random.rand(8) ----- array of 8 random values between 0 and 1
- df.index.strftime('%b %D, %Y) ----- abbreviated_month day, year from a datetime64 column
    * Look up the formats for more options
- can subtract two datetime64 values to get a time value, can divide that value by pd.Timedelta('1d') to get specifically the number of days (destroys the Timedelta object)
    - df.colname.max() - df.colname ----- find amount of time difference from value to max
    - same case with pd.Timedelta('1d')
#### Up/Down Sampling
- If your data is hourly, convert not-exactly-hourly times to hourly (upsample) and fill nulls, or aggregate (downsample) to daily/weekly/monthly/etc
- Upsampling: by_day = df.asfreq('D') ----- take df with datetime64 column(s), convert column(s) to days
- Upsampling has nulls: by_day.assign(ffill=lambda df: df.coffee_consumption.ffill(), bfill=lambda df: df.coffee_consumption.bfill()) ----- need to do this forward-fill and back-fill when upsampling creates null values, simply pushes previous value forward into null or pushes next value backwards into null
    * This is often used for date-based values where it makes sense to re-use previous or upcoming data in knowledge gaps
    * may also df.fillna(value) to fill these gaps with constants, average, etc
- Downsampling: df.resample('W').sum() ----- sum all days' values in a week, groupby week
    * '3W' - every three weeks, 'M', 'Y', 'H', ...
#### Lagging and Leading
- Great with pd.concat to add columns with calculations/reflections based on previous/upcoming values
- df.colname.diff() ----- difference between current element and previous one
    * can enter a number, .diff(3), to look at 3 elements ago
    * also enter negative values (-1) to look ahead
- df.colname.shift() ----- an array of colname but each value is shifted one index deeper
#### Timezones
- df.index.tz ----- shows timezone if available, probably not there
- df.tz_localize('America/Chicago') ----- sets timezone of all datetime64 columns
    * df.tz_localize(None) ----- removes timezone information
#### Plotting
- df.resample('W').sum().colname.plot() ----- line plot by week for a column
- df[[colname]].plot() ----- line plot a column
### Pandas tools
- df['column_name'].head(10) ----- returns rows 0 to 9 of the column (this avoids issues with spaces in column names or reserved words as column names)
- df.first_name.head(10) ----- also returns rows 0 to 9 of the column
    * first_name is NOT a variable, it is a named column that exists in df. 
- pd.Series(list_name) ----- creates a column (first index 0) of row-separated values from list_name
- pd.Series(dict_name) ----- creates label column and value column for dict_name keys and values, respectfully
- series.size ----- returns length of series
- df.index returns list of indices for dataframe, df.values returns list of values
- df.sample(num) ----- returns a random sample of num amount of values
- series.astype(object) ----- returns a copy of a series with its dtype changed to object
- series.value_counts(normalize=False, sort=True, ascending=False, bins=None, dropna=True)
- series_or_df.describe() ----- summary statistics of a series or dataframe 
    * for series type object: row count, unique values, most frequent value, how many times most frequent value occurs
    * for series type int64: count_uniques, mean, std, min, 25%, 50%, 75%, max
- (bool_mask).any() ----- returns True if any bool_mask value is True
- (bool_mask).all() ----- returns True if all bool_mask values are True, otherwise return False
- series_name[boolean_mask] ----- returns values of series_name that return True in boolean mask
- series.apply(function) ----- applies function to each element in the series, function can be user-defined, built-in, lambda, etc
- series_name.isin(series_name_2) ----- returns array of bool values where series_name is in series_name_2
    * series_name[series_name.isin(series_name)] ----- uses bool array as boolean mask
- dict_series["key1":"key2"] ----- returns rows between and including "key1" and "key2"
- dict_series[["key1", "key5", "key9"]] ----- return rows with index "key1", "key5", "key9"
- bin_assignment_array = pd.cut(series, [start, cut, cut, cut, stop]) ----- bin values from series into 4 different bins, stored as (start, cut], (cut, cut], (cut, cut], (cut, stop]
    * pd.cut(df, bin=bin_edges , labels=[bin_label, bin_label, bin_label]).value_counts().sort_index() ----- displays count of each bin, ordered by index (not highest count to lowest count)
### DataFrames
- 2-Dimensional data with a lot of functionality
- Made from pandas Series
- pd.DataFrame(list_of_dicts) ----- Make a dataframe from a list of dictionaries
    * Dictionary keys should be the same between all dictionaries in the list
#### DataFrame Syntax
- df.columns = ['col1', 'col2', 'col3'] ----- rename 0, 1, 2 columns to 'col1' 'col2' 'col3'
- np.repeat(df.col1.iloc[0], df.col2.iloc[0]) ----- create 1-D array of rows where # is df.col2.iloc[0] and value is df.col1.iloc[0]
- df.loc[df.index.repeat(df.col_with_aggregated_count)].reset_index(drop=True) ----- repeat in-order each index the number of times specified by df.col_with_aggregated_count, keeping the dataframe, reassigning the index to the new rows
- list_of_dicts_dataframe.key.sum() ----- sum all values of key in list_of_dicts_dataframe
    * .max(), .mean(), etc all work
- df[value].argmax() ----- gives index of df where max value exists
- df[df.index == 0] ----- give the entire row of first index of df
- df[df.key == value] ----- return entire row where key is set to value
- df.key.idxmax() ----- return index for the key's highest value in df
    * df[df.index == df.key.idxmax()] ----- return entire row of index with max value of key
- df[[key1, key2]] ----- returns dataframe with column key1 and key2
    * keys = [key1, key2]
    * df[keys]
- df.colname > 100 ----- returns bool mask
    * df[(df.colname > 100) & ((df.colname < 400) | (df.colname == 500))] ----- use & and | operators for AND and OR, needs parentheses because bool array is created in parentheses *then* bool arrays are compared
- df[condition1 & condition2] ----- no need for parentheses
- df_copy = df.copy() ----- makes a copy, can't assign df_copy to df or else they'll point to same dataframe
- df_copy.drop(columns=[colname], inplace=True) ----- permanently alters df_copy, drops colname
- df_copy.rename(columns={colname1: colname2, colname5: colname6}) ----- permanently alters df_copy, changes colname1 to colname2, changes colname5 to colname6
- df_copy[new_column] = df_copy.colname > 100 ----- returns bool array in new_column for each row that is > 100 in colname
    * can use the new column as a bool mask!!
- df_copy.assign(new_colname=df.colname > 100) ----- same as previous
- df.sort_values(by=col_name, ascending=False) ----- sort df by col_name in descending order
- df.nunique(axis=1) < ncols ----- setting ncols at start, then see if there are duplicates in a row. By setting this result to a new column, you can run this check for all rows in a dataframe and store the result in the column.
- Change individual numbers throughout df based on bool mask:
    * num = df._get_numeric_data()
    * num[num < 0] = 0 ----- all values less-than zero individually set to zero
### "Advanced" Dataframes
- Produce dataframe from dictionary: pd.Dataframe({'A': [1,2,3], 'B': [0,1,2])
- Produce dataframe from list: pd.Dataframe([[1,2,3], [4,5,6]])
- Labeled dataframe from list: pd.Dataframe(numpy_array, columns=['a', 'b', 'c'])
- Use specific columns from dataframe: df[['col1', 'col2, 'col5']]
- Slice row and column at once using names/bools: df.loc[row_indexer, col3:col4] ----- returns rows of row_indexer (can be bool mask!) and one column within the bounds (INCLUSIVE)
- Slice row and column at once using index: df.iloc[1:3, :]
- Run multiple aggregate functions on a dataframe: df[['col1', 'col2', 'col5']].agg(['mean', 'min']) ----- returns new dataframe with agg functions ran on all columns specified in df
- Group By in pandas: df.groupby('col_want_to_group_by').col_want_to_do_func_on.mean()
    * df.groupby('col_want_to_group_by').col_want_to_do_func_on.agg(['mean', 'median', 'count'])
    * can do multiple columns in groupby
    * can rename aggregate function columns: df.columns = ['name1', 'name2']
- Programatically insert values in new column: df['new_col'] = np.where(df.col > 100, 'me_true', 'me_false')
- Create new column on dataframe using agg functions: df.assign(new_col=df.groupby('show_me_col').calc_me_col.transform('mean')) ----- transform keeps index intact
- Join dataframes together: pd.concat([df1, df2], axis=0, ignore_index=True) ----- adds rows, use axis=1 to add columns
    * .concat here is very raw, may create nulls and not line up exactly
- SQL join in python: df1.merge(df2, left_on='df1_col', right_on='df2_col', how='outer', indicator=True) 
    * _x, _y, _merge in colnames help out, so does .drop and .rename
    * use .merge when columns in common between two dataframes, helps keeps things together
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
    * plt.hist((series1, series2), ...)
### Matplotlib Syntax
- Array x and array y passed as arguments for x columns (plt.bar(x,y))
- df.plot() ----- put dataframe to a plot
- df.plot.barh() ----- put dataframe to a bar plot
- x = list(range(150)) -- plt.plot(x) -- plt.show()
    * JupyterNB will automatically show a plot without plt.show(), but .py scripts ran from Terminal require plt.show()
- plt.rc('figure', figsize=(13,6)) ----- set overall
- plt.rc('axes.spines', top=False, right=False) ----- set overall
- plt.rc('font', size=13) ----- set overall
### Matplotlib Methods
- plot
    * defaults to line plot. plt.plot(x, y, c='color')
    * scatter(), bar(), barh(), hist(), and more
    * c= ----- color, can use alpha= to do transparency (0.0 - 1.0)
    * s= ----- size of dots on scatterplot
    * ls= ----- line type for line chart, ':' is dotted, '--' is dashed, etc
    * bins=[list_of_cuts]
    * align='left' ----- aligns to left
    * edgecolor= ----- sets edge for the data (ex: border on bars in chart)
- show()
- title('title'), xlabel('clabel'), ylabel('ylabel')
- xlim(bounds), ylim(bounds)
- xticks(list_of_int_ticks, list_of_str_tick_names), yticks(list, list)
    * rotation=num ----- rotate each tick num degrees
- text(left_boundary_coords_for_txt, txt_to_place, fontsize=num, color='color')
- annotate('text', xy=(coords_for_tip), xytext=(coords_for_left_bound), arrowprops={'key':'value'})
- figure(figsize=(num_width, num_height))
- legend(loc='upper right') ----- puts legend in upper right
- savefig('name_of_my_new_figure') ----- generates .png of your figure
- plt.subplot
    * subplot(num_of_rows, num_of_cols, index_start_at_1)
    * plt.plot(list, list)
    * plt.title('title1')
    * subplot(num_of_rows, num_of_cols, index_start_at_1)
    * plt.plot(list, list)
    * plt.title('title2')
    * plt.tight_layout() ----- fixes spacing
    * plt.suptitle('title') ----- super (wrapper) title for subplots
    * plt.show() ----- gens 2 subplots, then plt.show() puts them next to each other

## Seaborn
- Library that builds on matplotlib and integrates well with pandas
- Powerful in its defaults!
- relplot, displot, catplot return figure-level objects using kind= , but of course you can declare the specific plot itself and return an axes-level object instead
    * No advantage either way, just uses different syntax
### Seaborn Syntax, Methods
- import seaborn as sns
- df = sns.load_dataset('dataset') ----- does same as pydataset
- sns.relplot(x='col1', y='col2', data=df) ----- returns scatterplot for df using col1 for x axis and col2 for y axis
    * once plotted, can use plt.title, plt.xlabel, etc as normal
- sns.histplot(df.col_name, kde=True) ----- histogram (bar chart of frequency count) of col_name, with kernel density estimator
- sns.boxplot(data=df) ----- box and whisker plot (inter-quartile range, quartiles, median, and outliers all on a plot)
- sns.catplot(x=, y=, col=, col_wrap=, hue=, data=, kind=) ----- categorical plot (default is silo'd dot plot, can kind='count')
- sns.heatmap(data, annot=True, cmap=plt.cm.Greens) ----- heatmap with annotations using the Greens color palette
    * https://seaborn.pydata.org/tutorial/color_palettes.html
- sns.set_palette("colorblind") ----- makes your stuff colorblind-friendly
- sns.pairplot(df) ----- quickie for combinations of data in df
- sns.jointplot(data=df, x=, y=) ----- attaches a histogram per axis for a scatterplot
### Seaborn Arguments
- col='col1' ----- chart for each unique value in col1
- hue='col1' ----- separate color for each unique value in col1
- style='col1' ----- changes style of plot point for each unique value in col1
- kind='line' ----- draws a line to each plot point
### Seaborn Accessors
- You can use .axes or .fig to access, for example, sns.pairplot()
    - sns.pairplot(arguments).axes ----- each graph in figure
    - sns.pairplot(arguments).fig ----- figure as a whole (include all graphs)
    - sns.pairplot(arguments).axes.flat ----- list of pointers for each graph
    - for i in pairplot.axes.flat ----- access each pointer

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
    * all functions start with =
    * point function at another cell to run function on the other and return the value in the current cell
    * bottom-right of cell has a button... double-clicking it allows you to run the function for all rows... ex: extract year from a date
    * values will update for all connected cells if the looked-at cell changes... VLOOKUP works nice with this
- Conditional Formatting and Alternating Colors for readability
- fn + f4 is the absolute reference to a cell or cell range
- Pivot Table: Select All (the entire table, for convenience), Insert, Create Pivot Table (make a new sheet), add rows and columns using interface
    * Insert, Chart... ----- Produces chart, can customize
- Splitting text: Select data, Data, Split Data *OR* =SPLIT(cell, delimiter)
- =CONCATENATE(cell, delimiter_if_desire, cell, cell, delimiter, cell...)
### Spreadsheets Functions
- =YEAR(B2), =MONTH(B2)... ----- use existing functions against cell B2
- =B2-B3 ----- subtract B3 from B2 in cell
- Filtering ----- Select all, Data, Create Filter, hover over column you want to filter, apply a filter to it
    * Filter Views allows you to view the filtered version while the shared view for others is unchanged. Can save the view and share it with others if you want, it appears listed under the Filter Views tab in Google Sheets.
- =IF(condition, value_if_true, value_if_false)
    * =IF(AND(B2 > 100, B3 < 50), True, False)
- =SUM(value1, value2), =SUMIF(range, condition) =AVERAGE(A1:A100), =COUNT(A1:A100), =COUNTIF(range, condition), =MIN(B1:B100), =MAX(C42:C999)
    * Conditions (criterion) can be a pointer towards a cell with logic in it, so a cell that generates a list under it can be referenced as the criterion for =COUNTIF() to find the count of each value in the list from the whole table
    * Summary statistics can be initiated from any cell for any cell range... convention is to put a small table in the Sheet next to the values to show the statistics
- =VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE) ----- vertically searches range_to_search for key, if it finds it, returns col_to_return, if it's not exact match, ignores it (due to FALSE)
    * VLOOKUP looks at first column specified... be careful
- =LEFT(cell, char_count), =MID(cell, start_position, steps)
- IFERROR(try, except)
- =SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc}) ----- creates a red in-cell bar chart of data from range with maxed bar when reaching max value of range

## Tableau
- Visualization tool, can be used for presentations
- Public is free but cannot privately save your work (publishes everything)
    * Save with each new sheet as a standard... Nothing is autosaved so if it crashes you're donezo
- Faith's Tableau Public: https://public.tableau.com/app/profile/faith.kane
- Sean Oslin's Tableau Public: https://public.tableau.com/app/profile/sean.oslin
- A lot of people use the superstore CSV to learn and demo Tableau, you should consider using it to learn Tableau too
### Tableau Usage
- Consider exploring your data in Google Sheets first
    * Tableau is a bit slow for *exploration* compared to pivot tables in Google Sheets
    * Once you've discovered what you want, switch to Tableau for presentation and visualization creation
- CSV files are Text Files when ingesting data into Tableau
- Hide unnecessary columns using drop-downs in each column
    * Can unhide columns
- Filter results at top-right (intuitive)
- Put results to charts via button in bottom-left "Sheet 1"
    * Can rename tabs (will rename table [results])
    * Can add extra to name in the table and leave tab simplified
- Leftmost options (columns) - can adjust if needed
    * Can switch between Data tab and Analytics tab
    * Drag options up into Rows or Columns to add to table
    * Drag options into Marks, onto Label or Color to append certain data to table, right-click on existing Label/Color things and make changes to the appended data (very cool!), each drag is an added feature - move Legend to under Marks as a preference
    * Change number to currency - right click option, default properties, number format...
- Can click on leftmost options to display them
    * Rightmost tables are choices for displaying your data
- Semi-leftmost options (Measure Values) - change aggregations for any measure values
- Table - Right click on table things, change alias or other things about it
    * Change view width/height in dropdown at top of window (apparently Entire View is good for displaying later on)
- Transpose: Drag rows into column field, columns into row field (really simple)
- Change table format: select entire window, use MacOS File/Data/Etc bar (context menu), Format, Lines (change lines on table)
### Dashboard
- View multiple sheets in one dashboard
    * Drag sheets into playspace
    * "Entire View" option for sheets fills the box in the playspace
- Edit/hide titles, add "supertitle", etc in here
- Great for interactive deliverable for stakeholders that want to play with filters
### Story
- Essentially a slide deck/presentation for sheets/dashboards
    * Slides for one table in a slide... dashboard for multiple tables in a slide
- Captions are basically named slides
- Can drag text window from bottom left into slide and right click-edit it

## Storytelling
- Data requires velocity to be useful
### Visualization Considerations
- Expert-level visualizations != presentation-level visualization
    * The pivot tables are more appropriate for Appendix
    * If the audience has to read it, don't include it
- Serve the "why" first, then follow with the specifics
    * Leading with specifics will lose your audience
- Give the "why" some amplifying, relative information to help seat your audience
    * Avoid cluttering the "why" with too much amplification
- Design the velocity with your audience in mind
- Prepare to Create; Talk and Listen; Sketch; Prototype
    * Clear physical and mental room; Know your data; Understand your audience and Big Idea
    * Determine which framework to use (persuasive, man-in-hole, story), determine context, challenge, and solution
    * Understand your audience and use an appropriate approach
    * A topic isn't a big idea... use your chances to express the big idea
    * Explain out loud what your project is, take notes of feedback, make corrections [I'm working on... I'm trying to show... Why...]
    * Use everything so far to sketch out your ideas (brainstorm)
    * Refine the sketches into presentation material
- A non-correlation can be more important than a correlation
- Start with overview in presentation, dissect the focus later (start with churn v not churned, then dive into churn data)
- Relate the problem to the audience's interests and focus for maximum effect

## Statistics Notes
### Hot notes
- 1-Sample t-test (ttest-1samp) is done in non-optimal conditions, when categorical/discrete data isn't necessarily defined very well
    - assumes equal variance, normal distribution, and independence
- 2-Sample t-test (ttest-ind, mannwhitneyu) is done in most cases, when categories are fairly well-defined
    - parametric: same assumptions as ttest-1samp, non-parametric: assumes independence
- ANOVA (f-oneway, kruskal) is done more as discovery to check if categories/discretes have difference
    - same assumptions as parametric and non-parametric 2-sample t-tests
- Paired t-test (ttest_rel, wilcoxon) is done when one sample transforms in some way and you're checking if they're different before and after the transformation
- Linear correlation test (pearsonr, spearmanr) looks at the influence of change in one continuous variable against another continuous variable
    - parametric: assumes normal distribution, non-parametric: does not assume normality
- Categorical correlation test (chi2_contingency) looks at categorical variables against continuous variables rather than two continuous variables
    - same assumptionas as parametric and non-parametric for linear correlation
### Distributions
- Uniform - equal likelihood of all outcomes (coin)
    * stats.randint(low, high_not_including)
- Binomial - two outcomes (success/failure)
    * stats.binom(rolls, probability_of_one_outcome)
- Normal - continuous random variable (bell curve)
    * stats.norm(mean, standard_deviation)
- Poisson - events per time interval
    * stats.poisson(number)
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
    * Can take shortcuts, it's not standard practice but you can do this and explain what's going on
- Centering is important to take a pile of data purely as its distance away from the mean in positive/negative direction
    * Centering is also known as de-meaning a vector
- Z-Score is like centering but it's the distance from the mean in terms of standard deviation
    * zscore = (value - population_mean) / standard_deviation
    * zscore = (value - avg(value_list)) / std(value_list)
    * from scipy import stats, stats.zscore(value_list) ----- returns Z-Score of value_list
### Python/NumPy/Pandas
- Figure out a way to represent our data (ex: dice_outcomes = [1,2,3,4,5,6])
- Create a matrix of random data, rows = simulations, columns = trial
    * For example, rolling 2 dice 10,000 times means rows=10,000 and columns = 2 because we roll 2 dice each time
- Apply an aggregate function, row-wise to get the results of the simulation
- Apply a final aggregate to get our probability
#### Deeper on Python/np/pd
- setting rows as variable and columns as variable helps with dataframe formatting
    * nrows, ncols... df.reshape(nrows, ncols)
- .mean() against a boolean list will give count_of_trues / length_of_list
- Rolling two dice at once: to sum an iteration of rolling two die, use axis=1 as the argument for .sum()
- np.random.choice(outcomes, size=(simulations, trials))
    * rolls = np.random.choice([1,2,3,4,5,6], 1_000_000)
    * rolls[0:10] ----- shows first 10 rolls
    * (rolls == 5).mean() ----- times_rolled_5 / total_rolls, or the calculated probability (not theoretical)
    * ((rolls == 5) & (rolls == 6)).mean()
    * size=(experiments, number_of_dice per experiment)
- weigh outcomes: np.random.choice(outcomes, size=, p=[0.55, 0.45])
### Hypothesis Testing
- Taking sample data and generalizing for a larger population... Comparing, testing, predicting future outcomes... Final result is probability scores
- Often takes the form of distributions
- Null hypothesis: all cases that are NOT the alternative hypothesis, as $H_{0}$ -- H with subscript 0
    * Do those who churn spend more per month than those who don't? Null hypothesis: No, they spend less or equal to
- Alternative hypothesis: The hypothesis you decide, as $H_{a}$ -- H subscript a
    * Do those who churn spend more per month than those who don't? Alternative hypothesis: Yes, they spend more
#### Steps
1. ID the question
2. state the hypotheses
3. validate the assumptions
4. run our test, set our significance level (alpha)
    * industry standards are 5% or 1%, but other values are fine
5. get results: test statistic and p-value
    * p-value: probability that we observed this result due to chance... if it's less than our alpha, we reject the null hypothesis... there IS a difference, or a relationship.
6. evaluate results and draw conclusions
    * "We reject the alternative hypothesis" or "We reject the null hypothesis" is formalspeak
    * False Negative Rate: Probability of a false negative, or the probability of a type 2 error... P(FN) = P(Type II Error)... failure to reject the null hypothesis... exceeding alpha
    * False Positive Rate: Probability of a false positive, or the probability of a type 1 error... P(FP) = P(Type I Error)... said there was a difference or relationship, when there wasn't one... within alpha
#### Test Types
- Comparison of Means (t-test) ----- bool v continuous/numeric, the mean is calculated from the cont/num variable
- Comparison of Proportions/Relationships (chi-square) ----- bool v bool or bool v categorical
- Linear correlation (does one cont value affect another cont value) ----- numeric v numeric, continuous v continuous
- Check variances for equality: stats.levene(sample1, sample2)
    * the threshold for significant inequality is pvalue < .05 or .01
- Finding *linear* corr: corr, p = stats.pearsonr(x, y) ----- Pearson correlation coefficient calculation
    * Finding r using dataframe: df.corr() --- df[['col1', 'col2']].corr() ----- find r for col1 and col2
- Finding *non-linear* corr: stats.spearmanr()
- Chi2 Test (for Independence) ----- Compare two categorical variables, ex: gender v phone_manufacturer_choice, to see if they are independent of one another or not
    * pd.crosstab against two *categorical* columns, then stats.chi2_contingency of that dataframe (returns chi2, pvalue, degf, expected_values_array)
    * Degree of Freedom: (num_cols - 1) * (num_rows - 1)
    * Check df for potential categorical columns: df.nunique() ----- returns count of unique values for each column, if column has low count then good chance it's categorical
### Comparing Means
- "(x)-tail, (x)-sample t-test"
- mu is population mean, subscript is the population
- if t-statistic is proper and p-value is significant (less than 0.05), then we reject the null hypothesis
    * Null: sample <= theoretical, then if t-statistic > 0 and p-value < 0.05, we reject the null hypothesis. If not, we can't reject it.
    * Null: sample == theoretical, then we only care about p-value being 0.05 / 2
- Steps: Plot distributions (ex: histogram); Establish hypothesis; Set significance level alpha to .05; Verify assumptions (normal distribution, or at least 30 observations with normal-looking distribution [more observations = less needed to look like normal distribution]); Compute test statistic and probability using scipy.stats.ttest_1samp(); Decide. 
- .sf() * 2 is your friend... be careful though!
- Compare an observed mu to the theoretical mu (sample vs whole): One sample t-test, normally distributed
    * t, p = scipy.stats.ttest_1samp(array_of_sample, array_of_overall)
- Compare two observed mu (sample against sample): Independent t-test, normally distributed, equal variances
    * t,p = scipy.stats.ttest_ind(sample1, sample2, equal_var=False)
- Compare multiple observed mu: ANOVA, normally distributed, independent variables, equal variances
    * scipy.stats.f_oneway(sample1, sample2, sample3, ....,equal_var=False)
### Probabilities
- P(A), P(A|B), Bayes Theorem (P(A|B) = P(B|A)P(A)/P(B)) ----- probability of A, probability of A given B (when B happens, chance of A), Bayes Theorem (to calculate A or B using algebra)
- Quick probability of a given value among values: df.col.value_counts(normalize=True)
    * Can pass two or more columns too, df[['col1','col2']].value_counts(normalize=True), shows probability (occurence rate) of each combination
    * Can also do groupby with value_counts for two or more columns
- Low probability combination of observed values is an anomaly!


## Bringing it all together
- from env import user, password, host
- def get_connection(db, user=user, host=host, password=password): url = f'protocol://[user[:password]@]hostname/database_name'
    * url = mysql+pymysql://codeup:p@assw0rd@123.123.123.123/some_db ----- Notice some_db? Same as USE DATABASE;
    * pd.read_sql('SELECT * FROM employees LIMIT 10', url)
    * query = '''
    * SELECT
    *     emp_no,
    *     to_date
    * FROM employees
    * WHERE to_date > curdate()
    * LIMIT 100
    * '''
    * cur_emps = pd.read_sql(query, url)
- set df to file pulled from the MySQL database
- df.head() and df.tail() to return the data first 5 rows and last 5 rows
    * series attributes to check for more information
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
    * Data + Answers, with ML, creates rules
    * Traditional programming doesn't seek to create rules, it creates answers
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
    * Interpretable, Flexible, Easily-Implemented, Efficient
    * Need to remove unrelated attributes, not a top-performing algorithm
- **Decision Tree** - Sequence of rules to classify two or more classes via one-input-binary-output nodes
    * Simple to Understand/Visualize/Explain, Low-Prep, Handle numerical and categorical data, performs well
    * Overfitting risk, unstable
- Naive Bayes - contingent probabilities - low # of observations (in the hundreds)
- **K-Nearest Neighbors (KNN)** - Predictions based on how close new data is to known data (top-5 closest known datapoints are 'votes')
    * Simple, Robust to noise, just-in-time calculation, can be updated over time
    * Need to determine K, high computational cost, curse of dimensionality (distances can break down in high-dimensional space)
- **Random Forest** - Lots of decision trees
    * Less risk of overfitting than one decision tree, more accurate than decision tree (due to moar trees)
    * High computational demand, difficult to implement, hard to explain (black-box factor)
- Many more

## Regression
- Resources: "String and straw" animation, https://setosa.io/ev/ordinary-least-squares-regression/
- Supervised algorithm prosecuting a labeled target
- Instead of binary/multi target, **it's a continuous target**
- Involves scaling as part of preparation
    * A number like cost ($100k - $1,000k) compared to square footage (700-2500) would need to be scaled for the model (even rates of change)
    * Outliers affect regression greatly, discover and eliminate them
        * sns.boxplot(data=df) ----- box/whisker marks outliers
- Regression baseline generally involves mean or median (not mode)
    * Mode of continuous values doens't make sense... may only have one or two in common for thousands of observations
    * Plotted baseline is a horizontal line at the median/mean
- Evaluation is different
    * No true/false positives because no binary check
    * Looking at vertical distance of data and prediction from the trend line
        * Trying to minimize the **difference** in distance
    * May need polynomial trend line rather than linear... exploration decides it
- Regression tends to work better on normal distributions
- Relationships between variables being >80%, you can safely drop a variable
### Strategy 
- Model complexity choice: Reduction of error, variance, and bias^2 is the goal
### Regression Algorithms
- Linear Regression
- Ordinary Least Squares (OLS)
    * minimizes sum of squared differences in the linear model compared to the actual data points
- LASSO+LARS - LassoLars
    * uses regularization penalty for independent variables to minimize certain features (a form of automatic feature selection)
    * Can change slope of the regression line to reduce variance and increase bias
- Polynomial Regression
    * curved lines (be wary of overfitting with 'too curvy' regression line)
- Generalized Linear Model - TweedieRegressor
    * reduces multiple distribution options

## Clustering
- Using metric groupings to make predictions
- Great for anomaly detection (doesn't fit in normal cluster)
- Very important to scale data before clustering
### Techniques
- Heirarchical - Upwards or downwards
- **K-Means** - 'centroids', or mean-distance of a certain cluster (most popular) 
    * Randomly plots the chosen number of centroids, then moves the centroids to reduce the mean distance of datapoints to the centroids
    * Hyperparameter is the number of centroids
        * Choose this number based on: domain knowledge (iris: 3 species, 3 clusters)
        * Choose this number based on: alt knowledge (grouping by location)
        * Choose this number based on: exploration (viausalization has 3 clusters)
        * Choose this number based on: computing inertia (retroactively changing # clusters to find the 'elbow'- first few clusters drop inertia significantly, where the line goes more-horizontal from more vertical, choose that k value)
    * May be able to choose the centroid locations for lat/long clustering (choosing city centers)
        * Actually, I think you'd put lat/longs to categories (within x distance of [city]), which isn't the purpose of *algorithmic* clustering
- DBSCAN Video - density-based (different from centroids), good at finding weird shapes in data, but computationally expensive
    * Draws a perimeter around each datapoint, chains overlapping perimeters, datapoints without overlap are considered outliers
    * Hyperparameter is the radius size for the perimeter
    * C-based (that's what the DB references)
### Use Cases
- Exploration
    * Give names to groups/labels
    * Spread data into subgroups
    * Analyze relationship to target (think: Simpson's Paradox)
- Machine Learning
    * Use clusters as target
        * Setting y_train to train['cluster']
    * Use clusters as features
        * Done if one cluster is a good driver of the target
        * One-hot encode a column for that cluster, use in X_train
    * Model clusters separately (split data and run different algorithm)
        * model.fit(train[train.cluster == 0][['col1','col2']], y_train)
### Outliers
- Drop based on domain knowledge (an adult can't weight 19 pounds)
- If outlier doesn't change results, then feel free to drop
- If outlier affects *both* results and assumptions... compare including- and excluding-outlier results
### Syntax
- from sklearn.cluster import kmeans
- kmeans = KMeans(n_clusters=3, random_state=123)
- kmeans.fit(X_train_scaled) ----- notice there's no y_train, because there is no labeled target to serve as the answer for the prediction
- df['cluster'] = kmeans.predict(X_train_scaled) ----- no y_train
- train['cluster'] = kmeans.predict(X_train_scaled)
- kmeans.cluster_centers_ ----- location of each centerpoint
- kmeans.labels_ ----- labels of each observation
- kmeans.inertia_ ----- sum of (squared) distances between samples and their closest cluster centerpoint
- centroids = df.groupby('cluster')['col1','col2','col3',...].mean() ----- mean distance to centerpoint for each specified column of data against each cluster

## Time-Series
- Sub-methodology of supervised machine learning involving temporal data
- Focus is on time-wise trends, making time-based predictions on how data *will* be
- Time is linear... so time-series features involved are always linearly-correlated with each other (one goes up, another goes down... because it's on the linear timeline)
    * This means it has to be treated differently from linear regression
- Uses previous outcomes as features to predict future outcomes
    * EX: Customer growth in January (a target of regression) is one observation, multiple months' observed growth together are the feature
    * This differs from regression, which focuses on the attributes driving an outcome and has no time component
- Some examples include:
    - repeating upward/downward trends (seasonality)
    - fluctuation cycles (seasonality at >2 year increments), 
    - autocorrelation (regression of outcomes, "regression of self")
### Forecasting
- Last Observed Value (as prediction)
- Simple Average (average of all observations as prediction)
- Moving/Rolling Average (last portion of observed for this as prediction)
    * Usually last 7 days, the average of that, as the prediction
- Previous Cycle (exactly the last cycle as a whole [sliced] as prediction)
    * Year-Over-Year Difference is a form of this, and a good starting place when you haven't performed any time-series analysis yet. The reason is that each year has an even length, has its own seasons and trends that regularly occur in society, and is commonly referenced in most industries to check performance of production and sales. It's fairly easy to calculate, you do a .diff(365) on day-resampled data then take the mean of all values, showing the overall difference. Then you predict using the final observed year's values, adding the overall difference to each value. Then calculate RMSE as normal.
- Holt's Linear Trend (a regression of previous cycles applied at end of observations)
    * import statsmodels.tsa.api.Holt
    * model = Holt(train[col], exponential=)
    * model.fit(smoothing_level = .1, smoothing_slope=.1, optimized=False)
    * model.predict(start=validate.index[0], end=validate.index[-1])
- Facebook Prophet's Model (next expected cycle based on previous cycles)
    * "Pretty good, but hard to install and get working"
### Considerations
- In-Sample and Out-of-Sample splits are split on seasons, not randomly-selected observations
    * Human-based split if pattern, percentage-based split if no pattern
        * df.plot() for date index and outcome value
        * df.resample('D').mean().plot(ax=ax, alpha=.5, label='Daily) ----- plot the data resampled to daily, can do for weekly/monthly/yearly/etc
    * To determine seasonal splits, you'll have to look at data before you split
    * To determine percentage splits, set train size and test size, then look at the rowcount and split the first 80% from the last 20%
        * train_end_index = round(df.shape[0] * train_size)
        * train = df.iloc[:train_end_index]
        * test = df.iloc[train_end_index:]
- Rolling averages on 3-, 7-, and 30-day windows
    * Must apply aggregation to rolling, so: df.resample('D').mean().rolling(30).mean().plot()
- ax = df.resample('M').mean().diff().plot() ----- plot change over time, in practice plot difference between a month and the month prior, do this lineplot for all months
    * df.resample('M').mean().plot(ax=ax, label='Monthly Average) ----- plots using same ax as previously-defined graph
    * df.resample('M').shift(12).plot(ax=ax, label='Last Year') ----- plots 12 months prior in place, so you can compare last year to this year

## Anomaly Detection
- Finding outliers (numerical distance) and anomalies (general difference) for the purpose of further investigation
    * Can come from novel patterns or from outlier datapoints
### Cases
- Contextual: "This action is okay here, but not okay here"
- Noise: "This action is more clean than normal"
- Point Anomaly: "This action is too far from the norm"
- Collective: "This action had an unusual combination"
- Novelty: "This pattern is unseen"
### Techniques
- Stats: Standard metrics like average and standard deviation, also moving averages
- Classification: Support Vector Machine (a regression of classification), Random Forest, Isolation Forest (calculates number of splits needed to isolate a specified point)
- Clustering: KMeans and DBSCAN
- Density: KNN Local Outlier Factor
### Anomalies - Continuous Values
- Use IQR to detect outliers
- Use Z-score to detect outliers
- Be careful of 'dogmatic' approaches to this (EX: always using >2 STD [2 sigma] to detect outliers)
### Anomalies - Discrete Values
- Use probabilities to detect low-occurence combinations! value_counts(normalize=True)
- Given time-series data, group on minute, hour, day, etc then value_counts(normalize=True)

## Scaling
- Used to fix distance-based calculations (DO IT EVERY TIME)
    * Definitely use on KNN, K-Means, etc
    * Might be required on linear/logistic regression
    * No need for decision tree and random forest
- Split data before scaling, and only scale on train
- Scale often... and when you scale, scale *everything* going into the model.
- **Scaling fixes the weight of one feature compared to another**
    * Prevents one feature from being drowned by another
        * Mathematically, you're equalizing density of features
    * Specifically fixes the euclidian distance calculation
        * d = sqrt((x1 - x2)^2 + (y1 - y2)^2)
    * In layman's terms, raw comparison of a number between 1-10 and a number between 1-1000 will give obvious preference to the 1-1000 number (the 1-1000 number moves more greatly than the 1-10 number), so scaling is needed
- Scaling is easily done using sklearn.preprocessing functions
### Scaling Methods
- "Normalization" (MinMaxScaler) is scaling into range 0 to 1
- StandardScaler centers the distribution's density on 0 and limits range
    * Use this guy for normal-ish distributions!
- RobustScaler also centers the distribution's density on 0 and limits range, but it de-weighs outliers as well
- QuantileTransformer attempts to normalize a distribution and center it on 0... be careful, make sure to check the visualization
    * If you really want your data to be normal then use this... it's fairly complex
### Scaling Syntax
- Note: Generally you want to return the scaler in addition to the scaled data from helper functions
- **MinMaxScaler**, **StandardScaler**, **RobustScaler**
    * scaler = sklearn.preprocessing.MinMaxScaler() --- or the other two
    * scaler.fit(train[['col1','col2','col3']])
        * Make sure to pass with [['colname']], it keeps the dataframe format (where ['colname'] passes a series)
    * scaled = scaler.transform(train[['col1','col2','col3']]) ----- creates 3-column NumPy array
    * train[['newcol1','newcol2','newcol3']] = scaled ----- assigns array to new columns in dataframe (preserves original columns)
- **QuantileTransformer**
    * scaler = QuantileTransformer(output_distribution='normal')
    * Follow above steps for rest

## Data Acquisition
- pd.read_clipboard ----- VERY COOL store data from your clipboard
- pd.read_excel, pd.read_csv, pd.read_sql
- can pull from Google Sheets from within Python using following sample code:
    * sheet_url = 'https://docs.google.com/spreadsheets/d/1Uhtml8KY19LILuZsrDtlsHHDC9wuDGUSe8LTEwvdI5g/edit#gid=341089357'    
    * csv_export_url = sheet_url.replace('/edit#gid=', '/export?format=csv&gid=')
- can pull from ANY online document using following sample code (only public-facing documents work):
    * df_s3 = pd.read_csv('https://s3.amazonaws.com/irs-form-990/index_2011.csv', encoding='unicode_escape')
### Data Caching
- Can save money and time (doesn't use Cloud services)
- df.to_csv("file.csv") ----- writes dataframe to a cached file.csv (not saved to disk)
- df.to_file(filename) ----- writes dataframe to disk

## Data Preparation
- **DOCUMENT YOUR DATA PREP**
- Categorical/Discrete features need to become numbers
    * Pclass 1,2,3 are ordinal/discrete, but can be treated as categorical if converted
    * Pname is categorical even though each value is unique
- If algorithm relies on *distance*, Continuous features may need to be scaled
    * Just look it up if you don't remember
- df.colname.map(dict_with_map_logic) ----- replace colname values identified in dict_with_map_logic keys with the associated value of the key:value pair
- pointers v assignments... careful when assigning dataframes to dataframes!!!!!
    * df2 = df1.copy() ----- disconnects df1 from df2, where without .copy(), changes in df2 would reflect in df2
- df = df.drop_duplicates() ----- drop duplicate rows in df
- df = df.drop(columns=['colname', 'colname2', ...]) ----- drop columns
### Nulls
- df.isna().sum() ----- give count of each feature's nulls
    * Same as df.isnull().sum()
    * Similar thing is df.isna().any()
- df = df.colname.fillna(value='value_want_to_fill_nulls_with') ----- fill nulls
- df = df.dropna() ----- drop all observations having a null value in any column
- df = df.astype('int') ----- convert all columns to int --- some issues from having null value in int column from SQL query converts the column to float, this is a way to undo it
### Encoding
- Associate each unique value with a number (label encoding)
    * Use label encoding when categories have an inherit order
- One-hot encoding: 1 or 0 in new column if row is or isn't that value
    * Use one-hot when there's no order
- pd.get_dummies(df['col1', 'col2'], drop_first=[True, True]) ----- automagically does one-hot encoding for unique values in col1 and col2
    * creates a new column for each unique value in col1 and col2 with 0 or 1 representing False and True respectively, drops first new column for col1 and col2 (less dimensionality)
### Tidying Data
- Great link: https://vita.had.co.nz/papers/tidy-data.pdf
- One cell for one value, no repeat cells or multi-value cells
- df[['newcol1', 'newcol2']] = df.col.str.split(':', expand = True) ----- creates new dataframe with columns for the split items, columns are newcol1 and newcol2
- df.pivot_table(index = ['col1', 'col2', ...], columns = 'colx', values = 'coly', aggfunc='mean').reset_index() ----- creates pivot table, aggregates duplicate rows, resets it from sub-dataframe format
### Univariate Exploration (distribution visualizations)
- sns.displot(x='colname', data=df) ----- quick distribution plot
### Bivariate Exploration
- sns.heatmap(df.corr(), cmap='Greens', annot=True, vmin=0, vmax=1) ----- quick correlation chart
    * If everything correlates mostly, then it's called "Multicolinearity"
### Train-Test Split
- Randomize entire dataset *before* splitting to remove potential bias (dataset potentially sorted)
- Make sure all splits include all options (stratify target)
- sklearn does randomization/stratification for you!
### Data Prep Tips
- pd.melt(df, id_vars='colname') ----- creates 'variable' and 'value' columns from columns not specified and their values
    * melt has multiple useful arguments to help make this better
- Use for loop to iterate through columns in dataframe and nest plt methods to push out different graphs for each column
    * numeric: 
    * object columns: df['colname'].value_counts(), df['colname'].value_counts(normalize=True, dropna=False)
    * df.isnull().sum() ----- prints all columns of df with number of null values in each column
- Curse of dimensionality: try to limit columns
    * df_dummy ----- new dimension-limited dataframe of "dummy data" from full dataframe
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
    * train, test = train_test_split(df, test_size=0.2, random_state=123, stratify=df.colname) ----- create train and test dataframes, test dataframe is 20% of rows, randomization seed is 123, stratifies df.colname
    * train, validate = train_test_split(train, test_size=.25, random_state=123, stratify=train.survived) ----- modifies train, sets validate dataframe using new parameters
- from sklearn.impute import SimpleImputer ----- fills values by inference
    * fill with: 0, average, median, subgroup mean, most frequent value, build model to predict missing values, etc
    * strategy='average' ----- fills with average
    * will need to modify dataframes with impute results
- from sklearn.metrics import precision_score, accuracy_score, recall_score, classification_report ----- confusion matrix calc functions
    * df_report = pd.DataFrame(classification_report(df.actual_observed, df.model_guesses, labels=['colname', 'colname'], output_dict=True)).T ----- outputs nice df of metrics
### Syntax
- imputer = SimpleImputer(strategy='most_frequent')
- imputer = imputer.fit(train[['embark_town']])
- train[['embark_town']] = imputer.transform(train[['embark_town']])
- do same for validate and test datasets
    * imputer = SimpleImputer(strategy='most_frequent')
    * train[['embark_town']] = imputer.fit_transform(train[['embark_town']])
    * validate[['embark_town']] = imputer.transform(validate[['embark_town']])
    * test[['embark_town']] = imputer.transform(test[['embark_town']])
    * return train, validate, test

## Data Exploration
- Finding relationships and stories in data, documenting is and isn'ts
- Goal is to remove redundant/unimportant variables for the story
- Hypothesize and visualize loop, and if that isn't enough, run statistical tests
- "What data sources do we have, what are customers doing, how are we reaching people..."
- "What is our observation???"
    * titanic_db observations are... people on the titanic.
- Univariate stats (target), Bivariate stats (target and variable), multivariate stats (subgroups compare to each other)
    * **explore.py** - contains prebuilt functions for uni/bi/multivariate stats
    * pandas profiler does similar things to the explore.py but not as great
- Adding features... train['newcol'] = pd.cut(train.colname, bins=[0,15,100], right=False, labels=[0,1])
    * will need to amend train/validate/test datasets with 'newcol' and also cat_vars or quant_vars
### Documenting...
- Document the questions, the takeaways from visualization, the answer to questions, the null/alt hypotheses, etc
### Univariate Stats
- Split data into categorical vars and quantitative vars
    * cat_vars = ['var1', 'var2', 'var3', ...]
    * quant_vars = ['var42', 'var67', ...]
    * explore.explore_univariate(train_df, cat_vars, quant_vars) ----- builds visualization and statistics with columns var1, var2, var3, var42, var67, etc
### Bivariate Stats
- Same setup as univariate but with target variable (column) specified
    * explore.explore_bivariate(train, target, cat_vars, quant_vars)
### Multivariate Stats
- Adding the target as color in Seaborn
    * explore.explore_multivariate(train, target, cat_vars, quant_vars)

## Evaluation (Classification notes)
- Reviewing our model to see if our predictions matched actuals for a given number of observations
    * True Positive, FP, TN, FN
    * Baseline Prediction is predicting all outcomes as True
- Focus on cost: Accuracy, Recall, Precision, Specificity, F1 Score, ROC/AUC
- Confusion Matrix --- focus on Recall and Precision
    * df = pd.DataFrame({'prediction':[], 'actual':[]})
    * pd.crosstab(df.prediction, df.actual)
### Accuracy 
- Overall performance of model
- Easy to understand and doesn't matter what the 'positive' is
- Might be misleading when working with imbalanced class problems
- (TP + TN) / (TP + TN + FP + FN)
### Recall
- Positive actual against our predictions 
- Minimizing false negatives
- Use when FN is more costly than FP [credit card fraud detection]
- TP / (TP + FN)
### Precision 
- Our prediction against all possible actuals 
- Minimizing false positives
- Use when FP is more costly than FN [spam filter])
- TP / (TP + FP)
### More terms
- Sensitivity (Recall)
- Specificity (Recall for negative) 
- F1 Score (harmonic mean of Precision and Recall)
- ROC/AUC (how well your model discriminates between positive and negative)
### Usage
- Model Accuracy: (df.actual == df.prediction).mean()
- Baseline Accuracy: (df.actual == df.baseline_prediction).mean()
- Recall: subset = df[df.actual == 'coffee'] ----- look at actual Yes observations
    * use Model and Baseline Accuracy against this subset
- Precision: subset = [df.prediction == 'coffee'] ----- look at predicted Yes rows
    * use Model and Baseline Accuracy against this subset

## Evaluation (Regression notes)
- Does model add any value? Which model is better? How confident am I in the model's predictions?
- Root-Means Square (RMSE): How much error the typical prediction has, cast in same units as target; smaller is better
- R-Squared (R2): Variance in y (target) explained by x (predictor); closer to 1 is better
- Remember: **units are preserved**, predicting a dollar amount means unit is dollars
### Theoretical
- y_i = beta_0 + (beta_1 * x_i) + e_i
    * target = intercept + linear_addition_of_ind_vars + unexplained_error
    * unexplained_errors are independent, same variance, normally distributed
    * "Relationship is linear and additive"
- estimate_y_i = beta_0 + beta_1 * x_i
    * estimated_target = estimated_intercept + estimated_value_of_coefficients
    * residual: e = y_i - estimate_y_i
### Baseline
- sns.lineplot(x='x', y='baseline', data=df) ----- plots line for baseline
    - switch 'baseline' with 'predictions' for the regression line
    - plt.axhline(0, ls=':') ----- plots dotted line at y=0 for visual aid
- Regression baseline is the mean or median of all datapoints (horizontal line)
    * Check mean and median for better performance, select best performing
    * x-axis (independent variable) not affected by horizontal line
### Errors
- Residual: error (actual minus predicted) --- above line is positive, below line is negative
- SSE: sum of squared error --- square all error distances, then add up
    * If you especially care about outliers, this will weigh outliers higher
- MSE: mean of squared error --- square all error distances, then average
- **RMSE**: root mean squared error --- square all error distances, then average, then take the square root of the result
    * Most common one
- TSS (total error): distance from actual to baseline
- ESS (explained error): distance from prediction line to baseline
- SSE (unexplained error): distance from prediction line to actual
### R^2 - Explained Variance
- R^2 = ESS / TSS
- R^2 == 1.0 --- all data points fall perfectly on regression line
- R^2 == 0.0 --- all data points above and below the regression line have the same distance (mean baseline)
### sklearn syntax
- from sklearn.metrics import mean_squared_error
    * MSE2 = mean_squared_error(df.y, df.yhat)
    * MSE2_baseline = mean_squared_error(df.y, df.baseline)
    * SSE2 = MSE2 * len(df)
    * RMSE2 = mean_squared_error(df.y, df.yhat, squared=False)
    * RMSE2_baseline = mean_squared_error(df.y, df.baseline, squared=False)
- from sklearn.metrics import r2_score
    * r2_score(df.y, df.yhat) --- score of explained variance

## Feature Engineering (Regression notes)
- *Making* useful features for columns based on existing data
    * k-best and rfe do not need to take in scaled data, just encoded data
- Select K Best (SelectKBest, kbest) 
    * f regression test, checks each feature in isolation, checks whether model performs better than baseline
    * kbest = SelectKBest(f_regression, k=3) ----- returns top 3 'best' features using f regression
    * kbest.fit(X_train_scaled, y_train)
    * kbest.pvalues_
    * kbest.get_support() ----- array showing which columns were chosen (True, False, True...)
    * X_train.columns[kbest.get_support()] ----- shows column names
    * X_kbest = kbest.transform(X_train_scaled) ----- if k=3, return top-3 columns
- Recursive Feature Elimination (RFE, rfe) 
    * fits model, eliminates worst performing features (more computationally expensive)
        * Computational expense is largely driven by choice of estimator, simple estimator is recommended to quickly ascertain which features to use
    * rfe = RFE(estimator=LinearRegression(), n_features_to_select=3) ----- top-3
    * rfe.fit(X_train_scaled, y_train)
    * rfe.get_support()
    * X_train.columns[rfe.get_support()]
    * pd.Series(rfe.ranking_, index=X_train.columns)
    * **Great for determining features to further-investigate**


## Modeling
- Create model using algorithm+hyperparameters and training data
- Evaluate the model
- Repeat
- After time/repetitions, compare models
- After comparing models, use best against test split
- Decision Tree: DecisionTreeClassifier (covered extensively below), clf
- Random Forest: RandomForestClassifier, rf
    * rf, Lots of decision trees, averaging them all (coming to a consensus)
    * An "Ensemble ML algorithm" called Bootstrap Aggregation or bagging
    * Bootstrapping: take lots of samples, average each sample alone, then average all averages
    * Random Forest does bootstrapping for lots of decision tree predictions
    * After fitting, print(rf.feature_importances_) to see how important each feature is to predicting the classification (array of percentages)
        * The _ character at end indicates it's a parameter of a trained model
- K-Nearest Neighbors: KNeighborsClassifier, knn
        * n_neighbors=, weights='uniform' or weights='distance'
    * Supervised, makes predictions based on how close a new data point is to known data points (effective when there's more known data)
    * Just-in-time algorithm (makes prediction when receive data)
    * "Lazy" because it doesn't make an internal model, just stores data and uses stats to make predictions
    * K-value serves as "votes", top-(K-value)-closest known datapoints to new datapoint for KNN calculation
        * Most common is to try different K-values, some industries have a standard
- Logistic Regression: LogisticRegression, logit
    * Instead of fitting a linear regression, you fit a curved regression
    * Used for binomial/multinomial regression (one plot axis is not continuous/discrete values)
### Dummy Steps
- from sklearn.dummy import DummyClassifier
- from sklearn.metrics import classification_report
- X_train, y_train = train.drop(columns='target_col'), train.target_col
    * do same for validate and test subsets
- model = DummyClassifier(strategy='constant', constant=1) ----- we predict the target to be always 1 (not a great model, of course), these are hyperparameters
    * strategy='uniform' or 'most_frequent' or...
- model.fit(X_train, y_train)
- accuracy = model.score(X_train, y_train)
    * sklearn objects can use .score() .predict() .predict_proba() and more
    * .score is accuracy
    * .predict generates array of predictions
    * .predict_proba generates array or arrays for % sure-ness of guesses
### Decision Tree example
- from sklearn.tree import DecisionTreeClassifier
- from sklearn.tree import export_graphviz
- from sklearn.metrics import classification_report
- from sklearn.model_selection import train_test_split
- train, validate, test split
- Prepare data
- Explore data
- clf = DecisionTreeClassifier(max_depth=3, random_state=123) ----- clf is classifier, decision tree is limited to depth of 3 (more hyperparameters available)
    * Set depth to the number of features (Ryan does this, so...)
- clf = clf.fit(X_train, y_train)
- y_pred = clf.predict(X_train) ----- generate model prediction array against train dataset
- import graphviz
- from graphviz import Graph
- dot_data = export_graphviz(clf, feature_names= X_train.columns, class_names=clf.classes_, rounded=True, filled=True, out_file=None)
- graph = graphviz.Source(dot_data) 
- graph.render('iris_decision_tree', view=True) ----- display decision tree in PDF format (a picture)
<code> dot_data = export_graphviz(clf, feature_names= X_train.columns, 
                           class_names=('Yes', 'No'), rounded=True, 
                           filled=True, out_file=None)</code>
- classification_report(y_train, y_pred) ----- get metrics of train dataset
- clf.score(X_validate, y_validate) ----- accuracy of model against validate dataset
- y_pred = clf.predict(X_validate) ----- prediction array of model for validate dataset
- classification_report(y_validate, y_pred) ----- metrics of model against validate


## Combining Everything We've Learned
- Pull in data (easy)
    * pd.read_sql(query, url), pd.read_csv('filename.csv'), etc
- Assess what you've got (easy)
    * Figure out cols with nulls
        * df.isna().sum()
        * df[df.col1.isna()].col2.value_counts()
- Build appropriate clean-up code in a prepare.py file (complicated)
    * Reduce noise (set id col to index or drop it, drop duplicates)
    * Handle nulls
        * Drop columns with lots of nulls: df.drop(columns='col')
        * Fill null values in a kept column: df.col.fillna(value=df.col.median())
    * Consider dropping outliers (may use Inter-Quartile Rule)
- Encode appropriate data (easy)
    * One-hot encode columns quickly: pd.get_dummies(df[['col1', 'col2', ...]], dummy_na=False, drop_first=[True, True]
    * Drop original columns: df.drop
    * Stitch dataframes back together: df = pd.concat([df, dummy_df], axis=1)
- Split data (easy)
    * train_test_split, train validate test, separate X and y (matrix and target)
- Make some decisions on what to do for model (thoughtful)
    * Determine which features to keep
        * K Best and RFE
        * Drop features based on domain knowledge
        * Drop features that raise ethical issues
        * Drop features that are too 'loud'
        * Clean up remaining features
        * Do analysis on features
    * Create features!!
    * Run bivariate analysis
    * Check for feature overlap on target value (redundant population slows the model down)
- Scale data
    * Regression: Make sure data is one-hot encoded before doing this
    * Use sklearn.preprocessing MinMaxScaler, StandardScaler, RobustScaler
- Modeling (intermediate)
    * Create baseline
        * Classification: most frequent value in target
        * Regression: mean of target
    * Check baseline accuracy
        * Classification: Use recall, precision, or other metric as necessary
        * Regression: Calculate RMSE and R^2 values
    * Build model (sklearn modules)
    * Fit model: model.fit(X_train, y_train)
    * Use model against train: y_pred = model.predict(X_train)
    * Check model accuracy
        * Classification: Classification Report, Confusion Matrix
            * report = pd.DataFrame(classification_report(y_train, y_predictions, output_dict=True))
        * Regression: RMSE and R^2
    * Check model against validate dataset: model.predict(X_validate)
        * Classification: Classification Report, Confusion Matrix
        * Regression: RMSE, R^2
    * Compare accuracy of model for train and validate datasets 
        * Classification train_accuracy > validate_accuracy means model is overfit
    * Re-run model with different hyperparameters to optimize it
        * Consider running a loop for hyperparameters and output to nice table
        * With loop can save each model to list for later access: models_list[-1]
        * y_pred_proba > threshold ----- telling model to adjust its threshold for predictions, for example threshold=0.3 would mean True predictions with > 30% certainty would ultimately be called True instead of False (default is 50% split)

## Hot notes with Sam
- pd.read_csv(filename, index_col=0) ----- fixed Unnamed: 0
- Separate functions out in scripts and refer functions to functions (easier to understand)
- sns.set_style('darkgrid')
- sns.countplot() ----- categorical bins
    * histogram is numerical bins, should only really be used on continuous data
- https://seaborn.pydata.org/generated/seaborn.set_style.html
- https://matplotlib.org/stable/tutorials/introductory/customizing.html
- plt.grid(True, axis='both') ----- background grid


## Other hot notes
- Make script plotting all sorts of stuff, never think about again
- Plot distribution for data wrangling to check for outliers (histogram, box-whisker), then remove outliers if necessary, then plot new distributions
- a shotgun pattern in homoscedasticity check (pattern shows heteroscedasticity) isn't great, consider removing outliers or transforming... can take log of entire column (storing values in new column) then run log column through the model and visualization
- SQL databases are usually hosted on beefy systems, so doing processing in SQL can be a lot faster than doing it on a local machine using Python
- Data prep parameters are calculated from *train*, this excludes unseen data, so don't calculate on whole dataset
- sklearn pileine function exists to do cool stuff
- df.pipe allows you to throw a dataframe into a function and pass arguments to that function... pretty cool stuff
- sns.heatmap(df.corr(), cmap='coolwarm_r', vmin=-1, vmax=1, annot=True) ----- draw correlation heatmap with red negs blue pos
- ax.xaxis.set_major_formatter(lambda x, pos: '{:.1f} m'.format(x / 1_000_000)) ... ax.set(xlabel='x2 (millions)') ----- change sci notation to millions... kinda cool
- ax.xaxis.set_major_formatter('{:,.0f}'.format) ----- make x axis 100,000 ticks
- ax.yaxis.set_major_formatter('{:.0%}'.format) ----- make y axis percentage
- df.corr().style.background_gradient(vmin=-1, vmax=1, cmap='coolwarm_r').format('{:.3f}'.format) ----- more cool formatting for heatmap
- df.sample(5, random_state=123).style.highlight_max(axis=0) ----- highlight max values per column
- df.column.value_counts().plot.barh() ----- create bar plot of y labels and x values
- Don't forget pd.cut(series_name, bins=[0,5,100,100000])
    * Common to bin continuous values into ordinal/categorical to run boxplots per bin against another continuous value
- np.set_printoptions(suppress=True) ----- suppress scientific notation
- pd.DataFrame(np_array, columns=df.columns) ----- nice way to push array to labeled dataframe
- centroids.plot.scatter(y='petal_length', x='sepal_length', c='black', marker='x', s=1000, ax=plt.gca(), label='centroid') ----- plot syntax for... stuff

## Stakeholders
- Move functions and analysis to separate .ipynb as required for stakeholders
    * Stakeholders want just the end product: give them it
    * Stakeholders want the models and end product: give them it
    * Stakeholders want everything: give them everything
### Trello
- Requirements Stage: Talk with stakeholders about their requirements and a timeline
- Decision Stage: Decide which requirements you will be able to complete
    * Goal is to complete *all* user requirements for this "sprint" (the timeline)
    * You choose how in-depth to go for each requirement
### APIs
- Application Programming Interface: a way to interact with 'owned' data, has rules and ways to interact, you can scrape from the user level but often better to interact with APIs
- REST, RESTful: a standardized structure for URLs
- (RESTful) JSON API: an API where the URLs follow REST and the communication with the server is in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests (python library called 'requests')
- import requests --- response = requests.get('http_link') ----- returns object for server response like 404 and 500
    * response.ok, response.status_code, response.text ... all valuable
- response.text on requests.get('https://swapi.dev/api/people/5') will give data on Leia from Star Wars in the form of JSON dict (name, height, mass, hair/skin/eye color, etc)
- requests.get(http_url + '/documentation').json()['payload'] for http_url='https://python.zgulde.net' will give 'endpoints', other APIs give different stuff on a different link (maybe) using a different JSON container
    * '/api/v1/items/1' ----- Endpoints are prefixed with /api/{version} where version is "v1", then endpoints (essentially directories or folders) and page navigation
    * Can iterate through each page in a loop and pull all information with ['next_page'] and ['max_page'] until next_page hits 'None'

# Notes, Revision 2
## Environment
### CLI
### Jupyter Notebook
### .py Scripts
### Excel/Spreadsheets

## Acquisition
### SQL
### Other

## Preparation
### Python
### NumPy
### Pandas
### Scaling

## Feature Engineering

## Exploration

## Visualization
### Matplotlib
### Seaborn
### Tableau
### Other

## Statistical Tests

## Modeling
### Classification
- Deciding whether data is one thing or another
- Can optimize to reduce false positives (recall) or false negatives (precision)
### Regression
### Time-Series
### Clustering
### Anomaly Detection
- Detecting outliers and correctly classifying as anomalous

