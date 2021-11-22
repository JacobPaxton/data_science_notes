# Notes Planning/Brainstorming
My original ds_notes.md was intended to quickly capture curriculum into a digestible one-source location while it was being taught. For that purpose, it worked extremely well. It allowed me to focus on what I didn't immediately understand, improving my retention of advanced material, and stored things I might not remember off the top of my head.

This iteration of my notes is for long-term reference. I will keep my original notes, and I have access to the curriculum itself, so this version will have a different format. Instead of packing information on tools, this notes format will pack information on the workflow elements.

## Overall Organization - Brainstorming
- Environment
    * Jupyter Notebook
    * Terminal
    * Google Sheets
    * Power BI
    * Excel
    * Sequel ACE
    * VS Code
    * Tableau
- Acquisition & Preparation
    * Tidying Data
        * https://vita.had.co.nz/papers/tidy-data.pdf
        * One value per cell: split out combined data, handle nulls
    * Spark
    * SQL
    * APIs
    * Scraping
    * Kaggle
    * Python
    * NumPy
    * Pandas
    * REGEX
- Exploration & Delivery
    * Splitting Data
    * Uni-, Bi-, Multi-variate Exploration
    * Feature Engineering
    * Seaborn & Matplotlib
    * SciPy
- Prediction
    * Feature Preparation
        * Encoding
        * Scaling
    * Classification
        * SMOTE
    * Regression
    * Time-Series
    * Algorithmic Clustering
    * Natural Language Processing (NLP)
    * Anomaly Detection
    * Deep Learning
    * Computer Vision
    * Cross-Validation

# Notes

## Environment
### Git
- git clone github_repo_ssh_link
- git pull, git status, git add, git commit -m 'message', git push
- Use .gitignore
- git merge issue: pull repo down to new folder, copy changed files manually to new folder, push from new folder, delete old folder using rm -rf folder_name
### Jupyter Notebook
- Excellent interface for iPython with easy-to-use UI
### Terminal
- mkdir, rmdir, rm, cp, mv, cd, ls, pwd, cwd
- curl -O url_address ----- copy down a file from a URL (often used for raw Github files)
- Log in to a SQL server: -u username -p -h ip_address ----- -p prompts for a password
- Create a new file using VS Code: code filename.filetype
- Launch Jupyter Notebook server: jupyter notebook
### Excel & Google Sheets
- Call a function in a cell: =function_name_all_caps()
    * Point function cell at other cells, return output at function cell; if other cells change, output changes
        * fn + f4 is the absolute reference to a cell or cell range
        * VLOOKUP works great with this
    * Click bottom-right of cell to run for all values in column
- Use Conditional Formatting and Alternating Colors for readability
- Pivot Table: Select All (the entire table, for convenience), Insert, Create Pivot Table (make a new sheet), add rows and columns using interface
    * Insert, Chart... ----- Produces chart, can customize
- Splitting text: Select data, Data, Split Data *OR* =SPLIT(cell, delimiter)
- =CONCATENATE(cell, delimiter_if_desire, cell, cell, delimiter, cell...)
#### Excel & Google Sheets Functions
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
### Power BI
- From a cursory look, a mix of Excel and some table join functionality. Popular software.
### Sequel ACE
- Excellent interface for SQL database reads and querying
### VS Code
- One-stop interface for file editing and viewing
### Tableau Public
- Excellent software for interactive visualizations and dashboards

## Acquisition & Preparation
### Tidying Data
- https://vita.had.co.nz/papers/tidy-data.pdf
- One value per cell: split out combined data, handle nulls
### Spark
### SQL
### APIs
### Scraping
### Kaggle
### Python
### NumPy
### Pandas
### REGEX

## Exploration & Delivery
### Splitting Data
### Uni-, Bi-, Multi-variate Exploration
### Feature Engineering
### Seaborn & Matplotlib
### SciPy

## Prediction
### Feature Preparation
#### Encoding
#### Scaling
### Classification
#### SMOTE
### Regression
### Time-Series
### Algorithmic Clustering
### Natural Language Processing (NLP)
### Anomaly Detection
### Deep Learning
### Computer Vision
### Cross-Validation