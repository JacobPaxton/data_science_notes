# My notes for the Codeup Data Science course
AI vs ML vs DL: Machine Learning is a model adjustment tool that observes data, makes predictions using a model, and adjusts the model to make better predictions. The code to set this up is written by humans. Machine Learning is not entirely separate from AI- AI is an umbrella term for the automated handling of conditionals. Deep Learning is a specific application of Machine Learning that involves three or more layers of hidden (not human-designed) neural network nodes- the flexibility of Deep Learning allows systems to adjust to input in ways that humans can’t precisely code themselves.

Parameters, hyperparameters, features, targets: A feature is an input, a parameter is a machine- or human-set portion of a model, and a target is the output. Hyperparameters are human adjustments to a model in order to help it better reach the correct target.

SQL hot notes
use single quotes for strings
selecting multiple columns returns multiple columns

CLI:
access the database, -u username -p -h IP-address
show databases;
use database_name;
show tables;
describe table_name;
select column_name from table_name;
— you can also select * from table_name;
— you can also filter to an entry using WHERE, select * from table_name where entry ><= value;
— you can also select column_name, column_name from table_name;
— you can also create aliases for columns, select column_name AS Column from table_name;

SQL quick review pre-subquery lesson
Join - INNER uses AND logic, LEFT / RIGHT use OR logic and prepend/append
ON vs USING() - ON preserves the linked key while USING() merges the linked keys into one column
-- use the USING() function to merge multiple same-name columns, but this may mess up your query