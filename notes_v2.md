# Notes Planning/Brainstorming
My original ds_notes.md was intended to quickly capture curriculum into a digestible one-source location while it was being taught. For that purpose, it worked extremely well. It allowed me to focus on what I didn't immediately understand, improving my retention of advanced material, and stored things I might not remember off the top of my head.

This iteration of my notes is for long-term reference. I will keep my original notes, and I have access to the curriculum itself, so this version will have a different format. Instead of packing information on tools, this notes format will pack information on the workflow elements.

# Notes

<!-- -------------------------------- Environment ---------------------------------- -->

# Environment

## Terminal
- mkdir, rmdir, rm, cp, mv, cd, ls, pwd, cwd
- curl -O url_address ----- copy down a file from a URL (often used for raw Github files)
- Log in to a SQL server: -u username -p -h ip_address ----- -p prompts for a password
- Create a new file using VS Code: code filename.filetype
- Launch Jupyter Notebook server: jupyter notebook
- Multi-line cursor: Hold command, clickdrag

## Git
- git clone github_repo_ssh_link
- git pull, git status, git add, git commit -m 'message', git push
- Use .gitignore
- git merge issue: 
    1. pull repo down to new folder
    2. copy changed files manually to new folder
    3. push from new folder
    4. delete old folder using rm -rf folder_name

## Jupyter Notebook
- Excellent interface for iPython with easy-to-use UI
- Command mode for cell operations, edit mode for editing lines
- Command mode: dd for cell deletion, y for code cell, m for markdown cell
- Edit mode: TAB for autocomplete of methods/variables/filenames, Shift TAB for full context at cursor location
- Edit mode: Split cell into two cells at cursor with option shift -
- Hold option and left click to drag multi-line cursor

## Excel & Google Sheets
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
### Excel & Google Sheets Functions
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

## Power BI
- From a cursory look, a mix of Excel and some table join functionality. Popular software.

## Sequel ACE
- Excellent interface for SQL database reads and querying

## VS Code
- One-stop interface for file editing and viewing

## Tableau Public
- Excellent software for interactive visualizations and dashboards

<!-- -------------------------------- Acquisition & Preparation ---------------------------------- -->

# Acquisition & Preparation

## Tidy Data
- Tidying Data: https://vita.had.co.nz/papers/tidy-data.pdf
    * One value per cell: split out multi-value cells, 'melt' one-hot columns into single column, handle nulls

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
- import pyspark; spark = pyspark.sql.SparkSession.builder.getOrCreate(); ----- import, set up JVM
- from pyspark.sql.functions import * ----- import all functions, overwrite some regular python ones
- df = spark.createDataFrame(pandas_df); df = spark.read.csv('filepath'); ----- create spark dataframes
- df.show() ----- print operation (returns None), original data doesn't change unless: df = df2; df2.show()
    * vertical=True to do same as pandas df.T
    * combine vertical=True with truncate=False to see each row's values in a separate section
- df.head() ----- returns Spark row objects in a list
    * df[0] ----- return first row object
    * df[0].col4 ----- return value at first row, col4
- df.toPandas() ----- exactly what you think it is, be careful!
- df.count(), len(df.columns) ----- length, width of dataframe
- df.explain() ----- check Spark's intentions with current setup (not yet actioned)
    * Used mainly to diagnose performance issues; orders operations from bottom-upward
### PySpark Column Manipulation
- df.select('x', 'y'), df.select('*') ----- SQL-ish column selection
- df.x.cast('string') ----- cast column as string
- df.withColumn('year', year(df.date)).sort(col("year").asc()).show() ----- return dataframe with 'year' column sorted in ascending order
- df = df.withColumnRenamed("colname_before", "colname_after") ----- rename column
- df.orderBy(df.x) --- df.sort(df.x.asc()) --- df.sort(col('x').desc(), desc(df.y)) ---- sorting
- col = (df.x + df.y).alias('z'); df.select(*, col).show() ----- return df with new 'z' column for x + y
- df.selectExpr('*', 'x + y as z').show() ----- same operation as line above
- tips.select('*', expr('total_bill / size AS price_per_person')).show()
- df = df.withColumn("col1", expr('col1 == condition')).withColumn("col2", expr('col2 == condition')) ------ set columns to bool values on the conditions
- df.select(when(df.x > 10, 'gt 10').otherwise('not gt 10')) ----- if true then set value to first, if false then set value to second for df.x (use an alias)
- df.na.drop() --- df.na.drop(subset=['x', 'y']) ----- drop nulls
- df.na.fill(0) --- df.na.fill(0, subset=['x', 'y']) ----- fill nulls
- df1.join(df2, "joiner_col", "left").drop(col2.joiner_col).drop(col1.joiner_col) ----- join, drop joiner cols
### PySpark Filtering
- df.where(df.x < 10) --- df.filter(df.x < 10) ----- only return True rows, same thing
    * df.where(df.x > 10).where(df.y > 10) ----- AND logic
    * df.where((df.x > 10) | (df.y > 10)) ----- OR logic
### PySpark Datetime
- month('date_colname') ----- will do what you expect for all dates in column
- df.withColumn("col1", to_timestamp("col1", "M/d/yy H:mm")) ----- cast as datetime using specified date format
- df = df.withColumn("date_calc_col", datediff(current_timestamp(), "datecol")) ----- time difference from datecol value to now
### PySpark Functions for String Columns
- df.select(concat(lit('x:', df.x))) ----- column values of 'x: value' for values in df.x
- df = df.withColumn("col1", trim(lower(df.col1))) ----- deletes start and finish whitespace
- regexp_extract('col', re, g) ----- extract capture group g from re using col
- regexp_replace(col, re, repl) ----- replace occurences of re with repl using col
- df = df.withColumn("col1", format_string("%03d", col("col1").cast("int")),) ----- formatting
    * require 3 digits in values, if shorter, put 0 in front as needed to get to 3
### PySpark Aggregation
- df.select(sum(df.x)), df.select(mean(df.x)) ----- sum, mean all values in column
- df.groupBy("col1", "col2").count().show() ----- basic groupby
- df.groupBy('g').agg(mean(df.x), min(df.y), ...) ----- normal
- df.crosstab('g1', 'g2') ----- count aggregation of observations using g1 and g2 as rows, columns
- df.groupBy('g1').pivot('g2').agg(mean('x')) ----- normal
- df.createOrReplaceTempView('df') --- spark.sql(''' SELECT * FROM df ''') ----- SQL
### PySpark Data Split
- train, test = df.randomSplit([0.8, 0.2], seed=123) ----- split data into train and test
- train, validate, test = df.randomSplit([0.6, 0.2, 0.2], seed=123) ----- split data into train, val, test
- print('train', train.count(), 'colname', len(train.columns)) ----- print shape of train split
### PySpark to Exploration
- Use Spark to do the heavy lifting then use Pandas dataframes for visualization/otherwise
- pandas_df = train.groupBy("colname").count().toPandas() ----- Spark to do groupby, then pandas for viz
    * can chain pandas methods after toPandas() like this: spark_df.toPandas().sort_values()
- df.sample(fraction=0.01, seed=).toPandas() ----- Get data sample for pandas work
### PySpark Advanced Read Write
- spark.read.csv('file.csv', sep=',', header=True, inferSchema=True)
    * inferSchema just reads the file as-is and guesses schema; header is default False for spark
- spark.read.csv("source.csv", header=True, schema=schema) ----- sets schema from a variable
    * schema = StructType([StructField("col", StringType()), StructField("col", StringType()),])
- df.write.json("df_json", mode="overwrite")
    * write df to a Spark-distributed JSON file, one way to do it
- df.write.format("csv").mode("overwrite").option("header", "true").save("df_csv")
    * write df to a Spark-distributed CSV file, another way to do it
- df.printSchema() ----- check column dtypes

## SQL
- Structured Query Language used to query databases like MySQL for tabular data
### Simple Records Query
- show databases; use database_name; show tables; describe table_name;
- select date_col, col1 as Col1, col2, col3, 
- IF(date_col > curdate(), True, False) as "Future"
- case 
    * when year(date_col) like '19%%' then '1900s' 
    * when year(date_col) like '20%' then '2000s' 
    * else 'bad_input' 
    * end as Century
- from table_name 
- join table_2 using(date_col)
- where (col2 between 10 and 20) and (col2 not 15) and (col3 in ('irene', 'layla')) and (year(date_col) like '201%')
- order by col2 asc, Col1 desc
- limit 100;
### Aggregation Query
- select col1, AVG(col2) as average from table group by col1 having average >= 100;
### Subquery
- use employees;
- select concat(first_name, " ", last_name) as Name 
- from employees 
- where 
    * hire_date = (select hire_date from employees where emp_no = 101010) 
	* and
	* emp_no in (select emp_no from dept_emp where to_date > curdate());
### Temp Table Creation
- use employees;
- create temporary table germain_1457.employees_with_departments as
- select first_name, last_name, departments.dept_name
- from employees
- join dept_emp using(emp_no)
- join departments using(dept_no);

## APIs
- Application Programming Interface: a way to interact with 'owned' data
    * has rules and ways to interact
    * you can scrape from the user level, but it's often better to interact with APIs
- REST, RESTful: a standardized structure for URLs
- (RESTful) JSON API: an API where the URLs follow REST and the communication with the server is in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests
- import requests
- response = requests.get('http_link') ----- returns object for server response like 404 and 500
    * response.ok, response.status_code, response.text
- response.text on requests.get('https://swapi.dev/api/people/5') will give data on Leia from Star Wars in the form of JSON dict (name, height, mass, hair/skin/eye color, etc)
- requests.get(http_url + '/documentation').json()['payload'] for http_url='https://python.zgulde.net' will give 'endpoints', other APIs give different stuff on a different link (maybe) using a different JSON container
    * '/api/v1/items/1' ----- Endpoints are prefixed with /api/{version} where version is "v1", then endpoints (essentially directories or folders) and page navigation
    * Can iterate through each page in a loop and pull all information with ['next_page'] and ['max_page'] until next_page hits 'None'

## Web Scraping
- Overall tips:
    * [url].com/robots.txt ----- see if a site is OK with scraping or not
    * Keep timestamps on your work, websites change!!
- Requests, BeautifulSoup, and Selenium
    * requests ----- HTTP requests
    * bs4 ----- BeautifulSoup for HTML parsing, deep dive: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
    * selenium ----- Automated browser work using Selenium WebDriver
### Basic HTML
- <head></head> shows meta-information, like <title></title> (browser tab info)
- <body></body> is the contents of the page (what the client displays)
- <h1 class='class_name'></h1> is an element, class is attribute (defines what kind of element it is)
    * We often identify where to scrape by looking at this class section
- <div> is another element with tags <p></p> and <a></a> and others
### HTTP Requests
- import requests
- response = requests.get('https://web-scraping-demo.zgulde.net/news')
    * response.ok, response.status_code ----- check if request worked
- soup = BeautifulSoup(response.text)
### Parsing HTML with Beautiful Soup
- from bs4 import BeautifulSoup
- soup.prettify() ----- try to print the HTML in a neat format for initial understanding
- tag['id'] ----- get value of 'id' attr, use dict indexing on any single tag for maximum effect
- soup.select("body a") ----- look for <a></a> tags somewhere inside 'body'
- soup.select("p > a") ----- look for 'a' element *directly* below 'p' element
- soup.select("p #link1") ----- look for any element with attribute value "link1" below 'p' element
- soup.find_all("b") ----- return list of <b></b> tags
    - soup.find_all(["a","b"]) ----- return list of any <a></a> and <b></b> tags
- soup.find_all(has_class_but_no_id) ----- return tags that are returned as True from function
    * def has_class_but_no_id(tag): return tag.has_attr('class') and not tag.has_attr('id')
    * soup.find_all(True) ----- return all tags
- soup.find_all(id='link2') ----- search all tags with id attribute value of 'link2'
    * soup.find_all(href=re.compile("elsie")) ----- search all tags with href containing 'elsie'
    * soup.find_all(id=True) ----- return all tags that have the id attribute
    * soup.find_all(class_=re.compile("itl")) ----- if searching by class, use class_
- soup.select("p.strikeout.body") ----- search by contents of attrs for 'strikeout' and 'body' words
- soup.find_all(string=re.compile("Dormouse")) ----- search string (ex: <b>string_here</b>) for existence of 'Dormouse'
- data_soup.find_all(attrs={"data-foo": "value"}) ----- return tags that match attribute and attr value
- [el.attrs['od'] for el in soup.select('*') if 'id' in el.attrs] ----- 'od' attr values if tag has 'id' attr
- soup.select('p').attrs['href'] ----- return content of 'href' attr for 'p' tags
### Controlling Chrome using Selenium
- from selenium import webdriver
- driver = webdriver.Chrome(PATH) ----- PATH being the location of chromedriver.exe, this launches Chrome
- driver.get(url) ----- navigate Chrome to url
- soup = BeautifulSoup(driver.page_source) ----- convert current page to BeautifulSoup document (HTML)
#### Specific Selenium Work
- from selenium.webdriver.common.by import By ----- specify tags like By.ID, needed for some webdriver stuff
- from selenium.webdriver.common.keys import Keys ----- use Keys.TAB and otherwise to send keyboard inputs
- from selenium.webdriver.support.ui import WebDriverWait  ----- wait until specified element has loaded
    * from selenium.webdriver.support import expected_conditions as EC
    * myElem = WebDriverWait(browser, delay).until(EC.presence_of_element_located((By.ID, 'IdOfMyElement')))
- driver.find_elements_by_xpath('//*[@id="q_all"]') ----- return all tags that match the given XPATH
- from selenium.webdriver.common.action_chains import ActionChains
    * actions = ActionChains(driver) ----- create new action chain for webdriver called 'actions'
    * actions.move_to_element(driver.find_element_by_xpath('//*[@id="q_type"]/div[1]')).click().perform() ----- chain actions to move to dropdown box at this XPATH, click box, perform
    * actions.move_to_element(driver.find_element_by_xpath('//*[@id="q_type"]/div[3]/div[2]')).click().perform() ----- continuing on previous chain, click the designated dropdown item
### Saving Images to Local Drive
- import shutil
- r = requests.get(image_url, stream = True) ----- request the zipped image into cache as 'r' variable
- r.raw.decode_content = True ----- set the 'decode_content' of file.raw as True to unzip file when storing
- with open('image.jpeg','wb') as f: shutil.copyfileobj(r.raw, f) ----- save unzipped image data to 'image.jpeg'

## Python

## NumPy

## Pandas

## REGEX

<!-- -------------------------------- Exploration & Delivery ---------------------------------- -->

# Exploration & Delivery

## Splitting Data

## Uni-, Bi-, Multi-variate Exploration

## Feature Engineering

## Seaborn & Matplotlib

## SciPy

<!-- --------------------------------- Prediction --------------------------------- -->

# Prediction

## Feature Preparation
### Encoding
### Scaling

## Classification
### SMOTE

## Regression

## Time-Series

## Algorithmic Clustering

## Natural Language Processing (NLP)

## Anomaly Detection

## Deep Learning

## Computer Vision

## Cross-Validation
