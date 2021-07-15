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


## JupyterNB
### Basic usage
- Kernel > Restart and Clear Output to restart the shell without any cells having yet ran; Stop shell then start again for troubleshooting
- Option+Clickdrag to create vertical multi-cursor
- Command Mode uses Z for undo-cell operations, Edit Mode uses Command + Z.
- ESC from Edit mode into Command mode; RETURN from Command mode into Edit mode
- Shift+RETURN to run a cell
- Other Command mode shortcuts: dd to delete cell; y to change cell to Code; m to change cell to Markdown


## Statistics Notes
- Centering is important to take a pile of data purely as its distance away from the mean in positive/negative direction
- - Centering is also known as de-meaning a vector
- Z-Score is like centering but it's the distance from the mean in terms of standard deviation
- - zscore = (value - population_mean) / standard_deviation
- - zscore = (value - avg(value_list)) / std(value_list)
- - from scipy import stats, stats.zscore(value_list) ----- returns Z-Score of value_list