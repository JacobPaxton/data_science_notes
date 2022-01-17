# Notes Planning/Brainstorming
My original ds_notes.md was intended to quickly capture curriculum into a digestible one-source location while it was being taught. For that purpose, it worked extremely well. It allowed me to focus on what I didn't immediately understand, improving my retention of advanced material, and stored things I might not remember off the top of my head.

This iteration of my notes is for long-term reference. I will keep my original notes, and I have access to the curriculum itself, so this version will have a different format. Instead of packing information on tools, this notes format will pack information on the workflow elements.






<!-- 
#     #                            
##    #  ####  ##### ######  ####  
# #   # #    #   #   #      #      
#  #  # #    #   #   #####   ####  
#   # # #    #   #   #           # 
#    ## #    #   #   #      #    # 
#     #  ####    #   ######  ####  
-->

# Notes

<!-- Needs work -->
## Advice
- Zach: Consistency > Intensity, Motivation is important, Doing data science > learning about data science, Publish!, If it's worth doing, it's worth getting started
- Zach: ask in interview "what does professional development look like for your employees?"

<!-- Needs work -->
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

<!-- Needs work -->
## Tidy Data
- Tidying Data: https://vita.had.co.nz/papers/tidy-data.pdf
- One value per cell: split out multi-value cells, 'melt' one-hot columns into single column, handle nulls






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
- mkdir, rmdir, rm, cp, mv, cd, ls, pwd, cwd
- curl -O url_address ----- copy down a file from a URL (often used for raw Github files)
- Log in to a SQL server: -u username -p -h ip_address ----- -p prompts for a password
- Create a new file using VS Code: code filename.filetype
- Launch Jupyter Notebook server: jupyter notebook
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
- =B2-B3 ----- subtract cell B3 from cell B2
- =SUM(num_cells1, num_cells2), =AVERAGE(num_cells1, num_cells2), =COUNT(cells)
    * - =COUNTIF(), =SUMIF()
- =MOD(numeric_cells, number) ----- remainders
- =POWER(numeric_cells, number) ----- raise to a power
- =CEILING(numeric_cells) =FLOOR(numeric_cells) ----- round up, round down
- =CONCATENATE(cells, cells, " ", cells, " ", ...) ----- smash values together in new range
- =SPLIT(cells, delimiter) ----- as expected
- =LEN(cells) ----- number of characters in cell
- =REPLACE(text, position, length, new_text)
- =SUBSTITUTE(text_to_search, search_for, replace_with, [occurrence_number])
- =LEFT(cells, num_of_chars), =MID(cells, start_index, steps_to_read)), =RIGHT(cells, num_of_chars)
- =UPPER(cells), =LOWER(cells), =PROPER(cells)
- =NOW(), =TODAY(), =TIME(hour_cell, minute_cell, second_cell), =DATEDIF(start_cells, end_cells, step)
    * =YEAR(cells), =MONTH(cells), DAY(cells), =HOUR(cells), =MINUTE(cells), =SECOND(cells)
- =VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE) ----- vertically searches range_to_search for key, if it finds it, returns col_to_return, if it's not exact match, ignores it (due to FALSE)
    * VLOOKUP looks at first column specified... be careful
- =IF(AND(cond1, OR(cond2, cond3)), truth_value, false_value), =IFERROR(value, truth_value)
    * *Conditions can come from cells*
- =INDEX(range, MATCH(string_to_match, range))
- =SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc}) ----- creates a red in-cell bar chart of data from range with maxed bar when reaching max value of range

<!-- Needs work -->
## Power BI
- From a cursory look, a mix of Excel and some table join functionality. Popular software.

<!-- Needs work -->
## Sequel ACE
- Excellent interface for SQL database reads and querying

<!-- Needs work -->
## VS Code
- One-stop interface for file editing and viewing

<!-- Needs work -->
## Tableau Public
- Excellent software for interactive visualizations and dashboards
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
- | Anything: .                | Alphanumeric: \w \W | Whitespace: \s \S | Digit: \d \D  |
- | Zero or more (optional): * | One or more: +      | Optional: ?       |
- | {5} Repeat exactly 5 times | {3,6} Min 3, Max 6  | {3,} At least 3 times             |
- | Anchor front: ^            | Anchor back: $      | Word boundary: \b |
- | Capture group: ()  (?P<colname>regex_exp) |
### REGEX Queries
- re.search(regexg, subject) ----- random search, report first-found start/stop index and matched string
- re.match(regexp, subject) ----- re.search but from beginning
- re.findall(regexp, subject) ----- report all matches using list
- re.sub(regexp, sub_in, subject) ----- return string with subbed-in substring
- df.colname.str.extract(regexp) ----- return dataframe where each column is one capture group's results
#### REGEX Query Options
- re.IGNORECASE is as expected; re.MULTILINE is new query per line; re.VERBOSE is ignore whitespace
- use | to add multiple flags, ex: re.findall(regexp, subject, re.IGNORECASE | re.MULTILINE)
### REGEX examples
- r'a' ----- r marks string as a raw string, all characters taken as-is
- r'\w\w' ----- find two in-sequence alphanumeric chars
    * 'abc 123' becomes ['ab','12'] because it consumes 'ab' and '12', so no 'bc' or '23'
- r'\w+' ----- capture max combo of each alphanumeric
- r'.*' ----- everything. only use asterisks with capture groups, and when you don't know if chars will be there
- r'\w{3,6}' ----- only capture when 3 alphanumerics in sequence and as many as possible up to 6
- r'(\w)(\w)?' ----- optional capture group
- r'[a1][b2][c3]' ----- 'abc 123' returns ['abc','123'] and 'a2c 1b3' returns ['a2c', '1b3']





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
- import requests
- response = requests.get('http_link') ----- returns object for server response like 404 and 500
    * response.ok, response.status_code, response.text
- response.text on requests.get('https://swapi.dev/api/people/5') will give data on Leia from Star Wars in the form of JSON dict (name, height, mass, hair/skin/eye color, etc)
- requests.get(http_url + '/documentation').json()['payload'] for http_url='https://python.zgulde.net' will give 'endpoints', other APIs give different stuff on a different link (maybe) using a different JSON container
    * '/api/v1/items/1' ----- Endpoints are prefixed with /api/{version} where version is "v1", then endpoints (essentially directories or folders) and page navigation
    * Can iterate through each page in a loop and pull all information with ['next_page'] and ['max_page'] until next_page hits 'None'

<!-- Polished -->
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





<!-- 
 #####   #####  #            ##        #####                              
#     # #     # #           #  #      #     # #####    ##   #####  #    # 
#       #     # #            ##       #       #    #  #  #  #    # #   #  
 #####  #     # #           ###        #####  #    # #    # #    # ####   
      # #   # # #          #   # #          # #####  ###### #####  #  #   
#     # #    #  #          #    #     #     # #      #    # #   #  #   #  
 #####   #### # #######     ###  #     #####  #      #    # #    # #    # 
-->

<!-- Polished -->
## SQL
- Structured Query Language used to query databases like MySQL for tabular data
- SQL databases are usually hosted on beefy systems, so doing processing in SQL can be a lot faster than doing it on a local machine using Python
### SQL Simple Records Query
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
### SQL Aggregation Query
- select col1, AVG(col2) as average from table group by col1 having average >= 100;
### SQL Subquery
- use employees;
- select concat(first_name, " ", last_name) as Name 
- from employees 
- where 
    * hire_date = (select hire_date from employees where emp_no = 101010) 
	* and
	* emp_no in (select emp_no from dept_emp where to_date > curdate());
### SQL Temp Table Creation
- use employees;
- create temporary table germain_1457.employees_with_departments as
- select first_name, last_name, departments.dept_name
- from employees
- join dept_emp using(emp_no)
- join departments using(dept_no);

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
- print('hi', end='\n\n')
- ['hi', 'lo'] + ['med'] --- 5 * ['hi', 'lo']
- for i, col in enumerate(cols) ----- this is the correct order
- string.count('a') ----- count number of 'a' in string
- (" ".join(['c','a','r'])).split(" ") ----- make 'c a r' then split back into ['c','a','r']
- ' 123 '.strip().isnumeric() ----- deletes left/right whitespace, new lines, and tabs; returns True
- [x if x % 2 == 0 else x - 1 for x in [1,2,3,4,5]] ----- returns [0,2,2,4,4]
- print(f"|{x:<8}|{y:<8}|{z:<8}|") ----- formatted output
- food_list.sort(key=lambda x: len(x) * -1) ----- sort food_list by descending string lengths
    * Use lambda to create one-time functions or short functions

<!-- Polished -->
## NumPy
- Arrays!
- Excellent library for *numerical* data, especially w/ 3+ dimensions, and generating pseudo numbers for testing
### NumPy Implementation
- np.absolute(np.array([1,-2,3,-4,5])) ----- absolute values for very basic array
- np.arange(1,10,0.5) ----- returns array([1, 1.5, 2, 2.5, ..., 9.5]), 1 to 10 in steps of 0.5
- np.linspace(0,10,5) ----- returns array([0, 2.5, 5, 7.5, 10]), 5 equidistant steps between 0 and 10
- (np.random.rand(5, 5) * 10).round() ----- 5x5 array of integers 0-10
- a[a >= 2] ----- return a one-dimensional array of only the values that return True for a >= 2
    * a >= 2 is value-wise evaluation (preserves the matrix), but a[a >= 2] returns all True only
- a[:,0] ----- return first column; a[0,:] ----- return first row; a[0:3,:] ----- as expected
- array1 + array2, array1 * array2, etc for matrix operations
    * Line up a row on a matrix, multiply overlapping values or divide; same as column
    * For a 5x5 matrix, can only use a 1x5, 5x1, or 5x5 for multiply/divide/add/subtract
    * Dot product requires matrix 1's column count and matrix 2's row count to be equal
- df['over_100'] = np.where(df.col > 100, 'me_true', 'me_false')
- np.set_printoptions(suppress=True) ----- suppress scientific notation

<!-- Polished -->
## Pandas
- Series and Dataframes!
- Excellent library for tabular data (2 dimensions), especially non-numerical data with labeled axes
### Pandas Series
- pd.Series([1,2,3], name='numbers', index=['a','b','c'], dtype='object')
- s[11] = 12; s.drop(11, inplace=True); s.fillna('no_value'); s.dropna(); 
- s.dtype, s.size, s.shape, s.describe(), s.head(), s.tail(), s.value_counts(), s.astype('int'), s.isin(list)
- s.max(), s.min(), s.idxmax(), s.idxmin()
- s.any(), s.all() ----- True if any, True if all; returns column-wise when df.any() or df.all()
- s.isna(), s.notna(), s.fillna(value), s.dropna()
    - s.isna().sum(), s.isna().mean()
- s.map({'hi':'greeting', 'hello':'greeting'})
- s.str[0:4], s.str.capitalize(), and more string methods applied to values in a series
- pd.cut(s, bins=[0,2,5], labels=['low','high'], right=False).value_counts().sort_index(ascending=False)
- s[s > 3]; s[s.index == 1] ----- masks
    * s[s < 0] = 0 ----- replace all negatives with zero
### Pandas Dataframes
- pd.read_excel, pd.read_csv, pd.read_clipboard
    * pd.read_csv(filename, index_col=0) ----- fixes Unnamed: 0
    * pd.read_csv('https://docs.google.com/spreadsheets/d/1Uhtml8KY19LILuZsrDtlsHHDC9wuDGUSe8LTEwvdI5g/edit#gid=341089357'.replace('/edit#gid=', '/export?format=csv&gid='), encoding='unicode_escape')
    * pd.read_csv('https://s3.amazonaws.com/irs-form-990/index_2011.csv', encoding='unicode_escape')
- pd.read_sql
    * def get_connection(db, user=user, host=host, password=password): url = f'protocol://[user[:password]@]hostname/database_name' (EX: url = mysql+pymysql://codeup:p@assw0rd@123.123.123.123/some_db)
    * pd.read_sql('SELECT * FROM employees LIMIT 10', url)
- pd.DataFrame({'hi':[1,2,3,4], 'lo':[6,7,8,9]})
- pd.DataFrame([['Mary','12-7-1999',23], ['Joe','12-7-1997',25]], columns=['name','bday','age']) - row-wise
- df.info(); df.describe().T; df.sort_values(by=['col1,'col2'], ascending=False)
- df = original_df.copy(); df['col'] = value_list; df.assign(col=series)
- df.rename(index = {0:'first', 1:'second'}, columns={'hi':'high'}, inplace=True)
- df.drop(index=[0,2]); df.drop(columns=['hi]); df.drop_duplicates()
- df[['hi','lo']], df['hi'], df[0:2]
    * df.columns = ['high','low']; df.index = ['lowest','med-low','med-high','highest']
- pd.concat([s,s,s,s], axis=1, ignore_index=True) ----- create dataframe from series quickly
- df[['newcol1', 'newcol2']] = df.col.str.split(':', expand = True) ----- split string column into two new cols
- pd.melt(df, id_vars='colname') ----- creates 'variable' and 'value' columns from columns not specified and their values
    * melt has multiple useful arguments to help make this better
- **Dictionary comprehension:** pd.Series({key:function(value) for value in value_list})
- pd.cut(series_name, bins=[0,5,100,100000])
    * Common to bin continuous values into ordinal/categorical to run boxplots per bin against another continuous value
- pd.qcut() ----- bins equal amounts of data
    * different from pd.cut(), which makes equal-width bins
- df.append({'col1':value, 'col2':value}, ignore_index=True) ----- add new row
- df.applymap(lambda x: x if x < 3 else 5) ----- element-wise apply, will fail if can't complete on any value
- df.apply(lambda x: x + 1, axis=1) ----- axis-wise apply, few use cases... just use s = s.apply(function)
- df.loc[5, 'hi'], df.iloc[5]
    * loc can specify a labeled index and column, or just an index
    * iloc only looks at index and ignores index labels (specify integers)
- df[df.hi == 3], df[df.index == 1], df[(df.index == 2) | (df.hi == 4)]
    * df[df.col < 0] = None ----- null out rows with a negative value in col
- df.pipe ----- send dataframe through multiple functions (sklearn?)
- df.groupby('col1')[['col2','col3']].agg(['mean','max'])
- df1.merge(df2, left_on='df1_col', right_on='df2_col', how='outer', indicator=True)
- pd.crosstab(df.col1, df.col2, margins=True, normalize=True) ----- margins are rowwise, colwise totals
- df.pivot_table(index='col1', columns='col2', values='col3') ----- where col1 and col2 meet, take all col3 values and average them (default behavior)
#### Pandas and Datetime
- pd.to_datetime(date, format='%b:%d:%Y'); pd.to_datetime(df.date, format='%b:%d:%Y')
    * pd.date_range('start_date', freq='D', periods=num_of_days) ----- create date range from scratch
- df.loc[date_start:date_end] ----- inclusive slicing of dataframe when datetime is index
- pd.Timedelta('14d') + pd.to_datetime('2017-11-07') ----- add 14 days to date as expected
    * df.date.max() - df.date ----- find amount of time between most recent date and all dates (time delta)
- df.date.dt.day ----- element-wise conversion of date to day number, can do with more
    * .month, .year, .quarter, .day_name() --- use .value_counts().sort_index()!
- df.col.strftime('%b %D, %Y')
- df.resample('W').sum() ----- "Downsampling", sum all values more precise than a week in esssentially a groupby
    * requires pandas datetime index
    * '3W' is every three weeks, can also do '3H', '3M', '3Y', etc
- df.asfreq('D') ----- "Upsampling", create row for each day from a less-precise interval (weekly -> daily)
    * by_day.assign(ffill=lambda df: df.coffee_consumption.ffill()) ----- fill null with previous value
    * by_day.assign(bfill=lambda df: df.coffee_consumption.bfill()) ----- fill null with next value
    * can also fillna() as you need, or use .loc, etc
- df.colname.diff() ----- difference between current element and previous one (subtract values)
    * can enter a number, .diff(3), to look at 3 elements ago
    * also enter negative values (-1) to look ahead
- df.colname.shift() ----- an array of colname but each value is shifted one index deeper (shift values)
    * with proper indexing, can shift() a value column for lagging and leading
    * shift(1), shift(30), shift(-90), etc
- df.index.tz, df.tz_localize('America/Chicago'), df.tz_localize(None) ----- timezones
- df.resample('W').sum().colname.plot() ----- quick line plot of a column for weekly sum





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

<!-- Needs work -->
## Overall Exploration Visualization Notes
- Plot distribution for data wrangling to check for outliers (histogram, box-whisker), then remove outliers if necessary, then plot new distributions
- A shotgun pattern in homoscedasticity check (pattern shows heteroscedasticity) isn't great, consider removing outliers or transforming... can take log of entire column (storing values in new column) then run log column through the model and visualization

<!-- Polished -->
## Matplotlib Pyplot
- The bread and butter of data visualizations in Python
- Highly customizable, but needs a lot of work to be presentable
- Push plots to scripts to make things easily repeatable
- Visual walkthrough of everything-Pyplot: https://www.python-graph-gallery.com/all-charts/
- Customization options: https://matplotlib.org/stable/tutorials/introductory/customizing.html
### Pyplot Basics
- import matplotlib.pyplot as plt
- plt.show() ----- print the plot that was created up to that point
    * JupyterNB doesn't need plt.show() most of the time but .py scripts always need it
    * Loop chart creation per column by using plt.show() inside the loop
- plt.hist(x) ----- plot histogram
    * Create multiple plots before plt.show() to layer charts in one visual
- df.plot.line() ----- put dataframe to a line plot
    * Quick bar plot: df.column.value_counts().plot.barh()
    * Customize: df.corr().style.background_gradient(vmin=-1, vmax=1, cmap='coolwarm_r').format('{:.3f}'.format)
- plt.subplot(325) ----- 3 rows, 2 columns (6 charts), place chart in 5th position (bottom left)
    * Index starts at 1 in top left, increases right, then next row below and rightward until complete
    * plt.title() titles each individual charts, plt.suptitle() gives a title wrapping all titles
    * plt.tight_layout() to make everything look a bit nicer usually
- plt.rc('figure', figsize=(13,6)) ----- set configuration for figsize
    * plt.rc('axes.spines', top=False, right=False), plt.rc('font', size=13) ----- set overall
    * Consider creating a dictionary to save configuration(s)
- plt.savefig('chart.png')
### Pyplot Charts
- Common chart parameters: c, ec, alpha, s, ls, bins, align, and more
- Histogram: plt.hist(x)
- Line plot: plt.plot(x)
- Solid under line: plt.fill_between(x, y)
- Bar chart: plt.bar(), plt.barh()
- Scatterplot: plt.scatter()
### Pyplot Customization
- Chart labels: plt.title, legend, xlabel, ylabel, xticks, yticks, xlim, ylim, tick_params
- Annotations: plt.annotate() or text()
- Fonts: https://www.python-graph-gallery.com/custom-fonts-in-matplotlib
- Grid: plt.grid(True, axis='both') ----- background grid
- Margins around subplots: plt.subplots_adjust(top=0.3)
- Styles: plt.style.use('style') ----- check styles with plt.style.available
### Pyplot Advanced
- LateX Notation: Wrap math in dollar signs like $a^2$
    * Character chart: https://www.caam.rice.edu/~heinken/latex/symbols.pdf
    * Matplotlib walkthrough: https://matplotlib.org/stable/tutorials/text/mathtext.html
- Can use tuple as first argument in ex: hist() to do side-by-side, EX: plt.hist((series1, series2), ...)
- Change sizes of subplots: plt.subplot2grid()
- Remove certain plots from subplots: ax.remove()

<!-- Needs work -->
## Seaborn
- An excellent advancement on the foundation of Matplotlib
- https://seaborn.pydata.org/generated/seaborn.set_style.html
- sns.set_style('darkgrid')
- sns.countplot() ----- categorical bins
    * histogram is numerical bins, should only really be used on continuous data
- sns.heatmap(df.corr(), cmap='coolwarm_r', vmin=-1, vmax=1, annot=True) ----- draw correlation heatmap with red negs blue pos
- ax.xaxis.set_major_formatter(lambda x, pos: '{:.1f} m'.format(x / 1_000_000)) ... ax.set(xlabel='x2 (millions)') ----- change sci notation to millions... kinda cool
- ax.xaxis.set_major_formatter('{:,.0f}'.format) ----- make x axis 100,000 ticks
- ax.yaxis.set_major_formatter('{:.0%}'.format) ----- make y axis percentage
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

## Exploration Prep
### Split Data
- sklearn does randomization/stratification for you!
    * Randomize entire dataset *before* splitting to remove potential bias (dataset potentially sorted)
    * Make sure all splits include all options (stratify target)
- Data prep parameters are calculated from *train*, this excludes unseen data, so don't calculate on whole dataset
- from sklearn.model_selection import train_test_split ----- splits data in two sets
- train_validate, test = train_test_split(df, test_size=0.2, random_state=123, stratify=df.colname)
- train, validate = train_test_split(train_validate, test_size=.25, random_state=123, stratify=train.survived)
### Null Imputation
- from sklearn.impute import SimpleImputer ----- fills values by inference
- imputer = SimpleImputer(strategy='most_frequent')
    * fill with: 0, average, median, subgroup mean, most frequent value, build model to predict missing values, etc
    * strategy='average' ----- fills with average
    * will need to modify dataframes with impute results
- train[['embark_town']] = imputer.fit_transform(train[['embark_town']])
- validate[['embark_town']] = imputer.transform(validate[['embark_town']])
- test[['embark_town']] = imputer.transform(test[['embark_town']])

## Univariate Visualization
### Univariate Stats
- Focus on the target itself
- sns.displot(x='colname', data=df) ----- quick distribution plot

## Bivariate Exploration
- Try out Maggie's explore.py or Pandas Profiling if you want a quick solution
- Split data into categorical vars and quantitative vars
    * cat_vars = ['var1', 'var2', 'var3', ...]
    * quant_vars = ['var42', 'var67', ...]
    * explore.explore_univariate(train_df, cat_vars, quant_vars) ----- builds visualization and statistics with columns var1, var2, var3, var42, var67, etc
### Bivariate Stats
- See how each feature relates to target
- Same setup as univariate but with target variable (column) specified
    * explore.explore_bivariate(train, target, cat_vars, quant_vars)
- sns.heatmap(df.corr(), cmap='Greens', annot=True, vmin=0, vmax=1) ----- quick correlation chart
    * If everything correlates mostly, then it's called "Multicolinearity"
- df.sample(5, random_state=123).style.highlight_max(axis=0) ----- highlight max values per column

## Multivariate Exploration
### Multivariate Stats
- Compare features in terms of target
- Adding the target as color in Seaborn
    * explore.explore_multivariate(train, target, cat_vars, quant_vars)

<!-- Needs work -->
## Feature Engineering
- Determine which features to keep
    * K Best and RFE
    * Drop features based on domain knowledge
    * Drop features that raise ethical issues
    * Drop features that are too 'loud'
    * Clean up remaining features
    * Do analysis on features
- Create features!!
### Examples
- train['newcol'] = pd.cut(train.colname, bins=[0,15,100], right=False, labels=[0,1])
    * will need to amend train/validate/test datasets with 'newcol' and also cat_vars or quant_vars
### Feature Engineering (Regression notes)
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
    * zscore = (value - pop_mean) / stdev_size --- zscore = stats.zscore(value_list)

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
- When data can't be separated into categories: **Goodness of Fit** (chisquare, anderson_ksamp)
    * Assumptions of Parametric: identical distribution, no value overlap, all cells have more than 5 values
    * Assumptions of Non-Parametric (K-Sample Anderson Darling): cell independence, all cells more than 5 values
    * *Used when you can't separate data into independent samples*
    * **Need to create both observed and expected crosstabs for test**
- Testing if categories have divergent outcomes: **Contingency** (chi2_contingency)
    * Assumptions: cell independence, all cells have more than 5 values
    * **Only need to create observed crosstab for test**
#### Comparison of Means: Independent samples' differences in average continuous value
- Discovery of difference in independent samples: **ANOVA** (f_oneway, kruskal)
    * Assumptions of Parametric (One-Way ANOVA): equal variance, normal distribution, and independence
    * Assumptions of Non-Parametric (Kruskal-Wallis): independence
- Full comparison of two independent samples: **2-Sample t-test** (ttest-ind, mannwhitneyu)
    * Assumptions for Parametric (Independent T-Test): equal variance, normal distribution, and independence
    * Assumptions for Non-Parametric (MannWhitneyU): independence
- Comparison between a sample and the total population: **1-Sample t-test** (ttest-1samp)
    * Assumptions: equal variance, normal distribution, and independence
    * *Used when you can't separate data into independent samples*
- Comparison of same data before and after a change: **Paired t-test** (ttest_rel, wilcoxon)
    * Assumptions for Parametric (Relative T-Test): same observations, normal distribution, independence
    * Assumptions for Non-Parametric (Wilcoxon Signed-Rank): equal variance and independence
#### Correlation: The movement of continuous values against one another
- Relationship between two continuous variables: **Linear correlation** (pearsonr, spearmanr)
    * Assumptions for Parametric (Pearson R): linear (not curved), normal distribution
    * Assumptions for Non-Parametric (Spearman R): monotonic (only increases or only decreases)
    * *pearsonr assesses linear relationship strength, spearmanr assesses monotonic relationship strength*
### Statistical Test Implementation
- Equal Variance assumption test: stats.levene(sample1.y, sample2.y)
- Chi Square Goodness of Fit: t, crit_vals, significance = stats.anderson_ksamp(array_1d)
- Chi Square Independence: chi2, p, degf, expected = stats.chi2_contingency(observed_crosstab)
    * Degree of Freedom (degf): (num_cols - 1) * (num_rows - 1)
- ANOVA: t, p = stats.f_oneway(samp1.y, samp2.y, samp3.y, samp4.y, ...) or stats.kruskal
- Two-Sample T-Test: t, p = stats.ttest_ind(samp1.y, samp2.y, alternative=) or stats.mannwhitneyu
- One-Sample T-Test: t, p = stats.ttest_1samp(samp.y, totalpop.y, alternative=)
- Paired T-Test: t, p = stats.ttest_rel(before_samp.y, after_samp.y, alternative=) or wilcoxon
- Correlation: corr, p = stats.pearsonr(x, y) or stats.spearmanr
    * Calculate corr itself: df.corr()

<!-- Polished -->
## Probability
- Chances and rates
- Probability of outcome: P(outcome)
- Probability of A given B (when B is True): P(A|B)
- Low-probability combination of observed values is an anomaly!
### Calculating Probability
- Bayes Theorem: P(A|B) = P(B|A)P(A)/P(B)
    * If you have either A or B and want to calculate B or A, use Bayes Theorem
- Observed Rate: df.col or df[['col1','col2']].value_counts(normalize=True)
    * Other calculations: (x == 3).mean() --- ((x == 3) or (x == 2)).mean() --- (x <= 4).mean()
- Theoretical Distribution: stats.recipe(params).rvs(rolls).method()
    * Can pass array (EX: (3,4)) instead of rolls to generate an array
    * Nice chart for which method to use: https://ds.codeup.com/stats/pdf_pmf_cdf_ppf_sf_isf.png
- Calculated Probability: np.random.choice(outcome_list, size=rolls, p=[p1, p2, p3, ...])
    * Can pass array instead of rolls: size=(simulations, trials) as in size=(rows, columns)
### Theoretical Distributions from Parameters
- Equal likelihood of all outcomes: Uniform (coin)
    * Not very useful for our purposes
    * Recipe: stats.randint(low, high_not_including)
    * P(A) = 1 / len(Options)
- Two outcomes: Binomial (success/failure)
    * Not very useful for our purposes
    * Recipe: stats.binom(n=rolls, p=[p_True, p_False])
    * P(A) = our input
- Normal - continuous random variable (bell curve)
    * Very useful if we expect a normal distribution for something
    * stats.norm(mean_value, stdev_size)
    * P(A) = recipe.pdf(A) ----- .pdf because of continuous values
- Poisson - events per time interval
    * Useful for time-related events
    * stats.poisson(lambda_value)
    * P(A) = recipe.pmf(A) ----- .pmf because of discrete values
- Lots more distributions... check scipy documentation for stats module
#### Methods for Theoretical Distributions
- Chance of specific outcome: **.pmf**(discrete_value), and **.pdf**(continuous_value)
- Proportion higher: **.sf**(number) = proportion_higher, opposite is **.isf**(proportion_higher) = number
- Proportion lower/equal: **.cdf**(number) = proportion_lowequal, opposite is **.ppf**(proportion_lowequal) = number






<!-- 
######                                                      
#     # #####  ###### #####  #  ####  ##### #  ####  #    # 
#     # #    # #      #    # # #    #   #   # #    # ##   # 
######  #    # #####  #    # # #        #   # #    # # #  # 
#       #####  #      #    # # #        #   # #    # #  # # 
#       #   #  #      #    # # #    #   #   # #    # #   ## 
#       #    # ###### #####  #  ####    #   #  ####  #    # 
-->

# Prediction

## Feature Preparation
<!-- Needs work -->
### Encoding
- Associate each unique value with a number (label encoding)
    * Use label encoding when categories have an inherit order
- One-hot encoding: 1 or 0 in new column if row is or isn't that value
    * Use one-hot when there's no order
- pd.get_dummies(df['col1', 'col2'], drop_first=[True, True]) ----- automagically does one-hot encoding for unique values in col1 and col2
    * creates a new column for each unique value in col1 and col2 with 0 or 1 representing False and True respectively, drops first new column for col1 and col2 (less dimensionality)
### Scaling
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
#### Scaling Methods
- Use sklearn.preprocessing MinMaxScaler, StandardScaler, RobustScaler
- "Normalization" (MinMaxScaler) is scaling into range 0 to 1
- StandardScaler centers the distribution's density on 0 and limits range
    * Use this guy for normal-ish distributions!
- RobustScaler also centers the distribution's density on 0 and limits range, but it de-weighs outliers as well
- QuantileTransformer attempts to normalize a distribution and center it on 0... be careful, make sure to check the visualization
    * If you really want your data to be normal then use this... it's fairly complex
#### Scaling Syntax
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
## Classification
- from sklearn.metrics import precision_score, accuracy_score, recall_score, classification_report ----- confusion matrix calc functions
    * df_report = pd.DataFrame(classification_report(df.actual_observed, df.model_guesses, labels=['colname', 'colname'], output_dict=True)).T ----- outputs nice df of metrics
### SMOTE
- Needed when classes are imbalanced for classification modeling
- Used specifically for train to help models fit, improves performance on predicting unseen data

## Regression

## Time-Series

<!-- Needs work -->
## Algorithmic Clustering
- centroids.plot.scatter(y='petal_length', x='sepal_length', c='black', marker='x', s=1000, ax=plt.gca(), label='centroid') ----- plot syntax for... stuff

## Natural Language Processing (NLP)

## Anomaly Detection

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

## Computer Vision

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