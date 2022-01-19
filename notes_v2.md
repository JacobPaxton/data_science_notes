# Data Science Notes, v2

<!-- 
#######                                                  #####                                                 
   #      ##   #####  #      ######     ####  ######    #     #  ####  #    # ##### ###### #    # #####  ####  
   #     #  #  #    # #      #         #    # #         #       #    # ##   #   #   #      ##   #   #   #      
   #    #    # #####  #      #####     #    # #####     #       #    # # #  #   #   #####  # #  #   #    ####  
   #    ###### #    # #      #         #    # #         #       #    # #  # #   #   #      #  # #   #        # 
   #    #    # #    # #      #         #    # #         #     # #    # #   ##   #   #      #   ##   #   #    # 
   #    #    # #####  ###### ######     ####  #          #####   ####  #    #   #   ###### #    #   #    ####  
-->

# Table of Contents

I.    [General Notes                 ](#general-notes)
1.    [Advice                        ](#advice)
2.    [Storytelling                  ](#storytelling)
3.    [Datasets                      ](#datasets)

II.   [Software                      ](#software)
1.    [Terminal                      ](#terminal)
2.    [Git                           ](#git)
3.    [Jupyter Notebook              ](#jupyter-notebook)
4.    [Excel & Google Sheets         ](#excel-&-google-sheets)
5.    [Power BI                      ](#power-bi)
6.    [Sequel Ace                    ](#sequel-ace)
7.    [Visual Studio Code            ](#vs-code)
8.    [Tableau Public                ](#tableau-public)

III.  [Regular Expressions (REGEX)   ](#regular-expressions-(regex))
1.    [REGEX                         ](#regex)

IV.   [APIs & Scraping               ](#apis-&-scraping)
1.    [APIs                          ](#apis)
2.    [Web Scraping                  ](#web-scraping)

V.    [SQL & Apache Spark            ](#sql-&-apache-spark)
1.    [SQL                           ](#sql)
2.    [Apache Spark                  ](#apache-spark)

VI.   [Python, NumPy, Pandas         ](#python,-numpy,-pandas)
1.    [Python                        ](#python)
2.    [NumPy                         ](#numpy)
3.    [Pandas                        ](#pandas)

VII.  [Matplotlib & Seaborn          ](#matplotlib-&-seaborn)
1.    [Visualization in Python       ](#overall-notes-for-visualizations-in-python)
2.    [Matplotlib                    ](#matplotlib)
3.    [Seaborn                       ](#seaborn)

VIII. [Exploration                   ](#exploration)
1.    [Exploration Prep              ](#exploration-prep)
2.    [Exploration Visualization     ](#exploration-visualization)
3.    [Feature Engineering           ](#feature-engineering)
4.    [Feature Selection             ](#performance-based-feature-selection)

IX.   [Algorithmic Clustering        ](#algorithmic-clustering)
1.    [Cluster Assignment            ](#cluster-assignment)
2.    [K-Means Clustering            ](#k-means-clustering)
3.    [Hierarchical Clustering       ](#hierarchical-clustering)
4.    [DBSCAN                        ](#dbscan)

X.    [Statistics                    ](#statistics)
1.    [Metrics                       ](#metrics)
2.    [Hypothesis Testing            ](#hypothesis-testing)
3.    [Probability                   ](#probability)

XI.   [Model Preparation             ](#model-preparation)
1.    [Encoding                      ](#encoding)
2.    [Scaling                       ](#scaling)
3.    [Resampling                    ](#resampling)

XII.  [Classification                ](#classification)

XIII. [Regression                    ](#regression)

XIV.  [Time-Series                   ](#time-series)

XV.   [Natural Language Processing   ](#natural-language-processing-(NLP))

XVI.  [Anomaly Detection             ](#anomaly-detection)

XVII. [Deep Learning                 ](#deep-learning)

XVIII.[Computer Vision               ](#computer-vision)

IXX.  [Cross-Validation              ](#cross-validation)

<br>

<br>







<!-- 
#     #                            
##    #  ####  ##### ######  ####  
# #   # #    #   #   #      #      
#  #  # #    #   #   #####   ####  
#   # # #    #   #   #           # 
#    ## #    #   #   #      #    # 
#     #  ####    #   ######  ####  
-->

# General Notes

<!-- Polished -->
## Advice
- Zach: Consistency > Intensity, Motivation is important, Doing data science > learning about data science, Publish!, If it's worth doing, it's worth getting started
- Zach: ask in interview "what does professional development look like for your employees?"
### Tidy Data
- Tidying Data: https://vita.had.co.nz/papers/tidy-data.pdf
- One value per cell: split out multi-value cells, 'melt' one-hot columns into single column, handle nulls

<!-- Polished -->
## Storytelling
- Data requires velocity to be useful
- Finding relationships and stories in data, documenting is and isn'ts
- Goal is to remove redundant/unimportant variables for the story
- Hypothesize and visualize loop, and if that isn't enough, run statistical tests
- "What data sources do we have, what are customers doing, how are we reaching people..."
- "What is our observation???"
    * titanic_db observations are... people on the titanic.
### Trello
- Requirements Stage: Talk with stakeholders about their requirements and a timeline
- Decision Stage: Decide which requirements you will be able to complete
    * Goal is to complete *all* user requirements for this "sprint" (the timeline)
    * You choose how in-depth to go for each requirement
### Stakeholders
- Move functions and analysis to separate .ipynb as required for stakeholders
    * Stakeholders want just the end product: give them it
    * Stakeholders want the models and end product: give them it
    * Stakeholders want everything: give them everything
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

<!-- Polished -->
## Datasets
### From Python
- pandas datareader: https://pandas-datareader.readthedocs.io/en/latest/remote_data.html
- from pydataset import data --- df = data('iris')
- import seaborn as sns --- df = sns.load_dataset('iris')
- from vega_datasets import data --- df = data('iris')
- from sklearn import datasets --- array = datasets.load_iris()['data']
### Downloads
- Massive list: https://github.com/awesomedata/awesome-public-datasets
- Massive list: https://www.data-is-plural.com/archive/
- Search US Gov data: https://www.data.gov
- Search EU data: https://data.europa.eu/en
- Search research paper data: https://paperswithcode.com/datasets
- Search various: https://huggingface.co/datasets
- Search various: https://datasetsearch.research.google.com
- NLP: https://machinelearningmastery.com/datasets-natural-language-processing/
- Computer vision: https://visualdata.io/discovery
- Computer vision from satellites: https://github.com/chrieke/awesome-satellite-imagery-datasets

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                  
#     #  ####  ###### ##### #    #   ##   #####  ###### 
#       #    # #        #   #    #  #  #  #    # #      
 #####  #    # #####    #   #    # #    # #    # #####  
      # #    # #        #   # ## # ###### #####  #      
#     # #    # #        #   ##  ## #    # #   #  #      
 #####   ####  #        #   #    # #    # #    # ###### 
-->

# Software

<!-- Polished -->
## Terminal
- `mkdir`, `rmdir`, `rm`, `cp`, `mv`, `cd`, `ls`, `pwd`, `cwd`
- `curl -O url_address` ----- copy down a file from a URL (often used for raw Github files)
- Log in to a SQL server: `-u username -p -h ip_address` ----- -p prompts for a password
- Create a new file using VS Code: `code filename.filetype`
- Launch Jupyter Notebook server: `jupyter notebook`
- Multi-line cursor: Hold command, clickdrag

<!-- Polished -->
## Git
- git clone github_repo_ssh_link
- git pull, git status, git add, git commit -m 'message', git push
- Use .gitignore
- git merge issue: 
    1. pull repo down to new folder
    2. copy changed files manually to new folder
    3. push from new folder
    4. delete old folder using rm -rf folder_name

<!-- Polished -->
## Jupyter Notebook
- Excellent interface for iPython with easy-to-use UI
- Command mode for cell operations, edit mode for editing lines
- Command mode: dd for cell deletion, y for code cell, m for markdown cell
- Edit mode: TAB for autocomplete of methods/variables/filenames, Shift TAB for full context at cursor location
- Edit mode: Split cell into two cells at cursor with option shift -
- Hold option and left click to drag multi-line cursor

<!-- Polished -->
## Excel & Google Sheets
- Spreadsheets with extra functionality
- Use Conditional Formatting and Alternating Colors for readability
- Summary statistics can be initiated from any cell for any cell range... convention is to put a small table in the Sheet next to the values to show the statistics
- Filtering: Select all, Data, Create Filter, hover over column you want to filter, apply a filter to it
- Filter Views: allows you to view the filtered version while the shared view for others is unchanged 
    * Can save the view and share it with others if you want, it appears listed under the Filter Views tab in Google Sheets
- Pivot Table: Select All (the entire table, for convenience), Insert, Create Pivot Table (make a new sheet), add rows and columns using interface
    * Insert, Chart... ----- Produces chart, can customize
- Call functions with the character: =
- Absolute reference using hold_clickdrag + fn + F4
- Double-click bottom right of function cell to apply to all rows in selected column(s)
### Spreadsheet Functions
- `=B2-B3` ----- subtract cell B3 from cell B2
- `=SUM(num_cells1, num_cells2)`, `=AVERAGE(num_cells1, num_cells2)`, `=COUNT(cells)`
    * `=COUNTIF()`, `=SUMIF()`
- `=MOD(numeric_cells, number)` ----- remainders
- `=POWER(numeric_cells, number)` ----- raise to a power
- `=CEILING(numeric_cells)`, `=FLOOR(numeric_cells)` ----- round up, round down
- `=CONCATENATE(cells, cells, " ", cells, " ", ...)` ----- smash values together in new range
- `=SPLIT(cells, delimiter)` ----- as expected
- `=LEN(cells)` ----- number of characters in cell
- `=REPLACE(text, position, length, new_text)`
- `=SUBSTITUTE(text_to_search, search_for, replace_with, [occurrence_number])`
- `=LEFT(cells, num_of_chars)`, `=MID(cells, start_index, steps_to_read))`, `=RIGHT(cells, num_of_chars)`
- `=UPPER(cells)`, `=LOWER(cells)`, `=PROPER(cells)`
- `=NOW()`, `=TODAY()`, `=TIME(hour_cell, minute_cell, second_cell)`, `=DATEDIF(start_cells, end_cells, step)`
    * `=YEAR(cells)`, `=MONTH(cells)`, `DAY(cells)`, `=HOUR(cells)`, `=MINUTE(cells)`, `=SECOND(cells)`
- `=VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE)` ----- vertically searches range_to_search for key, if it finds it, returns col_to_return, if it's not exact match, ignores it (due to FALSE)
    * VLOOKUP looks at first column specified... be careful
- `=IF(AND(cond1, OR(cond2, cond3)), truth_value, false_value)`, `=IFERROR(value, truth_value)`
    * *Conditions can come from cells*
- `=INDEX(range, MATCH(string_to_match, range))`
- `=SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc})` ----- creates a red in-cell bar chart of data from range with maxed bar when reaching max value of range

<!-- Polished -->
## Power BI
- From a cursory look, a mix of Excel and some table join functionality. Popular software.

<!-- Polished -->
## Sequel ACE
- Excellent interface for SQL database reads and querying

<!-- Polished -->
## VS Code
- One-stop interface for file editing and viewing

<!-- Polished -->
## Tableau Public
- Excellent software for interactive visualizations and dashboards
- No autosaves and sometimes-glitchy upload... save your work often
### Tableau Resources
- The Superstore CSV is popular to learn and demo Tableau
- Faith: https://public.tableau.com/app/profile/faith.kane
- Sean Oslin: https://public.tableau.com/app/profile/sean.oslin
### Tableau Usage
- Explore your data in Google Sheets first
    * Tableau is a bit slow for *exploration* compared to pivot tables in Google Sheets
- Data Source: Used for changing files across the project
    * Hide unnecessary columns from project using drop-downs in each column
    * Filter results at top-right (intuitive)
- Sheets: Used for building individual charts
    * Plot by rows and columns, use Marks for conditional formatting and tooltips
    * Change chart type in top right, change chart dimensions using top-middle dropdown
    * Adjust display options for numbers, add trend lines, annotations, and more
        * Everything-formatting: Context Menu > Format
    * Create calculated fields for aggregation, level of detail (LOD) calculations, and more
    * If stuck, build new file using Python/Pandas and add the new file to new sheet
- Dashboard: Show multiple sheets in one place
    * Add non-sheet elements from bottom left
    * Create multi-sheet filters
- Story: Used for presentation of sheets and dashboards

[[Return to Top]](#table-of-contents)






<!-- 
######  #######  #####  ####### #     # 
#     # #       #     # #        #   #  
#     # #       #       #         # #   
######  #####   #  #### #####      #    
#   #   #       #     # #         # #   
#    #  #       #     # #        #   #  
#     # #######  #####  ####### #     # 
-->

# Regular Expressions (REGEX)

<!-- Polished -->
## REGEX
- Language for parsing and slicing strings to capture substrings
### REGEX Metacharacters
```
| Anything: .                | Alphanumeric: \w \W | Whitespace: \s \S | Digit: \d \D  |
| Zero or more (optional): * | One or more: +      | Optional: ?       |
| {5} Repeat exactly 5 times | {3,6} Min 3, Max 6  | {3,} At least 3 times             |
| Anchor front: ^            | Anchor back: $      | Word boundary: \b |
| Capture group: ()  EX: (?P<colname>regex_exp)    |
```
### REGEX Queries
- `re.search(regexg, subject)` ----- random search, report first-found start/stop index and matched string
- `re.match(regexp, subject)` ----- re.search but from beginning
- `re.findall(regexp, subject)` ----- report all matches using list
- `re.sub(regexp, sub_in, subject)` ----- return string with subbed-in substring
- `df.colname.str.extract(regexp)` ----- return dataframe where each column is one capture group's results
#### REGEX Query Options
- `re.IGNORECASE` is as expected; `re.MULTILINE` is new query per line; `re.VERBOSE` is ignore whitespace
- use `|` to add multiple flags, ex: `re.findall(regexp, subject, re.IGNORECASE | re.MULTILINE)`
### REGEX examples
- `r'a'` ----- r marks string as a raw string, all characters taken as-is
- `r'\w\w'` ----- find two in-sequence alphanumeric chars
    * 'abc 123' becomes `['ab','12']` because it consumes 'ab' and '12', so no 'bc' or '23'
- `r'\w+'` ----- capture max combo of each alphanumeric
- `r'.*'` ----- everything. only use asterisks with capture groups, and when you don't know if chars will be there
- `r'\w{3,6}'` ----- only capture when 3 alphanumerics in sequence and as many as possible up to 6
- `r'(\w)(\w)?'` ----- optional capture group
- `r'[a1][b2][c3]'` ----- 'abc 123' returns `['abc','123']` and 'a2c 1b3' returns `['a2c', '1b3']`

[[Return to Top]](#table-of-contents)






<!-- 
   #    ######  ###             ##        #####                                              
  # #   #     #  #   ####      #  #      #     #  ####  #####    ##   #####  # #    #  ####  
 #   #  #     #  #  #           ##       #       #    # #    #  #  #  #    # # ##   # #    # 
#     # ######   #   ####      ###        #####  #      #    # #    # #    # # # #  # #      
####### #        #       #    #   # #          # #      #####  ###### #####  # #  # # #  ### 
#     # #        #  #    #    #    #     #     # #    # #   #  #    # #      # #   ## #    # 
#     # #       ###  ####      ###  #     #####   ####  #    # #    # #      # #    #  ####  
 -->

# APIs & Scraping

<!-- Polished -->
## APIs
- Application Programming Interface: a way to interact with 'owned' data
    * has rules and ways to interact
    * you can scrape from the user level, but it's often better to interact with APIs
- REST, RESTful: a standardized structure for URLs
- (RESTful) JSON API: an API where the URLs follow REST and the communication with the server is in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests
- `import requests`
- `response = requests.get('http_link')` ----- returns object for server response like 404 and 500
    * `response.ok`, `response.status_code`, `response.text`
- `response.text` on `requests.get('https://swapi.dev/api/people/5')` will give data on Leia from Star Wars in the form of JSON dict (name, height, mass, hair/skin/eye color, etc)
- `requests.get(http_url + '/documentation').json()['payload']` for `http_url='https://python.zgulde.net'` will give 'endpoints', other APIs give different stuff on a different link (maybe) using a different JSON container
    * `'/api/v1/items/1'` ----- Endpoints are prefixed with `/api/{version}` where version is `"v1"`, then endpoints (essentially directories or folders) and page navigation
    * Can iterate through each page in a loop and pull all information with `['next_page']` and `['max_page']` until next_page hits 'None'

<!-- Polished -->
## Web Scraping
- Overall tips:
    * `[url].com/robots.txt` ----- see if a site is OK with scraping or not
    * Keep timestamps on your work, websites change!!
- Requests, BeautifulSoup, and Selenium
    * `requests` ----- HTTP requests
    * `bs4` ----- BeautifulSoup for HTML parsing, deep dive: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
    * `selenium` ----- Automated browser work using Selenium WebDriver
### Basic HTML
- `<head></head>` shows meta-information, like `<title></title>` (browser tab info)
- `<body></body>` is the contents of the page (what the client displays)
- `<h1 class='class_name'></h1>` is an element, class is attribute (defines what kind of element it is)
    * We often identify where to scrape by looking at this class section
- `<div>` is another element with tags `<p></p>` and `<a></a>` and others
### HTTP Requests
- `import requests`
- `response = requests.get('https://web-scraping-demo.zgulde.net/news')`
    * `response.ok`, `response.status_code` ----- check if request worked
- `soup = BeautifulSoup(response.text)`
### Parsing HTML with Beautiful Soup
- `from bs4 import BeautifulSoup`
- `soup.prettify()` ----- try to print the HTML in a neat format for initial understanding
- `tag['id']` ----- get value of 'id' attr, use dict indexing on any single tag for maximum effect
- `soup.select("body a")` ----- look for `<a></a>` tags somewhere inside 'body'
- `soup.select("p > a")` ----- look for 'a' element *directly* below 'p' element
- `soup.select("p #link1")` ----- look for any element with attribute value "link1" below 'p' element
- `soup.find_all("b")` ----- return list of `<b></b>` tags
    - `soup.find_all(["a","b"])` ----- return list of any `<a></a>` and `<b></b>` tags
- `soup.find_all(has_class_but_no_id)` ----- return tags that are returned as True from function
    * ```
        def has_class_but_no_id(tag): 
            return tag.has_attr('class') and not tag.has_attr('id')
        ```
    * `soup.find_all(True)` ----- return all tags
- `soup.find_all(id='link2')` ----- search all tags with id attribute value of 'link2'
    * `soup.find_all(href=re.compile("elsie"))` ----- search all tags with href containing 'elsie'
    * `soup.find_all(id=True)` ----- return all tags that have the id attribute
    * `soup.find_all(class_=re.compile("itl"))` ----- if searching by class, use class_
- `soup.select("p.strikeout.body")` ----- search by contents of attrs for 'strikeout' and 'body' words
- `soup.find_all(string=re.compile("Dormouse"))` ----- search string (ex: `<b>string_here</b>`) for existence of 'Dormouse'
- `data_soup.find_all(attrs={"data-foo": "value"})` ----- return tags that match attribute and attr value
- `[el.attrs['od'] for el in soup.select('*') if 'id' in el.attrs]` ----- 'od' attr values if tag has 'id' attr
- `soup.select('p').attrs['href']` ----- return content of 'href' attr for 'p' tags
### Controlling Chrome using Selenium
- `from selenium import webdriver`
- `driver = webdriver.Chrome(PATH)` ----- PATH being the location of chromedriver.exe, this launches Chrome
- `driver.get(url)` ----- navigate Chrome to url
- `soup = BeautifulSoup(driver.page_source)` ----- convert current page to BeautifulSoup document (HTML)
#### Specific Selenium Work
- `from selenium.webdriver.common.by import By` ----- specify tags like By.ID, needed for some webdriver stuff
- `from selenium.webdriver.common.keys import Keys` ----- use Keys.TAB and otherwise to send keyboard inputs
- `from selenium.webdriver.support.ui import WebDriverWait`  ----- wait until specified element has loaded
    * `from selenium.webdriver.support import expected_conditions as EC`
    * `myElem = WebDriverWait(browser, delay).until(EC.presence_of_element_located((By.ID, 'IdOfMyElement')))`
- `driver.find_elements_by_xpath('//*[@id="q_all"]')` ----- return all tags that match the given XPATH
- `from selenium.webdriver.common.action_chains import ActionChains`
    * `actions = ActionChains(driver)` ----- create new action chain for webdriver called 'actions'
    * `actions.move_to_element(driver.find_element_by_xpath('//*[@id="q_type"]/div[1]')).click().perform()` ----- chain actions to move to dropdown box at this XPATH, click box, perform
    * `actions.move_to_element(driver.find_element_by_xpath('//*[@id="q_type"]/div[3]/div[2]')).click().perform()` ----- continuing on previous chain, click the designated dropdown item
### Saving Images to Local Drive
```
import shutil
r = requests.get(image_url, stream = True)    # request the zipped image into cache as 'r' variable
r.raw.decode_content = True   # set the 'decode_content' of file.raw as True to unzip file when storing
with open('image.jpeg','wb') as f: 
    shutil.copyfileobj(r.raw, f)   # save unzipped image data to 'image.jpeg'
```

[[Return to Top]](#table-of-contents)






<!-- 
 #####   #####  #            ##        #####                              
#     # #     # #           #  #      #     # #####    ##   #####  #    # 
#       #     # #            ##       #       #    #  #  #  #    # #   #  
 #####  #     # #           ###        #####  #    # #    # #    # ####   
      # #   # # #          #   # #          # #####  ###### #####  #  #   
#     # #    #  #          #    #     #     # #      #    # #   #  #   #  
 #####   #### # #######     ###  #     #####  #      #    # #    # #    # 
-->

# SQL & Apache Spark

<!-- Polished -->
## SQL
- Structured Query Language used to query databases like MySQL for tabular data
- SQL databases are usually hosted on beefy systems, so doing processing in SQL can be a lot faster than doing it on a local machine using Python
### SQL Simple Records Query
```
show databases; use database_name; show tables; describe table_name;
select date_col, col1 as Col1, col2, col3, 
IF(date_col > curdate(), True, False) as "Future"
case 
    when year(date_col) like '19%%' then '1900s' 
    when year(date_col) like '20%' then '2000s' 
    else 'bad_input' 
    end as Century
from table_name 
join table_2 using(date_col)
where (col2 between 10 and 20) and (col2 not 15) and (col3 in ('irene', 'layla')) and (year(date_col) like '201%')
order by col2 asc, Col1 desc
limit 100;
```
### SQL Aggregation Query
```
select col1, AVG(col2) as average from table group by col1 having average >= 100;
```
### SQL Subquery
```
use employees;
select concat(first_name, " ", last_name) as Name 
from employees 
where 
    hire_date = (select hire_date from employees where emp_no = 101010) 
	and
	emp_no in (select emp_no from dept_emp where to_date > curdate())
```
### SQL Temp Table Creation
```
use employees;
create temporary table germain_1457.employees_with_departments as
select first_name, last_name, departments.dept_name
from employees
join dept_emp using(emp_no)
join departments using(dept_no);
```

<!-- Polished -->
## Apache Spark
- Computational cluster manager designed to handle data that lone computers have trouble with
    * Velocity (fast gathering, lots of data, streaming)
    * Volume (large data, bigger than memory or bigger than storage)
    * Veracity (reliability of data, esp. missing data)
    * Variety (different sources, unstructured data, data isn't uniform)
- Coordinates work for clusters via Java Virtual Machine (JVM) using the Scala programming language
- The 'pyspark' library translates Python to Scala, runs JVM, and performs JVM requests all in one library
- Can run 100% locally (coordinates computer cores) but is often overkill for one-computer tasks
- Is 'lazy'- adds to, optimizes queries until the execution order is given
- Alternatives: Hadoop, Dask
### PySpark Basics
- `import pyspark`; `spark = pyspark.sql.SparkSession.builder.getOrCreate()`; ----- import, set up JVM
- `from pyspark.sql.functions import *` ----- import all functions, overwrite some regular python ones
- `df = spark.createDataFrame(pandas_df)`; `df = spark.read.csv('filepath')`; ----- create spark dataframes
- `df.show()` ----- print operation (returns None), original data doesn't change unless: df = df2; df2.show()
    * `vertical=True` to do same as pandas df.T
    * combine `vertical=True` with `truncate=False` to see each row's values in a separate section
- `df.head()` ----- returns Spark row *objects* in a list
    * `df[0]` ----- return first row object
    * `df[0].col4` ----- return value at first row, col4
- `df.toPandas()` ----- exactly what you think it is, be careful!
- `df.count()`, `len(df.columns)` ----- length, width of dataframe
- `df.explain()` ----- check Spark's intentions with current setup (not yet actioned)
    * Used mainly to diagnose performance issues; orders operations from bottom-upward
### PySpark Column Manipulation
- `df.select('x', 'y'), df.select('*')` ----- SQL-ish column selection
- `df.x.cast('string')` ----- cast column as string
- `df.withColumn('year', year(df.date)).sort(col("year").asc()).show()` ----- return dataframe with 'year' column sorted in ascending order
- `df = df.withColumnRenamed("colname_before", "colname_after")` ----- rename column
- `df.orderBy(df.x)` --- `df.sort(df.x.asc())` --- `df.sort(col('x').desc(), desc(df.y))` ---- sorting
- `col = (df.x + df.y).alias('z'); df.select(*, col).show()` ----- return df with new 'z' column for x + y
- `df.selectExpr('*', 'x + y as z').show()` ----- same operation as line above
- `tips.select('*', expr('total_bill / size AS price_per_person')).show()`
- `df = df.withColumn("col1", expr('col1 == condition')).withColumn("col2", expr('col2 == condition'))` ------ set columns to bool values on the conditions
- `df.select(when(df.x > 10, 'gt 10').otherwise('not gt 10'))` ----- if true then set value to first, if false then set value to second for df.x (use an alias)
- `df.na.drop()` --- `df.na.drop(subset=['x', 'y'])` ----- drop nulls
- `df.na.fill(0)` --- `df.na.fill(0, subset=['x', 'y'])` ----- fill nulls
- `df1.join(df2, "joiner_col", "left").drop(col2.joiner_col).drop(col1.joiner_col)` ----- join, drop joiner cols
### PySpark Filtering
- `df.where(df.x < 10)` --- `df.filter(df.x < 10)` ----- only return True rows, same thing
    * `df.where(df.x > 10).where(df.y > 10)` ----- AND logic
    * `df.where((df.x > 10) | (df.y > 10))` ----- OR logic
### PySpark Datetime
- `month('date_colname')` ----- will do what you expect for all dates in column
- `df.withColumn("col1", to_timestamp("col1", "M/d/yy H:mm"))` ----- cast as datetime using specified date format
- `df = df.withColumn("date_calc_col", datediff(current_timestamp(), "datecol"))` ----- time difference from datecol value to now
### PySpark Functions for String Columns
- `df.select(concat(lit('x:', df.x)))` ----- column values of 'x: value' for values in df.x
- `df = df.withColumn("col1", trim(lower(df.col1)))` ----- deletes start and finish whitespace
- `regexp_extract('col', re, g)` ----- extract capture group g from re using col
- `regexp_replace(col, re, repl)` ----- replace occurences of re with repl using col
- `df = df.withColumn("col1", format_string("%03d", col("col1").cast("int")),)` ----- formatting
    * Require 3 digits in values, if shorter, put 0 in front as needed to get to 3
### PySpark Aggregation
- `df.select(sum(df.x)), df.select(mean(df.x))` ----- sum, mean all values in column
- `df.groupBy("col1", "col2").count().show()` ----- basic groupby
- `df.groupBy('g').agg(mean(df.x), min(df.y), ...)` ----- normal
- `df.crosstab('g1', 'g2')` ----- count aggregation of observations using g1 and g2 as rows, columns
- `df.groupBy('g1').pivot('g2').agg(mean('x'))` ----- normal
- `df.createOrReplaceTempView('df')` --- `spark.sql(''' SELECT * FROM df ''')` ----- SQL
### PySpark Data Split
- `train, test = df.randomSplit([0.8, 0.2], seed=123)` ----- split data into train and test
- `train, validate, test = df.randomSplit([0.6, 0.2, 0.2], seed=123)` ----- split data into train, val, test
- `print('train', train.count(), 'colname', len(train.columns))` ----- print shape of train split
### PySpark to Exploration
- Use Spark to do the heavy lifting then use Pandas dataframes for visualization/otherwise
- `pandas_df = train.groupBy("colname").count().toPandas()` ----- Spark to do groupby, then pandas for viz
    * Can chain pandas methods after toPandas() like this: `spark_df.toPandas().sort_values()`
- `df.sample(fraction=0.01, seed=).toPandas()` ----- Get data sample for pandas work
### PySpark Advanced Read Write
- `spark.read.csv('file.csv', sep=',', header=True, inferSchema=True)`
    * `inferSchema` just reads the file as-is and guesses schema; header is default False for spark
- `spark.read.csv("source.csv", header=True, schema=schema)` ----- sets schema from a variable
    * `schema = StructType([StructField("col", StringType()), StructField("col", StringType()),])`
- `df.write.json("df_json", mode="overwrite")`
    * Write df to a Spark-distributed **JSON** file, one way to do it
- `df.write.format("csv").mode("overwrite").option("header", "true").save("df_csv")`
    * Write df to a Spark-distributed **CSV** file, another way to do it
- `df.printSchema()` ----- check column dtypes

[[Return to Top]](#table-of-contents)






<!-- 
#####  #   # ##### #    #  ####  #    #             #    # #####              #####  #####  
#    #  # #    #   #    # #    # ##   #             ##   # #    #             #    # #    # 
#    #   #     #   ###### #    # # #  #    #####    # #  # #    #    #####    #    # #    # 
#####    #     #   #    # #    # #  # #             #  # # #####              #####  #    # 
#        #     #   #    # #    # #   ##             #   ## #                  #      #    # 
#        #     #   #    #  ####  #    #             #    # #                  #      #####  
 -->

# Python, NumPy, Pandas

<!-- Polished -->
## Python
- Python Standard Library: https://docs.python.org/3/library/
### Native Python
- `print('hi', end='\n\n')`
- `['hi', 'lo'] + ['med']` --- `5 * ['hi', 'lo']`
- `for i, col in enumerate(cols)` ----- this is the correct order
- `string.count('a')` ----- count number of `'a'` in string
- `(" ".join(['c','a','r'])).split(" ")` ----- make `'c a r'` then split back into `['c','a','r']`
- `' 123 '.strip().isnumeric()` ----- deletes left/right whitespace, new lines, and tabs; returns True
- `[x if x % 2 == 0 else x - 1 for x in [1,2,3,4,5]]` ----- returns `[0,2,2,4,4]`
- `print(f"|{x:<8}|{y:<8}|{z:<8}|")` ----- formatted output
- `food_list.sort(key=lambda x: len(x) * -1)` ----- sort food_list by descending string lengths
    * Use lambda to create one-time functions or short functions

<!-- Polished -->
## NumPy
- Arrays!
- Excellent library for *numerical* data, especially w/ 3+ dimensions, and generating pseudo numbers for testing
### NumPy Implementation
- `np.absolute(np.array([1,-2,3,-4,5]))` ----- absolute values for very basic array
- `np.arange(1,10,0.5)` ----- returns `array([1, 1.5, 2, 2.5, ..., 9.5])`, 1 to 10 in steps of 0.5
- `np.linspace(0,10,5)` ----- returns `array([0, 2.5, 5, 7.5, 10])`, 5 equidistant steps between 0 and 10
- `(np.random.rand(5, 5) * 10).round()` ----- 5x5 array of integers 0-10
- `a[a >= 2]` ----- return a one-dimensional array of only the values that return True for a >= 2
    * `a >= 2` is value-wise evaluation (preserves the matrix), but `a[a >= 2]` returns all True only
- `a[:,0]` ----- return first column; `a[0,:]` ----- return first row; `a[0:3,:]` ----- as expected
- array1 + array2, array1 * array2, etc for matrix operations
    * Line up a row on a matrix, multiply overlapping values or divide; same as column
    * For a 5x5 matrix, can only use a 1x5, 5x1, or 5x5 for multiply/divide/add/subtract
    * Dot product requires matrix 1's column count and matrix 2's row count to be equal
- `df['over_100'] = np.where(df.col > 100, 'me_true', 'me_false')`
- `np.set_printoptions(suppress=True)` ----- suppress scientific notation

<!-- Polished -->
## Pandas
- Series and Dataframes!
- Excellent library for tabular data (2 dimensions), especially non-numerical data with labeled axes
### Pandas Series
- `pd.Series([1,2,3], name='numbers', index=['a','b','c'], dtype='object')`
- `s[11] = 12`; `s.drop(11, inplace=True)`; `s.fillna('no_value')`; `s.dropna()`; 
- `s.dtype`, `s.size`, `s.shape`, `s.describe()`, `s.head()`, `s.tail()`, `s.value_counts()`, `s.astype('int')`, `s.isin(list)`
- `s.max()`, `s.min()`, `s.idxmax()`, `s.idxmin()`
- `s.any()`, `s.all()` ----- True if any, True if all; returns column-wise when df.any() or df.all()
- `s.isna()`, `s.notna()`, `s.fillna(value)`, `s.dropna()`
    - `s.isna().sum()`, `s.isna().mean()`
- `s.map({'hi':'greeting', 'hello':'greeting'})`
- `s.str[0:4]`, `s.str.capitalize()`, and more string methods applied to values in a series
- `pd.cut(s, bins=[0,2,5], labels=['low','high'], right=False).value_counts().sort_index(ascending=False)`
- `s[s > 3]`; `s[s.index == 1]` ----- masks
    * `s[s < 0] = 0` ----- replace all negatives with zero
### Pandas Dataframes
- `pd.read_excel`, `pd.read_csv`, `pd.read_clipboard`
    * `pd.read_csv(filename, index_col=0)` ----- fixes Unnamed: 0
    * ```
        url = https://docs.google.com/spreadsheets/d/1Uhtml8KY19LILuZsrDtlsHHDC9wuDGUSe8LTEwvdI5g/edit#gid=341089357
        pd.read_csv(url.replace('/edit#gid=', '/export?format=csv&gid='), encoding='unicode_escape')`
        ```
    * `pd.read_csv('https://s3.amazonaws.com/irs-form-990/index_2011.csv', encoding='unicode_escape')`
- `pd.read_sql`
    * ```
        def get_connection(db, user=user, host=host, password=password): 
            url = f'protocol://[user[:password]@]hostname/database_name' 
            # EX: url = mysql+pymysql://codeup:p@assw0rd@123.123.123.123/some_db)
            return url
        ```
    * `pd.read_sql('SELECT * FROM employees LIMIT 10', url)`
- `pd.DataFrame({'hi':[1,2,3,4], 'lo':[6,7,8,9]})`
- `pd.DataFrame([['Mary','12-7-1999',23], ['Joe','12-7-1997',25]], columns=['name','bday','age'])` - row-wise
- `df.info()`; `df.describe().T`; `df.sort_values(by=['col1,'col2'], ascending=False)`
- `df = original_df.copy()`; `df['col'] = value_list`; `df.assign(col=series)`
- `df.rename(index = {0:'first', 1:'second'}, columns={'hi':'high'}, inplace=True)`
- `df.drop(index=[0,2])`; `df.drop(columns=['hi])`; `df.drop_duplicates()`
- `df[['hi','lo']]`, `df['hi']`, `df[0:2]`
    * `df.columns = ['high','low']`; `df.index = ['lowest','med-low','med-high','highest']`
- `pd.concat([s,s,s,s], axis=1, ignore_index=True)` ----- create dataframe from series quickly
- `df[['newcol1', 'newcol2']] = df.col.str.split(':', expand = True)` ----- split string column into two new cols
- `pd.melt(df, id_vars='colname')` ----- creates 'variable' and 'value' columns from columns not specified and their values
    * melt has multiple useful arguments to help make this better
- **Dictionary comprehension:** `pd.Series({key:function(value) for value in value_list})`
- `pd.cut(series_name, bins=[0,5,100,100000])`
    * Common to bin continuous values into ordinal/categorical to run boxplots per bin against another continuous value
- `pd.qcut()` ----- bins equal amounts of data
    * different from `pd.cut()`, which makes equal-width bins
- `df.append({'col1':value, 'col2':value}, ignore_index=True)` ----- add new row
- `df.applymap(lambda x: x if x < 3 else 5)` ----- element-wise apply, will fail if can't complete on any value
- `df.apply(lambda x: x + 1, axis=1)` ----- axis-wise apply, few use cases... just use `s = s.apply(function)`
- `df.loc[5, 'hi']`, `df.iloc[5]`
    * loc can specify a labeled index and column, or just an index
    * iloc only looks at index and ignores index labels (specify integers)
- `df[df.hi == 3]`, `df[df.index == 1]`, `df[(df.index == 2) | (df.hi == 4)]`
    * `df[df.col < 0] = None` ----- null out rows with a negative value in col
- `df.pipe` ----- send dataframe through multiple functions (sklearn?)
- `df.groupby('col1')[['col2','col3']].agg(['mean','max'])`
- `df1.merge(df2, left_on='df1_col', right_on='df2_col', how='outer', indicator=True)`
- `pd.crosstab(df.col1, df.col2, margins=True, normalize=True)` ----- margins are rowwise, colwise totals
- `df.pivot_table(index='col1', columns='col2', values='col3')` ----- where col1 and col2 meet, take all col3 values and average them (default behavior)
#### Pandas and Datetime
- `pd.to_datetime(date, format='%b:%d:%Y')`; `pd.to_datetime(df.date, format='%b:%d:%Y')`
    * `pd.date_range('start_date', freq='D', periods=num_of_days)` ----- create date range from scratch
- `df.loc[date_start:date_end]` ----- inclusive slicing of dataframe when datetime is index
- `pd.Timedelta('14d') + pd.to_datetime('2017-11-07')` ----- add 14 days to date as expected
    * `df.date.max() - df.date` ----- find amount of time between most recent date and all dates (time delta)
- `df.date.dt.day` ----- element-wise conversion of date to day number, can do with more
    * `.month`, `.year`, `.quarter`, `.day_name()` --- use `.value_counts().sort_index()`!
- `df.col.strftime('%b %D, %Y')`
- `df.resample('W').sum()` ----- "Downsampling", sum all values more precise than a week in esssentially a groupby
    * requires pandas datetime index
    * '3W' is every three weeks, can also do '3H', '3M', '3Y', etc
- `df.asfreq('D')` ----- "Upsampling", create row for each day from a less-precise interval (weekly -> daily)
    * `by_day.assign(ffill=lambda df: df.coffee_consumption.ffill())` ----- fill null with previous value
    * `by_day.assign(bfill=lambda df: df.coffee_consumption.bfill())` ----- fill null with next value
    * can also `.fillna()` as you need, or use `.loc`, etc
- `df.colname.diff()` ----- difference between current element and previous one (subtract values)
    * can enter a number, `.diff(3)`, to look at 3 elements ago
    * also enter negative values (-1) to look ahead
- `df.colname.shift()` ----- an array of colname but each value is shifted one index deeper (shift values)
    * with proper indexing, can `.shift()` a value column for lagging and leading
    * `shift(1)`, `shift(30)`, `shift(-90)`, etc
- `df.index.tz`, `df.tz_localize('America/Chicago')`, `df.tz_localize(None)` ----- timezones
- `df.resample('W').sum().colname.plot()` ----- quick line plot of a column for weekly sum

[[Return to Top]](#table-of-contents)






<!-- 
#     #                                                              ##    
##   ##   ##   ##### #####  #       ####  ##### #      # #####      #  #   
# # # #  #  #    #   #    # #      #    #   #   #      # #    #      ##    
#  #  # #    #   #   #    # #      #    #   #   #      # #####      ###    
#     # ######   #   #####  #      #    #   #   #      # #    #    #   # # 
#     # #    #   #   #      #      #    #   #   #      # #    #    #    #  
#     # #    #   #   #      ######  ####    #   ###### # #####      ###  # 
                                                                           
 #####                                            
#     # ######   ##   #####   ####  #####  #    # 
#       #       #  #  #    # #    # #    # ##   # 
 #####  #####  #    # #####  #    # #    # # #  # 
      # #      ###### #    # #    # #####  #  # # 
#     # #      #    # #    # #    # #   #  #   ## 
 #####  ###### #    # #####   ####  #    # #    # 
 -->

# Matplotlib & Seaborn

<!-- Polished -->
## Overall Notes for Visualizations in Python
- **Amazing charts for inspiration:** https://www.python-graph-gallery.com/all-charts/
- LaTeX Notation: Wrap math in dollar signs like $a^2$
    * Character chart: https://www.caam.rice.edu/~heinken/latex/symbols.pdf
    * Matplotlib LaTeX walkthrough: https://matplotlib.org/stable/tutorials/text/mathtext.html

<!-- Polished -->
## Matplotlib
- The bread and butter of data visualizations in Python
- Highly customizable, but needs a lot of work to be presentable
- Push plots to scripts to make things easily repeatable
- Customization options: https://matplotlib.org/stable/tutorials/introductory/customizing.html
### Basic Matplotlib Example
```
s = pd.Series([-3,-2,-1,0,1,2,3])
cats = pd.Series(['1','2','1','1','1','2','1'])
df = pd.DataFrame({'category':cats, 'original':s, 'squared':s**2, 'absolute_times_two':s.abs()*2})
plt.figure(figsize=(10,5))
plt.style.use('bmh')
plt.subplot(121)
plt.plot(s, s ** 2, c='green')
plt.title("Plot of $a^2$")
plt.xlabel("x")
plt.yticks(s**2)
plt.annotate('Apex', xy=(0,.3), xytext=(-1,3), fontsize=15, arrowprops={'width':5, 'color':'green'})
plt.ylabel("y", rotation=0)
plt.xlim(-3.5, 3.5)
plt.subplot(122)
plt.grid(False)
plt.bar(s, s.abs()*2, color='#FFA500', alpha=.5, ec='black', align='center')
plt.title('Plot of $|a| * 2$')
plt.suptitle('Math')
plt.tight_layout()
plt.subplots_adjust(wspace=0.2)
plt.savefig('chart.png')
plt.show()
```
### Matplotlib from Dataframes
```
df.groupby('category')[['original','squared','absolute_times_two']].sum()\
    .plot.bar(color=['red','green','blue'], alpha=.6)
```
```
df.corr().style.background_gradient(vmin=-1, vmax=1, cmap='coolwarm_r').format('{:.3f}'.format)
```
### Working with Figures and Axes
- One-Chart Guide: https://matplotlib.org/stable/gallery/lines_bars_and_markers/bar_label_demo.html
- Multi-Chart Guide: https://matplotlib.org/stable/gallery/lines_bars_and_markers/categorical_variables.html
- `fig, ax = plt.subplots()`
    * `fig, axes = plt.subplots(1, 3)`
    * `axes[0].plot()`, `axes[1].bar()`, `axes[2].scatter()`
- `p1, p2 = ax.bar(x1, y1, ...), ax.bar(x2, y2, ...)`
- `ax.methods` --- similar methods to `plt.methods`, can reference p1 and p2 as parameters
    * `ax.xaxis.set_major_formatter()` or `ax.yaxis.set_major_formatter()`
- `plt.show()`

<!-- Polished -->
## Seaborn
- First stop for building charts, then customize charts further with Matplotlib methods
- Powerful in its defaults!
    * Generate charts with Seaborn and use Matplotlib `plt.methods` for customization
- Color palettes: https://seaborn.pydata.org/tutorial/color_palettes.html
    * `sns.set_palette("colorblind")`
- Cheat Sheet: https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf
    * Mirror: https://drive.google.com/file/d/1TkETSAad4zP0zdFT1KC5E573gJdEeK_Z/view
### Seaborn Basics
- `import seaborn as sns`
- Distributions: `sns.displot(data=df.col, kind='hist' or 'kde' or 'ecdf')`
- Scatterplot or Lineplot overlaid: `sns.relplot(data=df['col1','col2','col3',...], kind='line' or 'scatter')`
- Category-Separated plots: `sns.catplot(data=df[['cat','col1','col2','col3',...]], kind='violin')`
    * Options: `strip`, `swarm`, `box`, `violin`, `boxen`, `point`, `bar`, `count`
- Pairplot: `sns.pairplot(df)`
- Axis-level Heatmap: `sns.heatmap(crosstab (df.corr()), cmap='Greens', annot=True, vmin=0, vmax=1)`
- Axis-level Scatter with Regression Line: `sns.regplot(x=df.x, y=df.y, line_kws={'color':'red'})`
- Axis-level Scatter with Edge Histograms: `sns.jointplot(data=df, x='cont_col1', y='cont_col2', hue='category)`
### Seaborn Arguments
- `col='category'` ----- chart for each unique value in col1
- `hue='category'` ----- separate color for each unique value in col1
- `style='category'` ----- changes style of plot point for each unique value in col1
### Seaborn Accessors
- You can use `.axes` or `.fig` to access, for example, `sns.pairplot()`
`sns.pairplot(arguments).axes` # each graph in figure
`sns.pairplot(arguments).fig` # figure as a whole (include all graphs)
`sns.pairplot(arguments).axes.flat` # list of pointers for each graph
`for i in pairplot.axes.flat` # access each pointer

[[Return to Top]](#table-of-contents)






<!-- 
#######                                                                 
#       #    # #####  #       ####  #####    ##   ##### #  ####  #    #
#        #  #  #    # #      #    # #    #  #  #    #   # #    # ##   #
#####     ##   #    # #      #    # #    # #    #   #   # #    # # #  #
#         ##   #####  #      #    # #####  ######   #   # #    # #  # #
#        #  #  #      #      #    # #   #  #    #   #   # #    # #   ##
####### #    # #      ######  ####  #    # #    #   #   #  ####  #    #
-->

# Exploration

<!-- Polished -->
## Exploration Prep
- Plot distribution for data wrangling to check for outliers (histogram, box-whisker), then remove outliers if necessary, then plot new distributions
### Split Data
- Scikit-Learn (sklearn) handles randomization, stratification, and data sequestering
    * Randomize entire dataset *before* splitting to remove potential bias (dataset potentially sorted)
    * Make sure all splits include all options (stratify target)
- Data prep parameters are calculated from *train*, this excludes unseen data, so don't calculate on whole dataset
#### Syntax for Splitting Data
```
from sklearn.model_selection import train_test_split
train_validate, test = train_test_split(df, test_size=0.3, random_state=123, stratify=df.colname)
train, validate = train_test_split(train_validate, test_size=.325, random_state=123, stratify=df.colname)
```
### Null Imputation
- An imputer is **mainly** used for *algorithmic* null imputation
- from sklearn.impute import SimpleImputer
- `imputer = SimpleImputer(strategy='most_frequent')`
    * Use a different strategy as necessary
```
train[['embark_town']] = imputer.fit_transform(train[['embark_town']])
validate[['embark_town']] = imputer.transform(validate[['embark_town']])
test[['embark_town']] = imputer.transform(test[['embark_town']])
```

<!-- Polished -->
## Exploration Visualization
- Try out Maggie's explore.py or Pandas Profiling if you want a quick Exploration solution
### Univariate Exploration
- Use **histograms** or other distributions to visualize each feature and the target separately
- Use one-way statistical tests here like One-Way ANOVA or Chi Square Goodness of Fit
- Document features whose categories need to be one-hot encoded
    * Consider combining categories for stakeholder answers, or dropping categories entirely
    * Use keywords and one-hot encoding to make string-based columns useful
- Remove any unnecessary or high-null features as needed
### Bivariate Exploration
- Visualize **each feature** against the target
    * Bivariate viz are "best for the money" from stakeholder perspective, easily understood
- Use statistical testing to show correlations, relationships, and dependence
- Eliminate features that do not relate to the target
### Multivariate Exploration
- Compare **between features** in terms of target
    * Use conditional formatting to add a third dimension to a viz
- **Control for "strong" features** that may drive other features to falsely-relate to target
#### Algorithmic Clustering for Multivariate Exploration
- Consider algorithmic clustering techniques for features; **set manual rules for clusters**
- Apply clustering and visualize results
- Statistically-test clusters in terms of the target, select indicative clusters
- Determine min and max values of each feature for a selected cluster
- Use (less-than & greater-than) logic against each feature for an observation
- Apply truth value in new column to serve as feature

<!-- Polished -->
## Feature Engineering
- The art of data refocusing
- Use training split to create features assembled from other features, other sources, and more
- Post-creation evaluation for whether a feature has its intended effect
- Many of sklearn's models, once fit, generate values for `.feature_importances_` that reveal feature usefulness
### Feature Engineering Techniques
- Bins as features: `train['newcol'] = pd.cut(train.colname, bins=[0,15,100], right=False, labels=['Low','High'])`
#### Keyword Engineering
- Encoding on the existence of a keyword
- Basic existence of word: `df['has_word'] = df.col.str.contains('word')`
- Basic existence of multiple words: `df['has_word'] = df.col.str.contains('word1|word2')` or `'word1&word2'`
- **Keyword Categorization**
0. *NOTE: If column can have two different categories, then it will choose the last in the loop- be careful!*
    * Consider multiple features if this is the case, or simply one-hot encoding using basic existence of word
1. Determine which features and categories to create
    * Thoughtful process, document your brainstorming
    * EX: 'Peach' and 'Sunset' indicate category 'Orange' for feature 'color'
2. Create the keyword list for each category
3. Create a mapping function to read an observation and check for existence of at least one keyword
    * If a keyword exists, mark the new column with the category
4. Loop through each category and its keyword list, pass keywords, category, feature, and df to mapper
5. Handle remaining nulls

<!-- Polished -->
## Performance-Based Feature Selection
- Most common ways are SelectKBest and Recursive Feature Elimination (RFE)
    * **These are great for determining features to investigate further**
- K-Best and RFE do not need to take in scaled data, just encoded data
#### Select K Best
- `from sklearn.feature_selection import SelectKBest`
- Choose model algorithm, evaluate each feature's strength using algorithm, return best 'n' features
- `kbest = SelectKBest(f_regression, k=3)` ----- returns top 3 'best' features using f regression
- `kbest.fit(X_train, y_train)`
- `kbest.pvalues_`
- `kbest.get_support()` ----- array showing which columns were chosen (True, False, True...)
- `X_train.columns[kbest.get_support()]` ----- shows column names
- `X_kbest = kbest.transform(X_train_scaled)` ----- if k=3, return top-3 columns
#### Recursive Feature Elimination (RFE)
- `from sklearn.feature_selection import RFE`
- Choose model algorithm, evaluate each combination of 'n' features using algorithm, return best combination
    * More computationally-expensive than `SelectKBest`, but much better at feature selection
    * Mitigate computational expense by selecting a high-efficiency algorithm
```
rfe = RFE(estimator=LinearRegression(), n_features_to_select=3)
rfe.fit(X_train, y_train)
rfe.get_support()
X_train.columns[rfe.get_support()]
pd.Series(rfe.ranking_, index=X_train.columns)
```

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                           
#     # #      #    #  ####  ##### ###### #####  # #    #  ####  
#       #      #    # #        #   #      #    # # ##   # #    # 
#       #      #    #  ####    #   #####  #    # # # #  # #      
#       #      #    #      #   #   #      #####  # #  # # #  ### 
#     # #      #    # #    #   #   #      #   #  # #   ## #    # 
 #####  ######  ####   ####    #   ###### #    # # #    #  ####  
-->

# Algorithmic Clustering

<!-- Polished -->
## Cluster Assignment
- Designation of combined feature subsets into clusters using algorithms
- Excellent for 3+ feature grouping and anomaly detection
- Clusters can be useful features for supervised prediction techniques
- Distance-based clustering **requires** scaling
### Types of Algorithmic Clustering
- Hierarchical Clustering (dendrograms)
- K-Means Clustering (distance to centroid)
- DBSCAN Video (datapoint perimeter overlap)
### Cases for Clustering
- Exploration: Choose features, cluster, ANOVA for cluster differences, understand why differences exist
- Predicting which cluster: Choose features, cluster, use clusters as target, use multi-class to predict cluster
- Predict is in a cluster: Choose features, cluster, use clusters as target, use bianry-class to predict cluster
    * `model.fit(train[train.cluster == 0][['col1','col2']], y_train)`
- Feature Creation: Cluster, get min/max of features, use `>=` and `<=` logic for cluster determination column
    * Remember to evaluate your cluster features to see if they are useful for prediction
### Real World Examples of Clustering
- Text: Document classification, summarization, topic modeling, recommendations
    * Hierarchical using Cosine Similarity
- Geographic: Distance from store, crime zones, housing prices
- Marketing: Customer segmentation, market research
- Anomaly Detection: Account takeover, security risk, fraud
- Image Processing: Radiology, security
### General Strategy for Implementing Clustering
- Scale features and remove outliers as necessary
- Gather background info for initial cluster count choice
    * Hierarchical: Plot, slice dendogram
    * K-Means, DBSCAN: Domain knowledge
- Build, fit, predict using the technique
- Use scatterplots to visually-check results
- Use ANOVA to test clusters statistically
### Handling Cluster Outliers
- Drop based on domain knowledge (an adult can't weight 19 pounds)
- If outlier doesn't change results, then feel free to drop
- If outlier affects *both* results and assumptions... compare including- and excluding-outlier results

<!-- Polished -->
## K-Means Clustering
- Distance to centroids (most popular)
* Random centroid placement at first, check inertia, adjust centroid placement, check inertia, repeat
* Final result is centroid locations with lowest-found inertias
### Choosing Number of Clusters
* Use: **Domain knowledge** --- EX: 'iris' has 3 species, so choose 3 clusters
* Use: **Exploration** --- EX: Scatterplot looks like 3 clusters
* Use: **Inertia** --- EX: Use viz of x=n_clusters and y=inertia, pick the n_clusters at the 'elbow'
### K-Means Clustering Example
```
from sklearn.cluster import kmeans
kmeans = KMeans(n_clusters=3, random_state=123)
kmeans.fit(X_train_scaled)  # no y_train needed for clustering
train['cluster'] = kmeans.predict(X_train_scaled)
# centerpoint locations
print(kmeans.cluster_centers_)
# print labels of each centerpoint
print(kmeans.labels_)
# print intertia (lower is better)
print(kmeans.inertia_) # sum of (squared) distances between samples and their closest cluster centerpoint
# plot centerpoints
centroids = df.groupby('cluster')['col1','col2','col3',...].mean()
centroids.plot.scatter(
    y='petal_length', 
    x='sepal_length', 
    c='black', marker='x', 
    s=1000, 
    ax=plt.gca(), 
    label='centroid'
)
```

<!-- Polished -->
## Hierarchical Clustering
- Slicing dendograms, clustering a 1-D array
    * Guide: https://stackabuse.com/hierarchical-clustering-with-python-and-scikit-learn/
- **Agglomerative (Bottom-Up):** Each observation is its own cluster, then observations are grouped together
    * Starts with the two observations that are closest to one another
    * Groups next closest, then next closest, and so on until all observations belong to one cluster
    * Outputs array of cluster determinations
- Divisive (Top-Down): All observations first together in one cluster, then broken down into smaller clusters
### Choosing Number of Clusters
1. Create, plot dendogram
2. Draw horizontal line at the base of the longest vertical line
3. Count the number of vertical lines that the horizontal line overlaps
4. Use that count as your cluster count hyperparameter
### Agglomerative Clustering Example
```
from sklearn.cluster import AgglomerativeClustering
import scipy.cluster.hierarchy as shc
dend = shc.dendrogram(shc.linkage(data, method='ward')) # Determine cluster count here
cluster = AgglomerativeClustering(n_clusters=2, affinity='euclidean', linkage='ward')
cluster.fit_predict(X_train)
print(cluster.labels_)
plt.scatter(X_train[:,0],X_train[:,1], c=cluster.labels_, cmap='rainbow')
```

<!-- Polished -->
## DBSCAN
- Datapoint proximity overlap (density)
- Good at finding weird shapes in data, but computationally expensive
- Draws a perimeter around each datapoint, chains overlapping perimeters, datapoints without overlap are considered outliers
    * Hyperparameter is the radius size for the perimeter
    * C-based
### DBSCAN Clustering Example
```
from sklearn.cluster import DBSCAN
db = DBSCAN(eps=0.3, min_samples=10).fit(X_train)
```

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                    
#     # #####   ##   ##### #  ####  ##### #  ####   ####  
#         #    #  #    #   # #        #   # #    # #      
 #####    #   #    #   #   #  ####    #   # #       ####  
      #   #   ######   #   #      #   #   # #           # 
#     #   #   #    #   #   # #    #   #   # #    # #    # 
 #####    #   #    #   #   #  ####    #   #  ####   ####  
-->

# Statistics

<!-- Polished -->
## Metrics
- Keep your work inside of dataframes. Append calculations as new columns and build metrics dataframes.
- Centering data ("Demeaning a vector") is important for taking data purely in its distance from the mean
    * Normal centering isn't all that statistically-valuable
- Z-Score: statistical centering, using distance from the mean in standard deviations
    * `zscore = (value - pop_mean) / stdev_size` --- `zscore = stats.zscore(value_list)`

<!-- Polished -->
## Hypothesis Testing
- The science of significance
- Understand the question and the data, create hypotheses, test, evaluate results, report findings
- **Evaluation:** Confidence interval (95% or 99%), alpha (5% or 1%), p-value, and evaluation statistic
    * Rejecting the null hypothesis: p-value less than alpha, and "correct" evaluation statistic
- **Review:** Type I Error *(falsely rejected the null hypothesis)*, Type II Error *(falsely accepted the null)*
    * False Positive Rate: probability of Type I Error; False Negative Rate: probability of Type II Error
### Statistical Test Types
#### Chi Square: Categorical crosstab and its deviation from expectations
- When data can't be separated into categories: **Goodness of Fit** (`chisquare`, `anderson_ksamp`)
    * Assumptions of Parametric: identical distribution, no value overlap, all cells have more than 5 values
    * Assumptions of Non-Parametric (K-Sample Anderson Darling): cell independence, all cells more than 5 values
    * *Used when you can't separate data into independent samples*
    * **Need to create both observed and expected crosstabs for test**
- Testing if categories have divergent outcomes: **Contingency** (`chi2_contingency`)
    * Assumptions: cell independence, all cells have more than 5 values
    * **Only need to create observed crosstab for test**
#### Comparison of Means: Independent samples' differences in average continuous value
- Discovery of difference in independent samples: **ANOVA** (`f_oneway`, `kruskal`)
    * Assumptions of Parametric (One-Way ANOVA): equal variance, normal distribution, and independence
    * Assumptions of Non-Parametric (Kruskal-Wallis): independence
- Full comparison of two independent samples: **2-Sample t-test** (`ttest-ind`, `mannwhitneyu`)
    * Assumptions for Parametric (Independent T-Test): equal variance, normal distribution, and independence
    * Assumptions for Non-Parametric (MannWhitneyU): independence
- Comparison between a sample and the total population: **1-Sample t-test** (`ttest-1samp`)
    * Assumptions: equal variance, normal distribution, and independence
    * *Used when you can't separate data into independent samples*
- Comparison of same data before and after a change: **Paired t-test** (`ttest_rel`, `wilcoxon`)
    * Assumptions for Parametric (Relative T-Test): same observations, normal distribution, independence
    * Assumptions for Non-Parametric (Wilcoxon Signed-Rank): equal variance and independence
#### Correlation: The movement of continuous values against one another
- Relationship between two continuous variables: **Linear correlation** (`pearsonr`, `spearmanr`)
    * Assumptions for Parametric (Pearson R): linear (not curved), normal distribution
    * Assumptions for Non-Parametric (Spearman R): monotonic (only increases or only decreases)
    * *pearsonr assesses linear relationship strength, spearmanr assesses monotonic relationship strength*
### Statistical Test Implementation
- Equal Variance assumption test: `stats.levene(sample1.y, sample2.y)`
- Chi Square Goodness of Fit: `t, crit_vals, significance = stats.anderson_ksamp(array_1d)`
- Chi Square Independence: `chi2, p, degf, expected = stats.chi2_contingency(observed_crosstab)`
    * Degree of Freedom `(degf): (num_cols - 1) * (num_rows - 1)`
- ANOVA: `t, p = stats.f_oneway(samp1.y, samp2.y, samp3.y, samp4.y, ...)` or `stats.kruskal`
- Two-Sample T-Test: `t, p = stats.ttest_ind(samp1.y, samp2.y, alternative=)` or `stats.mannwhitneyu`
- One-Sample T-Test: `t, p = stats.ttest_1samp(samp.y, totalpop.y, alternative=)`
- Paired T-Test: `t, p = stats.ttest_rel(before_samp.y, after_samp.y, alternative=)` or `stats.wilcoxon`
- Correlation: `corr, p = stats.pearsonr(x, y)` or `stats.spearmanr`
    * Calculate corr itself: `df.corr()`

<!-- Polished -->
## Probability
- Chances and rates
- Probability of outcome: P(outcome)
- Probability of A given B (when B is True): P(A|B)
- Low-probability combination of observed values is an anomaly!
### Calculating Probability
- Bayes Theorem: P(A|B) = P(B|A)P(A)/P(B)
    * If you have either A or B and want to calculate B or A, use Bayes Theorem
- Observed Rate: `df.col` or `df[['col1','col2']].value_counts(normalize=True)`
    * Other calculations: `(x == 3).mean()` --- `((x == 3) or (x == 2)).mean()` --- `(x <= 4).mean()`
- Theoretical Distribution: `stats.recipe(params).rvs(rolls).method()`
    * Can pass array (EX: `(3,4)`) instead of rolls to generate an array
    * Nice chart for which method to use: https://ds.codeup.com/stats/pdf_pmf_cdf_ppf_sf_isf.png
- Calculated Probability: `np.random.choice(outcome_list, size=rolls, p=[p1, p2, p3, ...])`
    * Can pass array instead of rolls: `size=(simulations, trials) as in size=(rows, columns)`
### Theoretical Distributions from Parameters
- Equal likelihood of all outcomes: Uniform (coin)
    * Not very useful for our purposes
    * Recipe: `stats.randint(low, high_not_including)`
    * P(A) = 1 / len(Options)
- Two outcomes: Binomial (success/failure)
    * Not very useful for our purposes
    * Recipe: `stats.binom(n=rolls, p=[p_True, p_False])`
    * P(A) = our input
- Normal - continuous random variable (bell curve)
    * Very useful if we expect a normal distribution for something
    * Recipe: `stats.norm(mean_value, stdev_size)`
    * P(A) = `recipe.pdf(A)` ----- `.pdf` because of continuous values
- Poisson - events per time interval
    * Useful for time-related events
    * Recipe: `stats.poisson(lambda_value)`
    * P(A) = `recipe.pmf(A)` ----- `.pmf` because of discrete values
- Lots more distributions... check scipy documentation for stats module
#### Methods for Theoretical Distributions
- Chance of specific outcome: **.pmf**(discrete_value), and **.pdf**(continuous_value)
- Proportion higher: **.sf**(number) = proportion_higher, opposite is **.isf**(proportion_higher) = number
- Proportion lower/equal: **.cdf**(number) = proportion_lowequal, opposite is **.ppf**(proportion_lowequal) = number

[[Return to Top]](#table-of-contents)






<!-- 
#     #                                ######                                                                  
##   ##  ####  #####  ###### #         #     # #####  ###### #####    ##   #####    ##   ##### #  ####  #    # 
# # # # #    # #    # #      #         #     # #    # #      #    #  #  #  #    #  #  #    #   # #    # ##   # 
#  #  # #    # #    # #####  #         ######  #    # #####  #    # #    # #    # #    #   #   # #    # # #  # 
#     # #    # #    # #      #         #       #####  #      #####  ###### #####  ######   #   # #    # #  # # 
#     # #    # #    # #      #         #       #   #  #      #      #    # #   #  #    #   #   # #    # #   ## 
#     #  ####  #####  ###### ######    #       #    # ###### #      #    # #    # #    #   #   #  ####  #    # 
-->

# Model Preparation

<!-- Needs work -->
## Encoding
- Associate each unique value with a number (label encoding)
    * Use label encoding when categories have an inherit order
- One-hot encoding: 1 or 0 in new column if row is or isn't that value
    * Use one-hot when there's no order
- pd.get_dummies(df['col1', 'col2'], drop_first=[True, True]) ----- automagically does one-hot encoding for unique values in col1 and col2
    * creates a new column for each unique value in col1 and col2 with 0 or 1 representing False and True respectively, drops first new column for col1 and col2 (less dimensionality)

<!-- Needs work -->
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
- Use sklearn.preprocessing MinMaxScaler, StandardScaler, RobustScaler
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

<!-- Needs work -->
## Resampling
- Needed when classes are imbalanced for classification modeling
- Used specifically for train to help models fit, improves performance on predicting unseen data
### SMOTE
- Oversampling the minority class
### Tomek
- Undersampling the majority class

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                                             
#     # #        ##    ####   ####  # ###### #  ####    ##   ##### #  ####  #    # 
#       #       #  #  #      #      # #      # #    #  #  #    #   # #    # ##   # 
#       #      #    #  ####   ####  # #####  # #      #    #   #   # #    # # #  # 
#       #      ######      #      # # #      # #      ######   #   # #    # #  # # 
#     # #      #    # #    # #    # # #      # #    # #    #   #   # #    # #   ## 
 #####  ###### #    #  ####   ####  # #      #  ####  #    #   #   #  ####  #    # 
-->

# Classification

<!-- Needs work -->
## Classification Overall
- Predicting a discrete target
### Classifiers Summary
- **Decision Tree:** A sequence of rules for one-input-binary-output decisions
    * Simple to implement and explain, but prone to overfit
- **Random Forest:** Row-wise voting from many decision trees that were fit on random features and data samples
    * Difficult to explain and implement, but highly effective
- **K-Nearest Neighbors:** Use distances of known-class neighbors to predict unknown-class data
    * Simple and effectively-predictive, but prone to poor performance
- **Naive Bayes:** Probability of outcome multiplied by probability of option given outcome for each feature
    * Highly effective at prediction with few major downsides
- **Logistic Regression:** Regression (calculation of coefficients) but determinations are classes instead
    * A great baseline predictive model, but usually not the best
- **XG Boost:** Iteratively use loss function on random forest, eliminate 'weak learner trees' until loss is minimized
    * World-class performance but near-impossible to explain to stakeholders
### Evaluation Summary
- Reviewing our model to see if our predictions matched actuals for a given number of observations
    * True Positive, FP, TN, FN
    * Baseline Prediction is predicting all outcomes as True
- Focus on cost: Accuracy, Recall, Precision, Specificity, F1 Score, ROC/AUC
- Confusion Matrix --- focus on Recall and Precision
    * `df = pd.DataFrame({'prediction':[], 'actual':[]})`
    * `pd.crosstab(df.prediction, df.actual)`
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
- Model Accuracy: `(df.actual == df.prediction).mean()`
- Baseline Accuracy: `(df.actual == df.baseline_prediction).mean()`
- Recall: `subset = df[df.actual == 'coffee']` ----- look at actual Yes observations
    * use Model and Baseline Accuracy against this subset
- Precision: `subset = [df.prediction == 'coffee']` ----- look at predicted Yes rows
    * use Model and Baseline Accuracy against this subset

<!-- Needs work -->
## Classification Example
### Classifier Implementation
```
from sklearn.tree import DecisionTreeClassifier
clf = DecisionTreeClassifier(max_depth=3, random_state=123) 
clf = clf.fit(X_train, y_train)
y_train_pred = clf.predict(X_train)
y_train_pred_proba = clf.predict_proba(X_train)
```
```
from sklearn.tree import export_graphviz
import graphviz
from graphviz import Graph
dot_data = export_graphviz(clf, 
    feature_names=X_train.columns, 
    class_names=clf.classes_, 
    rounded=True, 
    filled=True, 
    out_file=None
)
graph = graphviz.Source(dot_data) 
graph.render('iris_decision_tree', view=True)   # display decision tree in PDF format (a picture)
```
### Classification Evaluation
- `from sklearn.metrics import precision_score, accuracy_score, recall_score, classification_report` ----- confusion matrix calc functions
    * `df_report = pd.DataFrame(classification_report(df.actual_observed, df.model_guesses, labels=['colname', 'colname'], output_dict=True)).T` ----- outputs nice df of metrics
- `classification_report(y_train, y_pred)` ----- get metrics of train dataset
- `clf.score(X_validate, y_validate)` ----- accuracy of model against validate dataset
- `y_pred = clf.predict(X_validate)` ----- prediction array of model for validate dataset
- `classification_report(y_validate, y_pred)` ----- metrics of model against validate
- `clf.feature_importances_` ----- return which features mattered most
    * The `_` character at end indicates it's a parameter of a trained model

[[Return to Top]](#table-of-contents)






<!-- 
######                                                            
#     # ######  ####  #####  ######  ####   ####  #  ####  #    # 
#     # #      #    # #    # #      #      #      # #    # ##   # 
######  #####  #      #    # #####   ####   ####  # #    # # #  # 
#   #   #      #  ### #####  #           #      # # #    # #  # # 
#    #  #      #    # #   #  #      #    # #    # # #    # #   ## 
#     # ######  ####  #    # ######  ####   ####  #  ####  #    # 
-->

# Regression

<!-- Needs work -->
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
### Evaluation
- A shotgun pattern in homoscedasticity check (pattern shows heteroscedasticity) isn't great, consider removing outliers or transforming... can take log of entire column (storing values in new column) then run log column through the model and visualization

<!-- Needs work -->
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

[[Return to Top]](#table-of-contents)






<!-- 
#######                     #####                                
   #    # #    # ######    #     # ###### #####  # ######  ####  
   #    # ##  ## #         #       #      #    # # #      #      
   #    # # ## # #####      #####  #####  #    # # #####   ####  
   #    # #    # #               # #      #####  # #           # 
   #    # #    # #         #     # #      #   #  # #      #    # 
   #    # #    # ######     #####  ###### #    # # ######  ####  
-->

# Time Series

<!-- Needs work -->
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

[[Return to Top]](#table-of-contents)






<!-- 
#     #                                             #                                                        
##    #   ##   ##### #    # #####    ##   #         #         ##   #    #  ####  #    #   ##    ####  ###### 
# #   #  #  #    #   #    # #    #  #  #  #         #        #  #  ##   # #    # #    #  #  #  #    # #      
#  #  # #    #   #   #    # #    # #    # #         #       #    # # #  # #      #    # #    # #      #####  
#   # # ######   #   #    # #####  ###### #         #       ###### #  # # #  ### #    # ###### #  ### #      
#    ## #    #   #   #    # #   #  #    # #         #       #    # #   ## #    # #    # #    # #    # #      
#     # #    #   #    ####  #    # #    # ######    ####### #    # #    #  ####   ####  #    #  ####  ###### 
                                                                                                             
######                                                            
#     # #####   ####   ####  ######  ####   ####  # #    #  ####  
#     # #    # #    # #    # #      #      #      # ##   # #    # 
######  #    # #    # #      #####   ####   ####  # # #  # #      
#       #####  #    # #      #           #      # # #  # # #  ### 
#       #   #  #    # #    # #      #    # #    # # #   ## #    # 
#       #    #  ####   ####  ######  ####   ####  # #    #  ####  
-->

# Natural Language Processing (NLP)

<!-- Needs work -->
## Natural Language Processing (NLP)
- Codeup's focus is on text classification, but there's a lot more ways to process natural language
- Same pipeline as other methodologies, but here, we're building the corpus (dataset) that we will analyze
### Vocab
- Corpus: entire dataset
- Document: one observation
- Tokenization: breaking up into tokens (pieces)
- Stemming and Lematizing: transforming words into their roots
    * stem slices words to base word, lem converts words to base word
- Stopwords: common words that usually don't add value
- ngrams: combination of n words
- POS: part of speech
    * Part-Of-Speech Tagging: what part of speech a word is (noun, verb, adjective, etc)
    * in nltk library, there are ways to do POS tagging!
- Bag of Words: columns for specific words, rows for observation, values for either the wordcount, true/false existence, or overall proportion
### Strategies
- Reduce word variability. EX: 'math' vs 'Math', make into one word. "Beijing" vs "Peking" (romanized foreign names), make into one word.
### Tactics
- Order of reduction: original -> lowercase -> remove accents/non-ascii -> remove special characters -> tokenize (break down) -> stem/lemmatize words (calls, calling, called to call) -> remove stopwords (the) -> store transformed text for exploration
### Specific Libraries
- import nltk
- from nltk.tokenize.toktok import ToktokTokenizer
- from nltk.corpus import stopwords
### Implementation
- **update stopwords:** python -c "import nltk; nltk.download('stopwords')"
- lowercase: article.lower() 
- normalize: unicodedata.normalize('NFKD', article).encode('ascii', 'ignore').decode('utf-8')
- remove special: re.sub(r"[^a-z0-9'\s]", "") 
- tokenize: tokenizer = nltk.tokenize.ToktokTokenizer(); article = tokenizer.tokenize(article, return_str = True) (by sentence: nltk sent_tokenize)
- stemming/lemmatization: 
    * stemming: ps = nltk.porter.PorterStemmer(); stems = [ps.stem(word) for word in article.split()]; article_stemmed = ' '.join(stems)
    * lemma: nltk.download('wordnet'); wnl = nltk.stem.WordNetLemmatizer(); lemmas = [wnl.lemmatize(word) for word in article.split()]; article_lemmatized = ' '.join(lemmas)
- remove stopwords: stopword_list = stopwords.words('english') (can add to list as necessary with .append('word') or remove from list using .remove('word'), or add/remove punctuation, etc); words = article_lemmatized.split(); filtered_words = [word for word in words if word not in stopword_list]; article_without_stopwords = ' '.join(filtered_words)
### Exploration
- from wordcloud import WordCloud
    * img = WordCloud(kwargs).generate(word_list)
    * http://amueller.github.io/word_cloud/
- Prepare by cleaning, normalizing, tokenizing, lemmatizing/stemming the content
    * can use df['content_length'] = df.text.apply(len)
    * can do df['word_count'] = df.text.split().apply(len)
    * use relplot on message length and word count with hue of target labels
- Now might be a good time to identify classification classes; ex: email spam, is_spam or not_spam
- Read value counts of each word, ideally by target label
    * for spam problem, focus on differentials, so high-good low-spam words, high-spam low-good words
    * for spam problem, use stacked=True plt.barh charts to see words high/low spam
- list(nltk.bigrams(sentence.split())) ----- create two-word combinations
    * create a series from this list, then plot value counts!
### Evaluation
- Sentiment analysis is hand-jammed. Afinn and Vader are sentiment analysis tools based on social media. It might be best to look at whitepapers to select the best-available tool for the job, or, hand-jam.
- nltk.sentiment; sia = nltk.sentiment.SentimentIntensityAnalyzer(); sia.polarity_scores(string) --- neg, neu, pos, compound scores returned for string
    * nearly matches human ability to identify sentiment (0.8 vs 0.88)
    * used primarily on short phrases (think sentences)
    * punctuations!!, CAPITALIZATION can increase intensity
    * df['sentiment'] = df.text.apply(lambda doc: sia.polarity_scores(doc)['compound'])

<!-- Needs work -->
## Modeling (NLP)
- TF-IDF: term frequency * inverse document frequency
    * helps identify how important a word is in a document
    * tf is how often a word shows, idf is how unique the word is in all documents
    * used by search engines
    * helps filter out stopwords
    * tf for single document, idf for corpus
- Try out bag of ngrams, try out stem v lemmatize, etc for different model approaches
### NLP Modeling Syntax
- from sklearn.feature_extraction.text import CountVectorizer
    * show value counts per document of each unique word (not very useful)
    * cv = CountVectorizer()
        * can set ngram_range, ex: CountVectorizer(ngram_range=(2,2)) shows bigrams
        * expects a string of documents or a 1-dimensional pandas series
        * pre-processing strp to transform data, turns list of strings into a matrix
        * different from tokenization because tokenization focuses on selection, countvector focuses on turning entire string into a vector
    * bag_of_words = cv.fit_transform(data)
        * 'sparse matrix' is a matrix with more zeroes than anything else
    * pd.DataFrame(bag_of_words.todense(), columns=cv.get_feature_names()) ----- push word matrix with column names to dataframe
    * cv.vocabulary_ ----- returns word counts
- from sklearn.feature_extraction.text import TfidfVectorizer
    * important for identifying stopwords (very useful)
    * tfidf = TfidfVectorizer()
    * bag_of_words = tfidf.fit_transform(data)
    * pd.DataFrame(bag_of_words.todense(), columns=cv.get_feature_names())
    * pd.Series(dict(zip(tfidf.get_feature_names(), tfidf.idf_))).sort_values() ----- show each word and their score
- SelectKBest or RFE to determine which words to use!
    * pd.Series(dict(zip(dv.get_feature_names(), tree.feature_importances_))).sort_values().tail(5) ----- see top-5 features (feature_importances_ is a built-in for DecisionTreeClassifier)
- DecisionTreeClassifier fit on train and predict train as usual, requires target as usual
    * cv = CountVectorizer() --- X_bow = cv.fit_transform(X_train) --- tree = DecisionTreeClassifier(max_depth=5) --- tree.fit(X_bow, y_train) --- tree.score(X_bow, y_train)
        * make sure to also transform out-of-sample split!
    * tfidf = TfidfVectorizer() --- X_tfidf = tfidf.fit_transform(X_train) --- tree.fit(X_tfidf, y_train) --- tree.score(X_tfidf, y_train)
        * make sure to also transform out-of-sample split!

[[Return to Top]](#table-of-contents)






<!-- 
#     #                                             #                                                        
   #                                                ######                                                   
  # #   #    #  ####  #    #   ##   #      #   #    #     # ###### ##### ######  ####  ##### #  ####  #    # 
 #   #  ##   # #    # ##  ##  #  #  #       # #     #     # #        #   #      #    #   #   # #    # ##   # 
#     # # #  # #    # # ## # #    # #        #      #     # #####    #   #####  #        #   # #    # # #  # 
####### #  # # #    # #    # ###### #        #      #     # #        #   #      #        #   # #    # #  # # 
#     # #   ## #    # #    # #    # #        #      #     # #        #   #      #    #   #   # #    # #   ## 
#     # #    #  ####  #    # #    # ######   #      ######  ######   #   ######  ####    #   #  ####  #    # 
-->

# Anomaly Detection

<!-- Needs work -->
## Anomaly Detection
- Finding outliers (numerical distance) and anomalies (general difference) for the purpose of further investigation
    * Can come from novel patterns or from outlier datapoints
- Domain knowledge is almost always preferable to raw detection techniques
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
### Anomalies - Time-Series Values
- Exponentially-weighted moving averages
    * Hyperparameter alpha set to 0 is traditional average (average all values in series
    * alpha set to 1 is most recent value (each moving average is most recent value)
    * alpha set to anything between 0 and 1 gives weight to past values and determines how quickly things fall off in terms of weight (weigh recent values more than older values, average the weighted values)
    * The value you set alpha to is dependent on how many anomalous values you want
- Bollinger bands - anomalies outside the bands
    * Used a lot in finance and stock market analysis
    * Calculate each band in dataframe... there might be a library out there to help
    * Midband is moving average (you set this, can also be exponentially-weighted moving average)
    * Upperband = Midband + (K * moving standard deviation), where K is hyperparameter
        * Standard values for K are 2 and 20
        * The value you set K to is dependent on how many anomalous values you want
    * Lowerband = Midband - (K * moving standard deviation)
    * %b is a calculation of volatility, anything above 1 or below 0 is outside the bands
### Anomalies - Clustering
- DBSCAN - anomalies by cluster
    * Distance-based (requires scaling) cluster creation algorithm
    * Often done against count and nunique agg funcs for discrete vars
    * dbsc = DBSCAN(eps=.1, min_samples=20).fit(scaled_df)
        * eps is radius, min_samples is minimum amount of datapoints within the radius to be determined non-outlier data - so here, require 20 values in radius .1, anything not included is considered an outlier
    * clustered_df = dbsc.transform(scaled_df)
    * clustered_df.labels ----- show cluster numbers
    * clustered_df[clustered_df.labels == cluster_num] ----- show values in a specific cluster
        * outlier cluster is always clustered_df.labels == -1

[[Return to Top]](#table-of-contents)






<!-- 
######                          #                                                   
#     # ###### ###### #####     #       ######   ##   #####  #    # # #    #  ####  
#     # #      #      #    #    #       #       #  #  #    # ##   # # ##   # #    # 
#     # #####  #####  #    #    #       #####  #    # #    # # #  # # # #  # #      
#     # #      #      #####     #       #      ###### #####  #  # # # #  # # #  ### 
#     # #      #      #         #       #      #    # #   #  #   ## # #   ## #    # 
######  ###### ###### #         ####### ###### #    # #    # #    # # #    #  ####  
-->

# Deep Learning

<!-- Needs work -->
## Deep Learning
- Obscured machine learning
- We'll use Tensor Flow, the Keras front end
    * PyTorch is a competitor to Tensor Flow
- Deep Learning takes a long time to perform, and obscures the answers in a way. Have to be careful about when to use it, but it may solve a problemset that an analyst can't
- Good at: Images/Video, Sound, NLP, Reinforcement Learning (nontabular, large)
- Artificial Neural Networks are good at recognizing/replicating patterns leading to an optimized outcome (self-driving cars as an example)
- Bad at: tabular, small data
### Design
- Uses neural nodes for weighing patterns
- Neural nodes combine into a perceptron
    * Input is however many features you're feeding in (A0, A1, A2)
    * Output is the number of classification outcomes
    * One layer of perception is an in-parallel layer
        * Input weights
    * Single-layer perceptron: one step of perception between input and output
    * Multi-layer perceptron: multiple steps of perception between input and output (series of perception)
- A tensor is higher-dimensionality data than a scalar (1D), vector (2D), or matrix (3D)
- Gradient Descent: seeking the minimum loss
    * Distance-based, optimizing connections to reach an answer
    * Backpropogation against feedforward
### Implementation
- from tensorflow import keras; from keras import models, layers
- from keras.datasets import mnist ----- very popular image classification dataset
- (train_images, train_labels), (test_images, test_labels) = mnist.load_data()
- train_images = train_images.reshape((60000, 28 * 28)); train_images = train_images.astype('float32') / 255 ----- reshape data for model
- test_images = test_images.reshape((10000, 28 * 28)); test_images = test_images.astype('float32') / 255
- network = models.Sequential() ----- create the model
- network.add(layers.Dense(512, activation='relu', input_shape(28*28,))) ----- add a layer
- network.add(layers.Dense(10, activation='softmax')) ----- add output layer
- network.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
    * compile the model
- train_labels = keras.utils.to_categorical(train_labels)
- test_labels = keras.utils.to_categorical(test_labels)
- network.fit(train_images, train_labels, epochs=20, batch_size=128)
- test_loss, test_acc = network.evaluate(test_images, test_labels)
- print(f'accuracy of network on test set: {test_acc}')

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                     #     #                          
#     #  ####  #    # #####  #    # ##### ###### #####     #     # #  ####  #  ####  #    # 
#       #    # ##  ## #    # #    #   #   #      #    #    #     # # #      # #    # ##   # 
#       #    # # ## # #    # #    #   #   #####  #    #    #     # #  ####  # #    # # #  # 
#       #    # #    # #####  #    #   #   #      #####      #   #  #      # # #    # #  # # 
#     # #    # #    # #      #    #   #   #      #   #       # #   # #    # # #    # #   ## 
 #####   ####  #    # #       ####    #   ###### #    #       #    #  ####  #  ####  #    # 
-->

# Computer Vision

<!-- Needs work -->
## Computer Vision
- 

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                    #     #                                                     
#     # #####   ####   ####   ####        #     #   ##   #      # #####    ##   ##### #  ####  #    # 
#       #    # #    # #      #            #     #  #  #  #      # #    #  #  #    #   # #    # ##   # 
#       #    # #    #  ####   ####  ##### #     # #    # #      # #    # #    #   #   # #    # # #  # 
#       #####  #    #      #      #        #   #  ###### #      # #    # ######   #   # #    # #  # # 
#     # #   #  #    # #    # #    #         # #   #    # #      # #    # #    #   #   # #    # #   ## 
 #####  #    #  ####   ####   ####           #    #    # ###### # #####  #    #   #   #  ####  #    # 
-->

# Cross Validation

<!-- Needs work -->
## Cross-Validation
- K-fold cross validation: split *train* into more train-test splits, average prediction score across fold combinations
    * from sklearn.model_selection import cross_val_score
    * cross_val_score(clf, X_train, y_train, cv=5).mean() ----- eval clf model w 5 folds
        * init empty 'scores' dictionary, loop through max_depths, eval score using this func, use scores[depth] = score
    * from sklearn.metrics import precision_score, make_scorer
    * cross_val_score(clf, X_train, y_train, cv=5, scorer=make_scorer(precision_score, pos_label='prediction')) ----- use a different scorer than default, pos_label converts non-binary values to binary by choosing what is 1, making everything else 0
    * One of those folds is a test split, the rest of the folds are train splits
    * Each fold rotates in as the test split
    * Common fold counts: 3, 4, 5, 10 (5 most common)
- Grid Search: use K-fold cross validation to determine best max_depth train split
    * Basically does validate for us- choose best model here and run against test
    * from sklearn.model_selection import GridSearchCV
    * Defaults to .score and r2
    * Only optimizes hyperparameters
### Examples
- grid = GridSearchCV(clf, {'n_neighbors': range(1, 21)}, cv=5)
    * Notice how you pass hyperparameter options to GridSearchCV

[[Return to Top]](#table-of-contents)