# <center><strong>Data Science Notes, v3</strong></center>

<!-- 
#######                                              
   #      ##   #####  #      ######     ####  ###### 
   #     #  #  #    # #      #         #    # #      
   #    #    # #####  #      #####     #    # #####  
   #    ###### #    # #      #         #    # #      
   #    #    # #    # #      #         #    # #      
   #    #    # #####  ###### ######     ####  #      
                                                     
 #####                                                 
#     #  ####  #    # ##### ###### #    # #####  ####  
#       #    # ##   #   #   #      ##   #   #   #      
#       #    # # #  #   #   #####  # #  #   #    ####  
#       #    # #  # #   #   #      #  # #   #        # 
#     # #    # #   ##   #   #      #   ##   #   #    # 
 #####   ####  #    #   #   ###### #    #   #    ####  
-->

# Table of Contents
I.    [Environment Meta-Work         ](#environment-meta-work)
1.    [Environment Setup             ](#environment-setup)
1.    [Git Setup                     ](#git-setup)
1.    [Git Work                      ](#git-work)

II.   [Dataset Reference             ](#dataset-reference)
1.    [Links to Datasets             ](#links-to-datasets)
1.    [REST APIs                     ](#rest-apis)

III.  [Advanced Web Scraping         ](#advanced-web-scraping)
1.    [Pandas Read-HTML              ](#pandas-read-html)
1.    [Requests                      ](#requests)
1.    [Selenium                      ](#selenium)
1.    [Image Download                ](#image-download)

IV.   [Building a Database           ](#building-a-database)
1.    [SQLite                        ](#sqlite)
1.    [PostgreSQL                    ](#postgresql)

V.    [Database Usage Mastery        ](#database-usage-mastery)
1.    [SQL and Variants              ](#sql-and-variants)
1.    [Elasticsearch                 ](#elasticsearch)
1.    [Spark                         ](#spark)

VI.   [Feature Transformation        ](#feature-transformation)
1.    [Dataframe Normalization       ](#dataframe-normalization)
1.    [Fixing Dataframes at Speed    ](#fixing-dataframes-at-speed)
1.    [Feature Engineering           ](#feature-engineering)
1.    [Speedy Data Structures        ](#speedy-data-structures)

VII.  [Algorithmic Clustering        ](#algorithmic-clustering)
1.    [Selecting Number of Clusters  ](#selecting-number-of-clusters)
1.    [Clustering Methods            ](#clustering-methods)
1.    [Cluster Analysis              ](#cluster-analysis)

VIII. [Natural Language Processing   ](#natural-language-processing)
1.    [Normalizing String Features   ](#normalizing-string-features)
1.    [Keywords and Sentiment        ](#keywords-and-sentiment)
1.    [NLP for Prediction            ](#nlp-for-prediction)

IX.   [Insight Delivery              ](#insight-delivery)
1.    [Statistical Analysis          ](#statistical-analysis)
1.    [Visualizations                ](#visualizations)
1.    [Magic in Jupyter              ](#magic-in-jupyter)

X.    [Classification                ](#classification)
1.    [Features for Classification   ](#features-for-classification)
1.    [Training Classifiers          ](#training-classifiers)
1.    [Evaluating Classifiers        ](#evaluating-classifiers)

XI.   [Regression                    ](#regression)
1.    [Features for Regression       ](#features-for-regression)
1.    [Training Regressors           ](#training-regressors)
1.    [Evaluating Regressors         ](#evaluating-regressors)

XII.  [Time Series                   ](#time-series)
1.    [Metrics of Time Series        ](#metrics-of-time-series)
1.    [Outcome Plotting              ](#outcome-plotting)
1.    [Time Series Modeling          ](#time-series-modeling)

XIII. [Anomaly Detection             ](#anomaly-detection)
1.    [Anomalic Metrics              ](#anomalic-metrics)
1.    [Getting to the Numbers        ](#getting-to-the-numbers)
1.    [Baselines and Deviation       ](#baselines-and-deviation)

XIV.  [Neural Networks               ](#neural-networks)
1.    [Establishing a Neural Network ](#establishing-a-neural-network)
1.    [Image Classification          ](#image-classification)
1.    [Deep Learning                 ](#deep-learning)

XV.   [Model Deployment              ](#model-deployment)
1.    [Building a Flask App          ](#building-a-flask-app)
1.    [Building a Django App         ](#building-a-django-app)
1.    [Deploying the Model           ](#deploying-the-model)

XVI.  [Project Management            ](#project-management)
1.    [Planning a Project            ](#planning-a-project)
1.    [Selecting the Framework       ](#selecting-the-framework)

XVII. [Business Tools                ](#tools-and-languages)
1.    [Excel and Google Sheets       ](#excel-and-google-sheets)
1.    [PowerBI                       ](#powerbi)
1.    [Tableau                       ](#tableau)

XVIII.[Programming Languages         ](#programming-languages)
1.    [Python Oddities               ](#python-oddities)
1.    [R                             ](#r)
1.    [C++                           ](#c)

<br>

<br>







<!-- 
#######                                                                 
#       #    # #    # # #####   ####  #    # #    # ###### #    # ##### 
#       ##   # #    # # #    # #    # ##   # ##  ## #      ##   #   #   
#####   # #  # #    # # #    # #    # # #  # # ## # #####  # #  #   #   
#       #  # # #    # # #####  #    # #  # # #    # #      #  # #   #   
#       #   ##  #  #  # #   #  #    # #   ## #    # #      #   ##   #   
####### #    #   ##   # #    #  ####  #    # #    # ###### #    #   #   
                                                                        
#     #                           #     #                      
##   ## ###### #####   ##         #  #  #  ####  #####  #    # 
# # # # #        #    #  #        #  #  # #    # #    # #   #  
#  #  # #####    #   #    # ##### #  #  # #    # #    # ####   
#     # #        #   ######       #  #  # #    # #####  #  #   
#     # #        #   #    #       #  #  # #    # #   #  #   #  
#     # ######   #   #    #        ## ##   ####  #    # #    #  
-->

# Environment Meta-Work
```
It's nice having a step-by-step reference for setting up Anaconda envs and Git.
Env setup can probably be copied over as-is; I use it fairly often.
Git can be mostly copy-pasted, but I'd like to add authentication instructions.
I might want to add a script to update packages...
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup
1. Download and install Anaconda: https://www.anaconda.com/products/distribution
    * Defaults are fine
1. Add Anaconda to Path variable
    * Control Panel > System and Security > System > Advanced system settings 
    * Environment Variables > Path > Edit
    * Add: C:\Users\Jake\Anaconda3\Scripts
    * Add: C:\Users\Jake\Anaconda3
    * Add: C:\Users\Jake\Anaconda3\Library\bin
1. Undo Window's stupid default aliasing
    * Start > Manage App Execution Aliases > Uncheck python.exe and python3.exe
1. Open CMD (we will be setting up using Windows' default terminal)
1. Enter: `conda config --append channels conda-forge` (add main package source)
1. Create your Conda environment and install basic data science packages into it
    * Basic: `conda create -n env1 numpy pandas matplotlib seaborn scikit-learn`
    * `conda install --name env1 statsmodels scipy imbalanced-learn jupyter`
1. Enable Windows CMD as a front for Conda: `conda init cmd.exe`
1. Activate your environment: `conda activate env1`
1. Install pip into your environment: `conda install pip`
1. Now that your env is active, choose the additional packages you need
    * Webscraping: `conda install bs4 selenium`
        * Selenium requires downloading a browser driver, ex: "chromedriver.exe"
    * Interactivity: `conda install dataclasses plotly dash flask django`
    * Big data: `conda install dask pyspark vaex scikit-learn-intelex`
    * Natural Language Processing: `conda install nltk`
    * Network data: `pip install ipcalc nfstream dash dash_cytoscape`
        * NFStream install: https://nfstream.org/docs/#installation-guide
    * Elasticsearch: `pip install elasticsearch elasticsearch-dsl`
    * Handling YAML: `pip install pyyaml ruamel.yaml`
1. Install PyTorch if you want
    * `conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch`
    * `conda install astunparse numpy ninja pyyaml setuptools cmake cffi`
    * `conda install typing_extensions future six requests dataclasses`
1. Install Keras and Tensorflow if you want
    * `conda install -c conda-forge keras`
    * `conda install -c conda-forge tensorflow`
1. Test package installation
    * Open CMD and enter `jupyter notebook`
    * Start up a new Python3 notebook
    * Try to import the packages you've installed and test them
1. Install VS Code (my preferred code editor beside Jupyter)
    * Defaults are fine; I recommend also "Open with Code" for context menus
    * Open a terminal anywhere and type: `code test.md`
        * This should open VS Code; try a second time if first didn't work
        * If it worked, great! This is my preferred way to create files
    * Install Python extension to VS Code (HIGHLY recommended)
    * 80/120 char width code lines: Settings -> editor.rulers -> set to [80,120]
1. Install Git (I do defaults except the following, my preferred settings)
    * Download: https://git-scm.com/downloads
    * I actually edit the registry to launch CMD on shift+rightclick context...
        * If you agree, disable Git Bash and Git GUI in context menus...
        * If you don't like registry editing, keep Git Bash (remove Git GUI)
    * Add Git Bash profile to Windows Terminal (for CMD!...)
    * Register VS Code as Git's default editor
1. Launch CMD (or Git Bash) and set your Git settings
    * Add your name: `git config --global user.name "Joe Schmoe"`
    * Add your email: `git config --global user.email "joeschmoe@gmail.com`
1. Done!!! For now...
### Registry CMD Launch
Windows + R > regedit > Computer\HKEY_CLASSES_ROOT\Directory\shell\cmd
- > Right click on `Directory\Background\shell\cmd` folder on left nav pane
    * > Permissions > Advanced
- > Owner Change > Type username (Jake) > Check Names > Ok
    * > Replace owner on subcontainers and objects > Apply 
- > Add > Select a principal > Type username (Jake) > Check Names > Ok 
    * > Check "Full Control" > Ok > Replace all child.. > Ok > Yes > Ok
- > Right click on HideBasedOnVelocityId (changing reg values now) 
    * > Rename > rename to ShowBasedOnVelocityId
- > Task Manager (ctrl+shift+escape) > More Details 
    * > select Windows Explorer > Restart
- > Open any folder > Shift + right click 
    * > If "open Powershell window here" displays, then success!
- > Right click on `Directory\Background\shell\cmd` folder on left nav pane
    * > Permissions > Advanced > Select user in window (Jake) > Remove 
    * > Check "Replace all child"... > Apply > Yes
- > Owner Change > type trusted installer service NT SERVICE\TrustedInstaller 
    * > Check Names > Ok 
    * > check "Replace owner on subcontainers..." > Ok > Ok > Close Regedit
### Env Commands
- See list of available environments: `conda env list`
- Create new environment: `conda create -n env_name`
- Activate environment: `conda activate env_name`
- Deactivate an active environment: `conda deactivate`
- Delete an environment: `conda env remove -n env_name`
- Check currently-installed packages: `conda list`
- Search for available versions of a package: `conda search package_name`
- Install a package with active environment: `conda install package_name`
    * Specify a package's version on install: `conda install package_name=1.0.0`
- Install package to inactive env: `conda install --name env_name package_name`
- Update a package: `conda update package_name`
- Remove a package: `conda remove package_name`
- Install an env-contained pip instance: `conda install pip` -> `pip install ..`
### Env Launch Script
```
cd C:\Users\Jake\Zen
call activate mighty
%SystemRoot%\explorer.exe "C:\Users\Jake\zen"
code "" "C:\Users\Jake\zen" | exit
jupyter notebook
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Git Setup
### Github
1. Create Github account
1. Set your Github credentials on your computer
    - Run command: `git config --global user.name "github_username"`
    - Run command: `git config --global user.email "github_email_address"`
1. Generate an SSH key for connecting with Github
    - Run command: `ssh-keygen -t rsa -b 4096 -C "github_email_address"`
    - Hit ENTER on keyboard when it asks where to save the key (save to default)
1. Add your SSH key to Github here: https://github.com/settings/ssh/new
    - Run command (Mac/Linux or Git Bash): `cat ~/.ssh/id_rsa.pub | pbcopy`
    - Paste that into the link and give it a title of your choice
1. Click "Add SSH Key", done
1. Check if it's working: 
    - Create new repository on Github
    - Click "Code" button dropdown
    - Click SSH
    - Copy that text
    - Open Terminal or Git BASH or CMD or whatever you use
    - Enter `git clone that_text_you_just_copied`
        - EX: `git clone git@github.com:JacobPaxton/data_science_notes.git`
        - EX2: `git clone https://github.com/JacobPaxton/data_science_notes.git`
    - If it clones, great- it worked
    - Add a random new file to the folder it created
    - Run command: 
        * `git add .`
        * `git commit -m 'my first commit'`
        * `git push`
1. If the above steps work, you are 100% ready to go
### Gitlab
1. 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Git Work
1. If you're creating a new project, start by creating a repo on Github/Gitlab
1. Grab the remote repository with `git clone` and `cd` into the created folder
1. Grab all branches of remote repo with `git remote update`
1. Switch to your branch of preference if needed with `git branch awesomething`
    * Create a new branch if desired with `git branch -c mynewbranch`
1. Make your changes in the branch
    * Consider adding a ".gitignore"! Set file exclusions (line-separated)
1. When you're ready to consider the remote repository, run `git remote update`
    * This is `git fetch`, but is fetching *all* branches in the remote repo
    * This automatically pulls any remote repo branch that the local repo lacks
        * Note: it will say "new branch" in the output if it pulls a new branch
    * This does not modify any files in branches that the local repo has
1. Run `git status` in the branch you're working on
    * If branch is "up to date", then you're done! And you can add, commit, push
        * If you created a new branch: `git push origin localthing:remotething`
        * When you're ready to merge into another branch, submit a merge request
    * If it says "Your branch is behind...", then keep reading...
1. Run `git diff @{u} --name-only` to show which files differ in local/remote
    * If no file involves your edits, run `git merge` now and add, commit, push
    * If one or more files *do* involve your edits, then keep reading...
1. Run `git diff @{u}` to see each file *and* its differences in local/remote
    * **This focuses on local files and what they have/don't have from remote**
    * Remote branch has a line that local branch doesn't: shows as "removed"
    * Remote branch doesn't have a line that local branch does: shows as "added"
1. Decide what to do with the differences
    * To destroy your changes & accept the remote repo, use `git restore file1`
    * If you want to keep your changes... check out Resolving Merge Conflicts
### Branch Work
- `git log --oneline -5` to see last 5 commits (including current [HEAD])
    * `git log --oneline -5 branch_name` see last 5 commits of specified branch
    * `git log --graph --all --oneline --decorate` see branch tree
- `reset` says "make my project look like it did before" (staged + commit + etc)
- `git reset --soft <tree-ish>`: Only move HEAD, leave staged/workdir alone
    * Used for undoing a `git commit` mainly; can also reset FORWARD
- `git reset --mixed <tree-ish>`: Adopt old staged file status + move HEAD
    * Used for undoing `git add` and `git commit`
- `git reset --hard <tree-ish>`: Adopt old workdir + all staged + move HEAD
    * Used for moving to a clean-repo for a commit; helps with branching work
    * `git reset --hard HEAD^` to parent, `git reset --hard HEAD^^` to grandpa
- `git merge new_code_branch` to merge code into current branch
    * "Fast forward: (branch exists 100% ahead) vs "true" (overlapping commits)
    * `git diff receiver..giver`: compare branches before merging
        * `git diff --color-words rcvr..gvr f1.txt` focus f1.txt, compare words
    * `git branch --merged`: see what branches are fully integrated into HEAD
        * If you're done with the listed branches, delete them!
    * Generally you should only merge with a clean repo
- Merge conflicts: just manually fix it...
    * `git show --color-words` during merge conflict to see what's conflicting
- Tags: typically "v1.0", "v1.1", "hyperviz1.0" etc (you're naming commits)
    * Tags are NOT implicitly sent to remote with `git push`
        * `git push remote v1.0` add to remote
        * `git push remote :v1.0` delete from remote; `git tag -d v1.0` local rm
    * `git tag -a v1.0 -m "Version 1.0" commit_hash` v1.0 tag with an annotation
        * Without commit_hash, HEAD is assumed
    * `git tag issue213 commit_hash` No annotation, just the tag
    * `git tag -d v1.0` delete tag v1.0
    * List tags: `git tag -l`, `git tag -l "v1.*"` (wildcard)
    * `git diff v1.0..v1.1` to see differences between tags!
- Stashing: `git stash save "add essay"`, `git stash list` (note: not flags)
    * `git stash pop` to add (and remove from stash) most recent stash back in
        * Specify a stash to add: `git stash list` -> `git stash pop stash@{3}`
    * `git stash apply` to **copy** the stash over (do not remove it)
    * `git stash drop stash@{1}` drop stash; `git stash clear` clear all stashes
### Resolving Merge Conflicts
- If you have a "merge conflict", this is how to resolve the issue (my method):
1. Pull the Github repo down to a new folder using `git clone`
2. Copy the changed files / changes manually to the clone
3. Run `git add filename` `git commit -m "message"` `git push` as normal
4. Delete the old folder after successfully pushing your work
5. Move the new folder to where the old folder was- good as new!!
### Handling Aftermath of Branch Merges
- If a team mate merged a branch into main, you've come to the right place
1. If you accept these changes run `git pull`, otherwise Safely Update Your Repo
2. To delete the merged-in branch locally, run `git branch -d branch_name`
3. To clean up the deletion you just performed, run `git fetch --prune`
4. Done! Merged-in branch has now been deleted locally.

[[Return to Top]](#table-of-contents)







<!-- 
######                                          
#     #   ##   #####   ##    ####  ###### ##### 
#     #  #  #    #    #  #  #      #        #   
#     # #    #   #   #    #  ####  #####    #   
#     # ######   #   ######      # #        #   
#     # #    #   #   #    # #    # #        #   
######  #    #   #   #    #  ####  ######   #   
                                                
######                                                          
#     # ###### ###### ###### #####  ###### #    #  ####  ###### 
#     # #      #      #      #    # #      ##   # #    # #      
######  #####  #####  #####  #    # #####  # #  # #      #####  
#   #   #      #      #      #####  #      #  # # #      #      
#    #  #      #      #      #   #  #      #   ## #    # #      
#     # ###### #      ###### #    # ###### #    #  ####  ###### 
-->

# Dataset Reference
```
This section outlines where and how to request data from internet sources.
I'd like to have a repository of links for datasets for future reference.
API notes should be structured in API request examples, with options explained.
The end state of both methods should be an initial dataframe pre-editing.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Links to Datasets
- Massive list: https://github.com/awesomedata/awesome-public-datasets
- Massive list: https://www.data-is-plural.com/archive/
- Search US Gov data: https://www.data.gov
- Search EU data: https://data.europa.eu/en
- Search research paper data: https://paperswithcode.com/datasets
- Search various: https://huggingface.co/datasets
- Search various: https://datasetsearch.research.google.com
- NLP: https://machinelearningmastery.com/datasets-natural-language-processing/
- Computer vision (CV): https://visualdata.io/discovery
- Satellite CV: https://github.com/chrieke/awesome-satellite-imagery-datasets
### Import-able Datasets (Python)
- `from pydataset import data` --- `df = data('iris')`
- `import seaborn as sns` --- `df = sns.load_dataset('iris')`
- `from vega_datasets import data` --- `df = data('iris')`
- `from sklearn import datasets` --- `array = datasets.load_iris()['data']`
- datareader https://pandas-datareader.readthedocs.io/en/latest/remote_data.html

--------------------------------------------------------------------------------
<!-- Needs work -->
## REST APIs
- Application Programming Interface: a way to interact with 'owned' data
    * There's rules and defined mathods for interacting with APIs
    * Scraping is still possible, but APIs may be better in some cases
- REST, RESTful: a standardized structure for URLs
- RESTful JSON API: URLs follow REST comms w/ server are in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests
- Endpoints are typically: "/api/v1/items/1" with ["next_page"]/["max_page"]
```
import requests
json_data = requests.get("https://swapi.dev/api/people/5").json()
print(json_data["name"])
```

[[Return to Top]](#table-of-contents)







<!-- 
   #                                                     
  # #   #####  #    #   ##   #    #  ####  ###### #####  
 #   #  #    # #    #  #  #  ##   # #    # #      #    # 
#     # #    # #    # #    # # #  # #      #####  #    # 
####### #    # #    # ###### #  # # #      #      #    # 
#     # #    #  #  #  #    # #   ## #    # #      #    # 
#     # #####    ##   #    # #    #  ####  ###### #####  
                                                         
#     #                   #####                                              
#  #  # ###### #####     #     #  ####  #####    ##   #####  # #    #  ####  
#  #  # #      #    #    #       #    # #    #  #  #  #    # # ##   # #    # 
#  #  # #####  #####      #####  #      #    # #    # #    # # # #  # #      
#  #  # #      #    #          # #      #####  ###### #####  # #  # # #  ### 
#  #  # #      #    #    #     # #    # #   #  #    # #      # #   ## #    # 
 ## ##  ###### #####      #####   ####  #    # #    # #      # #    #  ####  
-->

# Advanced Web Scraping
```
This is the rebel approach to data; not downloading it or registering for APIs.
Three main methods: pd.read_html, requests/beautifulsoup, selenium/beautifulsoup
- pd.read_html should be used to read HTML tables into dataframes
- requests should be used to scrape pages that don't use Javascript
- selenium should be used to scrape pages that use Javascript
I should use different examples for each, and incorporate REGEX usage.
The end state of all methods should be an initial dataframe pre-editing.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Pandas Read-HTML
- Use this method if you're working with *HTML tables*; it's easy and effective
- Sample HTML tables (testing): https://www.w3schools.com/html/html_examples.asp
```
import pandas as pd

# read from URL
url = "https://www.w3schools.com/html/tryit.asp?filename=tryhtml_table_headings"
df1 = pd.read_html(url)[0] # read HTML tables from URL, set first table as df1

# read from string
myhtml = "<table><tr><th>hi</th></tr><tr><td>12</td></tr></table>"
df2 = pd.read_html(myhtml)[0] # read HTML tables from string, set first as df2
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Requests
- Use this method if you need to scrape the contents of *static* HTML tags
- Requests grabs the page HTML, BeautifulSoup does the tag scraping
    * Note that any post-HTML loading (ex: Javascript) is not grabbed...
- To build a dataframe: use a sequence of `request.get` calls and build each row
- Beautiful Soup dive: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
```
import requests
from bs4 import BeautifulSoup
import re

def has_class_but_no_id(tag):
    """Get elements with class attribute but no ID attribute"""
    return tag.has_attr('class') and not tag.has_attr('id')

response = requests.get('https://www.duckduckgo.com', verify=True)
if not response.ok:
    print("HTTP status code:", response.status_code)
else:
    soup = BeautifulSoup(response.text)
    print(soup.prettify())

    # select tags
    all_tags = soup.find_all(True)
    all_tags_with_id = soup.find_all(id=True)
    a0 = soup.title
    a1 = soup.a.span              # <span> anywhere within <a>
    a2 = soup.select("a > span")  # <span> directly inside <a>
    a3 = soup.find_all("div", class_="header--aside")
    a4 = soup.find_all(attrs={"class": "search"})
    a5 = soup.find_all(class_=re.compile("logo"))
    a6 = soup.select("div.tag-home.tag-home--slide")                 # AND logic
    a7 = soup.find_all("div", class_=["tag-home.tag","home--slide"]) # OR logic
    a8 = soup.select(".content--home .cw--c .logo-wrap--home a")     # chain dig

    # run function to select tags
    b0 = soup.select(has_class_but_no_id)

    # grab tag attributes
    c0 = soup.a.span["class"]
    c1 = soup.find("link", {"rel":"canonical"})["href"]
    c2 = [ele["class"] for ele in soup.select("span", class_=True)]

    # grab contents of a tag
    d0 = soup.title.text
    d1 = [ele.text for ele in soup.find_all("span")]
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Selenium
- Use this method if you need to scrape the contents of a *dynamic* page
- Selenium stores all loaded page elements, BeautifulSoup does the tag scraping
    * You have to drive the browser through actions; a bit complicated, but good
```
from selenium import webdriver
from selenium.webdriver.common.by import By               # allow By.ID, etc
from selenium.webdriver.common.keys import Keys           # allow Keys.TAB, etc
from selenium.webdriver.support import expected_conditions as EC # detect tag
from selenium.webdriver.support.ui import WebDriverWait   # wait until tag loads
from selenium.webdriver.common.action_chains import ActionChains # script action

# basic page pull with Selenium
PATH = r"C:\Users\Jake\chromedriver.exe"
url = 
driver = webdriver.Chrome(PATH)
driver.get(url)
soup = BeautifulSoup(driver.page_source)

# pause script until a certain ID'd element is loaded
myElem = (
    WebDriverWait(browser, delay)
        .until(EC.presence_of_element_located((By.ID, 'IdOfMyElement')))
)
elements = driver.find_elements_by_xpath('//*[@id="q_all"]')

# run actions
actions = ActionChains(driver)
(
    # click on a dropdown box
    actions
        .move_to_element(
            driver.find_element_by_xpath('//*[@id="q_type"]/div[1]')
        )
        .click()
        .perform()
)
(
    # select option in the clicked dropdown box
    actions
        .move_to_element(
            driver.find_element_by_xpath('//*[@id="q_type"]/div[3]/div[2]')
        )
        .click()
        .perform()
)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Image Download
```
import shutil
r = requests.get(image_url, stream = True)  # stream file to cache
r.raw.decode_content = True                 # ensure binary is decoded on write
with open('image.jpeg','wb') as f:          # write from binary
    shutil.copyfileobj(r.raw, f)            # shutil writes to image.jpeg
```

[[Return to Top]](#table-of-contents)







<!-- 
######                                                   
#     # #    # # #      #####  # #    #  ####       ##   
#     # #    # # #      #    # # ##   # #    #     #  #  
######  #    # # #      #    # # # #  # #         #    # 
#     # #    # # #      #    # # #  # # #  ###    ###### 
#     # #    # # #      #    # # #   ## #    #    #    # 
######   ####  # ###### #####  # #    #  ####     #    # 
                                                         
######                                                  
#     #   ##   #####   ##   #####    ##    ####  ###### 
#     #  #  #    #    #  #  #    #  #  #  #      #      
#     # #    #   #   #    # #####  #    #  ####  #####  
#     # ######   #   ###### #    # ######      # #      
#     # #    #   #   #    # #    # #    # #    # #      
######  #    #   #   #    # #####  #    #  ####  ###### 
-->

# Building a Database
```
After data is acquired, a good option is storing it in a local database.
SQLite and PostgreSQL are popular options for local DB work and should be shown.
Both sections should be structured as an example with DB design tips throughout.
The end state of both explanations should be a "SELECT *"-style return (to DF).
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## SQLite
- Lightweight database that can be operated with Python
    * https://docs.python.org/3/library/sqlite3.html
    * https://docs.python.org/3/library/sqlite3.html#sqlite-and-python-types
    * https://docs.python.org/3/library/sqlite3.html#cursor-objects
- Creating tables: https://www.sqlite.org/lang_createtable.html
    * CREATE VIEW/INDEX work as expected; use PRAGMA to find table indices
- ALTER TABLE can rename a table or add columns; no col rename/remove/constrain
- UNSIGNED/SIGNED don't seem to do anything...
- Referential Integrity Violation Constraints are supported!
- There's no `TRUNCATE TABLE t1`; use this for SQLite: `DELETE FROM t1;`
```
# create a db
import sqlite3
con = sqlite3.connect("cool.db")
cur = con.cursor()

cur.execute("DROP TABLE IF EXISTS test")
cur.execute("DROP TABLE IF EXISTS author")
cur.execute("DROP TABLE IF EXISTS book")
cur.execute("DROP TABLE IF EXISTS publisher")

# set up row returns as dicts rather than tuples
def dict_factory(cur, row):
    fields = [column[0] for column in cur.description]
    return {key: value for key, value in zip(fields, row)}

# execute statements for the db
cur.execute("""
CREATE TABLE test(
    greeting CHAR(50) PRIMARY KEY NOT NULL, 
    number INT UNIQUE DEFAULT 5, 
    letter CHAR(1) CHECK(letter != "f"))
""")
data = [("hi", 15, "a"),("yo", 22, "b"),("sup", 8, "c"),("hey",19,"d")]
cur.executemany("INSERT INTO test VALUES(?, ?, ?)", data)
cur.execute("UPDATE test SET number = 1000 WHERE rowid = 3")
cur.execute("DELETE FROM test WHERE letter = "d")
# con.rollback() # use this if you need to abort the transaction
con.commit() # do this after inserts
con.row_factory = dict_factory
for row in con.execute("SELECT greeting, number, letter FROM test"):
    print(row)

# run a script of SQL statements
cur.executescript("""
    BEGIN;
    CREATE TABLE author(authorid PRIMARY KEY, firstname, lastname, age);
    CREATE TABLE book(
        bookid PRIMARY KEY, title, authorid, pubid, 
        FOREIGN KEY(authorid) REFERENCES author(authorid) ON DELETE CASCADE, 
        FOREIGN KEY(pubid) REFERENCES publisher(pubid) ON DELETE SET NULL);
    CREATE TABLE publisher(pubid PRIMARY KEY, name, address);
    COMMIT;
""")

# show changes are saved to the DB
con.close()
print("\nConnection closed; reopening...")
new_con = sqlite3.connect("cool.db")
new_cur = new_con.cursor()
result1 = new_cur.execute("SELECT rowid, greeting FROM test ORDER BY rowid")
rowid1, greeting1 = result1.fetchone()
print(f"Row {rowid1} greets you: {greeting1}!")
rowid2, greeting2 = result1.fetchone()
print(f"Row {rowid2} greets you: {greeting2}!")
rowid3, greeting3 = result1.fetchone()
print(f"Row {rowid3} greets you: {greeting3}!")

new_cur.execute("DELETE FROM test") # this is TRUNCATE TABLE
new_con.close()

import os
os.remove("cool.db")
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## PostgreSQL
- PostgreSQL is best operated with a GUI like pgAdmin
    * Can view multiple DBs' structure and use command line / statement runner
- `SHOW` is `\l`, `USE` is `psql -d mydb`, `DESCRIBE` is `\d` or `\dt`
- Call stored procedure: `CALL procedure_name(10000, 429);`
### PostgreSQL via CMD
- https://github.com/TrainingByPackt/SQL-for-Data-Analytics/tree/master/Datasets
    * Get "data.dump" from here for CMD example
- COPY operation: https://www.postgresql.org/docs/current/sql-copy.html
    * Consider doing CREATE VIEW before ETL then doing `COPY view_table TO...`
```
>>>createuser -s postgres
>>>createdb -U postgres sqlda
>>>\l
>>>\q
>>>psql -U postgres
>>>psql -U postgres -d sqlda -f data.dump
>>>\d
>>>\dt
>>>\q
>>>\copy table1 TO 'filepath/file.csv' WITH DELIMITER ',' CSV;
>>>\copy (SELECT DISTINCT ON (col1) col1, col2 FROM t1) TO STDOUT;
```
### Create Stored Procedure
```
CREATE OR REPLACE PROCEDURE procedure_name(IN val1 INT, IN val2 INT)
    BEGIN
        UPDATE col1
        SET col1 = col1 + val1
        WHERE col2 = val2;

        INSERT INTO col3 VALUES (TRUE, val1, val2);

        COMMIT;

        EXCEPTION WHEN OTHERS THEN
        ROLLBACK;
    END;
$ LANGUAGE plpgsql;
```

[[Return to Top]](#table-of-contents)







<!-- 
######                                                     #     #               
#     #   ##   #####   ##   #####    ##    ####  ######    #     #  ####  ###### 
#     #  #  #    #    #  #  #    #  #  #  #      #         #     # #      #      
#     # #    #   #   #    # #####  #    #  ####  #####     #     #  ####  #####  
#     # ######   #   ###### #    # ######      # #         #     #      # #      
#     # #    #   #   #    # #    # #    # #    # #         #     # #    # #      
######  #    #   #   #    # #####  #    #  ####  ######     #####   ####  ###### 
                                                                                 
#     #                                         
##   ##   ##    ####  ##### ###### #####  #   # 
# # # #  #  #  #        #   #      #    #  # #  
#  #  # #    #  ####    #   #####  #    #   #   
#     # ######      #   #   #      #####    #   
#     # #    # #    #   #   #      #   #    #   
#     # #    #  ####    #   ###### #    #   #   
                                                
-->

# Database Usage Mastery
```
Querying a database is just as important as establishing one.
Each database format has its own syntax/peculiarities which should be explained.
Query differences should be demo'd thoroughly on a common dataset, if possible.
The end state should be a dataframe that matches across query formats.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## SQL and Variants
- SQL has many variants; each has its own syntax, use their documentation!
- SQL is five languages: Definition, Manipulation, Query, Control, Transaction
    * Data Definition Language (DDL): creating database objects (tables, users)
    * Data Manipulation Language (DML): database contents work ("CUD" of CRUD)
    * Data Query Language (DQL): "SELECT" statements (DML handles FROM/WHERE)
    * Data Control Language (DCL): controls account accesses
    * Data Transaction Language (DTL): governs transactions (multi-queries)
- SQL databases are usually hosted on beefy systems; use SQL as much as possible
- Sequel ACE: Excellent GUI for SQL database reads and querying
### SQL Column Operations
- String cleaning: `UPPER('hi')`, `LOWER("HI")`, `TRIM("  sup  ")`
- String replacement: `REPLACE("Hey", "e", "a")`, `SUBSTRING("Hello", 1, 3)`
- Concatenate each col's string into one col: `CONCAT(str_col1, str_col2, ...)`
- Get current datetime: `CURDATE()`, `CURTIME()`, `NOW()` (date, time, datetime) 
- Date work: `DATE("2011-01-01 01:01:01")`, and `DAY()`, `MONTH()`, `YEAR()`
- Time work: `TIME("2011-01-01 01:01:01")`, and `HOUR()`, `MINUTE()`, `SECOND()`
- Difference in date / time: `DATEDIFF(early, late)`, `TIMEDIFF(early, late)`
### SQL Table Operations
- Left join: `SELECT * FROM left_t LEFT JOIN right_t ON left_t.id = right_t.id;`
- Right: `SELECT * FROM right_t RIGHT JOIN left_t ON right_t.id = left_t.id;`
- Cross: `SELECT * FROM a CROSS JOIN b;` (all possible combinations of a and b)
- Non-equijoin: `SELECT * FROM a, b WHERE a.value > b.value;`
- Union w/o duplicates: `SELECT x FROM t1 UNION SELECT x FROM t2`
    * Great for "all people" queries ex: first/last name from 2+ tables
- Union w/ duplicates: `SELECT x FROM t1 UNION ALL SELECT x FROM t2`
### Specific Use Cases
- `SELECT SUM(CASE WHEN col1 IS NULL THEN 1 ELSE 0 END)::FLOAT/COUNT(*) FROM t1`
    * Determine % null in column
- `SELECT COUNT(DISTINCT col1) FROM table;` NUNIQUE
- `SELECT COUNT(DISTINCT col1) = COUNT(*) AS is_all_unique;`
    * Return one value, True/False, if nunique == rowcount
- `SELECT PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY col1) AS median;`
    * Continuous values; also PERCENTILE_DISC (discrete values)
    * This syntax is also used for MODE()
- `SELECT c1, c2, COUNT(*) FROM t1 GROUP BY GROUPING SETS ((c1),(c2),(c1,c2));`
    * Basically a UNION of the three columns
### SQL Simple Records Query
```
show databases; 
use database_name; 
show tables; 
describe table_name;
select distinct                                    -- distinct: unique **rows**
    date_col, 
    col1 as Col1,                                  -- rename col1 to Col1
    col2::INTEGER,                                 -- cast col2 as INTEGER col
    col3::TEXT,                                    -- cast col3 as TEXT column
IF(date_col > curdate(), True, False) as "Future"  -- new column with True/False
case 
    when year(date_col) like '19__' then '1900s'   -- if 19xx then "1900s"
    when year(date_col) like '20%' then '2000s'    -- if 20... then "2000s"
    else 'bad_input'                               -- otherwise "bad_input"
    end as Century                                 -- end case, name column
from table_name 
join table_2 using(date_col)                       -- cleaner than ON sometimes
where
    (col2 between 10 and 20) and                   -- 10 <= x <= 20
    (col2 not 15) and                              -- x != 15
    (col3 in ('irene', 'layla')) and               -- y = "irene" or y = "layla"
    (year(date_col) like binary '201_')            -- 2010, 201M, 201., 201#
order by col2 asc, Col1 desc                       -- notice renamed Col1 here
limit 100;                                         -- return max of 100 rows
SELECT
    COALESCE(col1, "No Value!!!"),  -- Fill nulls with "No Value!!!"
    NULLIF(col1, "wat"),            -- Null-out all "wat" values in col1
    LEAST(100, col2),               -- Same as col2 <= 100
    GREATEST(100, col2)             -- Same as col2 >= 100
FROM t1;
```
### SQL Aggregation Query
- `COUNT`, `MIN`, `MAX`, `RAND`
- `SUM`, `AVG`, `ABS`, `LOG`, `POW(x, y)`, `ROUND(n, decimal_places)`, `SQRT(n)`
```
select SUM(x) + SUM(y) from table; -- sum x, sum y, then sum totals; nulls fine
select SUM(x + y);                 -- rowwise sum; CAREFUL, NULL + 100 = NULL
select MAX(x);
select col1, AVG(col2) as average from table group by col1 having average > 100;
SELECT x, MAX(y) FROM t GROUP BY x ORDER BY MAX(y); -- notice: ORDER BY MAX(y)
SELECT a, b, MAX(c) FROM t GROUP BY a, b HAVING MAX(c) > 100 ORDER BY a, MAX(c);
SELECT a, b, c FROM t AS f WHERE c > ( -- Where c is higher than...
    SELECT AVG(c) FROM t WHERE b = f.b -- ...average of c for each b category.
);
```
### SQL Subquery
- Typically done with either an operator (`>`, `<`, `=`, etc), `IN`, or `EXISTS`
    * Consider these your three options for subqueries
```
WITH d AS (SELECT * FROM t1 WHERE t1.a = 12)       -- create table "d" up front
SELECT * FROM t2 JOIN d.a = t2.a;

select concat(first_name, " ", last_name) as Name 
from employees 
where 
    hire_date = (select hire_date from employees where emp_no = 101010) and
	emp_no in (select emp_no from dept_emp where to_date > curdate()) and
    last_name is not null;

SELECT Name, CountryCode
FROM City AS C
WHERE EXISTS      -- Rows that match; use WHERE NOT EXISTS to find non-matches
(
    SELECT * 
    FROM CountryLanguage
    WHERE CountryCode = C.CountryCode   -- Outer table's cols available/selected
        AND Percentage > 97
);
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Spark
- Computational clustering for big data processing
    * Velocity (fast gathering, lots of data, streaming)
    * Volume (large data, bigger than memory or bigger than storage)
    * Veracity (reliability of data, esp. missing data)
    * Variety (different sources, unstructured data, data isn't uniform)
- Java Virtual Machine (JVM) coordinates clusters using Scala
- The 'pyspark' library translates Python to Scala and operates the JVM
- Can run 100% locally; it will coordinates computer cores
    * This is often overkill for one-computer tasks
- Is 'lazy'- adds to / optimizes queries until the execution order is given
- Alternatives: Hadoop, Dask
### Spark Commands
- Check Spark's intentions before query: `df.explain()`
    * Used for diagnosing performance issues; operation order from bottom-upward
- Switch to SQL: `df.createOrReplaceTempView('df')`
    * Run SQL statements: `spark.sql(''' SELECT * FROM df ''')`
- Build schema: `schema = StructType([(StructField(...), StructField(...)),])`
    * StructField syntax: `Structfield("col1", StringType())`
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
df.select(
    [count(when(isnan(c) | col(c).isNull(), c)).alias(c) for c in df.columns]\
).show(vertical=True)
# FILL, DROP NULLS
df = df.na.fill(0, subset=['x', 'y']).na.drop()
# CHECK DTYPES
df.printSchema()
# DTYPE, NAME CHANGES
df = df.withColumn('ordinals', df.x.cast('string'))\
.withColumnRenamed("colname_before", "colname_after")
# TO DATETIME, TO MONTH
df = df.withColumn("col1", month(to_timestamp("col1", "M/d/yy H:mm")))
# DATEDIFF
df = df.withColumn("date_calc_col", datediff(current_timestamp(), "datecol"))
# REGEX
df = df.withColumn('repl', regexp_replace(df.x, re, repl)\
.withColumn('substr', regexp_extract(df.col, re, g)))
# STRING WHITESPACE, FORMATTING
df = df.withColumn("c1", trim(lower(df.c1)))\
.withColumn("c1", format_string("%03d", col("c1").cast("int")),)
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
trn, val, test = df.randomSplit([0.6, 0.2, 0.2], seed=42)
# RUN ALL, SAVE LOCALLY
df.write.json("df_json", mode="overwrite")
trn.write.format("csv").mode("overwrite").option("header", "true").save("train")
val.write.format("csv").mode("overwrite").option("header", "true").save("val")
test.write.format("csv").mode("overwrite").option("header", "true").save("test")
```
### Spark Aggregation Example
```
# COLUMN CALCULATION
x_y = df.select(sum(df.x)), df.select(mean(df.x))
# VALUE COUNT TWO COLUMNS, WITH PROPORTIONS COLUMN
value_counts = df.groupBy('col','target').count().sort('count',ascending=False)\
.withColumn('proportion', round(col('count') / df.count(), 2))
# AGG GROUPBY
mean_min = df.groupBy('gb').agg(mean(df.x), min(df.y))
# CROSSTAB
crosstab = df.crosstab('g1', 'g2')
# PIVOT TABLE
mean_x_given_g1_g2 = df.groupBy('g1').pivot('g2').agg(mean('x'))
```
### Spark Machine Learning Example
```
from pyspark.ml.stat import ...    # chi square / correlation testing
from pyspark.ml.feature import ... # imputation, encoding, scaling, vectorize...
from pyspark.ml.classification import ... # modeling
from pyspark.ml.regression import ...     # modeling
from pyspark.ml.clustering import ...     # modeling
from pyspark.ml.tuning import ...         # model cross-validation
from pyspark.ml.evaluation import ...     # model evaluation
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Elasticsearch
- Popular SIEM system
- Python interacts with the Elasticsearch REST API on port 9200 (default)
- To connect: create an account in Kibana and use those creds in Python queries
- Elasticsearch-DSL makes API calls much easier
```
def flatten_json(json_input, splitout_lists=False):
    """
    Recursively-flatten a nested dictionary (JSON) using dot separators.
    - Input: {"hi":{"yo":{"odd":99}, "sup":25}, "what":44}
    - Output: {"hi.yo.odd":99, "hi.sup":25, "what":44}
    Can choose whether lists are stored in a cell or split out across columns.
    :param json_input: Python nested dictionary
    :param splitout_lists: Python bool indicating whether to split lists to cols
    :return: flattened Python dictionary
    """
    output_dict = {}
    def flatten(current_structure, name=""):
        """Flatten and assign to output dict"""
        if type(current_structure) is dict:
            # loop vertically (key -> value)
            for element in current_structure:
                flatten(current_structure[element], name + element + ".")
        elif type(current_structure) is list:
            if splitout_lists in [True, "True", "true", "Yes", "yes", "sure"]:
                # add new column for each element of a list (true flatten)
                for i, element in enumerate(current_structure):
                    flatten(element, name + str(i) + "_")
            else:
                # assign list as a single value (partial flatten)
                output_dict[name[:-1]] = current_structure
        else:
            # add flattened value to output, return to parent loop
            output_dict[name[:-1]] = current_structure
    # execute recursion
    flatten(json_input)
    return output_dict

def print_progress(i):
    """Pretty-print the number of returned records; i is current number"""
    if i < 1_000_000 and i % 1_000 == 0 and i != 0:
        print(f"{i // 1_000}k records found...", end="\r", flush=True)
    elif i % 10_000 == 0 and i != 0:
        print(f"{i / 1_000_000}mil records found...", end="\r", flush=True)

def query_the_stack(query_object, return_count=None):
    """
    Send an Elasticsearch query to the stack.
    Query object should be an Elasticsearch-DSL "Search" object.
    - EX: Search(using=Elasticsearch(), index="index_pattern", doc_type="doc")
    - EX: Search(...).query("match", event__module="sysmon")
    Can choose how many records are returned by setting return_count to an int.
    - EX: Settng this to 41 limits results to 41 records
    :param query_object: Prepared elasticsearch-dsl Search object
    :param return_count: Optional integer to limit returns
    :return: pandas DataFrame where JSON fields are flattened w/ dot separation
    """
    response = query_object.execute()
    if not response.success(): 
        print("Failed to connect!")
        return None
    rows = []
    for i, d in enumerate(query_object.scan()):
        if i == return_count:
            break
        print_progress(i)
        obj = d.to_dict()
        row = flatten_json(obj)
        del obj
        rows.append(row)
        del row
    print("Total records found:", "{:,}".format(i))
    if len(rows) == 0:
        return None
    df = pd.DataFrame(rows)
    del rows
    return df
```
```
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search, Q
import elk_basics    # these are the functions defined above in the notes
from env import ip, user, password

client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
search_context = Search(using=client, index="index_pattern", doc_type="doc")
s = search_context.query("match", winlog__event_id=4624)
df = elk_basics.query_the_stack(s, 10000)
```

[[Return to Top]](#table-of-contents)







<!-- 
#######                                                                         
   #    #####    ##   #    #  ####  ######  ####  #####  #    # # #    #  ####  
   #    #    #  #  #  ##   # #      #      #    # #    # ##  ## # ##   # #    # 
   #    #    # #    # # #  #  ####  #####  #    # #    # # ## # # # #  # #      
   #    #####  ###### #  # #      # #      #    # #####  #    # # #  # # #  ### 
   #    #   #  #    # #   ## #    # #      #    # #   #  #    # # #   ## #    # 
   #    #    # #    # #    #  ####  #       ####  #    # #    # # #    #  ####  
                                                                                
#######                                                 
#       ######   ##   ##### #    # #####  ######  ####  
#       #       #  #    #   #    # #    # #      #      
#####   #####  #    #   #   #    # #    # #####   ####  
#       #      ######   #   #    # #####  #           # 
#       #      #    #   #   #    # #   #  #      #    # 
#       ###### #    #   #    ####  #    # ######  ####  
-->

# Feature Transformation
```
Once a dataframe is established, data cleaning and engineering begins.
There are a variety of goals for this work, but goals share common methods.
Topics: Data structure normalization, cell work, string/number vectorization
- Normalization: melt/dummies, merge/join/concat, nulls/imputation
- Cell work: masks (incl. REGEX), loc, fast find, fast sort, apply/applymap
- String work: str methods, REGEX capture
- Number work: calculations, cut/bins, scaling
Other data structures like linked lists and hash tables can be useful too.
Explanations here shouldn't go any further than feature engineering.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Dataframe Normalization
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Fixing Dataframes at Speed
- 
```
# watch the speed of an `apply` operation
from tqdm import tqdm
tqdm.pandas()
df = pd.DataFrame([{"hi":1, "yo":5}] * 1_000_000)
(
    df["hi"].progress_apply(lambda x: x * 100),
    df.progress_apply(lambda x: x[0] * x[1], axis=1)
)

# check the size of an object
print(df.__sizeof__())
```
### Bounties
- Memory efficient dataframe write from list of dict
    * Writing to lists is fast because Python lists are mutable in memory
    * `.pop(0)` doesn't reduce memory use on each pop, but it does interval to 0
### Discoveries
- `[df for df in dfs if "hi" in df and "yo" in df if not df["hi"].isna().all()]`
    * `if` statements "gate" additional ones; "hi" must be in df for second `if`

--------------------------------------------------------------------------------
<!-- Needs work -->
## Feature Engineering
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Speedy Data Structures

### Leads
- Potential

[[Return to Top]](#table-of-contents)







<!-- 
   #                                                               
  # #   #       ####   ####  #####  # ##### #    # #    # #  ####  
 #   #  #      #    # #    # #    # #   #   #    # ##  ## # #    # 
#     # #      #      #    # #    # #   #   ###### # ## # # #      
####### #      #  ### #    # #####  #   #   #    # #    # # #      
#     # #      #    # #    # #   #  #   #   #    # #    # # #    # 
#     # ######  ####   ####  #    # #   #   #    # #    # #  ####  
                                                                   
 #####                                                           
#     # #      #    #  ####  ##### ###### #####  # #    #  ####  
#       #      #    # #        #   #      #    # # ##   # #    # 
#       #      #    #  ####    #   #####  #    # # # #  # #      
#       #      #    #      #   #   #      #####  # #  # # #  ### 
#     # #      #    # #    #   #   #      #   #  # #   ## #    # 
 #####  ######  ####   ####    #   ###### #    # # #    #  ####  
-->

# Algorithmic Clustering
```
Engineered features can go through clustering to establish new features.
The number of clusters is determined through three main methods:
- Domain Knowledge (three classes)
- Elbow Method (compare inertias for a range of cluster numbers)
- PCA (find clusters and "explainer" features using signal-noise ratio)
Popular clustering methods: K-Means, Hierarchical, and DBSCAN.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Selecting Number of Clusters
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Clustering Methods
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Cluster Analysis
- 

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                          
##    #   ##   ##### #    # #####    ##   #      
# #   #  #  #    #   #    # #    #  #  #  #      
#  #  # #    #   #   #    # #    # #    # #      
#   # # ######   #   #    # #####  ###### #      
#    ## #    #   #   #    # #   #  #    # #      
#     # #    #   #    ####  #    # #    # ###### 
                                                 
#                                                        
#         ##   #    #  ####  #    #   ##    ####  ###### 
#        #  #  ##   # #    # #    #  #  #  #    # #      
#       #    # # #  # #      #    # #    # #      #####  
#       ###### #  # # #  ### #    # ###### #  ### #      
#       #    # #   ## #    # #    # #    # #    # #      
####### #    # #    #  ####   ####  #    #  ####  ###### 
                                                         
######                                                            
#     # #####   ####   ####  ######  ####   ####  # #    #  ####  
#     # #    # #    # #    # #      #      #      # ##   # #    # 
######  #    # #    # #      #####   ####   ####  # # #  # #      
#       #####  #    # #      #           #      # # #  # # #  ### 
#       #   #  #    # #    # #      #    # #    # # #   ## #    # 
#       #    #  ####   ####  ######  ####   ####  # #    #  ####  
-->

# Natural Language Processing
```
String-type fields can be normalized to identify trends in words.
This is largely pipelined via tokenization and stem/lemmatization.
The results of NLP can be used to identify keywords and sentiment.
NLP's "bag of words" works nicely in conjunction with classification.
```
- NEED: Bring in notes from https://github.com/lets-talk-codeup/github-guesser
- NLTK: https://www.nltk.org/index.html

--------------------------------------------------------------------------------
<!-- Needs work -->
## Normalizing String Features
### Normalizing for Keyword Analysis
- NEED: Vectorized method for performing this cleaning work
    * NOTE: Add ngram compilation to this
```
import nltk
nltk.download('stopwords')
nltk.download('vader_lexicon')
nltk.download('punkt')
word_tokenizer = nltk.tokenize.toktok.ToktokTokenizer()
ps = nltk.porter.PorterStemmer()
wnl = nltk.stem.WordNetLemmatizer()
stopword_list = nltk.corpus.stopwords.words("english")
# stopword_list.append('word')
# stopword_list.remove('word')
import unicodedata
import re

# t = df["text"].str.cat(sep=' ')
t = "Hey there! How's it going?"
t = t.lower()
t = unicodedata.normalize('NFKD', t).encode('ascii', 'ignore').decode('utf-8')
t = re.sub(r"[^a-z0-9'\s]", "", t)                       # rm special chars
words = tokenizer.tokenize(t, return_str = True)         # word tokenization

stem_instead = False
if stem_instead:
    # stems of words; cheap on computations
    words = [ps.stem(word) for word in t.split()]
else:
    # lemmatized words; expensive but accurate
    words = [wnl.lemmatize(word) for word in t.split()]     

filtered_words = [word for word in words if word not in stopword_list]
clean_text = " ".join(filtered_words)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Keywords and Sentiment
### Keyword Analysis
- NEED: Bring in word cloud example from http://amueller.github.io/word_cloud/
```
# scatterplot of each row's char count by word count
df["content_length"] = df["text"].apply(len)
df["word_count"] = df["text"].split().apply(len)
sns.relplot(df["content_length"], df["word_count"], hue=df["target"])
# stacked bar chart of class proportions by word (PERFORM NORMALIZATION FIRST)
all_words = df["clean"].str.cat(sep=" ")
all_cts = pd.Series(all_words.split(" ")).value_counts().rename("all")
spam_words = df[df["target"] == "spam"]["clean"].str.cat(sep=" ")
spam_cts = pd.Series(spam_words.split(" ")).value_counts().rename("spam")
ham_words = df[df["target"] == "ham"]["clean"].str.cat(sep=" ")
ham_cts = pd.Series(ham_words.split(" ")).value_counts().rename("ham")
word_counts = pd.concat([all_cts, spam_cts, ham_cts], axis=1)
word_counts['p_spam'] = word_counts["spam"] / word_counts["all"]
word_counts['p_ham'] = word_counts["ham"] / word_counts["all"]
(
    word_counts[['p_spam','p_ham']]
        .tail(20)
        .sort_values(by='p_ham')
        .plot.barh(stacked=True)
)
```
### Sentiment Analysis
- Afinn and Vader are sentiment analysis tools based on social media
- Sentiment is best analyzed without normalization
```
# singular sentiment analysis
import nltk
from nltk.sentiment import SentimentIntensityAnalyzer
sia = SentimentIntensityAnalyzer()
text = "Hello my name is Bob. You look great!"
sentences = nltk.sent_tokenize(text)
scores = [sia.polarity_scores(sentence) for sentence in sentences]
print(scores)
```
```
# vectorized sentiment analysis
(
    pd.DataFrame({"text":[
        "Hello my name is Bob. You look great!",
        "My name is Bob too! How weird..."
    ]})
    ["text"]
        .apply(nltk.sent_tokenize)
        .apply(lambda sentences: [
            sia.polarity_scores(sentence) for sentence in sentences
        ])
)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## NLP for Prediction
- NEED: Apply SelectKBest or RFE to select most-predictive words for outcomes
- Count Vectorization: 
    * Each column is a word, each row is an record, each value is a **count**
- TFIDF Vectorization (Term Frequency * Inverse Document Frequency): 
    * Each column is a word, each row is an record, each value is a **weight**
    * TF is how often a word shows; IDF is how unique the word is in all records
    * Calculation identifies word importance (weight) and filters out stopwords
```
# perform prep and split before following the steps
do_CV = False
if do_CV:
    # Count Vectorization
    vectorizer = sklearn.feature_extraction.text.CountVectorizer()
    bow = vectorizer.fit_transform(train.clean_text)        # use y_train
    print(vectorizer.vocabulary_)                           # show word counts
else:
    # TFIDF Vectorization
    vectorizer = sklearn.feature_extraction.text.TfidfVectorizer()
    bow = vectorizer.fit_transform(train["clean_text"])     # use y_train
    bow = pd.DataFrame(bow.todense(), columns=vectorizer.get_feature_names())
    word_imps = dict(zip(vectorizer.get_feature_names(), vectorizer.idf_))
    print(pd.Series(word_importances).sort_values())        # show importances
# Decision Tree
tree = DecisionTreeClassifier(max_depth=5)
tree.fit(bow, y_train)
y_train_preds = tree.predict(bow)
features = dict(zip(vectorizer.get_feature_names(), tree.feature_importances_))
print(pd.Series(features).sort_values().tail(5))            # top-5 features
```

[[Return to Top]](#table-of-contents)







<!-- 
###                                     
 #  #    #  ####  #  ####  #    # ##### 
 #  ##   # #      # #    # #    #   #   
 #  # #  #  ####  # #      ######   #   
 #  #  # #      # # #  ### #    #   #   
 #  #   ## #    # # #    # #    #   #   
### #    #  ####  #  ####  #    #   #   
                                        
######                                             
#     # ###### #      # #    # ###### #####  #   # 
#     # #      #      # #    # #      #    #  # #  
#     # #####  #      # #    # #####  #    #   #   
#     # #      #      # #    # #      #####    #   
#     # #      #      #  #  #  #      #   #    #   
######  ###### ###### #   ##   ###### #    #   #   
-->

# Insight Delivery
```
Delivery of findings is key to project success.
Hypothesis testing and statistical analysis is complex, but it can be pipelined.
Good visualizations speak for themselves and you can template them for reuse.
Jupyter notebooks are optimal for report delivery and should be mastered.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Statistical Analysis
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Visualizations
### Dataframe Styling
```
print(df.to_markdown(tablefmt="grid"))
print(df.style.to_latex())
latex = df.style.set_table_styles([
    {"selector": "toprule", "props":":hline;"},
    {"selector": "midrule", "props":":hline;"},
    {"selector": "bottomrule", "props":":hline;"}]
).to_latex(column_format="|l|l|l|")
print(latex)
```
- `df.style.format({"col1": str.lower, "col2": "${:.1f}"}), na_rep="MISSING")`
- `df.style.background_gradient()` applies a default, can choose cmaps
```
def highlight_number(row):
    return [
        "background-color: red; color: white"
        if cell <= 0
        else "background-color: green; color: white"
        for cell in row
    ]
    styl
df.style.apply(highlight_number)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Magic in Jupyter
- 

[[Return to Top]](#table-of-contents)







<!-- 
 ####                                                                             
#    # #       ##    ####   ####  # ###### #  ####    ##   ##### #  ####  #    # 
#      #      #  #  #      #      # #      # #    #  #  #    #   # #    # ##   # 
#      #     #    #  ####   ####  # #####  # #      #    #   #   # #    # # #  # 
#      #     ######      #      # # #      # #      ######   #   # #    # #  # # 
#    # #     #    # #    # #    # # #      # #    # #    #   #   # #    # #   ## 
 ####  ##### #    #  ####   ####  # #      #  ####  #    #   #   #  ####  #    # 
-->

# Classification
```
Predicting outcomes and states of unseen data using trained models.
Features are chosen for modeling via chi2 tests, t-tests, SelectKBest/RFE
Training data includes "the answers" and can be resampled.
Model evaluation is important and done in two stages: validate and test.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Features for Classification
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Training Classifiers
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Evaluating Classifiers
- 

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
```
Predicting a numerical value for unseen data using trained models.
Features are chosen for modeling via correlation tests, t-tests, SelectKBest/RFE
Training data includes "the answers"; all data (incl. unseen) should be scaled.
Model evaluation is important and done in two stages: validate and test.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Features for Regression
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Training Regressors
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Evaluating Regressors
- 

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
```
Understanding previous trends and their anomalies to do various things.
You can calculate several metrics for time series data; monthly/weekly/daily/...
Generally, you're tracking one numerical feature over a time axis with plots.
Modeling varies from using past data with adjustment to actual trainable models.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Metrics of Time Series
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Outcome Plotting
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Time Series Modeling
- 

[[Return to Top]](#table-of-contents)







<!-- 
   #                                             
  # #   #    #  ####  #    #   ##   #      #   # 
 #   #  ##   # #    # ##  ##  #  #  #       # #  
#     # # #  # #    # # ## # #    # #        #   
####### #  # # #    # #    # ###### #        #   
#     # #   ## #    # #    # #    # #        #   
#     # #    #  ####  #    # #    # ######   #   
                                                 
######                                                   
#     # ###### ##### ######  ####  ##### #  ####  #    # 
#     # #        #   #      #    #   #   # #    # ##   # 
#     # #####    #   #####  #        #   # #    # # #  # 
#     # #        #   #      #        #   # #    # #  # # 
#     # #        #   #      #    #   #   # #    # #   ## 
######  ######   #   ######  ####    #   #  ####  #    # 
-->

# Anomaly Detection
```
Finding outliers in data as the goal.
Metrics are the main way of determining anomalies.
Getting to the number for a metric can be simple or fairly complicated.
Baselining a dataset to find anomalies in unseen data requires a careful hand.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Anomalic Metrics
- Calculate many metrics and do clustering!

--------------------------------------------------------------------------------
<!-- Needs work -->
## Getting to the Numbers
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Baselines and Deviation
- 

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                    
##    # ###### #    # #####    ##   #      
# #   # #      #    # #    #  #  #  #      
#  #  # #####  #    # #    # #    # #      
#   # # #      #    # #####  ###### #      
#    ## #      #    # #   #  #    # #      
#     # ######  ####  #    # #    # ###### 
                                           
#     #                                                 
##    # ###### ##### #    #  ####  #####  #    #  ####  
# #   # #        #   #    # #    # #    # #   #  #      
#  #  # #####    #   #    # #    # #    # ####    ####  
#   # # #        #   # ## # #    # #####  #  #        # 
#    ## #        #   ##  ## #    # #   #  #   #  #    # 
#     # ######   #   #    #  ####  #    # #    #  ####  
-->

# Neural Networks
```
When you don't have the capacity to do regular ML, you use neural networks.
Neural networks have special setup, so instructions would be nice to have.
Neural Networks are especially great for image and audio classification.
Deep learning leverages multiple neural networks; I might explain it, IDK yet.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Establishing a Neural Network
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Image Classification
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Deep Learning
- 

[[Return to Top]](#table-of-contents)







<!-- 
#     #                             
##   ##  ####  #####  ###### #      
# # # # #    # #    # #      #      
#  #  # #    # #    # #####  #      
#     # #    # #    # #      #      
#     # #    # #    # #      #      
#     #  ####  #####  ###### ###### 
                                    
######                                                               
#     # ###### #####  #       ####  #   # #    # ###### #    # ##### 
#     # #      #    # #      #    #  # #  ##  ## #      ##   #   #   
#     # #####  #    # #      #    #   #   # ## # #####  # #  #   #   
#     # #      #####  #      #    #   #   #    # #      #  # #   #   
#     # #      #      #      #    #   #   #    # #      #   ##   #   
######  ###### #      ######  ####    #   #    # ###### #    #   #   
-->

# Model Deployment
```
Once a model is trained and evaluated, we can deploy it.
A Flask application is fine if you just need model I/O and basic UI.
You can use Django if your application needs a wide range of functionality.
Docker, Kubernetes, and Kafka have handling considerations that should be noted.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Building a Flask App
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Building a Django App
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Deploying the Model
- 

[[Return to Top]](#table-of-contents)







<!-- 
######                                           
#     # #####   ####       # ######  ####  ##### 
#     # #    # #    #      # #      #    #   #   
######  #    # #    #      # #####  #        #   
#       #####  #    #      # #      #        #   
#       #   #  #    # #    # #      #    #   #   
#       #    #  ####   ####  ######  ####    #   
                                                 
#     #                                                               
##   ##   ##   #    #   ##    ####  ###### #    # ###### #    # ##### 
# # # #  #  #  ##   #  #  #  #    # #      ##  ## #      ##   #   #   
#  #  # #    # # #  # #    # #      #####  # ## # #####  # #  #   #   
#     # ###### #  # # ###### #  ### #      #    # #      #  # #   #   
#     # #    # #   ## #    # #    # #      #    # #      #   ##   #   
#     # #    # #    # #    #  ####  ###### #    # ###### #    #   #   
-->

# Project Management
```
It's important to note how projects work from a management perspective.
Project planning is vital to project success and can't be overestimated.
There are a lot of common project management frameworks and interpretations.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Planning a Project
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Selecting the Framework
- 

[[Return to Top]](#table-of-contents)







<!-- 
######                                              
#     # #    #  ####  # #    # ######  ####   ####  
#     # #    # #      # ##   # #      #      #      
######  #    #  ####  # # #  # #####   ####   ####  
#     # #    #      # # #  # # #           #      # 
#     # #    # #    # # #   ## #      #    # #    # 
######   ####   ####  # #    # ######  ####   ####  
                                                    
#######                             
   #     ####   ####  #       ####  
   #    #    # #    # #      #      
   #    #    # #    # #       ####  
   #    #    # #    # #           # 
   #    #    # #    # #      #    # 
   #     ####   ####  ######  ####  
-->

# Tools and Languages
```
Businesses like their tools... we should know the popular ones.
Excel is a monster with its wide variety of functions.
PowerBI is popular for Excel-like metastructures.
Tableau is popular for its interactive visualizations.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Excel and Google Sheets
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## PowerBI
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Tableau
- 

[[Return to Top]](#table-of-contents)







<!--                                                           
######                                                                   
#     # #####   ####   ####  #####    ##   #    # #    # # #    #  ####  
#     # #    # #    # #    # #    #  #  #  ##  ## ##  ## # ##   # #    # 
######  #    # #    # #      #    # #    # # ## # # ## # # # #  # #      
#       #####  #    # #  ### #####  ###### #    # #    # # #  # # #  ### 
#       #   #  #    # #    # #   #  #    # #    # #    # # #   ## #    # 
#       #    #  ####   ####  #    # #    # #    # #    # # #    #  ####  
                                                                         
#                                                               
#         ##   #    #  ####  #    #   ##    ####  ######  ####  
#        #  #  ##   # #    # #    #  #  #  #    # #      #      
#       #    # # #  # #      #    # #    # #      #####   ####  
#       ###### #  # # #  ### #    # ###### #  ### #           # 
#       #    # #   ## #    # #    # #    # #    # #      #    # 
####### #    # #    #  ####   ####  #    #  ####  ######  ####  
-->

# Programming Languages
```
This section is needed for what should be obvious reasons: syntax, examples, etc
Python is my manin language, so I'll just use the section to store odd snippets.
R is an alternative to Python and used especially in academia (use is waning).
C++ pointer manipulation is very fast, so C++ might play a role in development.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Python Oddities
- `reload(coolutil)` Reload your imports (Uses: `from importlib import reload`)
- `help(coolfunc)` or `print(coolfunc.__doc__)`: Read function's docstring
- `if __name__ == '__main__': (code)` to run code when directly invoking script
- `cool1, cool2 = sys.argv[1], sys.argv[2]` to store CMD args to variables
    * Make sure to do input validation in the script! `len(sys.argv)`, etc
    * Command line: `python cool.py 99 "hello"`, cool1 = 99, cool2 - "hello"
### Strings
- `"aaaaaa".replace("a","b",2)` only replaces first two matches
- `"5 is %20d" % 5` allocates 20 spaces at the %, where 5 takes up the rightmost
- `"pi is %0.2f" % 3.14159265358` makes room for only 2 decimal places
    * `'{2:.2f} {1}'.format('won\'t see', 'Gigawatts', 1.21187)`
- `f"|{123:^8}|{1:^8}|"` centers 123 and 1 in eight-whitespace area
    * `<` aligns left, `>` aligns right
- `f"|{123:^8b}|{1:^8b}|"` converts and centers binary representation of numbers
    * Convert to hex: "x"; Convert to exponent: "e"
- `"%r" % r"C:\\Windows"` keeps raw string
### Sets
- `s1 = {"hi"}` -- `s1.update({"yo", "hi"}, {"sup","yo","hey"})` (saved)
- INTERSECTION returns shared vals, DIFFERENCE returns s1's unshared vals
- UNION returns set + set, SYMMETRIC DIFFERENCE returns s1 and s2's unshared
### Lists
- `sorted(mylist)` returns sort, `mylist.sort()` performs and saves sort
    * Same with `reversed(mylist)` and `mylist.reverse()`
- `mylist.remove("f")` removes "f"; `mylist.insert(2, "m")` inserts at index 2
    * Remove has no gaps; Insert shifts old index 2 (and the rest) to the right
- `mylist[start:stop:step]`, especially backwards with `print("hello"[::-1])`
### Dicts
- Dict keys can be any immutable variable, like a tuple!
- `{"a":1, "b":2}.get("zzz", "doesn't exist!")` query for a key
- `x.update({"trees":["Oak"]})` add new key:value without reassignment
- `{ok:{ik:float(iv) for (ik, iv) in ov.items()} for (ok, ov) in d.items()}`
### Class Oddities
- Class methods alter the class itself, ex: `Cool1.name_me("Cool Guy")`
- Operator overloading
```
class CoolClass:
    def __init__(self, x):
        self.name = "Cool Guy"
        self.price = x
    def __str__(self):
        return ('{} costs only ${:.2f}.'.format(self.name, self.price))
    def __lt__(self, other):
        if self.price < other.price:
            return "Yup"
cool1 = CoolClass(10)
cool2 = CoolClass(15)
print(cool1 < cool2)
print(cool1)
```
```
import unittest
class Circle:
    def __init__(self, radius):
        self.radius = radius
    def compute_area(self):
        return 3.14159265358 * (self.radius ** 2)
class TestCircle(unittest.TestCase):
    def test_compute_area(self):
        c = Circle(0)
        self.assertEqual(c.compute_area(), 0)
if __name__ == "__main__":
    unittest.main()
```
### Errors
- SyntaxError and IndentationError are reported before *any* code runs; the rest is reported during runtime
- SyntaxError: "illegal" code, ex: `print("hi") print("there!") print("all on one line?...")`
- IndentationError: didn't indent properly, ex: not indenting a `for` loop
- ValueError: can't perform operation on that data type, ex: `int("hi")`
- TypeError: similar to value error, ex: `"abc" + 42`
- NameError: didn't initialize a variable before its use, ex: `print(greeting)`
- NotImplementedError: function has no body
- AssertionError: `assert` statement fails, or `import unittest` unit test assertion fails
- RuntimeError: example is when recursion function runs 1,000 times (can be adjusted via `sys.setrecursionlimit()`)
- Logic error: the code ran, but the output is wrong, ex: `42 * 1` when you meant `42 * 10` (this is also called a bug)
- Capture all but logic errors via `try`-`except` statements, ex: `try: code` -> `except NameError: code`
    * Use `try` with `raise` to force errors/non-errors to the `except` statement, ex: `raise TypeError("Not integer!")`
        * Can raise your own errors: `class CoolError(Exception): def __init__...` -> `raise CoolError(...)`
    * Use `finally` after the `except` statement to run code regardless of errors, ex: `finally: print("Terminated.")`

--------------------------------------------------------------------------------
<!-- Needs work -->
## R
- Popular alternative to Python's data science libraries
- Used extensively in academia; the language is not general-purpose like Python
### R Libraries
- `install.packages('lubridate')`, `install.packages('ggplot2')`, etc
- `library(lubridate)` date functions, ex: `ymd_hms` (read a ymd_hms column)
    * `some_date <- ymd_hms(chi[["datetime"]])` -> `month(some_date)`
    * `month(as.POSIXlt(date_col, format="%d/%m/%Y"))`
- `library(ggplot2)` visualizations
    * `qplot(x=categ_col, data=df, binwidth=10, xlab="hi")` to do histogram
        * `x=cats, y=conts, geom='boxplot'` boxplot, `x=conts, y=conts` scatter
        * `color=I('black')`, `fill=I('#F79420')`
    * `qplot(...) + scale_x_discrete(breaks=start:end)` set xticks, ex: 1:31
        * `qplot(...) + scale_x_continuous(limits=c(start, end))` set xlims
        * `qplot(...) + coord_cartesian(ylim = c(0, 1000))` set **VIEW** ylims
        * `qplot(...) + scale_x_continuous(..., breaks=seq(start,end,step))`
    * `qplot(...) + scale_x_discrete(...) + facet_wrap(~col2, ncol=3)` multiplot
        * Three columns of histograms; # of rows decided by unique vals in col2
        * Basically a `hue` but with separate plots; these share same y axis
    * `ggplot(aes(x=col1, y=col2), data=pf) + geom_points()` scatter as well
        * `ggplot(...) + geom_points(alpha=1/20)` set point alphas for scatter
            * `geom_jitter(alpha=1/20)` blends cont. col (ex: blend age_years)
        * `ggplot(...) + xlim(start, end)` visual cutoff; not data cutoff
### (R)andom Syntax
- `getwd()` is `pwd`, `list.files()` is `dir`
- `x = 5 + 3` (local scope) OR `x <- 5 + 3` (global scope)
    * `hi.my.name.is.bob = 42` is a valid variable assignment
    * `15 %% 3 == 0`
- `TRUE`, `FALSE`, `as.integer(TRUE)`, `class(TRUE)` (output: "logical")
### R Vector Work
- NOTE: Any reference to `c(val, val, ...)` will print as `val val ...`
- `c(1,2,3,2,1)` same as `pd.Series([1,2,3,2,1])`
    * `c(1, "hi", 3)` yields `c("1", "hi", "3")` (as expected)
    * `paste(1,2,3,4,5, sep="hi")` yields `1hi2hi3hi4hi5`
    * `paste(c(1,2,3,4,5), collapse="hi")` also yields `1hi2hi3hi4hi5`
    * `paste0('hi',1:5)` yields `"hi1" "hi2" "hi3" "hi4" "hi5"`
- `c(1,2,3,4,5) > 3` yields `c(FALSE,FALSE,FALSE,TRUE,TRUE)`
    * `any(c(...) > 3)`, `all(c(...) > 3)` returns TRUE or FALSE
    * `which(c(...) > 3)` returns indices where the value > 3
    * `subset(col_to_mask, c(...) > 3)` applies a mask to `col_to_mask`
- `column <- c("a","a","a","b","c","c"))` -> `table(column)` for value counts
    * `length(column)` to get length
- `c(rep(4, times=3), rep(2, times=5))` is same as `c(4,4,4,2,2,2,2,2)`
- `seq(1, 10, by=2)` yields `c(1,3,5,7,9)`; `by=length.out` does equal spacing
- `vector(mode='numeric', length=5)` yields `c(0,0,0,0,0)` (zero is default val)
    * 'numeric' is 0s, 'logical' is FALSEs, 'character' is empty strings
- `my.array = array(seq(1,4,1), dim=c(2,2))` yields `[[1,3],[2,4]]`
    * `my.array + 10` yields `[[11,13],[12,14]]`
    * `t(my.array)` transposes to `[[1,2],[3,4]]`
    * `my.array %*% my.array` does matrix multiplication
- `x <- 1:3` -> `y <- 10:12` -> `cbind(x, y)` yields dataframe! with cols x, y
    * `rbind(x, y)` will also yield dataframe with **rows** x, y
    * `df[1, ]` prints first row, `df[ ,1]` prints first column
    * Can assign list-likes to rows or to columns using above syntax
### R Dataframe Work
- `data.frame` is same as `pd.DataFrame`, `names(df)` is just `df.columns`
- `df = read.csv('mycool.csv')` -> `head(df, num_rows)`
- `head(df, 3)`, `tail(df, 7)`, `dim(df)` (shape), `summary(df)`
- `df$colname` returns colname, `min(df$colname)` returns min value of colname
    * `df$colname[1:42]` pull first 42 values of colname
    * `min`, `max`, `mean`, `median`, `sd`
- `subset(df, col1=='coolvalue' & col2 > 5)` applies the mask to df
    * `subset(df, !is.na(colname))` filter out nulls
- `by(df$col1, df$col2, func)` apply func on col1 by unique value in col2
    * EX: `by(df$friend_count, df$gender, summary)` friend_count stats by gender
### (R)andom Code Blocks
``` 
# Take Gapminder then select cols then filter for Kenya
gapminder %>%
    select(country, lifeExp, gdpPercap) %>%
    filter(country=="Kenya")
```
```
`if (val == 123) {
    for (i in 1:10) {print("hi")}
} else if (val == 321) {
    print("yo")
} else {
    print("no")
}
```
```
coolfunc = function(x=10, y=4) {
    cool = x * y
    return(cool)
}
```
```
ggplot(aes(x=age, y=friend_count), data=pf) +
    xlim(13, 90) +
    geom_point(alpha=0.05,
               position=position_jitter(h=0),
               color='orange') +
    coord_trans(y='sqrt') +
    geom_line(stat='summary', fun.y=mean) +
    geom_line(stat='summary', fun.y=quantile, probs=.1, linetype=2, 
              color='red') +
    geom_line(stat='summary', fun.y=quantile, probs=.5, color='red') +
    geom_line(stat='summary', fun.y=quantile, probs=.9, linetype=2, color='red')
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## C++
- Compiler converts statements one-by-one to machine code, once finished, runs
    * Comments do not get converted to machine code
    * Compiler skips spaces (except in string literals) and empty lines
- Fix errors: look at first-reported error by the compiler (compile-time error)
    * Correct the first error then recompile; don't check further errors
    * Errors may be reported later than they actually occur (think: block-quote)
    * If "erroneous" statement has no error, look prior to it
- Use namespaces in custom imports to prevent collisions, ex: seat in plane/bus
- Single line comment: `//`, multi-line comment: `/* */`
- Starts in `main()`, executes statements in `{ }` one at a time
- Each statement inside main() is terminated with semicolon
- Functions: `int CoolFunc (int x) { int y; ...statements... return y; }`
    * Can set defaults for parameters as expected: `int CoolFunc (int x = 0) ..`
    * Return nothing with `void` type functions
        * Functions for modifying an input should use `void` + pass by reference
    * Pass by reference: global scope in functions, `... (int& x) ...`
        * This refers to the global `x` variable, allows modification of it
- Each variable is declared with a type, ex: `int myVariable;`
    * int, float, double, char, short, long long, auto, bool, int[2][3], char[8]
        * char is only character literals, ex: 'a' (not "a")
        * Can put "unsigned" in front for what you expect
        * Booleans: `true`, `false`
        * Arrays: `int[numRows][numCols]`, `char[numChars + nullChar]`
    * Declaring variables allocates type-specific space in memory for it
    * Can just initialize the variable; `int myVariable = 20;`
    * Note: reading declared but un-initialized variables is BAD of course
- Can initialize constants, ex: `const int SECONDS_PER_HOUR = 3600;`
    * Constants are typically all-uppercase for readability purposes
    * Modifying a constant results in compiler errors (safety)
- For option-selection, use the enumeration type; this method is safe
    * `enum LightState {LS_RED, LS_GREEN, LS_YELLOW, LS_DONE};`
    * `LightState lightVal;` -> `lightVal = LS_RED` -> `lightVal == LS_RED`
- Can change type on the fly: `static_cast<double>(10)` -> 10.0
    * Great solution for fixing integer division issues
- `cin` statements take inputs, ex: `cin >> myVariable;`
- `cout` statements print things, ex: `cout << "Hello World!";`
    * Repeat `cout` will print to same line; use `cout << endl;` for "\n"
    * Can do: `cout << "Hello" << " " << "world!" << endl;`
    * `cout << fixed << setprecision(2) << myFloat;` (include iomanip)
- Comparison: `>`, `<`, `==`, `!=`, etc, `&&` (AND), `!` (NOT), `||` (OR)
    * Float equality: compare for "close enough", ex: `(x - y) < 0.001`
        * 0.001 here is called "epsilon" (difference threshold)
    * `coolWord = (x > 1) ? "cool" : "uncool"` (ternary operators)
        * Format: `x = (condition) ? result_if_true : result_if_false`
    * `if (x > 1) {statements} else if (x == 1) {statements} else {statements};`
    * `switch (x) {case 42: statements break; ... default: statements break;}`
        * `default` is executed when no cases are matched
        * Can omit `break` to allow "falling through" to next/further cases
    * `while (condition) {statements}`
    * `for (int i = 0; i < 5; ++i) {statements}`
        * `++i` here sends 1 as first input??; `i++` would send 0 as first input
        * Last statement is ran at start of loop, so ex: `i = i + 5` works too
- End the program with `return 0;` ("return without error")

## C++ Pointers
- A pointer is a variable that contains a memory address
- Typically declared with a data type, ex: `int* maxItemPointer;`
    * `maxItemPointer` has an unknown memory address at this stage; dangerous!
    * Safe method is initializing with null: `int* maxItemPointer = nullptr;`
- Typically initialized by assigning a pass-by-reference to a variable
    * EX: `intPointer = &myInteger;`, the `&` character refers a memory address
    * Print the contents of a stored address with: `PrintValue(myPointer);`
- The memory itself can be shown just by outputting the pointer's value
- The object at the pointer's value can be output with: `cout << *myPointer;`
    * **DANGER: this can break your program if `myPointer` isn't initialized!**
    * This is called "dereferencing"; ignore reference, access the stored value
- You can change the value stored at the pointer's location: `*myPointer = 10;`
- `new` is used for: `MyClass* test = new MyClass;`, `test` stores a pointer
    * This is mainly done for speed! Just dereference `test` as needed
        * Dereferencing an instantiated class: `(*test).MyMethod();`
        * Alternate method: `test->MyMethod();`
    * Can also pass arguments: `MyClass* test2 = new MyClass(4, 3);`
    * Can also create an array: `MyClass* test3 = new MyClass[6];`
        * A single, contiguous chunk of memory is allocated for the array, then 
        * ... the default constructor is called for each object in the array.
- Delete *what is stored* at a memory address: `delete myPointer;`
    * The pointer itself is unchanged!! `cout << myPointer;` is same before/aft
    * "Freeing" an array ex: `new MyClass[6]` is done with `delete[] test3;`

## C++ Libraries
- `#include "myFile.h"` - import your own file from the current directory
    * The .h is traditional for C++; quotes tell the compiler to look in CWD
    * myFile.h actually calls functions in myFile.cpp... that's the intention
- `#include <cassert>` - assertions / unit testing
    * `assert(HrMinToMin(0, 99) == 99);`, `assert(HrMinToMin(2, 30) == 150);`
    * Easily create a test harness / testbench this way (assert = test vector)
- `#include <cctype>` - character types; 
    * `isalpha('x')`, `isdigit`, `isalnum`, `isspace`, `islower`, `isupper`
    * More: `isblank`, `isxdigit(hex)`, `ispunct`, `isprint`, `iscntrl`
    * More: `toupper('e')`, `tolower('E')`, `
- `#include <cmath>` - math operations, ex: `cout << sqrt(16) << endl;`
    * log, log2, log10, exp, pow, ceil, floor, sin, cos, tan, etc
- `#include <cstdlib>` - `rand()` (random integer from 0 to "max"), `srand(42)`
    * Use modulo to set boundaries; `rand() % 10` (0-9), `rand() % 100` (0-99)
- `#include <cstring>` - C strings, these can be unstable
    * `strcpy(outStr, inStr)`, `strncpy(outStr, inStr, n)` copy string
    * `strcat(myStr, addStr)`, `strncat(myStr, addStr, n)` concat string
    * `strchr(myStr, findChar)`, `strlen(myStr)`, `strcmp(str1, str2)` (compare)
- `#include <ctime>` - `time(0)` is current number of seconds since Jan 1st 1970
- `#include <iostream>` - `cout`, `endl`, getting keyboard inputs, more
- `#include <iomanip>` - rounding numbers
- `#include <string>` - allow use of `string greeting = "Hello";`
    * `.at(5)`, `.length()`,`.append("hi")`,`str1 + str2`,`.find("me")`
        * In-place string modification works: `myString.at(5) = 'Q'`
        * One-character append: `.push_back('?')`
    * `.substr(i, steps)`,`.insert(i, "hi")`,`replace(i, stepsOverwrite, "hi")`
    * string is odd; `cin` with "Hi there!" sends only "Hi" (whitespace delim)
        * You must specify `getline(cin, storeHere);` to get a whole line...
- `#include <vector>` - array w/ preserved order; all items are of a given type
    * 1-D Vectors beat 1-D arrays; array: `int myArray[10];` (10 elements)
        * Vectors have `.size()`, `.at()`, and safety
    * `vector<int> gameScores(4);` declares a vector with 4 int elements
    * `vector<int> gameScores(4, 0);` initializes vector w/ 4 elements (each 0)
    * `vector<int> gameScores = {0, 14, 3};` looks like a set, but isn't
    * `.size()`, `.resize(42)`, `.push_back(element)`
    * `.back()` (return last element), `.pop_back()` (pop last element)
    * `newVector = origVector;` (copy), `v1 == v2` (comparison)

## C++ Examples
```
#include <iostream>
#include <string>
#include "roster.h"

using namespace std;

int main() {
	// print course title, programming language, WGU student ID, and your name
	cout << "C867-Scripting & Programming: Applications" << endl;
    cout << "Language: C++" << endl;
	cout << "Student ID: 10588242" << endl;
    cout << "Name: Jacob Paxton" << endl << endl;

	// instantiate classRoster object
	Roster classRoster;

	// initialize student data
	const string studentData[5] = {
		"A1,John,Smith,John1989@gm ail.com,20,30,35,40,SECURITY",
		"A2,Suzan,Erickson,Erickson_1990@gmailcom,19,50,30,40,NETWORK",
		"A3,Jack,Napoli,The_lawyer99yahoo.com,19,20,40,33,SOFTWARE",
		"A4,Erin,Black,Erin.black@comcast.net,22,50,58,40,SECURITY",
		"A5,Fname,Lname,email@site.com,42,10,11,12,SOFTWARE" };
	
	// add students
	for (int iter = 0; iter < 5; iter++) {classRoster.parse(studentData[iter]);}

	// print all students
	cout << "Displaying all students:" << endl;
	classRoster.printAll();
	cout << endl;

	// show any invalid emails
	cout << "Invalid Emails:" << endl;
	classRoster.printInvalidEmails();
	cout << endl;

	// calculate each student's average count of days per course
	cout << "Average Days Per Course:" << endl;
	for (int iter = 0; iter < 5; iter++) {
		classRoster.printAverageDaysInCourse(
            classRoster.classRosterArray[iter]->GetStudentID()
        );
	}
	cout << endl;

	// print only software students
	cout << "Showing students in degree program: SOFTWARE" << endl;
	classRoster.printByDegreeProgram(SOFTWARE);
	cout << endl;

	// remove student A3
	cout << "Removing student A3..." << endl;
	classRoster.remove("A3");
	cout << endl;

	// print all students
	cout << "Displaying all students:" << endl;
	classRoster.printAll();
	cout << endl;

	// try to remove student A3 again; should indicate A3 not found
	cout << "Removing student A3 again..." << endl;
	classRoster.remove("A3");
	cout << endl;

	// ~Roster() destructor called
	return 0;
}
```

[[Return to Top]](#table-of-contents)