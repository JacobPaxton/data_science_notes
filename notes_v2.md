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
3.    [Systems Development Lifecycle ](#systems-development-lifecycle-(SDLC))
4.    [Datasets                      ](#datasets)

II.   [Algorithms                    ](#algorithms)
1.    [Algorithm Basics              ](#algorithms-basics)

III.  [Data Structures               ](#data-structures)
1.    [Data Structures Basics        ](#data-structures-basics)
2.    [Data Structures Examples      ](#data-structures-examples)

IV.   [git                           ](#git)
1.    [git Basics                    ](#git-basics)

V.    [Software                      ](#software)
1.    [Terminal                      ](#terminal)
2.    [Jupyter Notebook              ](#jupyter-notebook)
3.    [Excel & Google Sheets         ](#excel-&-google-sheets)
4.    [Power BI                      ](#power-bi)
5.    [Sequel Ace                    ](#sequel-ace)
6.    [Visual Studio Code            ](#vs-code)
7.    [Tableau Public                ](#tableau-public)

VI.   [Regular Expressions (REGEX)   ](#regular-expressions-(regex))
1.    [REGEX                         ](#regex)

VII.  [APIs & Scraping               ](#apis-&-scraping)
1.    [APIs                          ](#apis)
2.    [Web Scraping                  ](#web-scraping)

VIII. [SQL                           ](#sql)
1.    [SQL Basics                    ](#sql-basics)
2.    [SQL Intermediate              ](#sql-intermediate)

IX.   [Apache Spark                  ](#apache-spark)
1.    [Spark Wrangling               ](#spark-wrangling)
2.    [Spark MAchine Learning        ](#spark-machine-learning)

X.    [Python                        ](#python)
1.    [Python Basics                 ](#python-basics)
2.    [Python Specifics              ](#python-specifics)

XI.   [NumPy and Pandas              ](#numpy-pandas)
2.    [NumPy                         ](#numpy)
3.    [Pandas                        ](#pandas)

XII.  [Matplotlib & Seaborn          ](#matplotlib-&-seaborn)
1.    [Visualization in Python       ](#overall-notes-for-visualizations-in-python)
2.    [Matplotlib                    ](#matplotlib)
3.    [Seaborn                       ](#seaborn)

XIII. [Exploration                   ](#exploration)
1.    [Exploration Prep              ](#exploration-prep)
2.    [Exploration Visualization     ](#exploration-visualization)
3.    [Feature Engineering           ](#feature-engineering)
4.    [Feature Selection             ](#performance-based-feature-selection)

XIV.  [Algorithmic Clustering        ](#algorithmic-clustering)
1.    [Cluster Assignment            ](#cluster-assignment)
2.    [K-Means Clustering            ](#k-means-clustering)
3.    [Hierarchical Clustering       ](#hierarchical-clustering)
4.    [DBSCAN                        ](#dbscan)

XV.   [Statistics                    ](#statistics)
1.    [Metrics                       ](#metrics)
2.    [Hypothesis Testing            ](#hypothesis-testing)
3.    [Probability                   ](#probability)

XVI.  [Model Preparation             ](#model-preparation)
1.    [Encoding                      ](#encoding)
2.    [Scaling                       ](#scaling)
3.    [Resampling                    ](#resampling)

XVII. [Classification                ](#classification)
1.    [Classification Overview       ](#classification-overview)
2.    [Classification Example        ](#classification-example)

XVIII.[Regression                    ](#regression)
1.    [Regression Overview           ](#regression-overview)
2.    [Regression Example            ](#regression-example)

XIX.  [Time-Series                   ](#time-series)
1.    [Time-Series Overview          ](#time-series-overview)
2.    [Time-Series Example           ](#time-series-example)

XX.   [Natural Language Processing   ](#natural-language-processing-(NLP))
1.    [NLP Overview                  ](#nlp-overview)
2.    [NLP Example                   ](#nlp-example)

XXI.  [Anomaly Detection             ](#anomaly-detection)
1.    [Anomaly Detection Strategy    ](#anomaly-detection-strategy)
2.    [Anomaly Detection Syntax      ](#anomaly-detection-syntax)
3.    [Anomaly Detection Examples    ](#anomaly-detection-examples)

XXII. [Deep Learning                 ](#deep-learning)
1.    [Deep Learning Basics          ](#deep-learning-basics)

XXIII.[Computer Vision               ](#computer-vision)
1.    [Computer Vision Basics        ](#computer-vision-basics)

XXIV. [Cross-Validation              ](#cross-validation)
1.    [Cross-Validation Basics       ](#cross-validation-basics)

XXV.  [Deployment                    ](#deployment)
1.    [Docker                        ](#docker)
2.    [Flask                         ](#flask)
3.    [Apache Kafka                  ](#apache-kafka)

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

## Systems Development Lifecycle (SDLC)
- Framework for delivering software
- Waterfall: takes it one step at a time, fully-complete each step then move on
    * All requirements defined ahead of time; inflexible for later requirements or issues, and may be restarted
- AGILE: quickly builds from scratch to small, doing the full "spiral", then repeats from small to big, big to bigger, and onward
    * Flexible for requirement changes or issues; but who knows when to call things "finished"
### Steps of SDLC
- Analysis: choosing which requirements to build for
    * Software requirements specification (SRS) used to define all finalized requirements (includes UML diagrams)
- Design: choosing the solutions to solve those requirements
- Implementation: building the chosen solutions
- Testing: ensuring the built solutions are functional and solve the requirements
### Universal Modeling Language (UML) Diagrams
- Often used in the SDLC
    * Analysis: Use case diagram, ex: user choices, choice results
    * Design: Class diagram, ex: classes and their initialized variables (with types!), inheritance arrows, "unfilled diamond"
    * Implementation: Activity diagram, a flowchart displaying the logic of the program plus code language
    * Testing: Sequence diagram, ex: client-server communication sequence
- Each diagram is not only prescribable to a single element of SDLC; they overlap somewhat
    * EX: can use the Use case diagram for multiple... but, you should use multiple/different diagrams

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
   #                                                             
  # #   #       ####   ####  #####  # ##### #    # #    #  ####  
 #   #  #      #    # #    # #    # #   #   #    # ##  ## #      
#     # #      #      #    # #    # #   #   ###### # ## #  ####  
####### #      #  ### #    # #####  #   #   #    # #    #      # 
#     # #      #    # #    # #   #  #   #   #    # #    # #    # 
#     # ######  ####   ####  #    # #   #   #    # #    #  ####  
-->

# Algorithms

## Algorithms Basics
- Efficient computation; decreased "computational complexity" (runtime + memory)
    * See also: space complexity (memory amount used), auxiliary space complexity (not including "n" datapoints)
- Simple changes to slow code can speed it up immensely
- Heuristic algorithms don't perfectly solve problems but are FAST (good enough solution, but much faster than great/perfect)
    * EX: knapsack problem, add the highest-value item that can fit until no more items can be added (good, not perfect)
- Knowing algorithms + use cases, and cases where algorithms don't work ("NP-complete"), is key to efficient code
### Example Algorithms
- Linear search: go element by element to check for a match
- Binary search: when data is ordered, split in half and check left/right of split, then choose and split again
- Bucket sort: using simpler operations to sort, then doing multiple complex-sort operations
    * EX: Sorting words, sort first on starting letter (a, b, c, ...) into buckets, then sort all of a, then all of b, ...
- Longest common substring
- Dijkstra's shortest path
### NP-Complete (lacking algorithms)
- Cliques: Detecting when n points are interconnected from a graph of points

[[Return to Top]](#table-of-contents)







<!-- 
######                          #####                                                               
#     #   ##   #####   ##      #     # ##### #####  #    #  ####  ##### #    # #####  ######  ####  
#     #  #  #    #    #  #     #         #   #    # #    # #    #   #   #    # #    # #      #      
#     # #    #   #   #    #     #####    #   #    # #    # #        #   #    # #    # #####   ####  
#     # ######   #   ######          #   #   #####  #    # #        #   #    # #####  #           # 
#     # #    #   #   #    #    #     #   #   #   #  #    # #    #   #   #    # #   #  #      #    # 
######  #    #   #   #    #     #####    #   #    #  ####   ####    #    ####  #    # ######  ####  
-->

# Data Structures

## Data Structures Basics
### Hash Table
- Hash something into an array's index, store that something at that index
- Hashing strategy is your choice; goal is to simplify lookups
    * EX: if you're looking up names, why not hash first letter like: a->0, b->1, c->2, d->3, ...
    * EX: if you're looking up values, why not hash first number like: 0->0, 1->1, 2->2, 3->3, ...
- Linked lists are attached to each index to handle multi-attribution
    * EX: name lookup, multiple names start with a; a->0, so append the (name, info) tuple onto the list at array[0]
    * Result is ex: `array[0] = [("aaron", "tall"), ("abigail", "short")]` --- `array[1] = [("bobby", "short")]` --- ...
- Lookups are much faster this way; hash the value you want to look up, then search in the short list for the info you want
    * EX: name lookup for `"abigail"`: hash the name via `hash("abigail") -> 0` --- go to 0 via `array[0]` --- find `"abigail"` there
    * Hash strategy should consider the length of the overall array and the length of each linked list; neither should be too long
    * The "short lists" in the array can be linked lists for easier append/sort operations
### Linked List
- A list that doesn't have the structure of a typical array; instead, one item links to the next
    * This structure doesn't exist in native Python but of course can be manually created (using classes; create class of each head)
    * Involves a **head** (data/next combo), the **data**, and the loc of the **next** item (and sometimes the previous item...)
    * A bit complicated to delete...
- Excellent at handling problemsets involving sorting long arrays
    * Just update the values of "next" for the head being moved and the head before it... done.
    * Typical arrays involve placing the value being moved and shifting every value after it, which is inefficient
- Can be simple linked (just has "next" in head), doubly linked ("next" and "previous"), and/or circular (last item links "next" to first)

## Data Structures Examples
### Hash Table - Linked Lists
- 

[[Return to Top]](#table-of-contents)







<!-- 
 ####  ##### ##### 
#    #   #     #   
#        #     #   
#  ###   #     #   
#    #   #     #   
 ####  #####   #   
-->

# git

<!-- Polished -->
## git Basics
- Excellent version control for files
- Get your git set up: 
    1. Install Git on your computer: https://git-scm.com/downloads
    2. Create Github account
    3. Set your Github credentials on your computer
        - In your Terminal or Command Prompt, run command: `git config --global user.name "github_username"`
        - In your Terminal or Command Prompt, run command: `git config --global user.email "email_used_for_github_account"`
    4. Generate an SSH key for connecting with Github
        - In your Terminal or Command Prompt, run command: `ssh-keygen -t rsa -b 4096 -C "email_used_for_github_account"`
        - Hit ENTER on keyboard when it asks where to save the key (ENTER uses default save location)
    5. Add your SSH key to Github here: https://github.com/settings/ssh/new
        - MacOS: Terminal or Windows: Git BASH, can simply run this command: `cat ~/.ssh/id_rsa.pub | pbcopy`
        - Paste that into the link and give it a title, whatever you want for title is fine
    6. Click "Add SSH Key", done
    7. Check if it's working: 
        - Create new repository on Github
        - Click "Code" button dropdown
        - Click SSH
        - Copy that text
        - Open Terminal or Git BASH or CMD or whatever you use
        - Enter `git clone that_text_you_just_copied`
            - EX: `git clone git@github.com:JacobPaxton/data_science_notes.git`
            - Can also do HTTPS clone: `git clone https://github.com/JacobPaxton/data_science_notes.git`
        - If it clones, great- it worked
        - Add a random new file to the folder it created
        - In Terminal or Git BASH or CMD or whatever, type `git add .` then `git commit -m 'my first commit'` then `git push`
        - If the above line works, you are 100% ready to go
- Protect your passwords and other secrets: `code .gitignore` -> add files as single lines for git to ignore, so they don't get pushed
    - Commit and push your .gitignore to your Github repository to start ignoring your secrets
- Always start with creating a new Github repo, not a local one. Starting locally is annoying, gotta do several more steps
- Access and modify your `git config` file (called .gitconfig): Navigate to home directory (`cd ~`) then type `code .gitconfig`
### git for Solo Dev Work
- No one's committing/pushing except you, so pushes are safe
- Create an empty repository on Git then clone it down with `git clone`
- Make changes to files as you need
- Check files that are different from most recent commit: `git status`
- Add files to be committed: `git add file1` or multiple at once `git add file2 file3 file4 foldername/file5` or all files `git add .`
    - Remove file from being added: `git restore --staged file1`
- Check files have been added: `git status`
- Commit file changes with a message: `git commit -m 'message goes here to state changes'`
    - Always use a commit message and keep the commit message useful, it's extremely helpful
- Check that the commit went through: `git status` (should no longer see the files you added and committed in status)
- Push the commit to Github: `git push`
### git for Team Dev Work
- Team dev work is much more convoluted than solo dev work
- Update your local files for changes made to the team repo using `git pull`
    - This command updates files you're not working with, and does not update files you're working with
    - Run this command often, and especially before committing your work
- Create a new branch for your changes: `git branch -c new_branch_name`
- Move to that branch: `git checkout new_branch_name`
    - This command copies your current branch and work to the new branch, and moves you there
- Run normal Add and Commit in the new branch like normal (`git add file1 file2 file42` `git commit -m 'add cool new feature'`)
- Push to the new branch: `git push origin new_branch_name:new_branch_name`
    - This command creates a new branch on Github called "new_branch_name" 
    - It maps the local branch to the Github branch like this: `git push origin name_of_local_branch_to_send_up:name_of_GitHub_branch_to_receive`
    - Creating a new branch is always very safe because it does not overwrite any work, it's separate
- For the new branch, create a merge request (do this on Github)
## Resolving Merge Conflicts
- If you make a mistake and have a "merge conflict", this is how to resolve the issue (my method):
1. Pull the Github repo down to a new folder using `git clone`
2. Copy the changed files manually to the new folder's repo that you just created and cloned
3. Run your Terminal/BASH/CMD in that new folder and do the `git add filename` `git commit -m "message"` `git push` as normal
4. Delete the old folder after successfully pushing your work
5. Move the new folder to where the old folder was- good as new!!

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
    * Need to have your PATH set up for this and have the software installed
- Multi-line cursor: Hold command, clickdrag

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
- Basic cell-to-cell operations: `=B2-B3` (subtraction)
- Multi-cell operations: Sum `=SUM(num_cells1, num_cells2)`, Average `=AVERAGE(num_cells1, num_cells2)`, Count `=COUNT(cells)`
    * `=COUNTIF(cells_to_check, condition_for_each_cell_to_satisfy_to_be_counted)`, `=SUMIF(cells, if_here_is_true_for_cell_then_sum)`
- Remainders: `=MOD(numeric_cells, number)`
- Raise cells by power: `=POWER(numeric_cells, number)`
- Round up to int: `=CEILING(numeric_cells)`, round down to int: `=FLOOR(numeric_cells)`
- Combine cells into one cell: `=CONCATENATE(cells, cells, " ", cells, " ", ...)`
- Split cell into many cells using delimiter: `=SPLIT(cells, delimiter)`, delimiter of "mn" allows split on all of any "m" or "n"
- Count number of characters in cell: `=LEN(cells)`
- Replace by index and steps: `=REPLACE(text, position, length, new_text)`
- Replace by matching: `=SUBSTITUTE(text_to_search, search_for, replace_with, [occurrence_number])`
- Return substring: from left `=LEFT(cells, num_of_chars)`, `=MID(cells, start_index, steps_to_read))`, from right `=RIGHT(cells, num_of_chars)`
- Capitalization: `=UPPER(cells)`, `=LOWER(cells)`, `=PROPER(cells)`
- Time and date request: `=NOW()`, `=TODAY()`, `=TIME(hour_cell, minute_cell, second_cell)`, `=DATEDIF(start_cells, end_cells, step)`
    * Convert time and date: `=YEAR(cells)`, `=MONTH(cells)`, `DAY(cells)`, `=HOUR(cells)`, `=MINUTE(cells)`, `=SECOND(cells)`
- Search cells: `=VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE)`
    * Vertically searches range_to_search for key, if it finds it, returns col_to_return, if it's not exact match, ignores it (due to FALSE)
    * VLOOKUP looks at first column specified... be careful
- Conditional returns: `=IF(AND(cond1, OR(cond2, cond3)), truth_value, false_value)`
    * *Conditions can come from cells*
- Return if error in cell: `=IFERROR(value, truth_value)`
- Find the index of a cell with matching contents: `=INDEX(range, MATCH(string_to_match, range))`
- Line inside cell: `=SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc})`
    * Creates a red in-cell bar chart of data from range with maxed bar when reaching max value of range

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
- Randomly search for match: `re.search(regexg, subject)`
- Search from beginning for match: `re.match(regexp, subject)`
- Put all matches in list (very useful): `re.findall(regexp, subject)`
- Return match with subbed-in substring: `re.sub(regexp, sub_in, subject)`
- Capture groups into dataframe columns: `df.colname.str.extract(regexp)`
#### REGEX Query Options
- Search while ignoring case: `re.IGNORECASE`
- Run new query on each line: `re.MULTILINE`
- Ignore whitespace: `re.VERBOSE`
- Use `|` to add multiple flags, ex: `re.findall(regexp, subject, re.IGNORECASE | re.MULTILINE)`
### REGEX examples
- `r'a'` ----- r marks string as a raw string, all characters taken as-is
    - Can go without raw strings, just need to "except" characters, ex: `r'yes/no'` is `'yes\/no`, `r'hi...'` is `'hi\.\.\.'`
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
    *   ```
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
 #####   #####  #       
#     # #     # #       
#       #     # #       
 #####  #     # #       
      # #   # # #       
#     # #    #  #       
 #####   #### # ####### 
-->

# SQL

<!-- Polished -->
## SQL Basics
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

## SQL Intermediate
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

[[Return to Top]](#table-of-contents)






<!-- 
 #####                              
#     # #####    ##   #####  #    # 
#       #    #  #  #  #    # #   #  
 #####  #    # #    # #    # ####   
      # #####  ###### #####  #  #   
#     # #      #    # #   #  #   #  
 #####  #      #    # #    # #    # 
-->

# Apache Spark

## Spark Wrangling
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
### Spark Commands
- Check Spark's intentions before query: `df.explain()`
    * Used mainly to diagnose performance issues; orders operations from bottom-upward
- Switch to SQL: `df.createOrReplaceTempView('df')` --- `spark.sql(''' SELECT * FROM df ''')`
- Build schema: `schema = StructType([StructField("col", StringType()), StructField("col", StringType()),])`
### Spark Wrangling Example
```
# SETUP
import pyspark
from pyspark.sql.functions import *
spark = pyspark.sql.SparkSession.builder.getOrCreate()
# INGEST
df = spark.read.csv('filepath', header=True, schema=schema_struct)
# JOIN DF
df = df.join(df2, "joiner_col", "left").drop(df.joiner_col).drop(df2.joiner_col)
# PRINT NULL COUNTS
df.select([count(when(isnan(c) | col(c).isNull(), c)).alias(c) for c in df.columns]).show(vertical=True)
# FILL, DROP NULLS
df = df.na.fill(0, subset=['x', 'y']).na.drop()
# CHECK DTYPES
df.printSchema()
# DTYPE, NAME CHANGES
df = df.withColumn('ordinals', df.x.cast('string')).withColumnRenamed("colname_before", "colname_after")
# TO DATETIME, TO MONTH
df = df.withColumn("col1", month(to_timestamp("col1", "M/d/yy H:mm")))
# DATEDIFF
df = df.withColumn("date_calc_col", datediff(current_timestamp(), "datecol"))
# REGEX
df = df.withColumn('repl', regexp_replace(df.x, re, repl).withColumn('substr', regexp_extract(df.col, re, g)))
# STRING WHITESPACE, FORMATTING
df = df.withColumn("c1", trim(lower(df.c1))).withColumn("c1", format_string("%03d", col("c1").cast("int")),)
# STRING CONCAT
df = df.withColumn('c2', concat(lit('x:', df.x)))
# ADD X + Y AS COLUMN 'Z' TWO DIFFERENT WAYS
df = df.select(*, expr(df.x + df.y).alias('z')).selectExpr('*', 'x + y as z') 
# WHEN
df = df.withColumn('ten', when(df.x > 10, 'over 10').otherwise('not over 10'))
# WHERE, OR + AND
df = df.where((df.x > 5) | (df.y < 5)).where(df.z ==7)
# SMALL SAMPLE
df = df.sample(fraction=0.01, seed=42)
# SPLIT
train, validate, test = df.randomSplit([0.6, 0.2, 0.2], seed=42)
# RUN ALL, SAVE LOCALLY
df.write.json("df_json", mode="overwrite")
train.write.format("csv").mode("overwrite").option("header", "true").save("train_csv")
validate.write.format("csv").mode("overwrite").option("header", "true").save("validate_csv")
test.write.format("csv").mode("overwrite").option("header", "true").save("test_csv")
```
### Spark Aggregation Example
```
# COLUMN CALCULATION
x_y = df.select(sum(df.x)), df.select(mean(df.x))
# VALUE COUNT TWO COLUMNS, WITH PROPORTIONS COLUMN
value_counts = df.groupBy('col', 'target').count().sort('count', ascending=False)\
    .withColumn('proportion', round(col('count') / df.count(), 2))
# AGG GROUPBY
mean_min = df.groupBy('gb').agg(mean(df.x), min(df.y))
# CROSSTAB
crosstab = df.crosstab('g1', 'g2')
# PIVOT TABLE
mean_x_given_g1_g2 = df.groupBy('g1').pivot('g2').agg(mean('x'))
```

## Spark Machine Learning
- PySpark's 'ml' library handles most non-wrangling data science tasks
    * `from pyspark.ml.stat import ...` for chi square and correlation tests
    * `from pyspark.ml.feature import ...` for imputation, encoding, scaling, vectorization, and more
    * `from pyspark.ml.classification import ...`, `ml.regression`, `ml.clustering` for modeling
    * `from pyspark.ml.tuning import ...` for cross-validation
    * `from pyspark.ml.evaluation import ...` for classification, regression, and clustering evaluation
- Many functions in this library are experimental, use with caution
### Spark Machine Learning Example
```
```

[[Return to Top]](#table-of-contents)






<!-- 
######                                   
#     # #   # ##### #    #  ####  #    # 
#     #  # #    #   #    # #    # ##   # 
######    #     #   ###### #    # # #  # 
#         #     #   #    # #    # #  # # 
#         #     #   #    # #    # #   ## 
#         #     #   #    #  ####  #    # 
 -->

# Python

<!-- Polished -->
## Python Basics
- Interpreted programming language (interpreter reads code one line at a time and performs computer actions)
- Typically one statement per line; though you can span multiple lines with parentheses surrounding a statement
- *Indentation is used for code blocks*; though you can run the following statement (and similar) just fine: `if True: print("It's true!!")`
- Excellent language for its community support and massive amount of libraries
- Python's ongoing improvements and Python style guides: https://peps.python.org/pep-0000/
### Python Variables
- Python only makes objects; these contain the value, type, and identity (memory location) for the object's contents
    * value: `print(x)`, type: `print(type(x))`, identity: `print(id(x))`; note that `x` can be a value itself, too (ex: `type(1))`
    * Each object is indexed at the variable... object at index `x` contains that variable's value, type, and identity
- Python creates and dumps objects as needed; when `i = 1` is done, object's value=1, type=int, and identity=i
    * Assigning j to i points j at the i object but with j identity; any further assignment unlinks these
- Python objects that contain numbers or strings are immutable, as in, a new object is created for the change and old is dumped
- Python objects that contain lists or dicts are mutable, as in, the object itself is modified (no creation/dump for changes)
### Python Errors
- SyntaxError and IndentationError are reported before *any* code runs; the rest is reported during runtime
- SyntaxError: "illegal" code, ex: `print("hi") print("there!") print("all on one line?...")`
- IndentationError: didn't indent properly, ex: not indenting a `for` loop
- ValueError: can't perform operation on that data type, ex: `int("hi")`
- TypeError: similar to value error, ex: `"abc" + 42`
- NameError: didn't initialize a variable before its use, ex: `print(greeting)`
- Logic error: the code ran, but the output is wrong, ex: `42 * 1` when you meant `42 * 10` (this is also called a bug)
### Python Libraries
- Python Standard Library: https://docs.python.org/3/library/
- Standard libraries come with Python itself and require no additional installation
- To install libraries not in the standard library, you can use pip, which comes with Python installation
    * From command line (not python IDE or ipython): `pip install package_name_here` aka `pip install pandas` or `pip install numpy`

## Python Specifics
- Output with no return: `print("Hello world!")` - `print(x)` - `print(x * 3)`, `print("Hello!", end="\n\n\n\n\n")`
    * Can print on same line using multiple print statements by changing `end`, ex: `print("Hello", end=" ")` -> `print("World!")`
- Assignment: `x = 123` - `x = x + 1` - `x += 1` - `x *= 5` - `x /= 5` - `x //= 3` - `x -= 1`
- Non-assignment: `x + 15` - `x * 3` - `x / 100` - `x // 2` - `x - 1.872`
- Evaluation: `x == "Hello!"` - `x >= 5` - `x < 10` - `1 in [3,2,1,"Go!"]` - `x * 3 == 22`
    * if/else: `if True: print("yup")` - `if False: print("never gonna see this")` --- `if x > 5: print("hi")` -> `else: print("yo")`
    * while: `while True: print("forever repeating!")` - `while x > 5: print("forever repeating until x not greater than 5!")`
- For-loop: `for x in [1,2,3,4,5]: print(x)` --- `for i, col in enumerate(columns)` (i starts at 0 and increments +1 each loop iteration)
    * Immediately skip to next iteration of the loop with `continue` --- Immediately end the loop with `break`
### Variables: String, Integer, Float, List, Dict
- **String** as you'd expect: `x = "Hello"` -- `x + " " + "world!"` -- `f"{x} world!"` -- `"-"*50` (fifty dashes)
    * Check out: `"e" in "Hello"` -- `"Hello".count('l')` -- `"Hello".split('e')` -- `"\n cool text\n  ".strip()` -- `"123".isnumeric()`
    * Also check: `"5 is %20d" % 5` -- `"pi is %0.2f" % 3.14159265358` -- `f"|{123:<8}|{1:<8}|"`
- **Integer** as you'd expect: `x = 1`; `x * 3`; `x / 2` (returns 0.5); `x // 2` (returns 0); `x + 3.1` (returns 4.1)
- **Float** as you'd expect: `x = 2.5`; `x * 2` (returns 5.0); `x / 2` (returns 1.25); `x // 2` (returns 1.0)
- **List** as you'd expect: `x = [6,8,2]`; `x + [3]` (returns [6,8,2,3]); `x * 2` (returns [6,8,2,6,8,2]); `x[1]` (returns 8)
    * Check out: `6 in x` - `x[1:]` - `x[:2]` - `x[1:29]` - `" ".join(["Hello","World!"])` - `"".join(["a","b","c","d"])`
    * Also check: `x.append(29)` - `x.extend([40,41,42])` - `52 + x.pop(0)` - `x[0] = 101` - `x.sort()` (this row causes permanent changes)
        * Specify sort method: `food_list.sort(key=lambda x: len(x) * -1)` ----- sort food_list by descending string lengths
    * Also check: `[d for d in x]` - `[d for d in x if d > 3]` (returns [6,8]) - `[d * 21 for d in x if d < 8]` (returns [126,42])
        * These are list comprehensions; they can do element-wise changes and even filter using if/else
        * Can get fairly complicated if you want, ex: `[x if x % 2 == 0 else x - 1 for x in [1,2,3,4,5]]` (returns `[0,2,2,4,4]`)
- **Dict** as you'd expect: `x = {'i':1, 'cats':["Luna", "Milo"]}` --- `x["dogs"] = ["Spot"]` -> `x["dogs"][0]` (returns "Spot")
    * Check out: `x.keys()` - `x.values()` - `"cats" in x.keys()` - `for key in x.keys(): print(x[key])`
    * Also check: `x["dogs"].append("Max")` (permanently modifies x["dogs"]) - `{"a":{"b":{"c":{"d":1}}}}["a"]["b"]["c"]["d"]`
- Convert to other type: `x = int(x)`, `x = float(x)`, `x = str(x)`, `x = dict(x)`, `x = list(x)`, ...
### Variable: Class
- Initialized with `class ClassName` or `class ClassName(param1, param2, ...)` --- start with capital letter typically for it
- A class's methods are initialized with `def method_name(self, param1, param2, ...)`
    * Use `def __init__(self, param1, param2, ...)` to store code that will run on class creation
    * Code should go into `__init__` or into other methods... don't leave code exposed inside a function
- An object is created via `cool_object1 = ClassName()` or `cool_object1 = ClassName(param1, param2, ...)`
- A created object's methods are called via `cool_object1.method_name()` or `cool_object1.method_name(param1, param2, ...)`
    * You do not need to assign the output of called methods to anything; methods will update the class
    * EX: `def method1(self, name): self.cool_name = name` -> `cool_object1.method1("Tim")` -> `cool_object1.cool_name` returns "Tim"
### Functions
- Biggest usage is repeatability / store-away code in other files, ex: util.py, called via `import filename` aka `import util`
    * Directory traversal to import your function files: `from scripts/custom import util`, `from .. import cool_util`
- Generally structured like this: `def function_name(param1, param2):` with an indented code block immediately following it
    * Called in code after definition like this: `function_name(24, "hello", [1,2,3,4,5])`
    * Can create empty functions by typing `pass` in the function's code block
- Can also be created on the fly and stored to variables with `lambda`
    * EX: `func = lambda param1, param2: param1 + param2` -> `func(2, 2)`
    * Mainly used for short/temporary functions like this example that don't really require function definition somewhere
### Oddities
- Run code from string: `exec(string_containing_code)` --- `exec(module_name + "." + function_name + "(" + param_input + ")")`
    * Can't assign output of `exec` to a variable; must assign inside the `exec()` call

[[Return to Top]](#table-of-contents)






<!-- 
#     #               ######                    ######                                     
##    # #    # #    # #     # #   #             #     #   ##   #    # #####    ##    ####  
# #   # #    # ##  ## #     #  # #              #     #  #  #  ##   # #    #  #  #  #      
#  #  # #    # # ## # ######    #      #####    ######  #    # # #  # #    # #    #  ####  
#   # # #    # #    # #         #               #       ###### #  # # #    # ######      # 
#    ## #    # #    # #         #               #       #    # #   ## #    # #    # #    # 
#     #  ####  #    # #         #               #       #    # #    # #####  #    #  ####  
 -->

# NumPy Pandas

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
- `s.sum()`, `s.mean()`, `s.std()`
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
    * Show all columns: `pd.set_option('display.max_columns', None)`
    * Set value precision: `pd.options.display.float_format = '{:.5f}'.format`
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
######                                        ##       ######                       
#     # #       ####  ##### #      #   #     #  #      #     #   ##    ####  #    # 
#     # #      #    #   #   #       # #       ##       #     #  #  #  #      #    # 
######  #      #    #   #   #        #       ###       #     # #    #  ####  ###### 
#       #      #    #   #   #        #      #   # #    #     # ######      # #    # 
#       #      #    #   #   #        #      #    #     #     # #    # #    # #    # 
#       ######  ####    #   ######   #       ###  #    ######  #    #  ####  #    # 
-->

# Plotly & Dash

<!-- Polished -->
## Plotly Express
- Very fast creation of interactive visualizations
- Great for data exploration with hover-tooltips, best used with drop-in scripts
- `import plotly.express as px`
### Plotly Examples
```
df = px.data.iris()

# scatterplot (2 numerical features) & category-based trendlines ("color" parameter), with violinplots on sides
fig = px.scatter(df, x="sepal_width", y="sepal_length", color="species", 
                 marginal_y="violin", marginal_x="box", 
                 trendline="ols", 
                 template="none")
fig.show()

# very cool plot... hard to explain... put in lots of numerical features... keep observation count small... go!
fig = px.parallel_coordinates(df, color="species_id", 
                              labels={"species_id": "Species", 
                                      "sepal_width": "Sepal Width", "sepal_length": "Sepal Length", 
                                      "petal_width": "Petal Width", "petal_length": "Petal Length"
                                     },
                              color_continuous_scale=px.colors.diverging.Tealrose, 
                              color_continuous_midpoint=2)
fig.show()

# clean box plots
df = px.data.tips()
fig = px.box(df, x="day", y="total_bill", color="smoker", notched=True)
fig.show()

# fast plot to geographical map, sized/colored circles
df = px.data.carshare()
fig = px.scatter_mapbox(df, lat="centroid_lat", lon="centroid_lon", color="peak_hour", size="car_hours",
                        color_continuous_scale=px.colors.cyclical.IceFire, 
                        size_max=15, zoom=10,
                        mapbox_style="carto-positron")
fig.show()

# 3-D scatterplot
df = px.data.election()
fig = px.scatter_3d(df, 
                    x="Joly", y="Coderre", z="Bergeron", 
                    color="winner", size="total", hover_name="district", symbol="result", 
                    color_discrete_map = {"Joly": "blue", "Bergeron": "green", "Coderre":"red"})
fig.show()
```

<!-- Polished -->
## Dash
- 

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
dbsc = DBSCAN(eps=.1, min_samples=20).fit(scaled_df) # eps: radius; min_samples: minimum num in radius to not be called outlier
clustered_df = dbsc.transform(scaled_df)
clustered_df.labels                                  # show cluster numbers (outliers are "-1")
clustered_df[clustered_df.labels == cluster_num]     # show values in a specific cluster
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
### Correlation
- The measure for linear relation between two variables; as one variable moves, does the other variable follow?
- 2^n correlates almost perfectly with 3^n because of **similar rate** and **monotonic increase**
- 2^n correlates very strongly with 2n - 1 and 0.5n because of **monotonic increase**
- 2^n correlates very strongly with -1n + 9 because of **monotonic decrease**
- 2^n does not correlate well with [1,2,1,2,1,2,1,2] because it is polytonic

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

<!-- Polished -->
## Encoding
- Turning categorical features into a model-readable format
- Two types: **Label encoding** (ordinal categories) and **One-hot encoding** (True/False column for each category)
### Encoding Examples
```
# label encoding
df.col.map({'lowest':0, 'low-middle':1, 'middle':2, 'middle-high':3, 'highest':4})
# one-hot encoding
pd.get_dummies(df['col1', 'col2'], drop_first=[True, True]) # returns encoded columns w first category dropped
```

<!-- Polished -->
## Scaling
- Making 1-10 mean the same to a machine learning model as 1-1000
- Specifically, it equalizes the density of continuous features for machine learning
    * Normalizes Euclidian Distance calculations: `d = sqrt((x1 - x2)^2 + (y1 - y2)^2)`
- Always use for KNN and K-Means (distance-based), no need for decision tree and random forest
- Split data before scaling, and only scale on train
- Scale often... and when you scale, scale *everything* going into the model.
### Scaling Methods
- MinMaxScaler: General use, compresses all values between 0 and 1
    * Sensitive to outliers
- StandardScaler: Used when data distribution is normal, centers on 0 and limits range
- RobustScaler: Same as StandardScaler but de-weighs outliers
- QuantileTransformer: Normalizes data that is not normally-distributed, centers on 0 and limits range
    * If you really want your data to be normal then use this... it's fairly complex
### Scaling Syntax
```
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler().fit(X_train[['col1','col2','col3']])
X_train_scaled = scaler.transform(X_train[['col1','col2','col3']])
```

<!-- Polished -->
## Resampling
- Generating or deleting rows to help train models
- Required for classification when target is largely imbalanced (EX: Anomaly detection)
- Oversampling the minority class: Synthetic Minority Oversampling Technique (SMOTE)
- Undersampling the majority class: TomekLinks
### Resampling Example
```
from imblearn.combine import SMOTETomek
smt = SMOTETomek(random_state=42)
X_train_res, y_train_res = smt.fit_resample(X_train, y_train)
```


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

<!-- Polished -->
## Classification Overview
- Predicting a discrete target
- **Features that have strong relationship with target are the best predictors**
### Classification Strategy
0. Prepare data; if there's decision ambiguity (ex: imputation), leave it for exploration (drop the column(s) for MVP, revisit)
1. Continuous/Ordinal features: Convert to categorical- bin continuous data into categories using visualizations or intervals
    * Best-case scenario: a scatterplot of x feature with y target shows distinct groupings; use those groups
    * Reason for this is simple: Categorical target can only really be statistically evaluated using Chi2 tests (category v category)
2. Categorical/Discrete features: Create crosstab for each feature's categories against the target categories for Chi Square tests
    * Visualize crosstabs using conditional formatting (heatmaps) or mosaic plots
3. After step #2 and #3: Eliminate features that do not have dependent relationship with target
4. Visualize all dependent features (the ones that remain after tests) using crosstab conditional formatting or mosaic plots
5. Select the main evaluation metric (Accuracy, Recall, Precision, F1 Score, etc)
6. One-hot-encode all features (because they are categorical)
7. Create, fit multiple models on model-training data
8. Evaluate baseline mode class and models on selected evaluation metric for train and validate splits
9. Tune hyperparameters and re-evaluate until satisfied
10. Evaluate model on sequestered test split
### Classifiers
- Choosing a classifier: https://www.kdnuggets.com/2020/05/guide-choose-right-machine-learning-algorithm.html
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
- **XG Boost:** Iteratively use loss function on random forest, drop 'weak learner trees' until loss is minimized
    * World-class performance but near-impossible to explain to stakeholders
- **One Vs Rest:** Breakdown of multiclass problem into several binary class problems
### Classifier Evaluation Metrics
- **Accuracy:** Overall performance of model --- (TP + TN) / (TP + TN + FP + FN)
    * Easy to understand; Imbalanced class problem may yield misleading results
- **Recall:** Positive actual against our predictions --- TP / (TP + FN)
    * Minimizing false negatives; Use when FN is more costly than FP [credit card fraud detection]
    * Also known as Sensitivity; opposite-class recall is called Specificity
- **Precision:** Our prediction against all possible actuals --- TP / (TP + FP)
    * Minimizing false positives; Use when FP is more costly than FN [spam filter])
- **F1 Score:** Harmonic mean of Precision and Recall --- TP / (TP + 0.5(FP + FN))
    * Prioritizing both Recall and Precision; Use for accuracy on an imbalanced class problem
- **Receiver Operating Characteristic:** False Positive Rate against True Positive Rate
    * Model performance at different thresholds; Calculate area under the curve (ROC AUC) as another metric

<!-- Polished -->
## Classification Example
### Classifier Syntax
- `sklearn.tree.DecisionTreeClassifier`
- `sklearn.ensemble.RandomForestClassifier`
- `sklearn.neighbors.KNearestClassifier`
- `sklearn.naive_bayes.GaussianNB`
- `sklearn.linear_model.LogisticRegression`
- `sklearn.xgboost.XGBClassifier`
- `sklearn.multiclass.OneVsRestClassifier`
### Classifier Implementation
```
# basic decision tree
from sklearn.tree import DecisionTreeClassifier
clf = DecisionTreeClassifier(max_depth=3, random_state=123) 
clf = clf.fit(X_train, y_train)
y_train_pred = clf.predict(X_train)
y_train_pred_proba = clf.predict_proba(X_train)
```
```
# visualize decision tree's nodes
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
```
from sklearn.metrics import classification_report
clf.score(X_validate, y_validate)
clf.feature_importances_
validate_report = pd.DataFrame(
    classification_report(
        validate.actuals, 
        validate.predictions, 
        labels=['true', 'false'], 
        output_dict=True
    )
).T
```

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

<!-- Polished -->
## Regression Overview
- Predicting a continuous target using a line
- Multi-dimensional line takes slopes as coefficients on each feature
- **Features that correlate strongly with the target are the best predictors** (positive or negative correlation)
    * For our purposes, each feature is sorted least-to-greatest on x-axis, then we look at how y varies
    * After plotting, we look for monotonicity and change rate to determine the correlation coefficient
### Regression Strategy
0. Prepare data; if there's decision ambiguity, leave it for exploration
1. One-hot-encode or label-encode categorical features (convert categorical data to numerical)
2. Create a correlation crosstab (ex: df.corr()) to see what features correlate with target
3. Eliminate features that do not strongly correlate with the target
    * *Also eliminate features that strongly >80% with other features*, due to features-learning-features issues
4. Visualize each feature against the target using scatterplots
    * Eliminate outliers- regression is highly sensitive to them
5. Understand each relationship with the target- is it linear? Polynomial? Monotonic? Polytonic?
6. Decide which regression model is best based on visualizations
    * Model complexity choice: Reduction of error, variance, and bias^2 is the goal
7. Create, fit model on model-training data
8. Evaluate baseline mean and model RMSE and R^2 for train and validate splits, plot residuals
    * If residuals aren't random, revisit exploration for feature engineering then re-fit and evaluate model
9. Tune hyperparameters and re-evaluate until satisfied
10. Evaluate model on sequestered test split
### Regressors
- **Ordinary Least Squares (OLS):** Minimizes sum of squared differences between prediction and actuals
    * Linear regression as everyone knows it, assumes normal distribution of data
- **LASSO+LARS:** Feature minimization using regularization penalties
    * Can change slope of the regression line to reduce variance and increase bias, assumes normality
- **Generalized Linear Model (GLM):** Best option when distributions are not normal
    * Safe option for most cases except polynomial
- **Support Vector Regression (SVR):** Hyperplane - Boundary capture of discrete values
    * Use for discrete value problem; if > 50,000 rows, use LinearSVR instead
- **Polynomial Regression:** Adjusting features to allow polynomial regression
    * Use number of curves from exploration as hyperparameter
### Regressor Evaluation Metrics
- **Regression line** --- y = b0 + b1x1 + b2x2 + ... bnxn + ϵ
    * y: target; b: coefficient (slope); x: input; ϵ: expected_error
    * Polynomial regression uses: y = b0 + b1x + b2x^2 + b3x^3 + ... + bnx^n + ϵ
- **Residual** --- e = predicted_y - actual_y
    * Obvious trends in residual plots (called heteroscedasticity) indicates unrecognized factors driving target
    * Fixing heteroscedasticity: Remove outliers, transform data, or convert feature(s) to logarithmic value(s)
- **Root Mean Square Error (RMSE)** --- RMSE = sqrt(mean(sum(residuals)))
    * RMSE is in target's units, so calculating home value has RMSE in dollars
    * Other error metrics: SSE (when outliers are the focus), MSE, ESS, TSS
- **Variance (R^2)** --- r2 = ESS / TSS
    * Indicates amount of data (0% - 100%) explained by regression line

<!-- Polished -->
## Regression Example
### Regressor Syntax
- `sklearn.linear_model.LinearRegression`
- `sklearn.linear_model.LassoLars`
- `sklearn.linear_model.TweedieRegressor`
- `sklearn.svm.SVR` or `sklearn.svm.LinearSVR`
- `sklearn.preprocessing.PolynomialFeatures`
### Regressor Implementation
```
# basic linear regression
from sklearn.linear_model import LinearRegression
ols = LinearRegression().fit(X_train, y_train)
y_train_pred = clf.predict(X_train)
```
```
# plot residuals
y_train_residuals = y_train_preds - y_train
sns.relplot(x=y_train, y=y_train_residuals)
plt.axhline(y=0, c='gray', alpha=.3)
```
### Regression Evaluation
```
from sklearn.metrics import mean_squared_error, r2_score
# calculate RMSE
MSE = mean_squared_error(validate.actuals, validate.predictions)
SSE = MSE * len(df) # in case you need SSE
RMSE = mean_squared_error(validate.actuals, validate.predictions, squared=False)
# calculate r2
r2 = r2_score(df.actuals, df.predictions)
```

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

# Time-Series

<!-- Polished -->
## Time-Series Overview
- Predicting the future using the past
- Specifically, using **seasonality,** **fluctuation cycles**, and **autocorrelation** for forecasting
### Time-Series Strategy
1. Understand the nature of your data
    * Is it years of information? months? weeks? days? hours?
    * From visualizations, are there immediate noticeable trends or seasonality?
2. Downsample (aggregate) or upsample (add rows) based on the analytic goal
    * EX: Downsample from minute-by-minute transaction data to daily transaction totals
    * EX: Upsample **patchy** minute-by-minute transaction data to fill gaps for 'even' analysis
3. Use rolling averages for seasonal data and autocorrelation (shifts and diffs) for all time-series options
4. Visualize various metrics for insights
5. Split into train and test using seasonality (if possible), or by percentage
6. Train models using training split then predict the future - **predict test using train**
7. Evaluate each model's RMSE, best model has lowest RMSE
8. Use best model for future forecasting
### Forecasters
- **Last Observed Value** (as prediction)
- **Simple Average** (average of all observations as prediction)
- **Moving/Rolling Average** (last portion of observed for this as prediction)
    * Usually last 7 days, the average of that, as the prediction
- **Previous Cycle** (exactly the last cycle as a whole [sliced] as prediction)
    * Year-Over-Year Difference is a form of this, and a good starting place when you haven't performed any time-series analysis yet. The reason is that each year has an even length, has its own seasons and trends that regularly occur in society, and is commonly referenced in most industries to check performance of production and sales. It's fairly easy to calculate, you do a .diff(365) on day-resampled data then take the mean of all values, showing the overall difference. Then you predict using the final observed year's values, adding the overall difference to each value. Then calculate RMSE as normal.
- **Holt's Linear Trend** (a regression line of previous cycles applied at end of observations)
- **Facebook Prophet's Model** (next expected cycle based on previous cycles)
    * "Pretty good, but hard to install and get working"
### Forecast Evaluation Metrics
- See regression section

<!-- Polished -->
## Time-Series Example
### Time-Series Syntax
- `pd.to_datetime(single_date, format='%b:%d:%Y')`; `pd.to_datetime(df.date, format='%b:%d:%Y')`
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
### Forecaster Implementation
```
# basic diff and shift plotting
ax = df.resample('M').mean().diff().plot()  # plot difference between a month and its previous month
df.resample('M').mean().plot(ax=ax, label='Monthly Average) # plots using same ax as previously-defined graph
df.resample('M').shift(12).plot(ax=ax, label='Last Year') # shifts 12 months to plot last year
# percentage splits
train_end_index = round(df.shape[0] * train_size)
train = df.iloc[:train_end_index]
test = df.iloc[train_end_index:]
# Holt's linear trend
from statsmodels.tsa.api import Holt
model = Holt(train[col], exponential=)
model.fit(smoothing_level = .1, smoothing_slope=.1, optimized=False)
model.predict(start=test.index[0], end=test.index[-1])
```
### Forecast Evaluation
- See regression section

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

<!-- Polished -->
## NLP Overview
- Analyzing words
- Can be used for: Classifying what the text is for / revealing, ex: word choice predicting dialect
    * Regression for NLP isn't really a thing
- Can be used for: Sentiment Analysis
    * Afinn and Vader are sentiment analysis tools based on social media
- Word clouds: http://amueller.github.io/word_cloud/
### Vocab
- Corpus: entire dataset
- Document: one observation
- Tokenization: breaking up into tokens (pieces)
- Stemming and Lematizing: transforming words into their roots
    * stem slices words to base word, lem converts words to base word
- Stopwords: common words that usually don't add value
    * Words with different spelling (word variability) is a common issue that needs handling
- ngrams: combination of n words
- POS: part of speech
    * Part-Of-Speech Tagging: what part of speech a word is (noun, verb, adjective, etc)
    * in nltk library, there are ways to do POS tagging!
- Bag of Words: columns for specific words, rows for observation, values for either the wordcount, true/false existence, or overall proportion
### Turning Text into a Classification Dataset
0. For each class and for the entire df, smash the text together into one single space-separated string
1. Convert all words to lowercase
2. Remove accents and non-ascii characters
3. Remove special characters
4. Tokenize (break down corpus into individual words)
5. Stem or Lemmatize the individual words (calling -> call)
6. Remove stopwords (words that don't matter to us, ex: "the")
7. Use `.value_counts()` on each class's string and the entire corpus, store results into separate pandas Series
8. Concatenate every Series together into a Dataframe (each Series index is the word, so it matches up)
### Text Classification 
- Same classifiers as before
- Prepare data for modeling by using word vectorizers
    * Apply vectorizers to each split
    * sklearn vectorizers can handle a corpus or a pandas Series; we use Series to preserve y_train
    * Count Vectorization: Each column is a word, each row is an observation, each value is a count
    * **TF/IDF Vectorization:** Each column is a word, each row is an observation, each value is a **weight**
        * Term Frequency * Inverse Document Frequency; a lot better than count vectorization
        * Helps identify each word's importance; also helps filter out stopwords; used by search engines
        * TF is how often a word shows, IDF is how unique the word is in all documents
    * Can use `ngrams=` to set word groupings, ex: (1,2) means 1-word and 2-word phrases, (2,2) means only 2-word
- Evaluate which words are most-determinative of class using SelectKBest or RFE

<!-- Polished -->
## NLP Example
- Update stopwords through command line: `python -c "import nltk; nltk.download('stopwords')`
- Sentiment analysis: `df['sentiment'] = df.text.apply(lambda doc: sia.polarity_scores(doc)['compound'])`
    * `sia = nltk.sentiment.SentimentIntensityAnalyzer()` --- `sia.polarity_scores(string)`
    * Used for short phrases (think sentences); Nearly matches human ability to identify sentiment (0.8 vs 0.88)
    * Punctuations!!, CAPITALIZATION can increase intensity
### NLP Preparation
- Combine all documents: `text = df.text.str.cat(sep=' ')`
- Lowercase text: `text = text.lower()`
- Accents, ASCII: `text = unicodedata.normalize('NFKD', text).encode('ascii', 'ignore').decode('utf-8')`
    * `import unicodedata`
- Remove special characters: `text = re.sub(r"[^a-z0-9'\s]", "", text)` --- `import re`
- Tokenize: `text = tokenizer.tokenize(text, return_str = True)`
    * `from nltk.tokenize.toktok import ToktokTokenizer` ---  Can do sentence-wise tokens: `sent_tokenize`
- Stemming: `ps = PorterStemmer()` ---  `stms = [ps.stem(word) for word in text.split()]`
    * `from nltk.porter import PorterStemmer`
- Lemmatization: `wnl = WordNetLemmatizer()` --- `lemmas = [wnl.lemmatize(word) for word in text.split()]`
    * `from nltk.stem import WordNetLemmatizer`
- Remove stopwords: 
    * `from nltk.corpus import stopwords`
    * `stopword_list = stopwords.words('english')`
        * Append/remove new stopwords: `stopword_list.append('word')` or `.remove('word')`
    * `filtered_words = [word for word in words if word not in stopword_list]`
- Rejoin stemmed/lemmatized words: `clean_text = ' '.join(stems)` or `clean_text = ' '.join(lemmas)`
- Regroup in two-word pairings: `pd.Series(list(nltk.bigrams(sentence.split())))`
- Count Vectorization: `from sklearn.feature_extraction.text import CountVectorizer`
- TFIDF Vectorization: `from sklearn.feature_extraction.text import TfidfVectorizer`
### NLP Exploration
```
# scatterplot of each row's char count by word count
df['content_length'] = df.text.apply(len)
df['word_count'] = df.text.split().apply(len)
sns.relplot(df.content_length, df.word_count, hue=df.target)
# stacked bar chart of class proportions by word
word_counts = clean(df.text)    # create dataframe of concatenated 'spam', 'ham', and 'all' Series (step 7 and 8)
word_counts['p_spam'] = word_counts.spam / word_counts['all']
word_counts['p_ham'] = word_counts.ham / word_counts['all']
word_counts[['p_spam','p_ham']].tail(20).sort_values(by='p_ham').plot.barh(stacked=True)
```
### NLP Text Classifier Implementation
```
# Count Vectorization
cv = CountVectorizer()
bag_of_words = cv.fit_transform(df.clean_text) # preserves index, so use y_train
cv.vocabulary_  # show word counts
# TFIDF Vectorization
tfidf = TfidfVectorizer()
tfidf_bag = tfidf.fit_transform(df.clean_text)  # preserves index, so use y_train
tfidf_bag = pd.DataFrame(tfidf_bag.todense(), columns=tfidf.get_feature_names())    # expensive condenser
pd.Series(dict(zip(tfidf.get_feature_names(), tfidf.idf_))).sort_values()   # series of words and their importance
```
```
# Decision Tree
X_train_tfidf, y_train, X_validate_tfidf, y_validate, X_test_tfidf, y_test = split_data(df)
tree = DecisionTreeClassifier(max_depth=5)
tree.fit(X_train_tfidf, y_train)
y_train_preds = tree.predict(X_train_tfidf)
pd.Series(dict(zip(dv.get_feature_names(), tree.feature_importances_))).sort_values().tail(5)   # top-5 features
```
### NLP Text Classification Evaluation
- See classification section

[[Return to Top]](#table-of-contents)






<!-- 
   #                                                ######                                                   
  # #   #    #  ####  #    #   ##   #      #   #    #     # ###### ##### ######  ####  ##### #  ####  #    # 
 #   #  ##   # #    # ##  ##  #  #  #       # #     #     # #        #   #      #    #   #   # #    # ##   # 
#     # # #  # #    # # ## # #    # #        #      #     # #####    #   #####  #        #   # #    # # #  # 
####### #  # # #    # #    # ###### #        #      #     # #        #   #      #        #   # #    # #  # # 
#     # #   ## #    # #    # #    # #        #      #     # #        #   #      #    #   #   # #    # #   ## 
#     # #    #  ####  #    # #    # ######   #      ######  ######   #   ######  ####    #   #  ####  #    # 
-->

# Anomaly Detection

<!-- Polished -->
## Anomaly Detection Strategy
- Distances, clustering, and domain knowledge to identify anomalies amongst normal data
- Wide variety of problem sets, overlapping technique use cases
### General Approach
0. Use domain knowledge / target first as MVP, then move on
1. Start with visuals for each available feature, investigate what is visually anomalous
    * Value counts (histogram) for categorical features (*consider normalizing*)
    * Numerical values over time (line plot) via resampling, averages, counts, sums
    * Categorical v numerical (bar chart) via groupby and aggregation (average, sum)
    * Numerical value v numerical value (scatter plot) via row-wise coords or `sns.pairplot`
2. Move to statistical outliers for each numerical feature using Z-score and IQR rule
3. Move to trend (time-relevant) outliers in categorical/numerical features using Bollinger bands
4. Document observations and potential lines of investigation
### Behavioral Anomalies Examples
- A user accessed, read, changed or copied files that are not associated with their work routine.
- A user copied files to a personal workstation when policy permits working with them only from a specialized system.
- A user accessed critical systems or data outside of normal business hours.
- A user tried to access a system not associated with their work.
- A user account was used to log on from multiple endpoints at the same time, or different users logged on from the same endpoint at the same time.
- There was an unusually large number of manipulations with sensitive data.
- Old accounts became active again.
### Prosecuting Anomalies by Availability
- Timestamps enable a lot of anomaly detection actions
- User identifiers (ex: user1, user2, ...; ex: admin, user, ...; ex: group1, group2, ...) also enable a lot
- Action details (ex: request details, inputs, errors, etc) are great for action grouping
- Observation timestamp + user details + action details allows nearly all anomaly detection techniques
### Time-Series Metrics
- Exponentially-Weighted Moving Average (EWMA) - used as "expected value" in distance-based outlier detection
    * Tune EWMA's alpha parameter to tighten/loosen conformity to most-current value (smoothing)
    * alpha=0: average at location of all previous values; alpha=1: current value exactly; larger alpha means more of past considered
- Bollinger Bands - upper/mid/lower bands for values in trend, used a lot in finance and stock market analysis
    * Mid band is moving average; Upper band is mid band + (K * moving STD); Lower band is mid band - (K * moving STD)
        * Standard values for K are 2 and 20; larger K means less outliers
    * %b is a calculation of volatility, anything above 1 or below 0 is outside the bands
### Anomaly Clustering - [DBSCAN](#dbscan)
- DBSCAN (Density-Based Spatial Clustering of Applications with Noise) - king of cluster-based outlier detection
- Requires minimum amount of points in a given radius to be considered a non-outlier cluster
    * SCALING NEEDED
- Any point(s) that don't meet given non-outlier requirements is returned in cluster "-1"
- Often done with count/nunique as numeric variable (nunique being too-low or too-high is anomalous)

<!-- Polished -->
## Anomaly Detection Syntax
### Time Anomalies
- Outside expected times: Manual determination of anomaly via date/time filter
    * `df["unexpected_time"] = ((df.time < time(9,0)) & (df.time > time(17,0)) | (df.date.weekday > 5) | df.date.isin(holidays)`
- Too quickly: Downsampling / Reduction of time precision in rows, then value count of event/imprecise_time combinations
    * `df["minute"] = df.time.dt.to_period("min")`, `df.groupby(["user_id","minute"]).url_path.count().sort_values(ascending=False)`
    * `df[df["group"].isin(group_list)].groupby('group').resample('W').size().unstack(0).plot()`
- Should never happen / Should always happen: New column for met_condition, filter by met_condition
    * `df["bad"] = df["commandline"] == "su -"`, `df[df["bad"]]`
    * `df["good"] = df["user_id"].isin(permitted_user_list)`
- Outside expected value range at time: Designate upper/lower/mid Bollinger bands (EWMA or rolling), classify outliers using filtering
    * `std = s.ewm(alpha=.1).std()`; `df['mid'] = s.ewm(alpha=.1).mean()`; `df['high'] = mid + K * std`; `df['low'] = mid - K * std`
    * `df[['high', 'low']].plot(color='black', alpha=.6, ls=':', figsize=(16, 6))`; `df.mid.plot(color='black', alpha=.6, ls='--')`
    * `df['%b'] = (s - df.low) / (df.high - df.low)`; `high_out = bands[bands['%b'] > 1]`, `low_out = bands[bands['%b'] < 0]`
    * `plt.plot(bands.index, bands.actual, label='coolname')`; `plt.vlines(up_out.index, *plt.ylim(), color='black', ls='--', label='Ups')`
### Numerical Anomalies
- Unusual observed y in x: IQR rule or Z-score, classify outliers using filtering
    * `q1 = col.quantile(0.25)`; `q3 = col.quantile(0.75)`; `iqr = q3 - q1`; `lower_bound = q1 - k * iqr`; `upper_bound = q3 + k * iqr`
    * `stats.zscore(col)`
### Combination Anomalies
- Unusual combination of categories: Value counts of 2+ categorical features
    * `df[["categorical_feature_1","categorical_feature_2","categorical_feature_3"]].value_counts().unstack().plot.barh()`
- Unusual numerical value attributed to category: Split numerical into ordinal categories, then value counts (same as above)
    * `pd.cut(s, bins=[0,2,5], labels=['low','high'], right=False)`
- Unusually-high amount of same categorical combo at time: New column for is_combination, downsample with count() logic, then EWMA
    * `df[["is_combination"]].resample("D").sum()`
- Outlier clustering for all-numerical features: DBSCAN clustering, scale features then train/plot clusters
    * See: [DBSCAN Clustering](#dbscan); **K-Means is worse for outlier detection** because it groups on centroids (includes outliers)
    * With categories EX: two categories, three all-numerical clusters per category, average each cluster's features, compare averages
### Pattern Anomalies
- Find specific sequence of events for actor: Filter to actor, resample as needed, use dataframe shifting to create met_condition column
    * `open_then_close = (df.actor == "p1") & (df.act == "open") & (df.actor.shift(-1) == "p1") & (df.act.shift(-1) == "close_doc")`
    * Consider merging event logs into one continuous dataframe using actor IDs as the key
- Find unusual sequence of events for actor: Filter to actor, list comprehension, value counts of same-values lists
    * `three_event_sequences = [[s[i],s[i+1],s[i+2]] for i in s.index if i+2 < len(s)]`
    * Consider merging event logs into one continuous dataframe using actor IDs as the key

<!-- Polished -->
## Anomaly Detection Examples
### Bollinger Bands and Anomalous Temperatures
```
plt.rc('figure', figsize=(13, 6))
plt.rc('axes.spines', top=False, right=False)
plt.rc('font', size=13)

def to_fahrenheit(k):
    return k * 9/5 - 459.67

url = "https://gist.githubusercontent.com/ryanorsinger/0ec766c66f4089bdcbc1d4fb294a3394/raw/197c1f0d7b55a45f29437811bc73d9c4ef8af647/sa_temps.csv"
s = pd.read_csv(url, index_col='datetime', parse_dates=True).temp
s = s.dropna()
s = to_fahrenheit(s)
s = s.resample('D').mean()

K = 2
N = 20
# std = s.rolling(N).std()
std = s.ewm(alpha=.1).std()
bands = pd.DataFrame()
# bands['mid'] = s.rolling(N).mean()
bands['mid'] = s.ewm(alpha=.1).mean()
bands['upper'] = bands['mid'] + K * std
bands['lower'] = bands['mid'] - K * std
bands['actual'] = s

t = bands.loc['2013']
t[['upper', 'lower']].plot(color='black', alpha=.6, ls=':', figsize=(16, 6))
t.mid.plot(color='black', alpha=.6, ls='--')
t.actual.plot()
plt.legend('')
plt.xlabel('')

bands['%b'] = (bands.actual - bands.lower) / (bands.upper - bands.lower)
upper_outliers = bands[bands['%b'] > 1]
lower_outliers = bands[bands['%b'] < 0]

plt.plot(bands.index, bands.actual, label='Temperature (deg F)')
plt.vlines(upper_outliers.index, *plt.ylim(), color='black', ls='--', label='Upper Outlier')
plt.vlines(lower_outliers.index, *plt.ylim(), color='black', ls=':', label='Lower Outlier')
plt.title('San Antonio Temperature Over Time')
plt.legend()
plt.xlim(pd.to_datetime('2013'), pd.to_datetime('2014'))
```

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
## Deep Learning Basics
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
```
from tensorflow import keras
from keras import models, layers
from keras.datasets import mnist # very popular image classification dataset
(train_images, train_labels), (test_images, test_labels) = mnist.load_data()
train_images = train_images.reshape((60000, 28 * 28)); 
train_images = train_images.astype('float32') / 255 # reshape data for model
test_images = test_images.reshape((10000, 28 * 28)); test_images = test_images.astype('float32') / 255
network = models.Sequential() # create the model
network.add(layers.Dense(512, activation='relu', input_shape(28*28,))) # add a layer
network.add(layers.Dense(10, activation='softmax')) # add output layer
network.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
# compile the model
train_labels = keras.utils.to_categorical(train_labels)
test_labels = keras.utils.to_categorical(test_labels)
network.fit(train_images, train_labels, epochs=20, batch_size=128)
test_loss, test_acc = network.evaluate(test_images, test_labels)
print(f'accuracy of network on test set: {test_acc}')
```

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
## Computer Vision Basics
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

# Cross-Validation

<!-- Needs work -->
## Cross-Validation Basics
- K-fold cross validation: split *train* into more train-test splits, average prediction score across fold combinations
- Grid Search: use K-fold cross validation to determine best max_depth train split
### K-Fold Cross Validation
- from sklearn.model_selection import cross_val_score
- cross_val_score(clf, X_train, y_train, cv=5).mean() ----- eval clf model w 5 folds
    * init empty 'scores' dictionary, loop through max_depths, eval score using this func, use scores[depth] = score
- from sklearn.metrics import precision_score, make_scorer
- cross_val_score(clf, X_train, y_train, cv=5, scorer=make_scorer(precision_score, pos_label='prediction')) ----- use a different scorer than default, pos_label converts non-binary values to binary by choosing what is 1, making everything else 0
- One of those folds is a test split, the rest of the folds are train splits
- Each fold rotates in as the test split
- Common fold counts: 3, 4, 5, 10 (5 most common)
### Grid Search
- Basically does validate for us- choose best model here and run against test
- from sklearn.model_selection import GridSearchCV
- Defaults to .score and r2
- Only optimizes hyperparameters
### Examples
- grid = GridSearchCV(clf, {'n_neighbors': range(1, 21)}, cv=5)
    * Notice how you pass hyperparameter options to GridSearchCV

[[Return to Top]](#table-of-contents)






<!-- 
######                                                               
#     # ###### #####  #       ####  #   # #    # ###### #    # ##### 
#     # #      #    # #      #    #  # #  ##  ## #      ##   #   #   
#     # #####  #    # #      #    #   #   # ## # #####  # #  #   #   
#     # #      #####  #      #    #   #   #    # #      #  # #   #   
#     # #      #      #      #    #   #   #    # #      #   ##   #   
######  ###### #      ######  ####    #   #    # ###### #    #   #   
-->

# Deployment

## Docker
- Containers: Easy replication and distribution of software solutions
- Sandboxing: Each container in a Docker daemon is **isolated** from one another, by nature
    * A container can replicate a computer in a safe state for testing, i.e. intrusion and malware
- Cloud Support: Install the Docker daemon on a virtual server, then simply build from an image and run
- Infinitely Scalable: Load balancers can coordinate many daemons and containers through ex: Kubernetes
- Lightweight: *Not* ran in a virtual machine, runs directly from OS kernel (Docker mediates)
    * Docker daemon will initialize a virtual machine if OS kernel does not match container 
- Base images for `docker pull` or `FROM`: https://hub.docker.com
- Official documentation: https://docs.docker.com/engine/reference/builder/
### Dockerfile
- Set of instructions to build a Docker image
- Starts with `FROM`, which takes a base image as a parameter
- Each instruction adds a layer or an intermediate layer to the image, and runs to completion before proceeding
- Instructions are couched in the base layer; `RUN` for the Ubuntu base image uses Linux commands, for example
- **RUN:** Execute a command when building the image
    * `RUN ["python3", "my_setup_script.py"]` is the same as typing this into Terminal: `python3 myscript.py`
    * Can also use: `RUN python3 myscript.py`, but the other form is recommended
- **COPY:** Copy a specified local directory's files into image's specified directory
    * Use `COPY . /app` to copy the current local directory's files into image's "app" folder
- **WORKDIR:** Specify the directory for the image to proceed to for next instructions
    * Navigate to the runtime-script folder and use ENTRYPOINT + CMD here to run the script
- **ENTRYPOINT:** Set the command for the image to run *every time*
    * Can't be modified through command line; if an image is designed to use a python kernel, specify python here
- **CMD:** Sets the command for the image to use when the image is ran
    * Often used with ENTRYPOINT; ENTRYPOINT is excellent for selecting a kernel ("python3") to run a script
    * With `ENTRYPOINT ["python3"]`, use: `CMD ["image_runtime_script.py"]`
### Initializing, Running Docker Containers
- Build image(s) from a Dockerfile, Run images from the Docker images folder
- Build: Specify the context where the Dockerfile + needed files live, ex: `docker build .`
    * `-t author/purpose:version`: add image tag (image name)
- Run: Specify which compiled image to use, ex: `docker run -d -p 80:80 --rm image_name`
    * `-d`: detach from Terminal; `p`: assign ports; `--rm`: remove container on exit
    * Run named image: `docker run author/purpose` (assumes latest version if not specified)
    * Alias an image during the run command: `--name alias_name`
### Example Dockerfile
```
FROM ubuntu:latest
RUN apt-get update -y
RUN apt-get install -y python3-pip python3-dev build-essential
COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt    # requirements.txt specifies py libraries to install
ENTRYPOINT ["python3"]
CMD ["app.py"]
```

## Flask
- Web interfacing framework built on Python
- Excellent for translating HTTP requests into function calls
- Walkthrough of everything-Flask: https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world
- Links, links, links for Flask-related content: https://www.fullstackpython.com/flask.html
### Flask Basic Routing
- Routing typically set in a file called views.py or app.py, allows page navigation from a Python framework
- Run function on every page navigation regardless of page: `@app.before_request()`
- Run function for specific page navigation: `@app.route('/cool_page')`
    - Common return: `return_template(cool_page.html, global_var_thingy="coolthing")` ----- loads cool_page.html when nav to /cool_page
    - Global variables can be called in HTML like this: `{{ global_var_thingy }}`, works as expected, do Python work in views.py or app.py
- Allow sending data (POST), rewriting page (PUT): `@app.route('/api/v1/users', methods=['GET','POST','PUT'])`
    * use: `if request.method == 'POST':` to specify what to do with which HTTP request type
- Capture args from URL input: `@app.route('/<int:year>/<int:month>/<title>')` --- `def func(x,y,z):`
### Flask Post-Route Functions
- Overall route conclusions: Generate page template, Provide response, or Redirect a user somewhere else
- Page template: `Flask(__name__, template_folder='templates')` --- ... --- `return render_template('index.html')`
- Return info for coders: `return make_response(programmatic_stuff, HTTP_response_code, headers=headers_dict)`
- Redirect a user from `@app.route('/cool_page.html')` to elsewhere: `return redirect('/cool_page_2.html')`
    * Better version: `return redirect(url_for('cool_page_2'))`
- Request for everything; `request.method`, `request.args.func`, `request.data`, `request.form`, `request.headers`
- Setting global values: `from flask import g` --- `g.key_name = value` --- `g.pop('value', None)`
- Error handling: `@app.errorhandler(404)`
### Flask Example
```
# Import all the packages you need for your model below
import pickle
import numpy as np
import sys
import os
from sklearn.ensemble import RandomForestClassifier
# Import Flask for creating API
from flask import Flask, request
port = int(os.environ.get('PORT', 5000))
# Load the trained model from current directory
with open('./anomaly_detection_model.sav', 'rb') as model_sav:
    rf = pickle.load(model_sav)
# Load the trained scaler from current directory
with open('./anomaly_scaler.sav', 'rb') as scaler_sav:
    scaler = pickle.load(scaler_sav)
# Initialise a Flask app
app = Flask(__name__)
# Create an API endpoint
@app.route('/predict')
def predict_anomaly():
    # read all necessary request parameters
    srv_count = request.args.get('srv_count')
    num_failed_logins = request.args.get('num_failed_logins')
    # create numpy array for inputs
    input_array = np.array([[srv_count, num_failed_logins]])
    # scale the input
    scaled_inputs = scaler.transform(input_array)
    # predict the scaled input
    predict_result = rf.predict(scaled_inputs)
    # return the result back
    return 'Predicted result for observation ' + str(input_array) + ' is: ' + str(predict_result)
if __name__ == '__main__':
    app.run(debug=True,host='0.0.0.0',port=port)

# Example call when running: http://localhost:5000/predict?srv_count=500&num_failed_logins=0
```

## Apache Kafka
- Distributed stream processing
- Kafka 'broker' listens on port 9092 for TCP connection
    * Distributed system has multiple brokers, each has full copy of topics, each listens on different ports
    * One broker is 'leader' on a *partition* or topic while others are followers, as necessary
- Kafka 'producer' publishes to a 'topic' in the Kafka broker, each publish adds a row in the topic marked by index
    * With partitions, the producer selects the partition to add a row to
    * Non-Kafka: Publish once, consume once (gone after): "Queue"; Publish once, consume many (not gone): "Pub/Sub"
    * Kafka: All consumers in a group is "Queue"-style, all in separate groups is "Pub/Sub"-style
- Kafka 'consumer' reads the topic and all its rows from index 0 onward
    * Consumer groups distribute the partitions of a topic evenly between consumers in the group on 'consume'
    * The max number of consumers in a group is the number of partitions in the topic