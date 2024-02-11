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
1.    [Read Local Files              ](#read-local-files)

III.  [Regular Expressions           ](#regular-expressions)
1.    [REGEX Syntax                  ](#regex-syntax)
1.    [REGEX Find                    ](#regex-find)
1.    [REGEX Capture                 ](#regex-capture)

IV.   [Advanced Web Scraping         ](#advanced-web-scraping)
1.    [Pandas Read-HTML              ](#pandas-read-html)
1.    [Requests                      ](#requests)
1.    [Selenium                      ](#selenium)

V.    [Building a Database           ](#building-a-database)
1.    [SQLite                        ](#sqlite)
1.    [SQLAlchemy                    ](#sqlalchemy)
1.    [PostgreSQL                    ](#postgresql)

VI.   [Database Usage Mastery        ](#database-usage-mastery)
1.    [SQL and Variants              ](#sql-and-variants)
1.    [SQL Examples                  ](#sql-examples)

VII.  [Fixing Nulls                  ](#fixing-nulls)
1.    [Basic Null Characterization   ](#basic-null-characterization)
1.    [Null Pattern Characterization ](#null-pattern-characterization)
1.    [Handling Nulls                ](#handling-nulls)
1.    [Evaluation of Null Handling   ](#evaluation-of-null-handling)

VIII. [Feature Transformation        ](#feature-transformation)
1.    [Dataframe Normalization       ](#dataframe-normalization)
1.    [Fixing Dataframes at Speed    ](#fixing-dataframes-at-speed)
1.    [Feature Engineering           ](#feature-engineering)

IX.   [Modeling Preparation          ](#modeling-preparation)
1.    [Scaling                       ](#scaling)
1.    [Feature Reduction             ](#feature-reduction)
1.    [Resampling                    ](#resampling)

X.    [Algorithmic Clustering        ](#algorithmic-clustering)
1.    [Selecting Number of Clusters  ](#selecting-number-of-clusters)
1.    [Clustering Methods            ](#clustering-methods)
1.    [Cluster Analysis              ](#cluster-analysis)

XI.   [Natural Language Processing   ](#natural-language-processing)
1.    [Normalizing String Features   ](#normalizing-string-features)
1.    [Keywords and Sentiment        ](#keywords-and-sentiment)
1.    [NLP for Prediction            ](#nlp-for-prediction)

XII.  [Geospatial                    ](#geospatial)
1.    [Geospatial Analysis           ](#geospatial-analysis)

XIII. [Statistics                    ](#statistics)
1.    [Probability                   ](#probability)
1.    [Hypothesis Testing            ](#hypothesis-testing)

XIV.  [Insight Delivery              ](#insight-delivery)
1.    [Visualizations                ](#visualizations)
1.    [Magic in Jupyter              ](#magic-in-jupyter)

XV.   [Classification                ](#classification)
1.    [Features for Classification   ](#features-for-classification)
1.    [Training Classifiers          ](#training-classifiers)
1.    [Evaluating Classifiers        ](#evaluating-classifiers)
1.    [Classification Shotgun        ](#classification-shotgun)

XVI.  [Regression                    ](#regression)
1.    [Features for Regression       ](#features-for-regression)
1.    [Training Regressors           ](#training-regressors)
1.    [Evaluating Regressors         ](#evaluating-regressors)
1.    [Regression Shotgun            ](#regression-shotgun)

XVII. [Time Series                   ](#time-series)
1.    [Timestamp Engineering         ](#timestamp-engineering)
1.    [Metrics of Time Series        ](#metrics-of-time-series)
1.    [Outcome Plotting              ](#outcome-plotting)
1.    [Time Series Modeling          ](#time-series-modeling)

XVIII.[Anomaly Detection             ](#anomaly-detection)
1.    [Anomalic Metrics              ](#anomalic-metrics)
1.    [Getting to the Numbers        ](#getting-to-the-numbers)
1.    [Baselines and Deviation       ](#baselines-and-deviation)

XIX.  [Neural Networks               ](#neural-networks)
1.    [Establishing a Neural Network ](#establishing-a-neural-network)
1.    [Image Classification          ](#image-classification)
1.    [Deep Learning                 ](#deep-learning)

XX.   [Generative AI                 ](#generative-ai)
1.    [Implementing LLMs             ](#implementing-llms)
1.    [Implementing Image Generation ](#implementing-image-generation)

XXI.  [Model Deployment              ](#model-deployment)
1.    [Pipelining a Model            ](#pipelining-a-model)
1.    [Building a Flask App          ](#building-a-flask-app)
1.    [Building a Django App         ](#building-a-django-app)
1.    [Deploying the Model           ](#deploying-the-model)

XXII. [Application Scaling           ](#application-scaling)
1.    [Kubernetes                    ](#kubernetes)
1.    [Apache Kafka                  ](#apache-kafka)

XXIII.[PySpark                       ](#pyspark)
1.    [Spark                         ](#spark)
1.    [PySpark Commands              ](#pyspark-commands)
1.    [PySpark Machine Learning      ](#pyspark-machine-learning)

XXIV. [ELK Stack                     ](#elk-stack)
1.    [Elasticsearch                 ](#elasticsearch)
1.    [Logstash                      ](#logstash)
1.    [Kibana                        ](#kibana)

XXV.  [Project Management            ](#project-management)
1.    [Planning a Project            ](#planning-a-project)
1.    [Selecting the Framework       ](#selecting-the-framework)

XXVI. [Business Tools                ](#tools-and-languages)
1.    [Excel and Google Sheets       ](#excel-and-google-sheets)
1.    [PowerBI                       ](#powerbi)
1.    [Tableau                       ](#tableau)

XXVII.[Programming Languages         ](#programming-languages)
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
- TODO: Add regression, time-series, anomaly detection, etc libraries if can
- TODO: Pare down Git commands to specific examples

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup
1. Download and install Anaconda: https://www.anaconda.com/products/distribution
    * Defaults are fine
1. Add Anaconda to Windows PATH variable (should work automagically in other OS)
    * Control Panel > System and Security > System > Advanced system settings 
    * Environment Variables > Path > Edit
    * Add: %USERPROFILE%\AppData\Local\anaconda3
    * Add: %USERPROFILE%\AppData\Local\anaconda3\condabin
1. Undo Window's stupid default aliasing
    * Start > Manage App Execution Aliases > Uncheck python.exe and python3.exe
1. Open the command line editor you want to use with Conda going forward
1. Enter: `conda config --append channels conda-forge` (add main package source)
1. Create your Conda environment and install basic data science packages into it
    * Basic: `conda create -n env1 numpy pandas matplotlib seaborn scikit-learn`
    * `conda install --name env1 scipy statsmodels jupyter`
1. Enable Conda in Windows CMD: `conda init cmd.exe` and restart CMD
    * Choose other terminal programs instead if you want!
1. Activate your environment: `conda activate env1`
    * Start each time with `env1`: add activate line to .bash_profile or .zshrc
1. Install pip into your environment: `conda install pip`
1. Now that your env is active, choose the additional packages you need
    * Classification: `conda install imbalanced-learn xgboost`
    * Webscraping: `conda install bs4 selenium`
        * Selenium requires downloading a browser driver, ex: "chromedriver.exe"
    * Interactivity: `conda install dataclasses graphviz plotly flask django`
    * Big data: `conda install dask pyspark sqlalchemy h5py`
    * Geospatial: `conda install geopandas folium shapely`
    * Natural Language Processing: `conda install nltk wordcloud`
        * Run `nltk.download(dataset_name)` to install a single required dataset
        * Required sets: 'stopwords' 'vader_lexicon' 'punkt' 'wordnet' 'omw-1.4'
    * Patch sklearn (only Windows systems): `pip install scikit-learn-intelex`
    * Network data: `pip install ipcalc nfstream dash dash_cytoscape vaex`
        * NFStream install steps: https://nfstream.org/docs/#installation-guide
    * Elasticsearch: `pip install elasticsearch elasticsearch-dsl`
    * Handling YAML: `pip install pyyaml ruamel.yaml`
    * Sample data: `pip install pydataset holidays ucimlrepo vega_datasets`
1. Install PyTorch if you want
    * `conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch`
    * `conda install astunparse numpy ninja pyyaml setuptools cmake cffi`
    * `conda install typing_extensions future six requests dataclasses`
1. Install Keras and Tensorflow if you want
    * `conda install -c conda-forge keras`
    * `conda install tensorflow`
        * On windows VM I had issues with conda install; pip worked fine though
1. Test package installation
    * Open CMD and enter `jupyter lab`
    * Start up a new Python3 notebook
    * Try to import the packages you've installed and test them
1. Install VS Code (my preferred code editor beside Jupyter)
    * Defaults are fine; I recommend also "Open with Code" for context menus
    * Launch file with VSCode in working dir from a terminal: `code test.md`
        * This should open VS Code; try a second time if first didn't work
        * If it worked, great! This is my preferred way to create files
        * If not working: open VSCode command palette, type 'code', install
    * In VSCode, click File > Open Folder... > open %USERPROFILE% > trust all
        * If you don't mind VSCode asking you repeatedly for trust, leave alone
    * Install Python and Jupyter extension to VS Code (HIGHLY recommended)
    * 80/120 char width code lines: Settings -> editor.rulers -> set to [80,120]
1. Install Git (I do defaults except the following, my preferred settings)
    * Windows: download from here: https://git-scm.com/downloads
    * MacOS: Open Terminal and run `git`; install Xcode from the popup, has git
    * I actually edit the registry to launch CMD on shift+rightclick context...
        * If you agree, disable Git Bash and Git GUI in context menus...
        * If you don't like registry editing, keep Git Bash (remove Git GUI)
    * Add Git Bash profile to Windows Terminal (for CMD!...)
    * Register VS Code as Git's default editor
1. Launch CMD (or Git Bash) and set your Git settings
    * Add your name: `git config --global user.name "Joe Schmoe"`
    * Add your email: `git config --global user.email "joeschmoe@gmail.com`
1. Done!!! For now...
### Change Windows Registry to Launch CMD from Right-Click
1. Regedit > `Computer\HKEY_CLASSES_ROOT\Directory\Background\shell\cmd`
1. Right click on the "cmd" folder > Permissions > Advanced
1. Owner Change > Administrators > Check Names > Ok
    * Replace owner on subcontainers and objects > Apply 
1. Add > Select a principal > Administrators > Check Names > Ok 
    * Check "Full Control" > Ok > Replace all child.. > Ok > Yes > Ok
1. Right click on HideBasedOnVelocityId (changing reg values now) 
    * Rename > rename to ShowBasedOnVelocityId
1. Task Manager (ctrl+shift+escape) > More Details 
    * select Windows Explorer > Restart
1. Open any folder > Shift + right click 
    * If "open command window here" displays, then success!
1. Right click on `Directory\Background\shell\cmd` folder on left nav pane
    * Permissions > Advanced > highlight Administrators > Edit > no Full Control
    * Check "Replace all child"... > Apply > Yes
1. Owner Change > type trusted installer service NT SERVICE\TrustedInstaller 
    * Check Names > Ok 
    * check "Replace owner on subcontainers..." > Ok > Ok > Close Regedit
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
cd %USERPROFILE%\zen
call activate mighty
%SystemRoot%\explorer.exe "%USERPROFILE%\zen"
code "" "%USERPROFILE%\zen" | exit
jupyter notebook
```
### Joining a Jupyter Hub
- Jupyter Hub hosts a Jupyter workspace for each user on a single system/server
- Great for multiple people working separately on a high-performance system
- Each workspace is configurable using the console in that workspace
```
-- log into the jupyter hub and open a console; to create your conda env:
conda create -n mighty ipykernel
conda init bash
conda activate mighty
conda install <all required packages here>
python -m ipykernel install --user --name mighty --display-name "mighty"
-- log out, log back in, select new kernel called "mighty" - done
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Git Setup
1. Create Github/Gitlab account
1. Set your Git credentials on your computer (if not already done)
    - Run command: `git config --global user.name "git_username"`
    - Run command: `git config --global user.email "git_email_address"`
1. If you can't do SSH... use https!
    * Go to account preferences, access tokens
    * Set token name, delete out expiry date, checkmark all boxes, create token
    * Save it somewhere; definitely do not save it on your desktop (or, do)
1. If you can use SSH, generate an SSH key for connecting with Github/Gitlab
    - Run command: `ssh-keygen -t rsa -b 4096 -C "github_email_address_here"`
    - Hit ENTER on keyboard when it asks where to save the key (save to default)
1. Add your publickey to Github/Gitlab here: https://github.com/settings/ssh/new
    - Copy the SSH public key to clipboard
        * (Mac/Linux): `cat ~/.ssh/id_rsa.pub | pbcopy`
        * (Windows Git Bash): `cat ~/.ssh/id_rsa.pub | clip`
    - Paste that into the link and give it a title of your choice
    - Click "Add SSH Key", done
1. Check if it's working
    - Create new repository on Github/Gitlab
    - Click "Code" or "Clone" button dropdown
    - Click SSH, copy that link to the repo
    - Open Terminal or Git BASH or CMD or whatever you use
    - Enter `git clone that_text_you_just_copied`
        - EX: `git clone https://github.com/JacobPaxton/data_science_notes.git`
        - SSH: `git clone git@github.com:JacobPaxton/data_science_notes.git`
    - If it clones, great- it worked
    - Add a random new file to the folder it created
    - Open a terminal in the folder and run these commands: 
        * `git add .`
        * `git commit -m 'my first commit'`
        * `git push`
1. Consider storing your passphrase (MacOS): add/edit `~/.ssh/config` with this:
```
Host *
  UseKeychain yes
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Git Work
1. If you're creating a new project, start by creating a repo on Github/Gitlab
1. Open a terminal in the directory where you want your repo to be located
1. Grab the remote repository with `git clone` then `cd` into the created folder
1. Switch to your branch of preference if needed with `git branch awesomething`
    * Create a new branch if desired with `git branch -c mynewbranch`
1. Make your changes in the branch
    * Consider adding a ".gitignore" here! Set file exclusions (line-separated)
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
1. Copy the changed files / changes manually to the clone
1. Run `git add filename` `git commit -m "message"` `git push` as normal
1. Delete the old folder after successfully pushing your work
1. Move the new folder to where the old folder was- good as new!!
### Handling Aftermath of Branch Merges
- If a team mate merged a branch into main, you've come to the right place
1. If you accept these changes run `git pull`, otherwise Safely Update Your Repo
1. To delete the merged-in branch locally, run `git branch -d branch_name`
1. To clean up the deletion you just performed, run `git fetch --prune`
1. Done! Merged-in branch has now been deleted locally.

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
- NOTE: CONSIDER ADDING STRUCTURAL CONVERSION (DATA STRUCTURES)
- TODO: Iris is fine, get another classification dataset!

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
- `from ucimlrepo import fetch_ucirepo` --- `wine = fetch_ucirepo(id=109)`
- datareader https://pandas-datareader.readthedocs.io/en/latest/remote_data.html
### Important Importing
- CSV: `df = pd.read_csv(fp, parse_dates=ts_cols)`
- XLSX: `xls = pd.ExcelFile(fp)` -> `df = xls.parse("sheet1")`
    * `df = xls.parse("s1", usecols=, skiprows=, ...)`
- SAS: `with SAS7BDAT(fp) as f:` -> `df = f.to_data_frame()`
    * `from sas7bdat import SAS7BDAT`
- Stata: `df = pd.read_stata(fp)`
- HDF5: `import h5py` -> `mydict = h5py.File(fp)`
- MATLAB: `import scipy.io` -> `mydict = scipy.io.loadmat(fp)`

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

--------------------------------------------------------------------------------
<!-- Needs work -->
## Read Local Files
```
import os
import pandas as pd
def find_csvs(dir=None, match=None, folder_start=None, folder_end=None):
    """
    Get filepaths of all CSVs nested inside a given directory.
    dir: directory compatible with `os.walk(dir)`
    match: only return files where: `match in filename` is True
    folder_start: only look in folders where: `folder.startswith(folder_start)`
    folder_end: only look in folders where: `folder.endswith(folder_end)`
    return: absolute filepaths of all CSVs matching the conditions
    """
    if dir is None:
        dir = os.getcwd()
    walk = os.walk(dir)
    all_filepaths = []
    for tup in walk:
        folder, files = tup[0], tup[2]
        if folder_start is not None:
            if not folder.startswith(folder_start): continue
        if folder_end is not None:
            if not folder.endswith(folder_end): continue
        files = [folder + "\\" + file for file in files if file[-4:] == ".csv"]
        if match is not None:
            files = [file for file in files if match in file]
        all_filepaths.extend(files)
    return all_filepaths
def read_csvs(filepaths, set_cols=False):
    """
    Read all CSVs from a list of filepaths, concat into one dataframe.
    filepaths: list of filepaths to iterate through and `read_csv` against
    set_cols: either bool (lock found cols) or col list (provide restrictions)
    return: one dataframe of concatenated read-in CSVs
    """
    if len(filepaths) == 0: return None
    first_is_csv = filepaths[0][-4:] == ".csv"
    first_file_exists = os.path.isfile(filepaths[0])
    if len(filepaths) == 1 and first_file_exists and first_is_csv:
        return pd.read_csv(filepaths[0])
    overprint = len("Done reading!") + len(max(filepaths, key=len))
    if first_file_exists and first_is_csv:
        print(f"Reading: {filepaths[0]:<{overprint}}", end="\r", flush=True)
        if type(set_cols) is list:
            filepaths = fps  # lmao 80char width
            set_cols = [c for f in fps for c in pd.read_csv(f, nrows=0).columns 
                        if col in set_cols]
            df = pd.read_csv(filepaths[0], usecols=set_cols)
        elif type(set_cols) is str:
            set_cols = [set_cols]
            df = pd.read_csv(filepaths[0], usecols=set_cols)
        elif type(set_cols) is bool:
            df = pd.read_csv(filepaths[0])
            if set_cols: set_cols = [col for col in df.columns]
            else: set_cols = None
        else: set_cols = None
    for filepath in filepaths[1:]:
        if os.path.isfile(filepath) and filepath[-4:] == ".csv":
            print("Reading: {filepath:<{overprint}}", end="\r", flush=True)
            df_new = pd.read_csv(filepath, usecols=set_cols)
            df = pd.concat([df, df_new])
    print(f"{Done reading!:<{overprint}}", end="\r", flush=True)
    if "@timestamp" in df.columns:
        df = df.sort_values(by="@timestamp").reset_index(drop=True)
    return df
```
```
import pandas as pd
import read_csvs, find_csvs
df = read_csvs(find_csvs(match="EID4624"), set_cols=False)
```

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

# Regular Expressions
```
This section shows off the power of Regular Expressions (REGEX).
Syntax is important and differs between implementations.
Find is important and REGEX can do things that normal find can't.
Capture is important and REGEX excels at this work.
```
- TODO: Change example spots to actual code examples

--------------------------------------------------------------------------------
<!-- Needs work -->
## REGEX Syntax
- Language for parsing and slicing strings to capture substrings
- Uses a mixture of string literals and metacharacters for multiple objectives
- REGEX by programming language: https://www.regular-expressions.info/tools.html
- Test your REGEX: https://regex101.com/
- Go deep learning REGEX: http://www.rexegg.com/regex-disambiguation.html
```
| Zero or more (optional): *  | One or more: +        | Optional: ?            |
| Any character: .            | Choices: [a12qx]      | Anything-but: [^a12qx] |
| Alphanumeric: \w \W         | Whitespace: \s \S     | Digit: \d \D           |
| {5} Repeat exactly 5 times  | {3,6} Min 3, Max 6    | {3,} At least 3 times  |
| Anchor front: ^             | Anchor back: $        | Word boundary: \b      |
| Capture group: So (cool)!   | Match group: (?:yooo) |
| Case insensitive: (?i)(?-i) | Ignore spaces: (?x)   | Single line mode: (?s) |
```
### REGEX Metacharacter Explanation
- If these explanations are confusing, see: [REGEX Examples](#regex-examples)
- `\.`: a period; the backslash escapes the metacharacter so it is just "."
- `.+`: infinite amount of characters in sequence, but at least one: "?q9 -aAr!"
- `.+?`: same as above, but not greedy; see: [REGEX Examples](#regex-examples)
- `.*`: infinite amount of characters in sequence, can be none (optional): "?q9"
- `.*?`: same as above, but not greedy; see: [REGEX Examples](#regex-examples)
- `\w+`: infinite alphanumerical characters in sequence, but at least one: "hhh"
- `\W\w`: a non-alphanumerical followed by an alphanumerical in sequence: "?q"
- `\s\w`: a whitespace followed by an alphanumerical in sequence: " f"
- `\S+`: infinite amount of non-whitespace in sequence, but at least one: "Hey"
- `\d\d\d\d-\d\d-\d\d`: digits following YYYY-MM-DD format, ex: "2022-09-22"
- `\d{4}-\d{2}-\d{2}`: digits following YYYY-MM-DD format, ex: "2022-09-22"
- `\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}`: IP address format, ex: "10.3.127.5"
- `\D+`: infinite amount of anything except digits in sequence, ex: "Hi there!!"
- `\w(\w)\w`: capture the second alphanumerical character in a sequence of three
- `[abc123]`: pick one, ex: `F[uiae]ll` matches "Full", "Fill", "Fall", "Fell"
- `[a-z]+`: infinite amount of any lowercase letter in sequence, ex: "fnjd"
- `(?i)[a-z]+(?-i)`: case-insensitive version of above, ex: "fNjD"
- `[a-zA-Z]+`: infinite amount of any lower/uppercase letter in sequence: "fNjD"
- `[^a-z]+`: infinite amount of anything but lowercase letters in sequence: "A7"
- `(?i)HELLO(?-i)HELLO`: any-case "hello" followed by all-caps, ex: "hELLoHELLO"
- `(?x) q r s t u v`: ignore whitespace; matches "qrstuv" but NOT "q r s t u v"
- `^yo[a-z]*$`: entire line must match; matches "yo" and "yodawg", but NOT "yo!"
### REGEX Querying in Python
- REGEX library: `import re`
- Randomly search for match: `re.search(regexg, subject)`
- Search from beginning for match: `re.match(regexp, subject)`
- Put all matches in list (very useful): `re.findall(regexp, subject)`
- Return match with subbed-in substring: `re.sub(regexp, sub_in, subject)`
- Capture groups into pandas dataframe columns: `df.colname.str.extract(regexp)`
#### REGEX in Python - Query Options
- Raw string: `string = r"c:\user\p1\Desktop"` (neutralizes backslash-escaping)
    * Only works in print statements and returns.....?
- Search while ignoring case: `re.IGNORECASE`
- Run new query on each line: `re.MULTILINE`
- Ignore whitespace: `re.VERBOSE`
- `|` for 2+ flags: `re.findall(regexp, subject, re.IGNORECASE | re.MULTILINE)`

--------------------------------------------------------------------------------
<!-- Needs work -->
## REGEX Find
- REGEX is fairly complicated, but is best explained/learned through examples
    * Try them on your own!!
- The following examples are done in Python with `re.findall(regex, search_str)`
    * `re.findall("\w\w", "A BB CCC DDDD")` ---> ["BB", "CC", "DD", "DD]
    * `re.findall("\d+", "ABCD")` ---> [] (no matches)
### Simple REGEX Examples
- `.+` -- *Everything!*
    * "Hello, Sam!" -------------> ["Hello, Sam!"] (one string for entire thing)
- `Hello,\s(.+)!` -- *Everything between "Hello, " and final-found "!" (greedy)*
    * "Hello,Sam!" --------------> []
    * "Hello, Sam!" -------------> ["Sam"]
    * "Hello, Sam!!!" -----------> ["Sam!!"] (notice in the REGEX: greedy "+")
    * "Hello, Sam Witwicky!!!" --> ["Sam Witwicky!!"] (one string for full name)
    * "Hello, saFBO43Ef$51bf!" --> ["saFBO43Ef$51bf"]
- `Hello,\s(.+?)!` -- *Everything between "Hello, " and first-found "!"*
    * "Hello, Sam!!!" -----------> ["Sam"] (".+?" makes it not greedy!)
    * "Hello, Sam Witwicky!!!": -> ["Sam Witwicky"] (one string for full name)
    * "Hello, saFBO43Ef$51bf!" --> ["saFBO43Ef$51bf"]
- `Hello,\s(\w+)!` -- *Alphanumerics between "Hello, " and "!" (greedy)*
    * "Hello, Sam!" -------------> ["Sam"]
    * "Hello, Sam!!!" -----------> ["Sam"] ("\w" only captures alphanumerics)
    * "Hello, Sam Witwicky!!!": -> [] (must be continuous alphanumerics)
    * "Hello, 12345!" -----------> ["12345"]
- `[a-zA-Z]+` -- *Alphabet characters in sequence*
    * "Hello, Sam!" -------------> ["Hello", "Sam"]
    * "Hello, Sam Witwicky!!!": -> ["Hello", "Sam", "Witwicky"]

--------------------------------------------------------------------------------
<!-- Needs work -->
## REGEX Capture
- `Hello,\s([a-zA-Z]+)!` *Alphabet characters between "Hello, " and "!"*
    * "Hello, Sam!" -------------> ["Sam"]
    * "Hello, Sam Witwicky!!!" --> []
- `^.+(\S+)!$` *Line ends with non-whitespace and "!" in sequence (greedy)*
    * "Hello, Sam!" -------------> ["m"]
    * "Hello, Sam Witwicky!" ----> ["y"]
- `^.+?(\S+)!$` *Line ends with earliest non-whitespace -> "!" in sequence*
    * "Hello, Sam!" -------------> ["Sam"]
    * "Hello, Sam Witwicky!!!" --> ["Witwicky"]
    * "f7g?3.rb3%79h&2398dh!" ---> ["f7g?3.rb3%79h&2398dh"]
- `([a-zA-Z]+)(?:\s([a-zA-Z]+))*!` *Two capture groups, second is optional*
    * First capture group: ([a-zA-Z]+)
        * A sequence of alphabet characters
    * Second capture group: (?:\s([a-zA-Z]+))*
        * Optional (capture group ends with asterisk)
        * Capture a sequence of alphabet chars that is preceded by a whitespace
        * Basically: `(?:\s(capture_inside_here))*`
    * "Hello, Sam!" -------------> [("Sam", "")] (two capture groups -> tuple)
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello!" ------------------> [("Hello", "")]
- `Hello,\s([a-zA-Z]+)(?:\s([a-zA-Z]+))*!` *Best solution of above*
    * Same as above example but with "Hello,\s" at the beginning
    * "Hello, Sam!" -------------> [("Sam", "")]
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello!" ------------------> []
- `name = "\s([a-zA-Z]+)"` -> `f"Hello,{name}(?:{name})*!"`
    * Clearer writing of above example, but with exactly the same output
- `^(.{15})\s+(\S+)\s+([^\s\[:]+)(\[\d*\])*:\s+(.+)$`
    * This captures: "timestamp hostname reporter[pid]: message"
    * Entire line must match (because it uses `^` start and `$` end)
    * Capture group #1: exactly 15 characters
    * Capture group #2: at least one of anything that's not whitespace
    * Capture group #3: at least one of anything but: whitespace, "[", and ":"
    * Capture group #4: optional; looking for this: "[123]", "[59102]", etc
    * Capture group #5: all remaining characters following the above
- `f"{n1}\s+{n2}\s+{any}\s+{any}\s+{any}\s+{any}\s+{any}\s+{any}"`
    * This captures: "[type] [pid] [pts] [user] [tty] [src] [dest] [timestamp]"
    * **The following variables are capturing the *inside* of the brackets...**
    * `n1 = "\[(\d)\]"`: capturing a single digit in brackets, ex: "[8]"
    * `n2 = "\[(\d+)\]"`: capturing digits in brackets, ex: "[1234]" or "[56]"
    * `any = "\[(\S+)*\s*\]"`: optional; captures "[Hello  ]", "[Hello]", "[  ]"

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
- requests should be used to pull specific files like images, video, etc
- selenium should be used to capture full page content
- beautifulsoup will parse HTML soup from requests, selenium, or otherwise
Draft an entity-relationship diagram first if crawling pages; save to dataframe
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Pandas Read-HTML
- Use this method if you're working with *HTML tables*; it's easy and effective
- Sample HTML tables (testing): https://www.w3schools.com/html/html_examples.asp
```
import pandas as pd
# READ FROM URL
url = "https://www.w3schools.com/html/tryit.asp?filename=tryhtml_table_headings"
df1 = pd.read_html(url)[0] # read HTML tables from URL, set first table as df1
# READ FROM STRING
myhtml = "<table><tr><th>hi</th></tr><tr><td>12</td></tr></table>"
df2 = pd.read_html(myhtml)[0] # read HTML tables from string, set first as df2
```
### Secret Method
- Sometimes the fastest solution is the best.
- `df = pd.read_clipboard()` makes a dataframe from many potential formats

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
    print("Bad response; status code:", response.status_code)
else:
    soup = BeautifulSoup(response.text)
    print(soup.prettify())
    # SELECT TAGS
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
    # RUN FUNCTION TO SELECT TAGS
    b0 = soup.select(has_class_but_no_id)
    # GRAB TAG ATTRIBUTES
    c0 = soup.a.span["class"]
    c1 = soup.find("link", {"rel":"canonical"})["href"]
    c2 = [ele["class"] for ele in soup.select("span", class_=True)]
    # GRAB CONTENTS OF TAG
    d0 = soup.title.text
    d1 = [ele.text for ele in soup.find_all("span")]
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Selenium
- Driving a browser and working with the browser's page content
- This method is much more robust because it handles results of Javascript too
    * Running GET commands gets content before Javascript is run (before loaded)
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
# BASIC PAGE PULL
chromepath = r"C:\Users\Jake\chromedriver.exe"
chrome = webdriver.Chrome(chromepath)
url = 
chrome.get(url)
soup = BeautifulSoup(chrome.page_source)
# WAIT FOR ELEMENT TO LOAD
myElem = WebDriverWait(chrome, 1)\
  .until(EC.presence_of_element_located((By.ID, 'IdOfMyElement')))
elements = chrome.find_elements_by_xpath('//*[@id="q_all"]')
# RUN ACTIONS
actions = ActionChains(chrome)
elem1 = chrome.find_element_by_xpath('//*[@id="q_type"]/div[1]')
actions.move_to_element(elem1).click().perform()  # open dropdown box
elem2 = chrome.find_element_by_xpath('//*[@id="q_type"]/div[3]/div[2]')
actions.move_to_element(elem2).click().perform()  # select an option in dropdown
```
### Walk Images
```
import os
import shutil
import requests
from bs4 import BeautifulSoup as SOUP
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait as WDW
dest = "C:\\Users\\CoolGuy\\CoolImages\\"
if not os.path.exists(dest):
    os.mkdir(dest)
gallery_urls = ["gallery1 img1 url", "gallery2 img1 url", "gallery3 img1 url"]
ffx = webdriver.Firefox()
i = 0
for gallery_url in gallery_urls:
    url = gallery_url
    while True:
        i += 1
        ffx.get(url)
        elem = WDW(ffx, 1).until(EC.presence_of_element_located(By.ID, "img"))
        soup = SOUP(ffx.page_source)
        img = soup.select("img#img")[-1]["src"]
        extension = re.findall("^.+(\..+?)$", img)[-1]
        imgnum = "%05d" % i                  # ex: 00001, 00002, ..., 05914, ...
        imgname = imgnum + extension         # ex: 00001.png, 00002.png, ...
        r = requests.get(img, stream=True)   # stream file to cache
        r.raw.decode_content = True          # ensure binary is decoded on write
        with open(dest + imgname, "wb") as f:   # write from binary
            shutil.copyfileobj(r.raw, f)        # shutil writes to image.jpeg
        nexturl = soup.select("a#next")[0]["href"]   # grab URL of next image
        if url == nexturl:     # if next image is current image (end of gallery)
            i -= 1
            break
        url = nexturl
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
- NOTE: CONSIDER ADDING IDEAL DB CREATION STRATEGY / CONCEPTS

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
# CREATE A DB
import sqlite3
con = sqlite3.connect("cool.db")
cur = con.cursor()
cur.execute('DROP TABLE IF EXISTS test')
cur.execute('DROP TABLE IF EXISTS author')
cur.execute('DROP TABLE IF EXISTS book')
cur.execute('DROP TABLE IF EXISTS publisher')
# SET UP ROW RETURNS AS DICTS RATHER THAN TUPLES
def dict_factory(cur, row):
    fields = [column[0] for column in cur.description]
    return {key: value for key, value in zip(fields, row)}
# EXECUTE STATEMENTS FOR THE DB
cur.execute("""
CREATE TABLE test(
    greeting CHAR(50) PRIMARY KEY NOT NULL, 
    number INT UNIQUE DEFAULT 5, 
    letter CHAR(1) CHECK(letter != "f"))
""")
data = [("hi", 15, "a"),("yo", 22, "b"),("sup", 8, "c"),("hey",19,"d")]
cur.executemany('INSERT INTO test VALUES(?, ?, ?)', data)
cur.execute('UPDATE test SET number = 1000 WHERE rowid = 3')
cur.execute('DELETE FROM test WHERE letter = "d"')
# con.rollback() # use this if you need to abort the transaction
con.commit() # do this after inserts
con.row_factory = dict_factory
for row in con.execute('SELECT greeting, number, letter FROM test'):
    print(row)
# RUN A SCRIPT OF SQL STATEMENTS
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
# SHOW CHANGES ARE SAVED TO THE DB
con.close()
print("\nConnection closed; reopening...")
new_con = sqlite3.connect("cool.db")
new_cur = new_con.cursor()
result1 = new_cur.execute('SELECT rowid, greeting FROM test ORDER BY rowid')
rowid1, greeting1 = result1.fetchone()
print(f'Row {rowid1} greets you: {greeting1}!')
rowid2, greeting2 = result1.fetchone()
print(f'Row {rowid2} greets you: {greeting2}!')
rowid3, greeting3 = result1.fetchone()
print(f'Row {rowid3} greets you: {greeting3}!')
new_cur.execute('DELETE FROM test') # this is TRUNCATE TABLE
new_con.close()
import os
os.remove("cool.db")
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## SQLAlchemy
```
import pandas as pd
from sqlalchemy import create_engine
engine = create_engine("sqlite:///MyDB.sqlite")
table_names = engine.table_names()
con = engine.connect()
df1 = pd.read_sql_query('SELECT * FROM TABLE1', con)
rs = con.execute('SELECT * FROM TABLE1')
df2 = pd.DataFrame(rs.fetchall())
df2.columns = rs.keys()
df3 = pd.DataFrame(rs.fetchmany(size=5))
df3.columns = rs.keys()
```
```
username, database, host, port = "postgres", "sqlda", "localhost", 5432
cnxn_string = f"postgresql+psycopg2://{username}"@{host}:{port}/{database}"
engine = create_engine(cnxn_string)
two_rows = engine.execute("SELECT * FROM customers LIMIT 2;").fetchall()
full_db = pd.read_sql_table("customers", engine)
top10cities_custbygender = """
SELECT 
    city, 
    COUNT(1) AS number_of_customers,         -- count all rows in table
    COUNT(NULLIF(gender, 'M')) AS female,    -- count all NOT matching "M"
    COUNT(NULLIF(gender, 'F')) AS male       -- count all NOT matching "F"
FROM customers
WHERE city IS NOT NULL
GROUP BY 1
ORDER BY 2 DESC LIMIT 10
"""
vc = pd.read_sql_query(top10cities_custbygender, engine)
vc.plot.bar("city", y=["female","male"], title='# of Customers, by Gender/City')
vc.to_sql('top_cities_data', engine, index=False, if_exists='replace')   # WRITE
pd.read_sql_table('top_cities_data', engine)               # READ FROM NEW TABLE
```
### Fast Write to DB via STDIN COPY
```
import csv
from io import StringIO
def gogo(table, conn, keys, data_iter):
    # gets a DBAPI connection that can provide a cursor
    dbapi_conn = conn.connection
    with dbapi_conn.cursor() as cur:
        s_buf = StringIO()
        writer = csv.writer(s_buf)
        writer.writerows(data_iter)
        s_buf.seek(0)
        columns = ", ".join('"{}"'.format(k) for k in keys) 
        if table.schema:
            table_name = '{}.{}'.format(table.schema, table.name) 
        else:   
            table_name = table.name
        sql = 'COPY {} ({}) FROM STDIN WITH CSV'.format(table_name, columns)
        cur.copy_expert(sql=sql, file=s_buf)
top10cities_custbygender = """SELECT city, COUNT(1) AS number_of_customers,
COUNT(NULLIF(gender, 'M')) AS female, COUNT(NULLIF(gender, 'F')) AS male
FROM customers WHERE city IS NOT NULL GROUP BY 1 ORDER BY 2 DESC LIMIT 10"""
vc = pd.read_sql_query(top10cities_custbygender, engine)
vc.to_sql("top10_table", engine, index=False, if_exists='replace' method=gogo)
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
        UPDATE col1 SET col1 = col1 + val1 WHERE col2 = val2;
        INSERT INTO col3 VALUES (TRUE, val1, val2);
        COMMIT;
        EXCEPTION WHEN OTHERS THEN ROLLBACK;
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
- TODO: Move Spark and Elasticsearch to their own sections at end of notes file

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

--------------------------------------------------------------------------------
<!-- Needs work -->
## SQL Examples
### SQL Simple Records Query
```
SHOW DATABASES; 
USE database_name; 
SHOW TABLES; 
DESCRIBE table_name;
SELECT DISTINCT                                    -- distinct: unique **rows**
    date_col, 
    col1 AS Col1,                                  -- rename col1 to Col1
    col2::INTEGER,                                 -- cast col2 as INTEGER col
    col3::TEXT,                                    -- cast col3 as TEXT column
IF(date_col > curdate(), True, False) AS "Future"  -- new column with True/False
CASE 
    WHEN year(date_col) LIKE '19__' THEN '1900s'   -- if 19xx then "1900s"
    WHEN year(date_col) LIKE '20%' THEN '2000s'    -- if 20... then "2000s"
    ELSE 'bad_input'                               -- otherwise "bad_input"
    END AS Century                                 -- end case, name column
FROM table_name 
JOIN table_2 USING(date_col)                       -- cleaner than ON sometimes
WHERE
    (col2 BETWEEN 10 AND 20) AND                   -- 10 <= x <= 20
    (col2 NOT 15) AND                              -- x != 15
    (col3 IN ('irene', 'layla')) AND               -- y = "irene" or y = "layla"
    (year(date_col) LIKE BINARY '201_')            -- 2010, 201M, 201., 201#
ORDER BY col2 ASC, Col1 DESC                       -- notice renamed Col1 here
LIMIT 100;                                         -- return max of 100 rows
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
SELECT SUM(x) + SUM(y) FROM t;     -- sum x, sum y, then sum totals; nulls fine
SELECT SUM(x + y);                 -- rowwise sum; CAREFUL, NULL + 100 = NULL
SELECT MAX(x);
SELECT col1, AVG(col2) AS average FROM t GROUP BY col1 HAVING average > 100;
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

SELECT concat(first_name, " ", last_name) AS Name 
FROM employees 
WHERE 
    hire_date = (SELECT hire_date FROM employees WHERE emp_no = 101010) AND
	emp_no IN (SELECT emp_no FROM dept_emp WHERE to_date > curdate()) AND
    last_name IS NOT NULL;

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
USE employees;
CREATE TEMPORARY TABLE germain_1457.employees_with_departments AS
    SELECT first_name, last_name, departments.dept_name
    FROM employees
    JOIN dept_emp USING(emp_no)
    JOIN departments USING(dept_no);
```

[[Return to Top]](#table-of-contents)







<!-- 
#######                             #     #                             
#       # #    # # #    #  ####     ##    # #    # #      #       ####  
#       #  #  #  # ##   # #    #    # #   # #    # #      #      #      
#####   #   ##   # # #  # #         #  #  # #    # #      #       ####  
#       #   ##   # #  # # #  ###    #   # # #    # #      #           # 
#       #  #  #  # #   ## #    #    #    ## #    # #      #      #    # 
#       # #    # # #    #  ####     #     #  ####  ###### ######  ####  
-->

# Fixing Nulls
```
Nulls are a common thing in real-world datasets for a variety of reasons.
In most cases, we run basic characterization to understand a dataset's nulls.
We have several remedies for nulls, including imputation or removal.
In rare cases, we see patterns in nulls; so we do null pattern characterization.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Basic Null Characterization
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import missingno as msno
# SAMPLE DATA
df = pd.DataFrame({"good1":[9,8,8,7,9,8]*15, "good2":["a","a","a","b","b"]*18, 
    "hi":[None,1,2]*30, "yo":[None,None,1]*30, "sup":[1,2,3]*30, 
    "hey":[1,None,2]*30, "hello":[None,None,1]*30})
# CALCULATE NULL METRICS
avg_c_nulls = int(df.isna().sum().mean())
c_nulls = [(c, df[c].isna().sum(), df[c].isna().sum()*100//len(df)) for c in df]
rowwise_nullct = df.isna().sum(axis=1)
r_nulls = {"counts":rowwise_nullct, "avg":int(rowwise_nullct.mean()),
    "oneplus": (rowwise_nullct > 0).sum(), "zero":(rowwise_nullct == 0).sum()}
dropna_percent_loss = round(1 - (len(df.dropna()) / len(df)), 3)
t_nulls = {"count": df.isna().sum().sum(), "dropna_result": dropna_percent_loss}
# PRINT STATS
print("Total number of missing values across the dataframe:", t_nulls["count"])
print("Average nullcount per col:", avg_c_nulls)
print("Cols with zero nulls:", len([_ for c in c_nulls if c[1] == 0]))
print("Cols with 1+ nulls:", len([_ for c in c_nulls if c[1] > 0]))
print("Average nullcount per row:", r_nulls["avg"])
print("Count of rows with zero nulls:", r_nulls["zero"])
print("Count of rows with at least one null:", r_nulls["oneplus"])
print(f"Data lost if drop all rows w/ nulls: {int(dropna_percent_loss * 100)}%")
# PLOT COL-WISE NULL PERCENTAGE HISTOGRAM
col_percents = pd.Series([c[2] for c in c_nulls])
plt.hist(col_percents[col_percents <= avg_c_nulls], bins=np.arange(0,101,2))
plt.hist(col_percents[col_percents > avg_c_nulls], bins=np.arange(0,101,2))
plt.axvline(avg_c_nulls, ls="--", c="black")
annot_xy = (avg_c_nulls, col_percents.value_counts().max() / 2)
plt.annotate("Average", xy=annot_xy, rotation=90)
plt.title("Percentage-Null By Column, Counts")
plt.xlabel("Null (Percentage)")
plt.ylabel("Count of Columns")
plt.show()
# PLOT ROW-WISE NULL COUNT HISTOGRAM
low_null_mask = rowwise_nullct <= r_nulls["avg"]
plt.hist(rowwise_nullct[low_null_mask], bins=np.arange(0,r_nulls["avg"]*2.1,1))
plt.hist(rowwise_nullct[~low_null_mask], bins=np.arange(0,r_nulls["avg"]*2.1,1))
plt.axvline(r_nulls["avg"], ls="--", c="black")
annot_xy = (r_nulls["avg"], rowwise_nullct.value_counts().max() / 2)
plt.annotate("Average", xy=annot_xy, rotation=90)
plt.title("Row-wise Nullcounts, Counts")
plt.xlabel("Count of Nulls in Row")
plt.ylabel("Count of Rows")
plt.show()
# PLOT MSNO CHARTS
plt.figure(1)
msno.matrix(df)
plt.figure(2)
msno.heatmap(df)
plt.figure(3)
msno.dendrogram(df)
plt.show()
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Null Pattern Characterization
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
df = pd.DataFrame({"good1":[9,8,8,7,9,8]*15, "good2":["a","a","a","b","b"]*18, 
    "hi":[None,1,2]*30, "yo":[None,None,1]*30, "sup":[1,2,3]*30, 
    "hey":[1,None,2]*30, "hello":[None,None,1]*30})
# NULL PATTERN HASHING
gd = ["good1","good2"]  # known drivers of null patterns
df["nullp"] = df.drop(columns=gd).isna().apply(lambda x: hash(tuple(x)), axis=1)
patt_df = df.set_index(drive_cols).sort_index()
# PATTERN HASH ASSESSMENT
cap = {}
for combo in patt_df.index.unique():
    subset = patt_df.loc[combo]
    p_cnt = len(subset["nullp"].unique())
    p_df = subset.isna().drop_duplicates().reset_index(drop=True)
    p_df.drop(columns="nullp", inplace=True)
    cap[combo] = {"p_count":p_cnt, "p_df":p_df, "exact":[], "close":[]}
    if p_cnt == 1:
        continue
    for col in subset.columns:
        if col == "nullp": continue
        valcount = len(subset[col].unique())
        if valcount == 1: continue
        values = subset[[col, "nullp"]].value_counts()
        if len(values) == p_cnt:
            cap[combo]["exact"].append(col)
        elif len(values) in [p_cnt + 1, p_cnt + 2]:
            cap[combo]["close"].append(col)
# PRINT PATTERN HASH ASSESSMENT RESULTS (INSIDE EXPANDABLE TEXT)
from IPython.display import display, HTML
onepatts = [k for k in cap.keys() if cap[k]["p_count"] == 1]
regulars = [k for k in cap.keys() if k not in onepatts]
dets = "<details>x</details>"
print("-"*20, "ONE NULL PATTERN (click each!)", "-"*20)
for p in sorted(onepatts):
    x = f"{cap[p]['p_df'].to_html()}<summary><b>- {p}</b></summary>"
    display(HTML(dets.replace("x",x)))
print("\n" + "-"*20, "NULL PATTERNS (click each!)", "-"*20)
for p in sorted(regulars):
    x = f"DRIVERS: {cap[p]['exact']}<br>POTENTIAL: {cap[p]['close']}"
    x += f"{cap[p]['p_df'].to_html()}<summary><b>- {p}</b></summary>"
    display(HTML(dets.replace("x",x)))
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Handling Nulls
### Null Removal
```
# DROP NULLS
c_nulls = [(c, df[c].isna().sum(), df[c].isna().sum()*100//len(df)) for c in df]
drop_cols = [c[0] for c in c_nulls if c[1] > 20]
print(f"DROPPING THESE COLUMNS (>20% NULL):\n{drop_cols}")
df = df.drop(columns=drop_cols)
nonnull_minimum = int(r_nulls["avg"])  # thresh is minimum number of NON-NULL
df = df.dropna(axis=1, thresh=nonnull_minimum, subset=df.columns[3:6])
```
### Basic Null Imputation
```
from sklearnex import patch_sklearn
patch_sklearn()
# SAMPLE DATA
from seaborn import load_dataset
df = load_dataset("titanic")
X, y = df.drop(columns="survived"), df["survived"]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# IMPUTATION
import pandas as pd
from sklearn.impute import SimpleImputer, Imputer
from fancyimpute import KNN, IterativeImputer   # having issues installing this
imps = dict()
imps["mostfreq"] = SimpleImputer(strategy="most_frequent").fit(X_train)
imps["mean"] = Imputer(missing_values="NaN",strategy="mean",axis=0).fit(X_train)
imps["knn"] = KNN().fit(X_train)
imps["mice"] = IterativeImputer().fit(X_train)
```
### Custom Null Imputation
```
def make_impute_recipe(df, subcats, impute_for):
    np.random.seed(42)
    subcats = [subcats] if type(subcats) is str else subcats
    subcats_str = ",".join(sorted(subcats))
    idx_name = df.index.name if df.index.name != None else "index"
    grp_df = df.reset_index().set_index(subcats).sort_index()
    cat_grps = grp_df.index.unique()
    recipes = {subcats_str:{cat_grp:{} for cat_grp in cat_grps}}
    for grp in cat_grps:
        idx = grp_df.loc[grp,idx_name].tolist()
        subset_df = df.loc[idx,impute_for]
        for col in impute_for:
            overall_mode = df[col].value_counts()
            null_idx = subset_df[subset_df[col].isna()].index
            vc = subset_df[col].value_counts(normalize=True)
            if vc.isna().all(): func = lambda x: np.random.choice(vc.index)
            else: func = lambda x: np.random.choice(vc.index, p=vc.tolist())
            df.loc[null_idx,col] = df.loc[null_idx].apply(func, axis=1)
            if grp not in recipes[subcats_str].keys(): 
                recipes[subcats_str][grp] = dict()
            recipes[subcats_str][grp][col] = vc
    return recipes
def use_impute_recipe(df, recipes):
    np.random.seed(42)
    str_grps = list(recipes.keys())
    idx_name = df.index.name if df.index.name != None else "index"
    cols_done = []
    for str_grp in str_grps:
        cols = str_grp.split(",")
        if cols in cols_done:
            continue
        cols_done.append(cols)
        grp_df = df.reset_index().set_index(cols).sort_index()
        for obs_grp in grp_df.index.unique():
            if obs_grp not in recipes[str_grp].keys():
                print("Couldn't find this grouping in recipes:", obs_grp)
                continue
            idx = grp_df.loc[obs_grp,idx_name].tolist()
            recipe = recipes[str_grp][obs_grp]
            recipe_cols = sorted(list(recipe.keys()))
            subset_df = df.loc[idx, cols + recipe_cols]
            for col in recipe.keys():
                vc = recipe[col]
                if vc.isna().all(): func = lambda x: np.random.choice(vc.index)
                else: func = lambda x: np.random.choice(vc.index, p=vc.tolist())
                null_idx = subset_df.loc[subset_df[col].isna()].index.tolist()
                df.loc[null_idx, col] = df.loc[null_idx].apply(func, axis=1)
    return df
```
```
# SAMPLE DATA
import numpy as np
import pandas as pd
from seaborn import load_dataset
df = load_dataset("titanic")
orig_df = df.copy(deep=True)
X, y = df.drop(columns="survived"), df["survived"]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# SET VARIABLES FOR IMPUTATION RECIPE
subcats = ["class","who"]        # group by these
impute_for = ["deck","embarked"] # impute using groupings' probability dist
# RUN IMPUTATION
d = True
impXtrain, impXval, impXtest = X_train.copy(d), X_val.copy(d), X_test.copy(d)
recipes = make_impute_recipe(impXtrain, subcats, impute_for) # get X_train imp
impXtrain = use_impute_recipe(impXtrain, recipes) # use X_train imp
impXval = use_impute_recipe(impXval, recipes)     # use X_train imp
impXtest = use_impute_recipe(impXtest, recipes)   # use X_train imp
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Evaluation of Null Handling
```
# SET VARIABLES FOR NULL HANDLING EVALUAITON
label_type = "cat"     # or, "cont"
col = "embark_town"
import pandas as pd
import statsmodels.api as sm
results = {}
for imp in imps.keys():
    X_train_imp = sm.add_constant(imps[imp].transform(X_train))
    X_train[col].plot(kind="kde", c="blue", linewidth=3, label=f"Original")
    X_train_imp[col].plot(kind="kde",c="red",linewidth=3,label=f"Impute:{imp}")
    plt.show()
    if label_type == "cat":
        from sklearn.metrics import confusion_matrix, accuracy_score
        model = sm.Logit(y_train, X_train_imp).fit()
        accuracy = (model.predict(X_train_imp) == y_train).mean()
        print(f"{imp} impute: acc={accuracy}")  # r2, larger is better
    if label_type == "cont":
        model = sm.OLS(y_train, X_train_imp).fit()
        print(f"{imp} impute: r2={model.rsquared_adj}")  # r2, larger is better
    results[imp] = model.params
print(pd.DataFrame(results))
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
- TODO: Fix this section, somehow. It's jumbled with misplaced examples.

--------------------------------------------------------------------------------
<!-- Needs work -->
## Dataframe Normalization
### Explode, Melt, Merge, ETC
```
# SPLIT A STRING COLUMN INTO MULTIPLE COLUMNS
df[["newcol1","newcol2"]] = df["col"].str.split(":", expand=True)
# MELT "WIDE" COLUMNS
import pandas as pd
melted = pd.melt(df, id_vars="cat", value_vars=[c for c in df if c != "cat"])
# MERGE TWO DATAFRAMES
df1.merge(df2, left_on="df1c1", right_on="df2c1", how="outer", indicator=True)
```
### "Apply" examples
```
import numpy as np
import pandas as pd
# SAMPLE DATA
df = pd.DataFrame({"good1":[9,8,8,7,9,8]*15, "good2":["a","a","a","b","b"]*18, 
    "hi":[None,1,2]*30, "yo":[None,None,1]*30, "sup":[1,2,3]*30, 
    "hey":[1,None,2]*30, "hello":[None,None,1]*30, "hiya":["x",None,"z"]*30})
# SERIES: PERFORM AN APPLY OPERATION CONDITIONALLY
cond_apply = lambda x: x.upper() if x not in [None, np.nan, "None"] else None
df["newcol0"] = df["hiya"].apply(cond_apply)
# SERIES: PERFORM AN APPLY OPERATION WITH MULTI-COLUMN RETURN
def determine(x):
    if type(x) is not str:
        return pd.Series({"start":None, "end":None, "all":x})
    a = "alive" if x.startswith("born") else "unalive"
    b = "dying" if x.endswith("died") else "undying"
    return pd.Series({"start":a, "end":b, "all":x})
out_df = df["hiya"].apply(determine)
# DATAFRAME: INCORPORATE MULTIPLE COLUMNS
row_calc = lambda row: row["good1"] * row["sup"]
df["number"] = df.apply(row_calc, axis=1)
```
### Nested JSON in DF column, explode to new columns
```
import pandas as pd
from util import flatten_json
json_breakouts = pd.DataFrame(df[json_col].apply(flatten_json).tolist())
df = pd.concat([df, json_breakouts], axis=1)
```
### Nested XML in DF column, explode to new columns
- Note: you can render XML to HTML using its <xsl:stylesheet> with XSLT/xsltproc
    * EX: `xsltproc myXMLfile.xml -o HTMLoutput.html`
```
import pandas as pd
import json
import xmltodict
from util import flatten_json
parse_xml = lambda x: flatten_json(json.loads(json.dumps(xmltodict.parse(x))))
xml_breakouts = pd.DataFrame(df[xml_col].apply(parse_xml).tolist())
df = pd.concat([df, xml_breakouts], axis=1)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Fixing Dataframes at Speed
- AVOID APPENDING ROWS TO DATAFRAMES (SLOW)
- Most numpy/pandas methods are NOT vectorized!!
- Non-numerical DF description: `df.describe(exclude="number")`
- Find duplicates: `df.duplicated(subset=["col1","col2",...], keep="first")`
```
import time
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
df = pd.DataFrame([{"hi":1, "yo":5, "sup":3.2}] * 1_000_000)
# CHECK SPEED OF OPERATION
tic = time.perf_counter()
df["hey"] = df["yo"] * df["sup"]
toc = time.perf_counter()
print(f"Completed in {toc - tic:0.4f} seconds")
# DF.APPLY WITH PROGRESS BAR
from tqdm.auto import tqdm
tqdm.pandas(desc="times100")
s1 = df["hi"].progress_apply(lambda x: x * 100)
df1 = df.progress_apply(lambda x: x[0] * x[1], axis=1)
# CHECK MEMORY ALLOC FOR DF
print(df.__sizeof__())
# UNIQUE COMBOS OF COLUMNS
combos = df.set_index(["hi","yo"]).index.unique() # df.index.get_level_values(i)
for combo in combos:
    mask = (df["hi"] == combo[0]) & (df["yo"] == combo[1])
    print(f"--- {list(combo)} ---\nMax 'Sup':", df[mask]["sup"].max())
# RESHAPE AN ARRAY (FAILS IF NOT POSSIBLE)
array = np.array([1,2,3,4,5,6])  # 6x1 array
array.reshape((2,3))             # 2x3 array
# ZIP TWO NUMPY ARRAYS
zipped = np.column_stack((m.feature_names_in_, m.coef_))
# FIND TOP {x} VALUES OF NUMPY ARRAY
best_idx = np.argpartition(m.feature_importances_, n_feats * -1)[n_feats * -1:]
best_feats = [c for (i, c) in enumerate(m.feature_names_in_) if i in best_idx]
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
- `.pipe(func)` df-wise, `.apply(func)` col/rowwise, `.applymap(func)` cellwise
```
import numpy as np
import pandas as pd
# FIX NUMERICAL FEATURES
log_unskewed = df[["col1","col2","col3"]].apply(lambda x: np.log(x + 1))
df["sqrt_col4"] = df["col4"] ** 0.5  # get to line for linear regression
# SET STRINGS TO NEW CATEGORIES
df["cats"] = df["string"].map({"hi":"greet","yo":"greet","bye":"dismiss"})
df["is_good"] = df["string"].str.startswith("good")
df["is_hot"] = df["string"].str.contains("hot|scalding|scorching|searing")
# CONTINUOUS TO CATEGORICAL
df["ht_cats"] = pd.cut(df["height"], bins=[0,160,190,300], labels=["s","n","t"])
df["spt_cats"] = pd.cut(df["split"], bins=np.arange(0,101,50), labels=["s","l"])
df["wt_cats"] = pd.cut(df["weight"], bins=np.linspace(0,100,3),labels=["l","h"])
df["versus_avg"] = np.where(df["height"] > 175, "Above Avg", "Below Avg")
df["quartiles"] = pd.qcut(df["bmi"], q=4, labels["low","normal","high","obese"])
# ENCODING
df["c1_enc"] = df["col1"].map({"lowest":0,"low-mid":1,"high-mid":2,"highest":3})
df["hat_style"] = pd.get_dummies(df["hat_style"], prefix="hat", drop_first=True)
dummy_df = pd.get_dummies(df["cats1", "cats2"], drop_first=[True, True])
```
### Outliers
- Defined in various ways, ex: z-score, percentage, fixed threshold
- Leverage: how extreme an outlier is
- Influence: what happens to the model when an outlier is removed
    * Cook's Distance is a measure of influence
```
summary = sm_model.get_influence().summary_frame()
df["leverage"] = summary["hat_diag"]
df["cooks_dist"] = summary["cooks_d"]
df.sort_values(by="cooks_dist", ascending=False)  # big values indicate weird
```

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                             
##   ##  ####  #####  ###### #      # #    #  ####  
# # # # #    # #    # #      #      # ##   # #    # 
#  #  # #    # #    # #####  #      # # #  # #      
#     # #    # #    # #      #      # #  # # #  ### 
#     # #    # #    # #      #      # #   ## #    # 
#     #  ####  #####  ###### ###### # #    #  ####  
                                                    
######                                                                  
#     # #####  ###### #####    ##   #####    ##   ##### #  ####  #    # 
#     # #    # #      #    #  #  #  #    #  #  #    #   # #    # ##   # 
######  #    # #####  #    # #    # #    # #    #   #   # #    # # #  # 
#       #####  #      #####  ###### #####  ######   #   # #    # #  # # 
#       #   #  #      #      #    # #   #  #    #   #   # #    # #   ## 
#       #    # ###### #      #    # #    # #    #   #   #  ####  #    # 
-->

# Modeling Preparation
```
After we're done with a phase of exploration, we prepare for modeling.
Ubiquitous in model preparation is scaling; scaling de-weighs features.
We should also consider reducing our dataset to improve model prediction speed.
In classification problems, we might face imbalanced classes; use resampling.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Scaling
- Making 1-10 mean the same to a machine learning model as 1-1000
    * "Equalizes density of continuous features for machine learning"
    * Normalizes Euclidian Distance calcs: `d = sqrt((x1 - x2)^2 + (y1 - y2)^2)`
    * Always use for KNN and K-Means (distance-based); no need for tree-based
    * Split data before scaling; fit on train; transform all splits
- **MinMaxScaler**
    * General use, compresses all values between 0 and 1, sensitive to outliers
- **StandardScaler**
    * Used when data distribution is normal, centers on 0 and limits range
- **RobustScaler**
    * Same as StandardScaler but de-weighs outliers
- **QuantileTransformer**
    * Transform features into uniform or normal dist; de-weighs outliers
    * Get ECDF line -> discretize to uniform dist -> plot on dist
    * Complex; if you really want your data to be normal, then use this
- Not shown (yet): MaxAbsScaler, Normalizer
```
import numpy as np
import pandas as pd
# SCALING
from sklearn.preprocessing import StandardScaler
s = pd.Series(np.random.randint(-3, 4, size=1000))
df = pd.DataFrame({'orig':s, 'squared':s**2, 'abs_x2':s.abs()*2})
encoded_df = df.dropna(thresh=len(df.columns))
encoded_df = df.reset_index(drop=True)
scaler = StandardScaler().fit(encoded_df)
scaled_df = scaler.transform(encoded_df)
# QUANTILE TRANSFORM
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import QuantileTransformer as QT
rng = np.random.RandomState(0)
X = np.sort(rng.normal(loc=0.5, scale=0.25, size=(250, 1)), axis=0)
qt_norm = QT(n_quantiles=10, output_distribution="normal", random_state=0)
X_norm = qt_norm.fit_transform(X)
qt_unif = QT(n_quantiles=10, output_distribution="uniform", random_state=0)
X_unif = qt_unif.fit_transform(X)
plt.plot(X)
plt.plot(X_norm)
plt.plot(X_unif - 1.0)
plt.plot(qt_unif.inverse_transform(X_unif) + 1)
plt.legend(["original", "normalized", "uniform minus 1.0", "inversed plus 1.0"])
plt.show()
```
### Example of Why Scaling is Important: KNN (Without Actually Training KNN!)
```
# GENERATE DATA: TRUCK VS CAR, VEHICLE WEIGHT AND TIRE SIZE METRICS
np.random.seed(0)
trucks_ts = np.abs(np.random.normal(loc=6, scale=4, size=100)) + 22
cars_ts = np.abs(np.random.normal(loc=3, scale=2, size=100))*-1 + 24
plt.figure(figsize=(8,4))
ax = plt.subplot(121)
ax.hist(trucks_ts, alpha=0.5, label="trucks")
ax.hist(cars_ts, alpha=0.5, label="cars")
ax.fill_between([22, trucks_ts.max()], 0, 25, alpha=0.2)
ax.fill_between([cars_ts.min(), 24], 0, 25, alpha=0.2)
plt.legend()
plt.title("Tire Size")
plt.subplot(122)
cars_vw = np.random.normal(loc=3500, scale=400, size=100)
trucks_vw = np.random.normal(loc=4500, scale=400, size=100)
plt.hist(trucks_vw, alpha=0.5, label="trucks", orientation="horizontal")
plt.hist(cars_vw, alpha=0.5, label="cars", orientation="horizontal")
plt.legend()
plt.title("Vehicle Weight")
plt.tight_layout()
plt.show()
# SCALE THE DATA
scaled_cars_vw = cars_vw / 100
scaled_trucks_vw = trucks_vw / 100
# SET XLIM, YLIM TO BE FAIR BETWEEN CHARTING UNSCALED AND SCALED DATA
width_y = scaled_trucks_vw.max() - scaled_cars_vw.min()
mean_x = (cars_ts.sum() + trucks_ts.sum()) / (len(cars_ts) + len(trucks_ts))
min_x, max_x = mean_x - (0.5 * width_y), mean_x + (0.5 * width_y)
min_y, max_y = (scaled_cars_vw.min(), scaled_trucks_vw.max())
# PLOT UNSCALED VS SCALED SCATTERPLOTS; VISUALIIZATION SHOWS STARK DIFFERENCE
plt.figure(figsize=(8,4))
plt.subplot(121)
plt.scatter(x=trucks_ts, y=trucks_vw, label="trucks", alpha=0.5)
plt.scatter(x=cars_ts, y=cars_vw, label="cars", alpha=0.5)
plt.xlim((min_x, max_x))
plt.ylim((4100 - min_y, 4100 + max_y))
plt.plot(28, 4100, "x", color="red", markersize=8, label="unlabeled")
legend = plt.legend()
for label in legend.legend_handles: 
    label.set_alpha(1)
plt.title("Without Scaling")
plt.xlabel("Tire Size")
plt.ylabel("Vehicle Weight (Unscaled)")
plt.subplot(122)
plt.scatter(x=trucks_ts, y=scaled_trucks_vw, label="trucks", alpha=0.5)
plt.scatter(x=cars_ts, y=scaled_cars_vw, label="cars", alpha=0.5)
plt.plot(28, 41, "x", color="red", markersize=8, label="unlabeled")
plt.xlim((min_x, max_x))
plt.ylim((41 - min_y, 41 + max_y))
legend = plt.legend()
for label in legend.legend_handles: 
    label.set_alpha(1)
plt.title("With Scaling")
plt.xlabel("Tire Size")
plt.ylabel("Vehicle Weight (Scaled)")
plt.tight_layout()
plt.savefig("scaling_comparison.png")
plt.show()
# SET UP DATASET FOR EUCLIDEAN DISTANCE CALCULATION
def euclid(tgtxy, labxy):
    distance = (labxy[0] - tgtxy[0])**2 + (labxy[1] - tgtxy[1])** 2
    return distance
unscaled_cars = np.column_stack((cars_ts, cars_vw))
unscaled_trucks = np.column_stack((trucks_ts, trucks_vw))
scaled_cars = np.column_stack((cars_ts, scaled_cars_vw))
scaled_trucks = np.column_stack((trucks_ts, scaled_trucks_vw))
# SET UNLABELED DATAPOINT
unscaled_new = (28, 4100)
scaled_new = (28, 41)
# CALCULATE EUCLIDEAN DISTANCES
unscaled_res = []
for i in range(100):
    euc_uns_car = euclid(unscaled_new, unscaled_cars[i])
    euc_uns_truck = euclid(unscaled_new, unscaled_trucks[i])
    unscaled_res.extend([euc_uns_car,euc_uns_truck]) # even is car, odd is truck
scaled_res = []
for i in range(100):
    euc_s_car = euclid(scaled_new, scaled_cars[i])
    euc_s_truck = euclid(scaled_new, scaled_trucks[i])
    scaled_res.extend([euc_s_car,euc_s_truck])       # even is car, odd is truck
# SET K FOR KNN, FIND NEAREST K NEIGHBORS
k = 5
euc_uns_k_nearest_idx = np.argpartition(unscaled_results, (0,k))[:k]
euc_s_k_nearest_idx = np.argpartition(scaled_results, (0,k))[:k]
uns_votes_truck = len([x for x in euc_uns_k_nearest_idx if x % 2 != 0])
s_votes_truck = len([x for x in euc_s_k_nearest_idx if x % 2 != 0])
print(f"Unscaled data, votes for truck: {uns_votes_truck}/{k} correct")
print(f"Scaled data, votes for truck: {s_votes_truck}/{k} correct")
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Feature Reduction
- Get rid of features without variance (ex: only one unique value)
- Get rid of features with high null count
- Get rid of features that correlate with another feature (multicollinearity)
- Select features using linear regression coefficients (furthest vals from zero)
- Select features using SelectKBest or Recursive Feature Engineering
- Can do feature reduction with LASSO regularization (increases bias/underfit)
    * `LassoCV()` does cross-validation to tune regularization to best one
    * `lcv = LassoCV()`, `lcv.fit(X_train, y_train)`, `lcvmask = lcv.coef_ != 0`
    * use val of `sum(lcvmask)` to set `n_features_to_select` in RFE
- `votes = np.sum([lcvmask, rfmask, gbmask], axis=0)`
    * `mask = votes >= 2` -> `reduced_X = x.loc[:,mask]`
```
# SET UP SAMPLE DATASET
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
df = X_train.copy(deep=True) # expensive copy; you might not want to use this
# STANDARD FEATURE REDUCTION: NUNIQUE, NULLS
col_nonnull = 0.9           # each column that is at least {value*100}% non-null
row_nonnull = 0.9           # each row that is at least {value*100}% non-null
df = df[[col for col in df if df[col].nunique() > 1]]   # cols w/ 2+ unique vals
df = df.dropna(axis=1, thresh=len(df) * col_nonnull)           # col null thresh
df = df.dropna(axis=0, thresh=len(df.columns) * row_nonnull)   # row null thresh
# VARIANCE INFLATION FACTOR (MULTICOLLINEARITY REDUCTION)
vif = 10
from pandas.api.types import is_numeric_dtype as ISNUMERIC
from statsmodels.stats.outliers_influence import variance_inflation_factor as VF
temp = df[[col for col in df if ISNUMERIC(df[col])]]  # VIF needs numerical cols
highvif_cols = [col for (i, col) in enumerate(temp) if VF(temp.values, i) > vif]
df = df.drop(columns=highvif_cols)                    # drop cols with > 10 VIF
dropped_cols = set(X_train.columns).symmetric_difference(set(df.columns))
dropped_cols = sorted(list(dropped_cols), key=lambda x: int(x))  # numeric cols
print(f"Columns dropped: {len(dropped_cols)}\n- " + "\n- ".join(dropped_cols))
```
### Principal Component Analysis (PCA) Dimensionality Reduction
- A dataset has "intrinsic dimension" that can be approximated by feature subset
- Reducing physical dataset size without significant loss of information
    * Use PCA if your dataset has a lot of features (many dozens, hundreds, etc)
    * PCA also de-correlates features by its non-linear feature transformation
- Principal components (PCs) are eigenvectors of the dataset's covariance matrix
    * Covariance: correlation, but in original units (not simply from -1 to +1)
    * Cov matrix: `cov_matrix = np.cov(df, rowvar=False)`
        * 2D: [[COVxx,COVxy],[COVxy,COVyy]], a 2x2 matrix; 3D is 3x3 matrix
    * Eigenvectors/eigenvalues: `eigs = np.linalg.eig(cov_matrix, rowvar=False)`
- Order PCs highest to lowest by their associated eigenvalue (their variance)
    * Solve for lambda: determinant(cov_matrix_2d - lambda[[1,0],[0,1]]) = 0
        * D([[7,3],[3,-1]]) --> ((7-y) * (-1-y)) - ((3-0) * (3-0)) --> y=8, y=-2
        * 3D EX: determinant(cov_matrix_3d - lambda[[1,0,0],[0,1,0],[0,0,1]])
    * Calculate/order PCs: `pca = sklearn.decomposition.PCA().fit_transform(df)`
- Calculate cumulative sum of explained variance ratio for descending-order PCs
    * PC explained variance ratio: PC_eigenvalue / total_variance; between 0-1
- Select PCs by setting a cutoff threshold for this cumulative sum
    * Plot cumulative sum of PC explained variance ratios against count of PCs
    * EX1: Use 11 PCs when cumsum of 11 PCs (723 total PCs) explains 95% of info
    * EX2: Use 20 PCs when cumsum of 20 PCs (165 total PCs) explains 90% of info
- The selected PCs are your dataset, reduced, while still retaining information
- Real world example: plane flying along known flight path (fixed height/path)
    * Variance is small in height/path, but huge in the plane's forward movement
    * PCA will "identify" forward movement as containing significant information
```
# SAMPLE DATA FOR MODEL TESTING
import numpy as np
import pandas as pd
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# RUN PCA, PLOT CUMULATIVE EXPLAINED VARIANCE
from sklearn.decomposition import PCA
pca = PCA().fit(X_train)
explained_variance_ratios = np.concatenate([[0], pca.explained_variance_ratio_])
print("Explained variance ratios:\n", explained_variance_ratios)
plt.plot(explained_variance_ratios.cumsum())
plt.title("Cumulative Explained Variance")
plt.xlabel("Component Count")
plt.ylabel("Explained Variance")
plt.grid()
plt.show()
```
```
# ELBOW METHOD: USE FIVE COMPONENTS, CUMSUM > 90% EXPLAINED VARIANCE
pca5 = PCA(n_components=5)
pca_df = pca5.fit_transform(X_train)
components_df = pd.DataFrame(pca5.components_, columns=X_train.columns)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Resampling
### Resampling for Model Training
- SMOTE: Synthetic Minority Oversampling TEchnique
    * Fit each class's data values, generate more rows for minority class
- Tomek Links
    * Delete from majority class the records that majority/minority overlap on
```
from imblearn.combine import SMOTETomek
def resampler(X_train, y_train):
    """ Use SMOTE+Tomek to eliminate class imbalances for train split """
    smtom = SMOTETomek(random_state=42)
    X_train_res, y_train_res = smtom.fit_resample(X_train, y_train)
    print("Before SMOTE+Tomek applied:", X_train.shape, y_train.shape)
    print("After SMOTE+Tomek applied:", X_train_res.shape, y_train_res.shape)
    return X_train_res, y_train_res    # return resampled train data
```

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
- Categorical columns should be ignored; we can use categories for filtering.
### Goals of Clustering
- Clustering to discover groupings
    * ANOVA test will show if clusters are significantly different
- Clustering to attribute to groupings (multi-class)
- Clustering to determine if in grouping (binary-class; filter train f/ cluster)
- Clustering to add a new feature for modeling
- Clustering to be able to match target (try crosstab of "cluster" and "target")
### Real World Examples of Clustering
- Text: Document classification, summarization, topic modeling, recommendations
    * Hierarchical using Cosine Similarity
- Geographic: Distance from store, crime zones, housing prices
- Marketing: Customer segmentation, market research
- Anomaly Detection: Account takeover, security risk, fraud
- Image Processing: Radiology, security

--------------------------------------------------------------------------------
<!-- Needs work -->
## Clustering Methods
- Scale features and remove outliers as necessary
    * Drop outliers based on domain knowledge; an adult can't weigh 19 pounds
    * If outlier doesn't change results, then feel free to drop
    * If outlier affects results/assumptions, check with/without-outlier results
- Gather background info for initial cluster count choice
    * Hierarchical: Plot, slice dendogram
    * K-Means, DBSCAN: Domain knowledge
- Build, fit, predict using the technique
- Use scatterplots to visually-check results
- Use ANOVA to test clusters statistically
### t-SNE
- Visualize multidimensional clustering in a 2D (default) or 3D plot
- Stochastically modifies the dataset to spread tight data, condense sparse data
- Will sequence differently with new data... not useful for preparation/modeling
```
# t-SNE: EXPLORE POTENTIAL CLUSTERS FROM 3+ DIMENSIONS IN 2D PLOT
tsne = TSNE(learning_rate=50)
transformed = tsne.fit_transform(X_train)
explore = X_train.copy(deep=True)
explore["TSNE_x"] = transformed[:,0]
explore["TSNE_y"] = transformed[:,1]
sns.scatterplot(x="TSNE_x", y="TSNE_y", hue="cat_col", data=explore)
plt.show()  # try different params on TSNE for different clustering!
```
### KMeans
- KMeans: Use euclidian distances, select cluster count subjectively
- Domain knowledge ("3 types"), exploration ("looks like 3"), intertia (elbow)
    * Inertia: sum([distance(x,center) ** 2 for x in cluster])
```
from sklearnex import patch_sklearn
patch_sklearn()
# SAMPLE DATA FOR MODEL TESTING
from ucimlrepo import fetch_ucirepo
wine = fetch_ucirepo(id=109)    # great clustering dataset
X, y = wine.data.features, wine.data.targets["class"]
# PREPARE DATA
from sklearn.model_selection import train_test_split as SPLIT
from sklearn.preprocessing import StandardScaler
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_val, X_test = scaler.transform(X_val), scaler.transform(X_test)
# PERFORM K-MEANS CLUSTERING
from sklearn.cluster import KMeans
min_clusters = 1
max_clusters = 10
step = 1
clustercount_selection = np.arange(min_clusters, max_clusters + 1, step)
results = {}
for i in clustercount_selection:
    print(f"Working on cluster count: {i} (may take some time!)", end="\r")
    kmeans = KMeans(n_clusters=i, random_state=42).fit(X_train)
    clusters = kmeans.predict(X_train)
    results[f"kmeans{i}"] = (kmeans, clusters, kmeans.inertia_)
    print(f"{i} clusters inertia: {kmeans.inertia_}" + " "*100)
# SCREE PLOT: FIND THE CLUSTER COUNT AT THE "ELBOW"
plt.plot([results[f"kmeans{i}"][2] for i in clustercount_selection])
plt.xticks(range(len(clustercount_selection)), clustercount_selection)
plt.title("Elbow for Cluster Count Selection")
plt.xlabel("Cluster count")
plt.ylabel("Inertia")
plt.grid()
plt.show()
```
```
# SELECT CLUSTER COUNT FROM SCREE PLOT AND GET CLUSTER ASSIGNMENTS
selected_count = 3  # selected from elbow method
kmeans, clusterings, inertia = results[f"kmeans{selected_count}"]
X_train_c = pd.Series(clusterings, name="cluster")
vc = X_train_c.value_counts(normalize=True).sort_index()
vc.plot.bar(xlabel="Cluster", ylabel="Proportion", grid=True)
plt.title("Cluster Assignment Proportions")
plt.show()
# LABELED TARGET: VIEW PERFORMANCE OF CLUSTERS USING CROSSTAB
ctab = pd.crosstab(X_train_c, y_train.reset_index(drop=True))
print(ctab)
# PLOT CENTROIDS
X_train = pd.DataFrame(X_train, columns=X.columns)
col1, col2 = X.columns[0], X.columns[1]
with_clusters = pd.concat([X_train, X_train_c], axis=1)
centroids = with_clusters.groupby(["cluster"]).mean()
sns.scatterplot(x=X_train[col1], y=X_train[col2], hue=X_train_c)
centroids.plot.scatter(x=col1, y=col2, marker="x", c"red", s=100, ax=plt.gca())
plt.show()
```
### Hierarchical (Agglomerative)
- Clustering using dendrogram-plotted distances in hierarchy
    * Merge point, y-axis height, is the distance between the two being merged
- https://stackabuse.com/hierarchical-clustering-with-python-and-scikit-learn
    * Each record is a cluster; group clusters until only one cluster remains
    * Agglomerative moves closest two clusters into one cluster, repeatedly
    * This operation walks vertically; long-unmerged clusters become candidates
    * Draw horizontal line at base of longest-unmerged line, count intersections
    * Count of horizontal line's vertical intersections is the cluster count.
- Divisive (not shown) is opposite of agglomerative: single cluster -> many
```
# SAMPLE DATA FOR MODEL TESTING
import numpy as np
import pandas as pd
from ucimlrepo import fetch_ucirepo
wine = fetch_ucirepo(id=109)    # great clustering dataset
X, y = wine.data.features, wine.data.targets["class"]
# PREPARE DATA
from sklearn.model_selection import train_test_split as SPLIT
from sklearn.preprocessing import StandardScaler
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_val, X_test = scaler.transform(X_val), scaler.transform(X_test)
# PLOT DENDROGRAM
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import linkage as lnk, dendrogram as dnd
mergings = lnk(X_train, method="ward")  # makes the hierarchy clusters
dend = dnd(mergings, leaf_rotation=90, leaf_font_size=6)
plt.show()
```
```
# SET HYPERPARAMETERS FROM DENDROGRAM
height = 12
n_clust = 3
# CLUSTER USING HEIGHT FROM DENDROGRAM: BOTTOM OF LONGEST LINE, HORIZONTAL
from scipy.cluster.hierarchy import fcluster
labels1 = fcluster(mergings, height, criterion="distance")  # physical distance
ctab1 = pd.crosstab(labels1, y_train)
print(ctab1)
plt.scatter(x=X_train[:,0], y=X_train[:,1], c=labels1)
plt.title("FCLUSTER")
plt.show()
# CLUSTER USING NUMBER OF CLUSTERS TO HALT AT (DETERMINE BY DENDROGRAM)
from sklearn.cluster import AgglomerativeClustering as AC
ac = AC(n_clusters=n_clust, affinity="euclidean", linkage="ward").fit(X_train)
labels2 = ac.labels_
ctab2 = pd.crosstab(labels2, y_train)
print(ctab2)
plt.scatter(x=X_train[:,0], y=X_train[:,1], c=labels1)
plt.title("AGGLOMERATIVE")
plt.show()
```
### DBSCAN
- DBSCAN: Overlaps of proximity boundaries; great at finding weird data shapes
- Computationally-expensive
```
# DBSCAN
from sklearn.cluster import DBSCAN
dbsc = DBSCAN(eps=.1, min_samples=20).fit(X_train_scaled)
clustered_train = dbsc.transform(X_train_scaled)
print(clustered_df.labels)  # labels; outliers are -1
cluster = clustered_df[clustered_df.labels == cluster_num]
plt.scatter(
    clustered_df, hue="labels"
)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Cluster Analysis
- Classification: use crosstab of clusters and target

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
- NEED: Add PCA example for TruncatedSVD
- Natural Language Toolkit (NLTK): https://www.nltk.org/index.html

--------------------------------------------------------------------------------
<!-- Needs work -->
## Normalizing String Features
- Fuzzy matching: `thefuzz.process.extract("matchme", listlikehere, limit=None)`
    * Return list of match score tuples like: [(string1, score, rank), ...]
### Normalizing for Keyword Analysis
- NEED: Vectorized method for performing this cleaning work
    * NOTE: Add ngram compilation to this
```
# DOWNLOAD DATASETS FOR WORD PLAY
import nltk
nltk.download('stopwords')
nltk.download('vader_lexicon')
nltk.download('punkt')
nltk.download('wordnet')
nltk.download('omw-1.4')
```
```
import nltk
import unicodedata as UNICODE
import re
import numpy as np
np.random.seed(42)
import pandas as pd
# CREATE 'APPLY' FUNCTION
def cleanup(txt, tokenizer, stopwords, wnl=None, ps=None):
    txt = txt.lower()
    txt = UNICODE.normalize('NFKD',txt).encode('ascii','ignore').decode('utf-8')
    txt = re.sub(r"[^a-z0-9'\s]","",txt)          # remove special characters
    words = tokenizer.tokenize(txt)               # tokenize words
    filtered = [word for word in words if word not in stopwords]
    if wnl is not None:  chopped = [wnl.lemmatize(word) for word in filtered]
    elif ps is not None: chopped = [ps.stem(word) for word in filtered]
    else:                chopped = filtered
    clean_text = " ".join(chopped)
    return clean_text
# CREATE SAMPLE DATA FOR CLEANUP
tokenizer = nltk.tokenize.TweetTokenizer()
ps = nltk.porter.PorterStemmer()
wnl = nltk.stem.WordNetLemmatizer()
stopwords = nltk.corpus.stopwords.words("english")
stopwords.append("coolword")
stopwords.remove("coolword")
word_array = np.random.choice(["red.","the?","happy's","$big times$"],size=5000)
s = pd.DataFrame(word_array.reshape(1000,5)).apply(lambda x: " ".join(x),axis=1)
# RUN CLEANUP: LEMMATIZATION, OR, WORD STEMS
clean_lemmad = s.apply(lambda txt: cleanup(txt, tokenizer, stopwords, wnl=wnl))
clean_stemmed = s.apply(lambda txt: cleanup(txt, tokenizer, stopwords, ps=ps))
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Keywords and Sentiment
### Keyword Analysis
- Cool: https://github.com/amueller/word_cloud/blob/master/examples/parrot.py
```
import pandas as pd
import my_util         # import "cleanup" function from normalize-string section
word_array = np.random.choice(["red.","the?","happy's","$big times$"],size=5000)
s = pd.DataFrame(word_array.reshape(1000,5)).apply(lambda x: " ".join(x),axis=1)
tgt = pd.Series(np.random.choice(["spam","ham"], size=1000, p=[0.2,0.8]))
s.name, tgt.name = "text", "target"
df = pd.concat([s, tgt], axis=1)
# SCATTERPLOT OF EACH ROW'S CHARACTER COUNT BY WORD COUNT
df["content_length"] = df["text"].apply(len)
df["word_count"] = df["text"].str.split(" ").apply(len)
sns.relplot(x=df["content_length"], y=df["word_count"], hue=df["target"])
plt.title("Word Count vs Char Count, by Class")
plt.show()
# STACKED BAR CHART OF CLASS PROPORTIONS BY WORD (PERFORM NORMALIZATION FIRST)
tok = nltk.tokenize.TweetTokenizer()
ps = nltk.porter.PorterStemmer()
wnl = nltk.stem.WordNetLemmatizer()
stops = nltk.corpus.stopwords.words("english")
df["clean"] = df["text"].apply(lambda t: my_util.cleanup(t,tok,stops,wnl=wnl))
all_words  = df["clean"].str.cat(sep=" ")
spam_words = df[df["target"] == "spam"]["clean"].str.cat(sep=" ")
ham_words  = df[df["target"] == "ham"]["clean"].str.cat(sep=" ")
all_cts  = pd.Series(all_words.split(" ")).value_counts().rename("all")
spam_cts = pd.Series(spam_words.split(" ")).value_counts().rename("spam")
ham_cts  = pd.Series(ham_words.split(" ")).value_counts().rename("ham")
word_cts = pd.concat([all_cts, spam_cts, ham_cts], axis=1)
word_cts['p_spam'] = word_cts["spam"] / word_cts["all"]
word_cts['p_ham'] = word_cts["ham"] / word_cts["all"]
word_cts[['p_spam','p_ham']].tail().sort_values('p_ham').plot.barh(stacked=True)
plt.title("Class Proportion by Word")
plt.show()
# PLOT A WORDCLOUD
from os import path
from PIL import Image
import numpy as np
import matplotlib.pyplot as plt
import os
from wordcloud import WordCloud, STOPWORDS
# BUILD THE WORDCLOUD AND SAVE TO FILE
mask = np.array(Image.open("blackwhite.png")) # white-black img, words in black
wc = WordCloud(
    background_color="white",    # set the color behind the words
    max_words=2000,              # set max words in wordcloud
    mask=mask,                   # choose image to use as wordcloud mask
    contour_width=3,             # make background thicker (think: thin lines)
    colormap="Blues",            # set words to Matplotlib colormap
    # color_func=lambda *args, **kwargs: "black",   # set all words to one color
    contour_color='steelblue',   # background: white -> steelblue
    collocations=False           # True: show a bigram if see enough of it
)
wc.generate(df["clean"].dropna().str.cat(sep=" ").replace("'s",""))  # gen cloud
# wc.to_file("output.png")                    # store to file
# SHOW THE WORDCLOUD
plt.imshow(wc, interpolation='bilinear')
plt.axis("off")
plt.title("Wordcloud, Unique Words")
plt.show()
```
### Sentiment Analysis
- Afinn and Vader are sentiment analysis tools based on social media
- Sentiment is best analyzed without normalization
```
# SINGULAR SENTIMENT ANALYSIS
import nltk
from nltk.sentiment import SentimentIntensityAnalyzer
sia = SentimentIntensityAnalyzer()
text = "Hello my name is Bob. You look great!"
sentences = nltk.sent_tokenize(text)
for sentence in sentences:
    score = sia.polarity_scores(sentence)
    print(f"--SCORE: {score} for SENTENCE:--\n", sentence)
# VECTORIZED SENTIMENT ANALYSIS
records = ["Hello, I'm Bob. You look great!", "I'm Bob too! How weird..."]
s1 = pd.Series(records, name="text").apply(nltk.sent_tokenize).explode()
df = s1.reset_index().rename(columns={"index":"step"})
df = pd.concat([df, pd.json_normalize(s1.apply(sia.polarity_scores))], axis=1)
df
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## NLP for Prediction
- NEED: Sparse matrices (bag of words) efficiently: `scipy.sparse.csr_matrix`
    * Not compatible with PCA
- NEED: Apply SelectKBest or RFE to select most-predictive words for outcomes
- Count Vectorization: 
    * Each column is a word, each row is an record, each value is a **count**
- TFIDF Vectorization (Term Frequency * Inverse Document Frequency): 
    * Each column is a word, each row is an record, each value is a **weight**
    * TF is how often a word shows; IDF is how unique the word is in all records
    * Calculation identifies word importance (weight) and filters out stopwords
```
# PERFORM PREP AND SPLIT BEFORE FOLLOWING THE STEPS
do_CV = False
if do_CV:
    # COUNT VECTORIZATION
    vectorizer = sklearn.feature_extraction.text.CountVectorizer()
    bow = vectorizer.fit_transform(train.clean_text)        # use y_train
    print(vectorizer.vocabulary_)                           # show word counts
else:
    # TFIDF VECTORIZATION
    vectorizer = sklearn.feature_extraction.text.TfidfVectorizer()
    bow = vectorizer.fit_transform(train["clean_text"])     # use y_train
    bow = pd.DataFrame(bow.todense(), columns=vectorizer.get_feature_names())
    word_imps = dict(zip(vectorizer.get_feature_names(), vectorizer.idf_))
    print(pd.Series(word_importances).sort_values())        # show importances
# DECISION TREE
tree = DecisionTreeClassifier(max_depth=5)
tree.fit(bow, y_train)
y_train_preds = tree.predict(bow)
features = dict(zip(vectorizer.get_feature_names(), tree.feature_importances_))
print(pd.Series(features).sort_values().tail(5))            # top-5 features
```
```
from sklearn.decomposition import TruncatedSVD
model = TruncatedSVD(n_components=3)
model.fit(documents)  # documents is scipy csr_matrix
transformed = model.transform(documents)
```
### Non-Negative Matrix Factorization (NMF)
- Break down a matrix into "metafeatures" describing the matrix
- Better than PCA for NLP because it handles sparse non-negative matrices better
    * A bag of words has extremely low variance and most values are already zero
    * NMF retains the data structure but reduces the dataset
- NMF approximates a V matrix by two smaller matrices, W and H
    * V matrix: original data; each column is observation, each row is feature
    * W matrix: approximates data; each column is basis vector
    * H matrix: runs (activates) W matrix; each column is "weights" or "gains"
    * All three matrices must have non-negative values
- The math is complicated, and technically, you can't solve for smallest W and H
```
# SILENCE CONVERGENCE WARNING FOR LIMIT ON ITERATIONS
import warnings
from sklearn.exceptions import ConvergenceWarning as CW
warnings.filterwarnings("ignore", category=CW)
# GRAB DATASET
from sklearn.datasets import fetch_20newsgroups
cats = ['alt.atheism','soc.religion.christian','comp.graphics','sci.med']
kws = {"categories":cats,"shuffle":True,"random_state":42}
twenty_train = fetch_20newsgroups(subset="train", **kws)
twenty_test = fetch_20newsgroups(subset="test", **kws)
# CREATE TFIDF-VECTORIZED BAG OF WORDS
from sklearn.feature_extraction.text import CountVectorizer, TfidfTransformer
count_vect = CountVectorizer()
X_train_counts = count_vect.fit_transform(twenty_train.data)
X_test_counts = count_vect.transform(twenty_test.data)
go_tfidf = TfidfTransformer()
X_train_tfidf = go_tfidf.fit_transform(X_train_counts)
X_test_tfidf = go_tfidf.transform(X_test_counts)
# PERFORM NON-NEGATIVE MATRIX FACTORIZATION (NMF)
from sklearn.decomposition import NMF
from sklearn.preprocessing import normalize
nmf = NMF(n_components=4, random_state=42).fit(X_train_tfidf)
n_comps = int(nmf.reconstruction_err_)   # number of topics; consider manual num
nmf = NMF(n_components=n_comps, random_state=42).fit(X_train_tfidf)
nmf_train = normalize(nmf.transform(X_train_tfidf))
nmf_test = normalize(nmf.transform(X_test_tfidf))
# TRAIN CLASSIFIER
from sklearn.naive_bayes import MultinomialNB
clf = MultinomialNB().fit(nmf_train, twenty_train.target)
train_preds = clf.predict(nmf_train)
accuracy = (train_preds == twenty_train.target).mean()
print(f"Model accuracy after CV, TFIDF, NMF, MNB: {accuracy:0.3f}\n\n" + "-"*30)
# COSINE SIMILARITY OF ONE RECORD TO ALL OTHER RECORDS
import numpy as np
record_num = 23
record_row = nmf_train[record_num,:]
record_class = twenty_train.target_names[twenty_train.target[record_num]]
similarities = nmf_train.dot(record_row)
best10idx = np.argpartition(similarities, -10)[-10:]
print(twenty_train.data[record_num], "\n"*3 + "-"*30 + "\n"*3)
for i in best10idx:
    print(twenty_train.data[i], "\n"*3 + "-"*30 + "\n"*3)
```

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                           
#     # ######  ####   ####  #####    ##   ##### #   ##   #      
#       #      #    # #      #    #  #  #    #   #  #  #  #      
#  #### #####  #    #  ####  #    # #    #   #   # #    # #      
#     # #      #    #      # #####  ######   #   # ###### #      
#     # #      #    # #    # #      #    #   #   # #    # #      
 #####  ######  ####   ####  #      #    #   #   # #    # ###### 
-->

# Geospatial
```
Latitudes, longitudes, coordinates, and trends.
```

--------------------------------------------------------------------------------
<!-- Needs Work -->
## Geospatial Analysis
### Geospatial Data
- Coord Reference System (CRS) baselines the coordinates for plotting
    * EPSG:4326 in decimal degrees; used by Google Earth
    * EPSG:3857 in meters; used by Google Maps, Bing Maps, Open Street Maps
- RASTER file: grid; great at doing semi-3D plotting like topographical map
- VECTOR file: points, lines, polygons; great for drawing
- Shapefiles contain geospatial geometry that we can plot
    * SHP contains geometry, DBF holds attrs, SHX links attrs and geometry
- GeoJSON is a modern version that combines SHP, DBF, SHX into one file
- Fiona: API between Python and OpenGIS Simple Features Reference, is VECTORs
- GDAL: Geospatial Data Abstraction Library, is RASTERs
- Chloropleth: Thematic map with color variation to differentiate regions
### Geospatials in Geopandas
- `geopandas` is an excellent library for geospatial work
- A cell in a row can contain a point, line, or polygon; `geo_df.loc[0, 'poly']`
    * Printing the cell will result in object with coord array for ex: line
```
import folium
district1_map = folium.Map(location=[48.858373,2.292292], zoom_start=12)
folium.GeoJson(district_one.geometry).add_to(district1_map)
for row in df.iterrows():
    location, popup = [row["lat"], vals["lng"]], row["popup"]
    marker = folium.Marker(location=location, popup=popup)
    marker.add_to(district1_map)
display(district1_map)
import geopandas as gpd
from shapely.geometry import Point
geo_df1 = gpd.read_file('my_map.shp')
geo_df2 = gpd.read_file('geo.geojson')
schools["geoms"] = schools.apply(lambda x: Point((x.lng, x.lat)), axis=1)
schools_crs = {"init": "epsg:4326"}
geo_df3 = gpd.GeoDataFrame(schools, src=schools_crs, geometry=schools.geoms)
geo_df3.changed_crs = geo_df3.geoms.to_crs(epsg="3857")
leg_kwds = {"title":"District Number", "loc":"upper left", 
            "bbox_to_anchor":(1,1.03), "n_col":3}
geo_df1.plot(column="district", cmap="Set3", legend=True, legend_kws=leg_kwds)
plt.title("Council Districts")
plt.show()
schools["polygon_area"] = schools.geometry.area            # calc on each row
schools["polygon_center"] = schools.geometry.centroid      # calc on each row
schools["distance_from_other"] = schools.geometry.distance(other)  # each row
```
```
import geopandas as gpd
# initialize two geodataframes and join the plots
d1 = gpd.sjoin(gdf1, gdf2, op="contains")  # gdf2 entirely inside gdf1 boundary
d2 = gpd.sjoin(gdf1, gdf2, op="intersect") # gdf2 is inside or on gdf1 boundary
d3 = gpd.sjoin(gdf2, gdf1, op="within")    # backwards "contains"
print(len(d1))                             # number of gdf2 things inside gdf1
```
```
import folium
nashville = [36.1636, -86.7823]
m = folium.Map(location=nashville, zoom_start=10)
folium.Cloropleth(
    geo_data=districts_with_counts,
    name="geometry",
    data=districts_with_counts,
    columns=["district","school_density"],
    key_on="feature_properties.district",
    fill_color="YlGn",
    fill_opacity=0.75,
    line_opacity=0.5,
    legend_name="Schools per km squared by School District
).add_to(m)
```
### Shapely
- Set correct coord reference system for Geopandas for max accuracy

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
```
Statistical analysis is vital for verifying our work.
We can calculate probabilities to see whether outcomes are rare or common.
We can run hypothesis tests to understand whether our findings are significant.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Probability
- Chances and rates
- Probability of outcome: P(outcome) = (count_get_outcome) / (count_get_any)
    * P(heads flip) = (1) / (2) -> (1) / (2) -> ... (independent events)
    * P(name drawn) = (1) / (4) -> (1) / (3) -> ... (dependent events)
- "Total Probability Law": Add each probability together
    * Overall chance of defect: (1% * 50%) + (2% * 25%) + (3% * 25%) = 0.0175
- "Bayes Theorem": P(A|B) = (P(B|A) * P(A)) / P(B)
    * Probability that A is true given B is true: P(A|B)
    * Probability that you survived if you had a gun: P(lived|gun)
    * Probability that you had a gun if you survived: P(gun|lived)
    * You know: P(lived) = 6/10, P(gun) = 3/10, P(gun|lived) = 2/6
    * Bayes: P(lived|gun) = ((2/6) * (6/10)) / (3/10) -> (2/10) / (3/10) -> 2/3
- Get P(A|B) of dataset: `(df["A"] & df["B"]).sum() / (df["B"].sum() / len(df))`
    * Get P(A) given 2+ cols: `(df["A"] & mask).sum() / (mask.sum() / len(df))`
    * Low probability here indicates "A" outcomes are anomalous!
### Building Distributions
- "Law of Large Numbers": larger sample brings sample mean closer to theoretical
- Probability distribution: chart of outcomes and their chances
- Probability from distribution: area
    * Chance of rolling 1 or 2 from 6: 2/6 of the distribution (1/3)
- Theoretical Distribution: `dist = stats.recipe(params)`
    * Probability from distribution: `dist.method()`
- Rolls from Theoretical Distribution: `dist = stats.recipe(params).rvs(size=x)`
    * Set size to array (`(3,4)`) instead of `x` to do `(simulations, trials)`
    * Alternate: `np.random.choice(avail_options, size=rolls, p=[p1, p2, ...])`
### Theoretical Distributions from Parameters
- Equal likelihood of all outcomes: Uniform (dice rolls)
    * Not very useful for our purposes
    * Recipe: `stats.randint.rvs(gte_val, lt_val, size=(10,10))`
    * P(A) = 1 / len(Options)
- Two outcomes: Binomial (coin flips)
    * Not very useful for our purposes
    * Recipe: `stats.binom.rvs(tries, chance_to_win, size=(10,10))`
    * P(A) = `stats.binom.pmf(wintarget, tries, chance_to_win)` (discrete)
- Outcomes congregating on one value: Normal (bell curve)
    * Very useful if we expect a normal distribution for something
    * Recipe: `stats.norm.rvs(center, size_one_stdev, size=(10,10))`
    * P(A) = `stats.norm.pdf(mark, center, size_one_stdev)` (continuous)
    * Between points: `stats.norm.cdf(0) - stats.norm.cdf(-1)` (AUC)
    * Strategy: Identify mean and stdev, build distribution
    * Central Limit Theorem: increase sample size, stats metrics get more normal
- Events over time: Poisson (probability of an outcome in a time interval)
    * Useful for time-related events; mu is average events per time interval
        * With Poisson, lambda and mu are the same value
    * Recipe: `stats.poisson.rvs(mu, size=(10,10))`
    * P(A) = `stats.poisson.pmf(x, mu)` (discrete)
    * Between counts: `stats.poisson.cdf(5, 2) - stats.poisson.cdf(3, 2)` (AUC)
        * "3 to 5 events when the average is 2 events for that time interval"
    * Strategy: Identify avg event count for time interval, build distribution
    * Peak of distribution is always the lambda value (average count)
- Time between events: Exponential (probability of wait time for Poisson event)
    * Useful for time-related events; lambda is average events per time interval
    * Recipe: `stats.expon.rvs(scale=events_per_interval, size=(10,10))`
    * P(A) = `stats.expon.pdf(x, scale=events_per_interval)` (continuous)
    * Between times: `stats.expon.cdf(4, scale=2) - stats.expon.cdf(1, scale=2)`
        * "Between minute 1 and minute 4 when events are (avg) twice per minute"
    * Strategy: Identify avg event count for time interval, build distribution
- Failed attempts: Geometric (probability of consecutive failures)
    * Useful when calculating probability of failing x times (CDF)
    * Recipe: `stats.geom.rvs(success_chance, size=(10,10))`
    * P(A): `stats.geom.pmf(attempt_when_successful, fail_chance)`
    * Between attempts: `stats.geom.cdf(4, 0.3) - stats.geom.cdf(2, 0.3)`
        * "2 to 4 attempts when the success chance is 30%"
    * Strategy: Groupby each actor, avg successful attempt #, build distribution
- Wider normal distribution: t-Distribution (sharper peak, wider flanges)
    * Increasing degrees of freedom makes it look more like normal distribution
- Right-skewed for normal: Log-Normal (0 to infinite, normal)
    * When you can't go below a number, but the distribution is basically normal
    * Lots of real-world examples for this
- Lots more distributions... check scipy documentation for stats module
### Methods for Distributions
- Nice chart: https://ds.codeup.com/stats/pdf_pmf_cdf_ppf_sf_isf.png
- Probability from Theoretical Distribution: `dist.method()`
    * Chance of specific outcome: `dist.pmf(discrete)`, `dist.pdf(continuous)`
    * Area larger than a mark: `dist.sf(num)`, `dist.isf(proportion)`
    * Area less than or equal to a mark: `dist.cdf(num)`, `dist.ppf(proportion)`
- Probability from Discrete Records: `vc = s.value_counts(normalize=True)`
    * Chance of specific outcome: `vc.loc[x] if x in vc.index else "Not found"`
    * CDF and SF: `cdf = vc.loc[(vc.index <= x)].sum()`, `sf = 1 - cdf`
    * P(Between Marks): `vc.loc[(vc.index > left) & (vc.index < right)].sum()`
- Probability from Continuous Records: `t = s.rank(method='average', pct=True)`
    * Chance of specific outcome: draw density and plot point? hmm. thinking...
    * Compare to value: `cdf = (s <= x).mean()`, `sf = 1 - cdf`
- Proportions of Outcomes: `vc = df[["A","B"]].value_counts(normalize=True)`
    * `vc.loc[("lived","gun")]` (previous step orders multi-index as "A","B")
### Likelihood from Probabilities
- Probability: probability, given the model, that a datapoint is predicted
- Likelihood: probability, given the data, that a model could output the data
```
# HOW MODELS SELECT BEST FIT LINE
mu_guess = np.mean(sample_distances)
sigma_guess = np.std(sample_distances)
probs = np.zeros(len(sample_distances))
for n, distance in enumerate(sample_distances):
    coeff_part = 1/(np.sqrt(2 * np.pi * sigma_guess**2))
    exp_part = np.exp( - (x - mu_guess)**2 / (2 * sigma_guess**2))
    probs[n] = coeff_part * exp_part
likelihood = np.product(probs)
loglikelihood = np.sum(np.log(probs))
# MAXIMUM LIKELIHOOD ESTIMATION
low_guess = sample_mean - 2*samp_stdev
high_guess = sample_mean + 2*samp_stdev
mu_guesses = np.linspace(low_guess, high_guess, 101)
# LOGLIKELIHOOD FOR EACH GUESS
loglikelihoods = np.zeros(len(mu_guesses))
for n, guess in enumerate(mu_guesses):
    loglikelihoods[n] = compute_loglikelihood(samp_distances, guess, samp_stdev)
max_loglikelihood = np.max(loglikelihoods)
best_mu = mu_guesses[loglikelihoods == max_loglikelihood]
```
### Probabilities for KDE line, where KDE is built from numerical observations
```
# SET RANGE TO CALCULATE PROBABILITY FOR
left = -3
right = 7
# CREATE MISSHAPEN DATASET
np.random.seed(1)
s = stats.norm.rvs(loc=2, scale=12, size=10_000, random_state=1).tolist()
s.extend(stats.norm.rvs(loc=20, scale=4, size=5_000, random_state=1).tolist())
s.extend(np.random.choice([-10, -5], p=[0.7,0.3], size=1_000).tolist())
# CALCULATE KDE OF DATASET
hist = sns.histplot(s, kde=True)
inp, out = hist.lines[0].get_data()
plt.axvline(left, c="red")
plt.axvline(right, c="red")
# SLICE KDE BASED ON SELECTED RANGE
inp_left, out_left = inp[inp <= left], out[inp <= left]
inp_right, out_right = inp[inp <= right], out[inp <= right]
# GET CDF OF EACH SELECTED LIMIT
from sklearn.metrics import auc
full_area = auc(inp, out)
cdf_gt = auc(inp_left, out_left)
cdf_lte = auc(inp_right, out_right)
# CALCULATE PROBABILITY OF BEING BETWEEN MARKS
prob_between = (cdf_lte - cdf_gt) / full_area
print(f"Probability of being between {left} and {right}: {prob_between}")
# PROBABILITY OF ONE MARK
loc_nearest_right = np.abs(inp - right).argmin()
loc_nearest_left = np.abs(inp - left).argmin()
prob_right = out[loc_nearest_right] / len(s)
prob_left = out[loc_nearest_left] / len(s)
print(f"Probability of {right}: {prob_right}")
print(f"Probability of {left}: {prob_left}")
```

--------------------------------------------------------------------------------
<!-- Needs Work -->
## Hypothesis Testing
- X categoricals against y categorical: chi2; independent cells, cells are > 5
    * Degree of Freedom: (num_cols - 1) * (num_rows - 1)
- X categoricals against y continuous: t-test; 1samp/2samp, normality, variance
    * One-sample t-test: when comparing a sample to a general population mean
    * Two-sample t-test: when comparing a distinct sample to another sample
- X conts against X conts or the y cont: corr; linearity, normality / monotonic
    * Correlation statistic: strength and direction of correlation (-1.0 to 1.0)
    * Strength indicators: similar rate of change, both monotonic / polytonic
    * Always plot correlations to check for linearity
    * Can transform one or both: `np.log(col)`, `np.sqrt(col)`, `1 / col`, more
- ERRORS: Type I (falsely-reject null), Type II (falsely-accept null)
    * False Positive Rate: probability of a Type I error
    * False Negative Rate: probability of a Type II error
```
import pandas as pd
from scipy import stats
# SINGLE COLUMN METRICS
sum_all_squares = ((col - col.mean()) ** 2).sum()
sum_samp_squares = ((samp - samp.mean()) ** 2).sum()
variance_of_all = sum_all_squares / col.count()           # np.var(col)
variance_of_samp = sum_samp_squares / (samp.count() - 1)  # np.var(samp, ddof=1)
stdev_of_all = variance_of_all ** 0.5                     # np.std(col)
stdev_of_samp = variance_of_samp ** 0.5                   # np.std(samp, ddof=1)
zscore = stats.zscore(values)      # "demeaning vectors"; # of STDEVs from mean
mean_absolute_deviation = np.mean(np.abs(col - col.mean()))
quantile = np.quantile(col, 0.5)
quartiles = np.quantile(col, np.linspace(0, 1, 5))  # [0, 0.25, 0.5, 0.75, 1]
quintiles = np.quantile(col, np.linspace(0, 1, 6))  # [0, 0.2, 0.4, 0.6, 0.8, 1]
q1, q3 = np.quantile(col, 0.25), np.quantile(col, 0.75)
iqr = q3 - q1                                             # stats.iqr(col)
outliers = (col < (q1 - (1.5 * iqr))) | (col > (q3 + (1.5 * iqr)))
multiple_metrics = col.describe()
# MULTI COLUMN METRICS
pivot_table = df.pivot_table(index="col1", columns="col2", values="col3")
category_metrics = df.groupby("col1")[["col2","col3"]].agg(["mean","max","std"])
crosstab = pd.crosstab(df.col1, df.col2, margins=True, normalize=True)
corr = df[[col1, col2]].corr()
# PASSED NORMALITY AND OTHER ASSUMPTIONS (PARAMETRIC TESTS)
t, p = stats.f_oneway(samp1.y, samp2.y, samp3.y, ...)  # multiple "check" ttests
t, p = stats.ttest_ind(samp1.y, samp2.y, alternative=) # independence from other
t, p = stats.ttest_1samp(samp1.y, pop.y, alternative=) # independence from all
t, p = stats.ttest_rel(past.y, future.y, alternative=) # independence from self
corr, p = stats.pearsonr(col1, col2)  # correlation between two linear cont cols
chi2, p, degf, expected = stats.chi2_contingency(observed_crosstab)
# DID NOT PASS NORMALITY (NON-PARAMETRIC TESTS)
t, p = stats.kruskal(samp1.y, samp2.y, samp3.y, ...)   # multiple "check" ttests
t, p = stats.mannwhitneyu(samp1.y, samp2.y, alternative=) # one- or two-sample
t, p = stats.wilcoxon(past.y, future.y, alternative=)     # paired
corr, p = stats.spearmanr(col1, col2)    # corr between ord/monotonic-cont cols
chi2, p, degf, expected = stats.chi2_contingency(observed_crosstab)
```
### Marketing
```
import scikitplot as skplt
import matplotlib.pyplot as plt
# CUMULATIVE GAINS: HOW MANY SAMPLES TO GET A CERTAIN AMOUNT OF PREDICTION 1
skplt.metrics.plot_cumulative_gain(actuals, preds) # preds are 0 or 1
plt.show()
# LIFT CURVE: MODEL'S PERFORMANCE ABOVE AVG TO TARGET PREDICTION 1 BY THRESH
skplt.metrics.plot_lift_curve(actuals, preds)
plt.show()
# PER-GROUP OUTCOMES (INCIDENCE): % OF TARGETS IN EACH GROUP (CAT/CONT GROUPS!)
```
### Do Statistics!!
```
import pandas as pd
from scipy import stats
def test_normality(s):
    """Print results of normality test; is the Series normally distributed?"""
    result = stats.anderson(s, 'norm')
    if (result.statistic < result.critical_values[2]): # index 2 is p_value=0.05
        print(f"Column '{s.name}' has normal distribution!")
        return True
    print(s.name, "does not have normal distribution!")
    return False
def run_chi2(x, y):
    """Print results of chi2; x, y are Series"""
    observed_crosstab = pd.crosstab(x, y, margins=True)
    if (observed_crosstab < 5).sum().sum() == 0:
        chi2, p, degf, expected = stats.chi2_contingency(observed_crosstab)
        if p < 0.05:
            print(f"{x.name} and {y.name} have dependent relationship!")
def run_ttest(x, y, normal_y=False):
    """Print results of ttests; x, y are Series; normal_y flags normal dist"""
    samples = {category:y[x == category] for category in x.unique()}
    stat, p = stats.levene(*samples.values())  # equal variance test
    if p < 0.05 or normal_y is False:  # if can't do parametric t-test
        for key in samples:
            drops = samples[key].index
            t, p = stats.mannwhitneyu(samples[key], y.drop(drops))  # two-sample
            if p < 0.05:
                direction = "statistically " + "greater" if t > 0 else "less"
                print(f"{key} is {direction} than other category(s). (>95%)")
    else:                         # if *can* do parametric t-test
        for key in samples:
            drops = samples[key].index
            t, p = stats.ttest_ind(samples[key], y.drop(drops))  # two-sample
            if p < 0.05:
                direction = "statistically " + "greater" if t > 0 else "less"
                print(f"{key} is {direction} than other category(s). (>95%)")
def run_corr(col1, col2, pearsonr=False):
    """Print results of corr tests; col1, col2 are Series; pearsonr is flag"""
    if pearsonr is True:
        corr, p = stats.pearsonr(col1, col2)  # normal, linear
    else:
        corr, p = stats.spearmanr(col1, col2) # monotonic
    if p < 0.05:
        print(f"{col1.name} correlates with {col2.name}! (>95%)")
def do_stats(df, y=None, chi2s=None, ttests=None, corrs=None, pearsonr=False):
    """Run chi2, ttest, and corr tests using a dataframe and column names"""
    print("Starting tests...")
    if y is not None:
        numeric_y = df[y].dtype.kind in 'biufc'
        if numeric_y:
            normal_y = test_normality(df[y])  # returns bool
        if chi2s is not None:
            for col in chi2s:
                run_chi2(df[col], df[y])
        if ttests is not None and numeric_y: 
            for col in ttests:
                run_ttest(df[col], df[y], normal_y)
        if corrs is not None: 
            for col in corrs:
                run_corr(df[col], df[y], pearsonr is True)
    elif len(corrs) >= 2:
        print("No target! Can only do correlation tests on independent vars!")
        tried = []
        for col1 in corrs:
            for col2 in corrs:
                cond1 = col1 != col2
                cond2 = (col1, col2) not in tried
                cond3 = (col2, col1) not in tried
                if cond1 and cond2 and cond3:
                    run_corr(df[col1], df[col2], pearsonr is True)
                    tried.append((col1, col2))
    else:
        print("Please select column labels for tests!")
    print("Tests complete! All significant results are shown; none may show!")
```
```
import numpy as np
s1 = np.random.choice(list("gattaca"), size=70000)
s2 = pd.Series(list("agttatg")*10000)
s3 = np.random.normal(3, 1, size=70000)
df = pd.DataFrame({"hi":s1, "yo":s2, "sup":s3})
do_stats(df, y="hi", chi2s=["yo"])                        # run chi2 test
do_stats(df, y="sup", ttests=["hi","yo"], corrs=["sup"])  # run t-tests, corrs
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
Good visualizations speak for themselves and you can template them for reuse.
Jupyter notebooks are optimal for report delivery and should be mastered.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Visualizations
- Inspiration: https://www.python-graph-gallery.com/all-charts
- Custom: https://matplotlib.org/stable/tutorials/introductory/customizing.html
    * Check out lines_bars_and_markers/bar_label_demo.html (one chart guide)
    * Check out lines_bars_and_markers/categorical_variables.html (multi-chart)
- Cheatsheet: "Python Seaborn Cheat Sheet PDF" on Google
- `sns.set_palette("colorblind")`
### Chart Choices
- Figure-level plots for multiple sub-charts; axis-level plot for a single chart
- Continuous x-axis: `displot` (hist, kde, ecdf) or `relplot` (line, scatter)
    * ECDF is awesome! Plot it overlapping a histogram for very cool plots
- Categorical x-axis: `catplot` w/ `kind`: count,bar,box,violin,swarm,strip,more
- `pairplot`, `heatmap`, `regplot`(scatter+reg), `jointplot`(scatter+edge hists)
    * `pairplot` charts can be accessed/modified with `.axes`
    * `regplot` uses `line_kws={'color':'red'}`
- Normality: `statsmodels.api.qqplot`; x: theoretical quants, y: observed quants
- Residuals: Scale-Location plot (deviation is change in largeness), `residplot`
```
# GRAB THE ORANGE COLOR FROM SEABORN'S DEFAULT PALETTE
import seaborn as sns
d = sns.color_palette()[1]     # (1.0, 0.4980392156862745, 0.054901960784313725)
# DECIMAL TO HEX
x = '#%02x%02x%02x' % tuple([int(255 * i) for i in d])           # "#ff7f0e"
# HEX TO DECIMAL
d = tuple([(int(f"0x{x[i:i+2]}", 16) / 255) for i in range(1, len(x), 2)])
```
```
# HEATMAP WITH A SPECIFIED COLOR FOR THE LOWEST VALUE
rblugrn = plt.get_cmap("BuGn_r")
num_colors = crosstab.max().max()
colors = ["whitesmoke"] + [rblugrn(i / num_colors) for i in range(2,num_colors)]
cmap = LinearSegmentedColormap.from_list('', colors, num_colors)
sns.heatmap(crosstab, cmap=cmap, cbar=False, 
    vmin=low_threshold, vmax=high_threshold, center=center, annot=True, fmt="d")
```
```
# SCALE-LOCATION PLOT
resids = sm_model.get_influence().resid_studentized_internal
abs_sqrt_resids = np.sqrt(np.abs(resids))
sns.regplot(x=sm_model.fittedvalues, y=abs_sqrt_resids, ci=None, lowess=None)
plt.xlabel("fittedvalues")
plt.ylabel("SQRT of ABS of STDized Residuals")
```
```
# HISTOGRAM WITH OVERLAPPING ECDF (COOL!)
import seaborn as sns
import pandas as pd
df = sns.load_dataset("penguins").reset_index(drop=True)
species_list = df["species"].unique()
fig, axes = plt.subplots(1, 3, figsize=(8,4), sharey=True)
for i, species in enumerate(species_list):
    ax = axes[i]
    temp = df[df["species"] == species]
    sns.ecdfplot(data=temp, x="bill_length_mm", ax=ax, color="red")
    sns.histplot(data=temp, x="bill_length_mm", ax=ax, stat="proportion")
    ax.set_title(species)
    ax.set_xlim(df["bill_length_mm"].min(), df["bill_length_mm"].max())
plt.show()
```
### Dataframe Styling
- `df.style` is used for changing data presentation (not changing the data)
- `df.plot` is only really useful for lightweight/few-line df plotting
```
# STYLE DF: FORMAT/BAR NUMBERS, COLOR LEVELS, FORMAT STRINGS; PRINT TO HTML FILE
from IPython.display import display, HTML
import numpy as np
import pandas as pd
a1 = np.random.randint(30_000,200_000,1_000)
a2 = np.random.randint(1,11,1_000)
a3 = np.random.choice(list("abcdefghijklmnopqrstuvwxyz"),1_000)
df = pd.DataFrame({"salary":a1, "level":a2, "title":a3})
# with open("my.md", "w") as f:
#     f.write(df.to_markdown())
styler = df.head(10).style\
    .format({"salary":"${:,.0f}", "title":str.upper})\
    .hide(axis="index")\
    .background_gradient(cmap="Oranges")\
    .highlight_max(subset="salary", color="green")\
    .highlight_min(subset="salary", color="red")\
    .bar(subset="salary", color="#1f77b4")\
    .export()
html = df.head(10).style.use(styler).to_html()
# with open("my.html", "w") as f:
#     f.write(html)
display(HTML(html))
```
### Chart Approaches
- For interactivity, check out plotly: https://plotly.com/python/plotly-express/
    * `import plotly.express as px`
```
plt.figure(figsize=(14,5))
bar_color = (0.0, 0.267, 0.106) # dark green, hint of blue
splot = sns.barplot(x=x, y=y, color=bar_color, alpha=0.9)  # splot for bar annot
bar_height = splot.containers[0]  # containers[0] contains each bar's height
plt.title(title)
plt.xlabel(xlabel)
plt.ylabel(ylabel)
plt.xticks(rotation=x_rot)
plt.bar_label(bar_height, bar_labels)
plt.show()
```
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
# %matplotlib inline              # uncomment for Jupyter notebooks
# GENERATE DATA
s = pd.Series([-3,-2,-1,0,1,2,3])
cats = pd.Series(['a','b','a','a','a','b','a'])
df = pd.DataFrame({'cats':cats, 'orig':s, 'squared':s**2, 'abs_x2':s.abs()*2})
# PREFERRED METHOD FOR: 2-variable charting, separate charts by a 3rd var's cats
fig = sns.relplot(df, x="orig", y="squared", col="cats")    # "col" can be "row"
ax0, ax1 = fig.axes[0][0], fig.axes[0][1]            # for "row", fig.axes[1][0]
ax0.axvline(0, alpha=0.2, ls=":")
ax1.axhline(0, alpha=0.2, ls=":")
arrow_p = {'facecolor': 'black', 'shrink': 0.1, 'headlength': 10, 'width': 2,}
ax0.annotate('Apex', xy=(0,.3), xytext=(-1,3), fontsize=15, arrowprops=arrow_p)
# plt.savefig("chart_cols.png")
plt.show()
# PREFERRED METHOD FOR: complete freedom over multiple charts
fig, axes = plt.subplots(1, 2, figsize=(8,4), sharey=True)  # param: gridspec_kw
fig.suptitle("hi")
ax0, ax1 = axes[0], axes[1]
ax0.set_title("$Y_o$")
ax0.axis([-2,10,-2,20])
ax0.set_yticks(s**2)
ax1.set_title("sup")
ax1.set_xlabel("dawgs", rotation=20, color="tab:blue")    
ax1.tick_params(axis="y", labelcolor="tab:blue")
sns.barplot(df, x="cats", y="squared", ax=ax0, color=sns.color_palette()[1])
sns.barplot(df, x="cats", y="abs_x2", ax=ax1)
fig.tight_layout()
plt.subplots_adjust(wspace=0.2)
# plt.savefig('chart_customs.png')
plt.show()
```
```
# PLOT DF: USING DF METHODS FOR FAST PLOTTING
import pandas as pd
import matplotlib.pyplot as plt
s = pd.Series([-3,-2,-1,0,1,2,3])
cats = pd.Series(['1','2','1','1','1','2','1'])
df = pd.DataFrame({'cats':cats, 'orig':s, 'squared':s**2, 'abs_x2':s.abs()*2})
# PLOT COL HIST FROM DF
plt.figure(1)
df.hist("orig")
# PLOT TWO VAR LINE FROM DF
plt.figure(2)
df[['orig','squared','abs_x2']].plot.line("orig", "abs_x2")
plt.title("line")
plt.axis([-4,4,-2,10])  # try also: plt.axis("equal") or "squared"
plt.axline(xy1=(8,8), slope=0, linewidth=10, color="orange")
plt.axhline(0, ls='--',alpha=.3)
plt.axvline(0, ls='--',alpha=.3)
# PLOT DF FROM GROUPBY
plt.figure(3)
df.groupby('cats')[['orig','squared','abs_x2']].sum().sort_index()\
.plot.bar(color=['red','green','blue'], alpha=.6)
plt.title("bar")
plt.legend(shadow=True, loc="upper right")
plt.text(0.8, 10, "hi")
plt.show()
```
```
# SEVERAL CHARTS IN ONE
from mpl_toolkits.axes_grid1 import host_subplot
from mpl_toolkits import axisartist
import matplotlib.pyplot as plt
host = host_subplot(111, axes_class=axisartist.Axes)  # create figure
plt.subplots_adjust(right=0.75)                       # add rightside buffer
par1 = host.twinx()                                   # parasite of figure
par2 = host.twinx()                                   # parasite of figure
par2.axis["left"] = par2.new_fixed_axis(loc="left", offset=(-60, 0))  # tick loc
par1.axis["right"].toggle(all=True)                   # force ticks show right
par2.axis["left"].toggle(all=True)                    # force ticks show left
p1, = host.plot([0, 1, 2], [0, 1, 2], label="Density")
p2, = par1.plot([0, 1, 2], [0, 3, 2], label="Temperature")
p3, = par2.plot([0, 1, 2], [50, 30, 15], label="Velocity")
host.set(xlim=(0, 2), ylim=(0, 2), xlabel="Dist", ylabel="Dens") # limit plot
par1.set(ylim=(0, 4), ylabel="Temperature")                      # limit plot
par2.set(ylim=(1, 65), ylabel="Velocity")                        # limit plot
host.legend()
host.axis["left"].label.set_color(p1.get_color())     # acqure, use color
par1.axis["right"].label.set_color(p2.get_color())    # acqure, use color
par2.axis["left"].label.set_color(p3.get_color())     # acqure, use color
plt.show() 
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Magic in Jupyter
- MD LaTeX: `$H_0$`, see: https://www.caam.rice.edu/~heinken/latex/symbols.pdf
- PLT LaTeX: https://matplotlib.org/stable/tutorials/text/mathtext.html
### Command Mode
- dd for cell deletion, y for code cell, m for markdown cell
### Edit Mode
- TAB for autocomplete of methods/variables/filenames
- Shift TAB for full context at cursor location
- Option Shift - to split cell into two cells at cursor
- Option Dragclick to drag multi-line cursor
- Run shell commands with `!` like this: `!echo "hi"`
    * I think the commands depend on what terminal program is running Jupyter
- Run ipython commands with `%` like this: `%ls`
### iPyWidgets
```
from IPython.display import display
import ipywidgets
from datetime import date
mydate = date(2023,1,1)
dateobject = ipywidgets.widgets.DatePicker(value=mydate)
display(dateobject)
# RUNNING NEXT CODE UPDATES ALL DISPLAYED OBJECTS IN REAL TIME
dateobject.value = date(2023,5,20)
```

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
Validate is used for checking model performance.
Test (hold-out set) is used for checking the best model's performance.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Features for Classification
- Convert continuous/ordinal columns to categorical ones, ex: binning
    * Can use histograms to determine these groupings
- Use chi-square tests to find which categorical features are related to target
    * Can use heatmaps/mosaic plots to visualize these crosstabs
- One-hot encode all selected columns for modeling
- Features that correlate with other features contribute to multicollinearity
    * Multicollinearity reduces model performance
    * Reduce multicollinearity by thresholding variance inflation factor (VIF)
- You can always train a model first and evaluate which features were best!
```
from sklearnex import patch_sklearn
patch_sklearn()
# SAMPLE DATA FOR MODEL TESTING
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# SELECTKBEST: EVALUATE ESTIMATOR ONCE, KEEP BEST {K} FEATURES
from sklearn.feature_selection import SelectKBest, f_classif
k = 11
kbest = SelectKBest(score_func=f_classif, k=k).fit(X_train, y_train)
p_values = kbest.pvalues_
best = X_train.columns[kbest.get_support()]
print(f"SelectK: Best features from {k} selected:\n- " + "\n- ".join(best) + "")
X_train_kb, X_val_kb, X_test_kb = X_train[best], X_val[best], X_test[best]
# RECURSIVE FEATURE ENGINEERING (RFE): ITERATE EVALS, REMOVE FEATURES UNTIL {K}
from sklearn.feature_selection import RFE
from sklearn.tree import DecisionTreeClassifier as TREE
k = 11
rfe = RFE(estimator=TREE(random_state=42), n_features_to_select=k)  # verbose=1
rfe.fit(X_train, y_train)
best = X_train.columns[rfe.get_support()]
col_rankings = pd.Series(rfe.ranking_, index=X_train.columns)
print(f"RFE: Best features from {k} selected:\n- " + "\n- ".join(best) + "")
X_train_RFE, X_val_RFE, X_test_RFE = X_train[best], X_val[best], X_test[best]
# RFE WITH CROSS VALIDATION (MOST EXPENSIVE, MOST THOROUGH)
from sklearn.feature_selection import RFECV
from sklearn.tree import DecisionTreeClassifier as TREE
rfecv = RFECV(estimator=TREE(random_state=42), cv=5, scoring='accuracy')
rfecv.fit(X_train, y_train)
k = rfecv.n_features_
print("Best # of features from RFECV:", k)
print("Best features:\n- " + "\n- ".join(rfecv.get_feature_names_out()))
X_train_RFE, X_val_RFE, X_test_RFE = X_train[best], X_val[best], X_test[best]
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Training Classifiers
- Ultimately, classifiers always take an input and map it to a discrete output
- Different classification algorithms use different mapping methodologies
### Available Classifiers
- **Decision Tree (CART)**
    * A sequence of rules or a decision boundary for decisions
    * Nodes in tree are chosen to maximize "information gain" (class separation)
    * Measures of IG: "Gini-index" (impurity), "entropy", or MSE at each node
        * Unconstrained trees end in leaf when IG(node) = 0; otherwise, maxdepth
    * Simple to implement and explain, but prone to overfit
- **Random Forest**
    * Many decision trees, all rows, rand features; metamodel counts row's votes
    * Different from "bagging", which uses all features, row subset, diff models
    * Feature importance: avg of how much a feature reduces impurity in the tree
- **K-Nearest Neighbors**
    * Use distances of known-class neighbors to predict unknown-class data
    * Simple and effectively-predictive, but prone to poor performance
- **Multinomial Naive Bayes**
    * Evaluate a record's score for each class, choose class with highest score
    * Score: P(class) * P(col1 = "a" | class) * P(col2 = 42 | class) * ...
        * No P(...) should eval to 0; in histogram, add alpha=1 to each count
    * High bias ("naive", doesn't care about order), low variance (good predict)
    * Highly effective at prediction with few major downsides
- **Logistic Regression**
    * Regression, but uses thresholds on the regression line to choose class
    * A great baseline predictive model, but usually not the best
- **AdaBoost**
    * Sequential training of predictive models, each learning from the previous
    * A model is trained/evaluated; incorrect preds are weighed higher in next
        * You can lessen the learning rate (weight strength) with hyperparameter
    * Classifier: weighted majority votes; Regressor: weighted average
    * Repeat this learning until N predictors are trained
- **XG Boost**
    * Sequential training of predictive models, each learning from the previous
    * A model is trained/evaluated; the residual errors are the labels for next
        * `res1 = actual - pred` --> `res2 = res1 - pred_res1` --> ...
        * You can lessen the learning rate (weight strength) with hyperparameter
    * Gradient Boosted Trees use CART as base learner; XGB uses random forest
    * Stochastic Gradient Boosting uses random non-replaced rows, rand features
    * Repeat this learning until N predictors are trained
    * World-class performance but near-impossible to explain to stakeholders
- **Stochastic Gradient Descent**
- **Support Vector Machine**
- **One Vs Rest**
    * Breakdown of multiclass problem into several binary class problems
```
# SAMPLE DATA FOR MODEL TESTING
import pandas as pd
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# CREATE, FIT CLASSIFIER
from sklearn.tree import DecisionTreeClassifier as TREE
tree = TREE(max_depth=3, random_state=42)    # min_samples_leaf = 0.15
tree = clf.fit(X_train, y_train)
y_train_preds = tree.predict(X_train)
y_train_preds_proba = tree.predict_proba(X_train)
# VOTING CLASSIFIER: MULTIPLE MODELS VOTE ON EACH ROW'S CLASS
from sklearn.linear_model import LogisticRegression as LOGIT
from sklearn.neighbors import KNeighborsClassifier as KNN
from sklearn.ensemble import VotingClassifier as VC
logit, knn, tree = LOGIT(), KNN(), TREE()
classifiers = [("logit", logit), ("knn", knn), ("tree", tree)]
vc = VotingClassifier(estimators=classifiers)
vc.fit(X_train, y_train)
y_pred_vc = vc.predict(X_test)
print("Voting Classifier: {.3f}".format(accuracy_score(y_test, y_pred)))
# BAGGING: MANY MODELS ON DATA BOOTSTRAPS (RANDOM SUBSETS WITH REPLACEMENT)
from sklearn.ensemble import BaggingClassifier as BAGGER
tree = TREE()
bc1 = BAGGER(base_estimator=tree, n_estimators=300, n_jobs=-1)
bc1.fit(X_train, y_train)
y_pred_bc1 = bc1.predict(X_train)
bc2 = BAGGER(base_estimator=tree, n_estimators=300, n_jobs=-1, oob_score=True)
bc2.fit(X_train, y_train)
y_pred_bc2 = bc2.predict(X_train)
print(bc2.oob_score_)  # out of bag score; essentially score on cross-validation
```
### Cross-Validation
- Remove bias from selection of train split's records for model generalization
- The training split itself is split into K folds; K=3 and K=5 are common
    * Leave-One-Out: `K=len(df)`, useful for small datasets
- With K=5, a model is trained using 4 folds for "train" and 1 fold for "test"
- With K=5, five models are trained, each with a different fold as "test"
- We select an evaluation metric, evaluate all 5 models, and calculate the mean
    * Options: https://scikit-learn.org/stable/modules/model_evaluation.html
- The mean value across models is what we'd expect on out-of-sample data!
- If more errors on CV than on full training split: high variance / overfit
    * Decrease model complexity (ex: less max_depth, more min samples)
    * Gather more data so CV performs better
- If error on CV is similar to train, but still too high: high bias / underfit
    * Increase model complexity (ex: more max_depth, more min_samples)
    * Gather more features
```
# K-FOLDS CROSS VALIDATION
from sklearn.model_selection import cross_val_score as CVS
from sklearn.metrics import precision_score, make_scorer
e1, e2, e3 = "accuracy", "roc_auc", make_scorer(precision_score, pos_label=1)
X, y = X_train, y_train["in_actuals"]
acc = CVS(model, X, y, cv=5, scoring=e1, n_jobs=-1).mean() # n_jobs=-1 multiproc
roc_auc = CVS(model, X, y, cv=5, scoring=e2, n_jobs=-1).mean()
precision = CVS(model, X, y, cv=5, scoring=e3, n_jobs=-1).mean()
```
#### Grid Search Cross Validation
- Grid Search mixes cross validation with your hyperparameter tuning
- We pass the hyperparameter grid and K folds, and it trains/evals each model
- Set `n_jobs = -1` to use multi-core processing! Speed gains!
- For even more speed gains: try `RandomizedSearchCV`
    * Doesn't try out the entire grid; "hones in" on the best, faster
```
# GRID SEARCH
import numpy as np
from sklearn.model_selection import GridSearchCV
from sklearn.ensemble import RandomForestClassifier as RF
params = {"max_features":[1.0]}
params["n_estimators"] = [100,200,500,1000]
params["max_depth"] = list(range(1,8))
grid = GridSearchCV(RF(random_state=42), params, cv=5, verbose=2)
if type(y_train) is type(pd.DataFrame()):
    y_train = y_train["in_actuals"]
grid.fit(np.array(X_train), y_train)  # cast X_train as array to avoid warnings
print(grid.best_params_)
print(grid.best_estimator_)
accuracy = (grid.best_estimator_.predict(X_train) == y_train).mean()
```
#### Randomized Grid Search Cross Validation
- Grid Search, but randomly selecting hyperparameters, not trying all of them
- Pretty good performance, less computationally expensive than full grid search
```
# RANDOMIZED GRID SEARCH
import numpy as np
from sklearn.ensemble import RandomForestRegressor as RFR
from sklearn.metrics import make_scorer, mean_absolute_error
from sklearn.model_selection import RandomizedSearchCV as RSCV
import joblib
grid = {"max_depth":[2,4], "max_features":range(2,11), "min_samples_split":[2]}
grid["n_estimators"] = [100,200,500,1000]
grid["max_depth"] = range(1,8)
rfr = RFR(random_state=42)
if type(y_train) is type(pd.DataFrame()):
    y_train = y_train["in_actuals"]
rnd = RSCV(estimator=rfr, param_dist=grid, n_iter=40, cv=5)  # 40 models
rnd.fit(np.array(X_train), y_train)  # cast X_train as array to avoid warnings
print(rnd.best_params_)
print(rnd.best_estimator_)
rfr = rnd.best_estimator_
joblib.dump(rfr, "rfr_best.pkl")
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Evaluating Classifiers
- **Accuracy:** Overall performance of model: (TP + TN) / (total count)
    * Easy to understand; how many outcomes did the model accurately predict?
    * Imbalanced class problem may yield misleading results
- **Recall:** Positive actual against our predictions: TP / (TP + FN)
    * Example: Credit card fraud detection (maximize fraud capture)
    * Minimizing false negatives; Use when FN is more costly than FP 
    * Also known as Sensitivity; opposite-class recall is called Specificity
- **Precision:** Our prediction against all possible actuals: TP / (TP + FP)
    * Minimizing false positives; Use when FP is more costly than FN
    * Example: Spam filter (maximize normal-mail capture)
- **F1 Score:** Harmonic mean of Precision and Recall: TP / (TP + 0.5(FP + FN))
    * Prioritizing both Recall and Precision; similar to accuracy
    * Use for accuracy on an imbalanced class problem
- **Receiver Operating Characteristic:** False Positive Rate, True Positive Rate
    * Model performance at different decision thresholds
    * The model with best ROC AUC is best across decision thresholds
```
# SAMPLE DATA FOR MODEL TESTING
import pandas as pd
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# CREATE CLASSIFIER
from sklearn.tree import DecisionTreeClassifier as TREE
params = {"max_depth":5, "random_state":42}
model = TREE(**params).fit(X_train, y_train)
y_train_preds = model.predict(X_train)
# SHOW DECISION TREE IN VISUAL
from sklearn.tree import export_graphviz as EG
from graphviz import Graph, Source
dot_data = EG(model, feature_names=X_train.columns, 
    class_names=[str(x) for x in model.classes_], 
    rounded=True, filled=True, out_file=None)
graph = Source(dot_data) 
graph.render('iris_decision_model', view=True)   # display model via PDF
# EVALUATE CLASSIFIER
from sklearn.metrics import classification_report as CR
print("Out of Sample Score:", model.score(X_val, y_val))
report = CR(y_train, y_train_preds, output_dict=True)
validate_report = pd.DataFrame(report).T
# RECEIVER OPERATING CHARACTERISTIC (ROC) AREA UNDER CURVE (AUC)
from sklearn.metrics import roc_curve, auc, roc_auc_score
import matplotlib.pyplot as plt
bl_probs = [True for _ in range(len(y_val))]
model_probs = model.predict_proba(X_val)[:,1]
bl_auc = roc_auc_score(y_val.astype("bool"), bl_probs)
model_auc = roc_auc_score(y_val.astype("bool"), model_probs)
print(f"Baseline:  ROC AUC={bl_auc:0.3f}")
print(f"Our Model: ROC AUC={model_auc:0.3f}")
bl_fpr, bl_tpr, bl_thresholds = roc_curve(y_val, bl_probs)
model_fpr, model_tpr, model_thresholds = roc_curve(y_val, model_probs)
plt.plot(bl_fpr, bl_tpr, linestyle='--', label='Baseline')
plt.plot(model_fpr, model_tpr, marker='.', label='Our Model')
plt.xlabel("False Positive Rate")
plt.ylabel("True Positive Rate")
plt.title("Receiver Operating Characteristic")
plt.legend(loc="lower right")
plt.show()
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Classification Shotgun
- Train a bunch of classifiers on a given dataset
- Various classification algorithms with various parameter sets
- Meant for MVP work; tune more precisely, reduce/increase params, etc later
```
# IMPORT EVERYTHING
import pandas as pd
from sklearn.tree import DecisionTreeClassifier as TREE
from sklearn.ensemble import RandomForestClassifier as RF
from sklearn.linear_model import LogisticRegression as LOGIT
from sklearn.naive_bayes import GaussianNB as NB
from sklearn.neighbors import KNeighborsClassifier as KNN
from sklearn.ensemble import AdaBoostClassifier as ABC
from sklearn.ensemble import GradientBoostingClassifier as GBC
from xgboost import XGBClassifier as XGB
from sklearn.multiclass import OneVsRestClassifier as OVR
# CLASSIFICATION SHOTGUN: TRAIN MODELS
def classification_shotgun(X_train, y_train, X_out, y_out):
    """
    Build various classification models and get their predictions on a dataset.
    - Models: DecisionTree, RF, LogisticRegression, GaussianNB, KNeighbors, XGB
    """
    if type(y_train) != type(pd.DataFrame()):
        y_train = pd.DataFrame(y_train.rename('in_actuals'))
    if type(y_out) != type(pd.DataFrame()):
        y_out = pd.DataFrame(y_out.rename('out_actuals'))
    y_train, y_out = mode_bl(y_train, y_out)
    y_train, y_out = decisiontree(X_train, y_train, X_out, y_out)
    y_train, y_out = randomforest(X_train, y_train, X_out, y_out)
    y_train, y_out = logisticregression(X_train, y_train, X_out, y_out)
    y_train, y_out = naivebayes(X_train, y_train, X_out, y_out)
    y_train, y_out = knearestneighbors(X_train, y_train, X_out, y_out)
    y_train, y_out = xgboosts(X_train, y_train, X_out, y_out)
    return y_train, y_out   # return dataframes of predictions
# CLASSIFICATION SHOTGUN: EVALUATE ACCURACY, RECALL, PRECISION, F1 SCORE
def print_classification_results(y_train, y_out):
    """Get metrics for a dataframe of model predictions columns, return a df."""
    cols = ['Model','InSample_Accuracy','OutSample_Accuracy','InSample_Recall'
        'OutSample_Recall','InSample_Precision','OutSample_Precision',
        'InSample_F1_Score','OutSample_F1_Score']
    running_list = []
    # LOOP THROUGH EACH MODEL
    for i, model in enumerate(y_train.columns[1:]):
        train_TP = ((y_train[model] == 1) & (y_train['in_actuals'] == 1)).sum()
        train_TN = ((y_train[model] == 0) & (y_train['in_actuals'] == 0)).sum()
        train_FP = ((y_train[model] == 1) & (y_train['in_actuals'] == 0)).sum()
        train_FN = ((y_train[model] == 0) & (y_train['in_actuals'] == 1)).sum()
        out_TP = ((y_out[model] == 1) & (y_out['out_actuals'] == 1)).sum()
        out_TN = ((y_out[model] == 0) & (y_out['out_actuals'] == 0)).sum()
        out_FP = ((y_out[model] == 1) & (y_out['out_actuals'] == 0)).sum()
        out_FN = ((y_out[model] == 0) & (y_out['out_actuals'] == 1)).sum()
        # CALCULATE ACCURACY, RECALL, PRECISION, F1 SCORE
        in_acc = (y_train[model] == y_train.in_actuals).mean()
        out_acc = (y_out[model] == y_out.out_actuals).mean()
        in_recall = train_TP / (train_TP + train_FN)
        out_recall = out_TP / (out_TP + out_FN)
        in_prec = train_TP / (train_TP + train_FP)
        out_prec = out_TP / (out_TP + out_FP)
        in_f1 = (2 * in_prec * in_recall) / (in_prec + in_recall)
        out_f1 = (2 * out_prec * out_recall) / (out_prec + out_recall)
        # BUILD RESULTS DATAFRAME
        row = {'Model':model, 
            'InSample_Accuracy': round(in_acc, 4), 
            'OutSample_Accuracy': round(out_acc, 4),
            'InSample_Recall': round(in_recall, 4),
            'OutSample_Recall': round(out_recall, 4),
            'InSample_Precision': round(in_prec, 4),
            'OutSample_Precision': round(out_prec, 4),
            'InSample_F1_Score': round(in_f1, 4),
            'OutSample_F1_Score': round(out_f1, 4)}
        running_list.append(row)
    return pd.DataFrame(running_list)  # return dataframe of model performances
# CLASSIFICATION SHOTGUN: INDIVIDUAL MODELS
def manual_baseline(y_train, y_out, baseline_value):
    """Add a column for the manually-selected baseline prediction"""
    y_train['manual_baseline'] = baseline_value
    y_out['manual_baseline'] = baseline_value
    return y_train, y_out   # return DATAFRAMES with new preds columns
def mode_bl(y_train, y_out):
    """Calculate baseline using mode class for model comparison"""
    mode = y_train.in_actuals.mode().tolist()[0]  # find baseline
    y_train['mode_baseline'] = mode
    y_out['mode_baseline'] = mode
    return y_train, y_out   # return DATAFRAMES with new preds columns
def decisiontree(X_train, y_train, X_out, y_out):
    """Creates decision trees with max_depth 1,2,3,5,10 and random_state=42"""
    for i in [1,2,3,5,10]:  # decision node depth
        model_name = f"tree_maxdepth{i}"
        tree = TREE(max_depth=i,random_state=42).fit(X_train,y_train.in_actuals)
        y_train[model_name] = tree.predict(X_train)
        y_out[model_name] = tree.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def randomforest(X_train, y_train, X_out, y_out):
    """Creates random forests with max_depth 1,2,3,5,10 and random_state=42"""
    for i in [1,2,3,5,10]:
        model_name = f"rf_depth{i}"
        rf = RF(max_depth=i, random_state=42).fit(X_train, y_train.in_actuals)
        y_train[model_name] = rf.predict(X_train)
        y_out[model_name] = rf.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def logisticregression(X_train, y_train, X_out, y_out):
    """Creates logistic regressions with random_state=42"""
    logit = LOGIT(random_state=42).fit(X_train, y_train.in_actuals)
    y_train['logit'] = logit.predict(X_train)
    y_out['logit'] = logit.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def naivebayes(X_train, y_train, X_out, y_out):
    """Creates Naive-Bayes with var_smoothing of .001, .01, 10, 100"""
    for smooth_level in [.00001, .0001, .001, .01, 10, 100]:
        model_name = f"nb_vsmooth{smooth_level}"
        nb = NB(var_smoothing=smooth_level).fit(X_train, y_train.in_actuals)
        y_train[model_name] = nb.predict(X_train)
        y_out[model_name] = nb.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def knearestneighbors(X_train, y_train, X_out, y_out):
    """Create KNNs with neighbor counts of 3, 5, 10, 25, 75"""
    for neighbor_count in [3,5,10,25,75]:
        model_name = f"knn_n{neighbor_count}"
        knn = KNN(n_neighbors=neighbor_count).fit(X_train, y_train.in_actuals)
        y_train[model_name] = knn.predict(X_train)
        y_out[model_name] = knn.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def adaboostclass(X_train, y_train, X_out, y_out):
    """Create AdaBoost classifier models with random_state=42"""
    tree = TREE(max_depth=1, random_state=42)  # "decision stump"
    abc = ABC(base_estimator=tree, n_estimators=100)
    abc.fit(X_train, y_train.in_actuals)
    y_train['adaboostclass'] = abc.predict(X_train)
    y_out['adaboostclass'] = abc.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def gradboostclass(X_train, y_train, X_out, y_out):
    """Create Gradient-Boosted Trees Classifier with weak learners"""
    gbc = GBC(n_estimators=300, max_depth=1, random_state=42)
    gbc.fit(X_train, y_train.in_actuals)
    y_train['gradboostclass'] = gbc.predict(X_train)
    y_out['gradboostclass'] = gbc.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
def xgboosts(X_train, y_train, X_out, y_out):
    """Create XGBoost models with max_depth 3,5,7,9 and random_state=42"""
    for i in [3,5,7,9]:
        model_name = f"xgb_maxdepth{i}"
        xgb = XGB(max_depth=i, random_state=42).fit(X_train, y_train.in_actuals)
        y_train[model_name] = xgb.predict(X_train)
        y_out[model_name] = xgb.predict(X_out)
    return y_train, y_out    # return DATAFRAMES with new preds columns
```
```
# SAMPLE DATA FOR MODEL TESTING
from sklearn.datasets import make_classification as MC
X, y = MC(n_samples=10_000, n_features=20, n_classes=2, 
          n_informative=6, n_redundant=10, random_state=42)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# CLASSIFICATION SHOTGUN
y_train, y_val = classification_shotgun(X_train, y_train, X_val, y_val)
print_classification_results(y_train, y_val)
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
```
Predicting a numerical value for unseen data using trained models.
Features are chosen for modeling via correlation tests, t-tests, SelectKBest/RFE
Training data includes "the answers"; all data (incl. unseen) should be scaled.
Model evaluation is important and done in two stages: validate and test.
Validate is used for checking model performance.
Test (hold-out set) is used for checking the best model's performance.
```
- TODO: snippet about polynomial transformation of features to make more linear
- TODO: snippet about other transforms (log, exponent, etc) to better correlate

--------------------------------------------------------------------------------
<!-- Needs work -->
## Features for Regression
- Keep features that highly-correlate with the target: `df.corr()`
- Interactions are awesome! They can have better correlations; `s1 * s2`
    * Example: `df["cat1_col2"] = (df["col1"] == "cat1") * df["col2"]`
- Features that correlate with other features contribute to multicollinearity
    * Multicollinearity reduces model performance
    * Reduce multicollinearity by thresholding variance inflation factor (VIF)
- Scatterplots can show outliers; consider removing outlier datapoints
    * Removing outliers can improve model performance
- You can always train a model first and evaluate which features were best!
```
from sklearnex import patch_sklearn
patch_sklearn()
# SAMPLE DATA FOR MODEL TESTING
from sklearn.datasets import make_regression as MR
X, y = MR(n_samples=10_000, n_features=20, n_informative=6, random_state=0)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# SELECTKBEST: EVALUATE ESTIMATOR ONCE, KEEP {K} FEATURES
from sklearn.feature_selection import SelectKBest, f_regression
k = 9
kbest = SelectKBest(score_func=f_regression, k=k).fit(X_train, y_train)
p_values = kbest.pvalues_
best = X_train.columns[kbest.get_support()]
print(f"SelectK: Best features from {k} selected:\n- " + "\n- ".join(best) + "")
X_train_kb, X_val_kb, X_test_kb = X_train[best], X_val[best], X_test[best]
# RECURSIVE FEATURE ENGINEERING (RFE): ITERATE EVALS, REMOVE FEATURES UNTIL {K}
from sklearn.feature_selection import RFE
from sklearn.linear_model import LinearRegression as OLS
k = 9
rfe = RFE(estimator=OLS(), n_features_to_select=k) # verbose=1
rfe.fit(X_train, y_train)
best = X_train.columns[rfe.get_support()]
col_rankings = pd.Series(rfe.ranking_, index=X_train.columns)
print(f"RFE: Best features from {k} selected:\n- " + "\n- ".join(best) + "")
X_train_RFE, X_val_RFE, X_test_RFE = X_train[best], X_val[best], X_test[best]
# DETERMINE "K-BEST" COUNT VIA ALGORITHM (IF NEEDED)
from sklearn.feature_selection import RFECV
from sklearn.linear_model import LinearRegression as OLS
rfecv = RFECV(estimator=OLS(), cv=5, scoring='neg_root_mean_squared_error')
rfecv.fit(X_train, y_train)
k = rfecv.n_features_
print("Best # of features from RFECV:", k)
print("Best features:\n- " + "\n- ".join(rfecv.get_feature_names_out()))
X_train_RFE, X_val_RFE, X_test_RFE = X_train[best], X_val[best], X_test[best]
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Training Regressors
- Plotting various regression lines, using a loss function to find best fit line
- The regression line is indicated by the regression equation
    * A regression equation looks like this: `y = a1x1 + a2x2 + a3x3 + ...`
    * Each independent variable (each feature) has a "coefficient" (line slope)
    * Regression equations (each is a line's equation) have an intercept
    * Feature coefficients are added together in the regression equation
- Many regression lines are plotted; a loss function calculates each line's loss
    * The regression line with least loss is best
- You choose the loss function; lots of examples, ex: OLS, LASSO+LARS, GLM, more
    * A good loss function can yield a better-fit regression line
    * The best loss functions help plot a line that can generalize accurately
- As always, poor feature engineering can't be saved by great loss functions
    * You need to add an intercept to your data; this is just a column of 1s
    * Numerical feature scaling "balances" each feature in loss calculation
    * Features with a linear relationship to the target are best
### Available Regressors
- **Ordinary Least Squares (OLS)**
    * Computationally simple and efficient regression
    * `y = a1x1 + a2x2 + a3x3 + ...`
    * Prone to overfitting because it fits the best line to the sample data
- **Ridge**
    * Great for generalizing OLS to unseen data (with `alpha` hyperparameter)
    * `y = a1x1 + a2x2 + ... + (alpha * ((a1)^2x1 + (a2)^2x2 + ...))`
    * Regularized, because we "punish" large coefficients by tuning `alpha`
    * High alpha yields underfitting; low alpha yields overfitting
- **LASSO**
    * Great for feature selection (with `alpha` hyperparameter)
    * `y = a1x1 + a2x2 + ... + (alpha * (abs(a1)x1 + abs(a2)x2 + ...))`
    * Regularized, because we "punish" small coefficients by tuning `alpha`
    * Improper tuning of `alpha` can remove too many or too few features
- **LASSO+LARS** 
    * Feature minimization using regularization penalties
    * Can change slope to reduce variance / increase bias; assumes normality
- **Generalized Linear Model (GLM)** 
    * Generalized OLS; safe; best option when distributions are not normal
    * Avoid when dealing with polynomial curves
- **Support Vector Regression (SVR)** 
    * Hyperplanes; boundary capture of discrete values, use for discretes
    * If > 50,000 rows, use LinearSVR instead
- **Polynomial Regression** 
    * Really just feature engineering to make polynomial features
    * Use number of curves from exploration as hyperparameter
- **Gradient Boosting Regressor**
```
# SAMPLE DATA FOR MODEL TESTING
import pandas as pd
from sklearn.datasets import load_wine
from sklearn.model_selection import train_test_split as SPLIT
df = pd.DataFrame(load_wine()["data"], columns=load_wine()["feature_names"])
df["intercept"] = 1
X, y = df.drop(columns="alcohol"), df.alcohol
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# SIMPLE OLS WITH SKLEARN
from sklearn.linear_model import LinearRegression as OLS
ols1 = OLS().fit(X_train, y_train)
y_train_preds1 = ols1.predict(X_train)
y_val_preds1 = ols1.predict(X_val)
# SIMPLE OLS MODEL WITH STATSMODELS
import statsmodels.api as sm
ols2 = sm.OLS(y_train, X_train).fit()
y_train_preds2 = ols2.predict(X_train)
y_val_preds2 = ols2.predict(X_val)
print(list(y_val_preds2)[:10])
ols2.summary()
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Evaluating Regressors
- **Regression line**
    * Regression equation: `y = b0 + b1x1 + b2x2 + ... bnxn + ϵ`
    * y: target; b: coefficient (slope); x: input; ϵ: expected_error
    * Polynomial regression uses: y = b0 + b1x + b2x^2 + b3x^3 + ... + bnx^n + ϵ
- **Root Mean Square Error (RMSE)**
    * Calculate RMSE: `RMSE = sqrt(mean(sum(residuals)))`
    * RMSE is in target's units, so calculating home value has RMSE in dollars
    * Other error metrics: SSE (when outliers are the focus), MSE, ESS, TSS
- **Variance (r2)**
    * Calculate variance: `r2 = ESS / TSS`
    * Indicates amount of data (0% - 100%) explained by regression line
- **Residual**
    * Calculate a datapoint's residual error: `e = predicted_y - actual_y`
- **Heteroscedasticity**
    * Trend in residual plot, unaccounted-for drivers remain
    * Fix heteroscedasticity by removing outliers or log/expon/etc transform
```
# SAMPLE DATA FOR MODEL TESTING
import pandas as pd
from sklearn.datasets import load_wine
from sklearn.model_selection import train_test_split as SPLIT
df = pd.DataFrame(load_wine()["data"], columns=load_wine()["feature_names"])
X, y = df.drop(columns="alcohol"), df.alcohol
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# SINGLE MODEL: GET REGRESSION RESULTS
def regression_results(actuals, preds):
    """Returns SSE, ESS, TSS, MSE, RMSE, Residuals, and r2"""
    mse = ((preds - actuals)**2).mean()
    rmse = mse ** 0.5
    sse = mse * len(actuals)
    ess = ((preds - actuals.mean())**2).sum()
    tss = ess + sse
    r2 = ess / tss
    res = preds - actuals
    d = {"MSE":mse,"RMSE":rmse,"SSE":sse,"ESS":ess,"TSS":tss,"err":res,"r2":r2}
    return d
# SINGLE MODEL: PLOT RESIDUALS
def plot_residuals(model_name, actuals, residuals):
    sns.relplot(x=actuals, y=residuals, kind='scatter')
    plt.axhline(y=0, c='gray', alpha=.3)
    plt.title(f"Residual Plot for Model: {model_name}")
    plt.xlabel("Actual Values")
    plt.ylabel("Residuals")
    plt.show()
# CREATE OLS MODEL
from sklearn.linear_model import LinearRegression as OLS
ols = OLS().fit(X_train, y_train)
y_train_preds = ols.predict(X_train)
y_val_preds = ols.predict(X_val)
# GET PREDICTION RESULTS
import seaborn as sns
import matplotlib.pyplot as plt
train_res = regression_results(y_train, y_train_preds)
val_res = regression_results(y_val, y_val_preds)
print(f"TRAIN OLS: RMSE: {train_res['RMSE']:0.2f}, r2: {train_res['r2']:0.2f}")
print(f"VAL OLS: RMSE: {val_res['RMSE']:0.2f}, r2: {val_res['r2']:0.2f}")
plot_residuals("OLS", y_val, val_res["err"])
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Regression Shotgun
- Train a bunch of regressors on a given dataset
- Various regression algorithms with various parameter sets
- Meant for MVP work; tune more precisely, reduce/increase params, etc later
```
# IMPORT EVERYTHING
import pandas as pd
from sklearn.linear_model import LinearRegression as OLS  # need simplicity
from sklearn.linear_model import LassoLars as LASSOLARS   # lower r2, raise bias
from sklearn.linear_model import TweedieRegressor as GLM  # dist is non-normal
from sklearn.preprocessing import PolynomialFeatures as PF    # polynomial data
from sklearn.svm import SVR                               # < 50k, discrete tgt
from sklearn.svm import LinearSVR as LSVR                 # > 50k, discrete tgt
from sklearn.ensemble import GradientBoostingRegressor as GBR  # go big
# REGRESSION SHOTGUN: TRAIN MODELS
def regression_shotgun(X_train, y_train, X_out, y_out):
    """ 
    Create various regression models and get their predictions on a dataset.
    - Models: OLS, LASSO+LARS, GLM, Polynomial OLS, SVR, LSVR, GBR
    """
    if type(y_train) != type(pd.DataFrame()):
        y_train = pd.DataFrame(y_train.rename('in_actuals'))
    if type(y_out) != type(pd.DataFrame()):
        y_out = pd.DataFrame(y_out.rename('out_actuals'))
    y_train, y_out = baselines(y_train, y_out)
    y_train, y_out = lm(X_train, y_train, X_out, y_out)
    y_train, y_out = lassolars(X_train, y_train, X_out, y_out)
    y_train, y_out = glm(X_train, y_train, X_out, y_out)
    y_train, y_out = pf_ols(X_train, y_train, X_out, y_out)
    y_train, y_out = svr49k(X_train, y_train, X_out, y_out)
    y_train, y_out = lsvr51k(X_train, y_train, X_out, y_out)
    y_train, y_out = gradboost(X_train, y_train, X_out, y_out)
    return y_train, y_out   # return dataframes of predictions
# REGRESSION SHOTGUN: EVALUATE RMSE, r2
def print_regression_results(y_train, y_val):
    """Calculate RMSE, r2 using insample and outsample predictions dataframes"""
    cols = ["Model", "Train_RMSE", "Validate_RMSE", "Train_r2", "Validate_r2"]
    rows = []
    for model in y_train.columns[1:]:
        rmse_train = mean_squared_error(y_train.actuals, y_train[model]) ** 0.5
        rmse_out = mean_squared_error(y_val.actuals, y_val[model]) ** 0.5
        r2_train = r2_score(y_train.actuals, y_train[model])
        r2_out = r2_score(y_val.actuals, y_val[model])
        rows.append({
            "Model":model, "Train_RMSE":rmse_train, "Validate_RMSE":rmse_out,
            "Train_r2":r2_train, "Validate_r2":r2_validate
        })
    results = pd.DataFrame(rows, columns=cols)
    return running_df
# REGRESSION SHOTGUN: INDIVIDUAL MODELS
def baselines(y_train, y_out):
    """Create two baseline models: Mean and Median for model comparison"""
    y_train['mean_bl'] = y_train.in_actuals.mean()
    y_out['mean_bl'] = y_out.out_actuals.mean()
    y_train['median_bl'] = y_train.in_actuals.median()
    y_out['median_bl'] = y_out.out_actuals.median()
    return y_train, y_out   # return DATAFRAMES with new preds columns
def lm(X_train, y_train, X_out, y_out):
    """Predict with OLS model, return predictions"""
    ols = OLS().fit(X_train, y_train.in_actuals)
    y_train['ols'] = ols.predict(X_train)
    y_out['ols'] = ols.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def lassolars(X_train, y_train, X_out, y_out):
    """Predict with various LASSO+LARS models, return predictions"""
    alpha_list = [.0001, .001, .01, .1, 1, 10, 100, 1000]
    for alpha in alpha_list:   # iterate regularization penalties
        model_name = f"lassolars_{alpha}"
        lasso = LASSOLARS(alpha=alpha).fit(X_train, y_train.in_actuals)
        y_train[model_name] = lasso.predict(X_train)
        y_out[model_name] = lasso.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def glm(X_train, y_train, X_out, y_out):
    """Predict with various GLM models, return predictions"""
    power_dict = {0:"gaussian", 1:"poisson", 2:"gamma", 3:"inversegaussian"}
    power = 0
    alpha_list = [.0001, .001, .01, .1, 1, 10, 100, 1000]
    for alpha in alpha_list:
        pname = power_dict[power]
        model_name = f"glm_{pname}_a{alpha}"
        tweed = GLM(power=power, alpha=alpha).fit(X_train, y_train.in_actuals)
        y_train[model_name] = tweed.predict(X_train)
        y_out[model_name] = tweed.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def pf_ols(X_train, y_train, X_out, y_out):
    """Create polynomial features, predict with OLS, return predictions"""
    degree_list = [2,3,4,5,6]
    for degree in degree_list:
        model_name = f"ols_pf{degree}"
        X_train_pf = PF(degree=degree).fit_transform(X_train)
        X_out_pf = PF(degree=degree).fit(X_train).transform(X_out)
        ols = OLS().fit(X_train_pf, y_train.in_actuals)
        y_train[model_name] = ols.predict(X_train_pf)
        y_out[model_name] = ols.predict(X_out_pf)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def svr49k(X_train, y_train, X_out, y_out):
    """Predict with SVR model, return predictions"""
    Cs = [0.01, 0.1, 1, 10, 100]
    for C in Cs:
        model_name = f"svr{C}"
        svr = SVR(C=C).fit(X_train, y_train.in_actuals)
        y_train[model_name] = svr.predict(X_train)
        y_out[model_name] = svr.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def lsvr51k(X_train, y_train, X_out, y_out):
    """Predict with LinearSVR model, return predictions"""
    Cs = [0.01, 0.1, 1, 10, 100]
    for C in Cs:
        model_name = f"lsvr{C}"
        lsvr = LSVR(C=C).fit(X_train, y_train.in_actuals)
        y_train[model_name] = lsvr.predict(X_train)
        y_out[model_name] = lsvr.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
def gradboost(X_train, y_train, X_out, y_out):
    """Predict with GBR model, return predictions"""
    gbr = GBR(max_depth=1, subsample=.8, max_features=.2, random_state=42)
    gbr.fit(X_train, y_train)
    y_train['gbr'] = gbr.predict(X_train)
    y_out['gbr'] = gbr.predict(X_out)
    return y_train, y_out   # return DATAFRAMES with new preds columns
```
```
# SAMPLE DATA FOR MODEL TESTING
import pandas as pd
from sklearn.datasets import make_regression as MR
X, y = MR(n_samples=10_000, n_features=20, n_informative=6, random_state=0)
X, y = pd.DataFrame(X), pd.Series(y, name="target")
X.columns = [str(col) for col in X.columns]
from sklearn.model_selection import train_test_split as SPLIT
X1, X_test, y1, y_test = SPLIT(X, y, test_size=0.2, random_state=42)
X_train, X_val, y_train, y_val = SPLIT(X1, y1, test_size=0.25, random_state=42)
# RUN AND EVALUATE REGRESSION SHOTGUN
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.metrics import mean_squared_error, r2_score
y_train, y_val = regression_shotgun(X_train, y_train, X_val, y_val)
print_regression_results(y_train, y_val)
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

# Time Series
```
Understanding previous trends and their anomalies to do various things.
You can calculate several metrics for time series data; monthly/weekly/daily/...
Generally, you're tracking one numerical feature over a time axis with plots.
Modeling varies from using past data with adjustment to actual trainable models.
```
- TODO: Resampling into consistent intervals, reducing precision, etc
- TODO: Filling forward/backwards by averaging, etc
- TODO: Creating tons of numerical features

--------------------------------------------------------------------------------
<!-- Needs work -->
## Timestamp Engineering
- VERY POWERFUL: `df.set_index("interval_ts").reindex([t1,t2,t3,t4]).fillna(0)`
- ALSO POWERFUL: `quadr_interp = ts_index_df.interpolate(method="quadratic")`
    * Options: "linear","quadratic","nearest"
    * `df["col1"].plot(title="figtitle",marker="o",figsize=(30,5))`
    * `quadr_interp["col1"].plot(color="red",marker="o",linestyle="dotted")`
```
with open(r"C:\Users\Jake\sample_linux_authlog.txt") as f: text_data = f.read()
regexp = "^(.{15})\s+(\S+)\s+([^\s\[:]+)(\[\d*\])*:\s+(.+)$"
cols = ["timestamp", "hostname", "reporter", "pid", "message"]
rows = re.findall(regexp, text_data, re.MULTILINE)
df = pd.DataFrame(rows, columns=cols)
df["ts"] = pd.to_datetime(df["ts"], format="%Y %b %d %H:%M:%S", errors="coerce")
df["day"] = df["ts"].dt.strftime("%Y-%m-%d")
df["hour"] = df["ts"].dt.strftime("%Y-%m-%d %H:00:00")
df["minute"] = df["ts"].dt.strftime("%Y-%m-%d %H:%M:00")
```
```
interpolations = {"Linear Interpolation": linear_interp, ...} # do imputes too!!
for ax, df_key in zip(axes, interpolations):
    interpolations[df_key]["col"].plot(color="red", marker="o",
                                       linestyle="dotted", ax=ax)
    df["col"].plot(title=f"{df_key} - col", marker="o", ax=ax)
```
```
def get_holidays(selected_year):
    """
    Gather US holidays for a given year.
    :param selected_year: Integer for selected year
    :return: Python list of US holidays (dates only) in string format
    """
    us_holidays = []
    for item in holidays.UnitedStates(years=selected_year).items():
        us_holidays.append(str(item[0])) # only pull date of holiday- no name
    return us_holidays
def amplify_timestamps(timestamps_series, only_do_day=False):
    """
    Create a dataframe of timestamp amplification.
    :param timestamps_series: pandas Series where values are pandas datetimes
    :param only_do_day: Bool to just return a pandas-type timestamps series
    :return: pandas DataFrame containing timestamps and amplifying information
    """
    try:
        timestamps_series.rename("datetime", inplace=True)
        timestamps_series = pd.to_datetime(timestamps_series)
    except:
        return "Error: can not convert specified series to datetime format!"
    if only_do_day:
        return timestamps_series.dt.date
    years = [int(yr) for yr in timestamps_series.dt.year.astype("str").unique()]
    us_holidays = []
    for year in years:
        us_holidays.extend(get_holidays(year))
    df = pd.DataFrame(timestamps_series)
    df["date"] = df["datetime"].dt.date
    df["time"] = df["datetime"].dt.time
    df["weekday"] = df["datetime"].dt.weekday # 0 for Monday, 1 for Tuesday, ...
    df["dayname"] = df["datetime"].dt.day_name()
    df["is_weekday"] = df["weekday"] < 5      # 5 is Saturday, 6 is Sunday
    df["not_holiday"] = ~df["date"].astype("str").isin(us_holidays)
    df["is_working_day"] = df["is_weekday"] & df["not_holiday"]
    past_dawn = df["datetime"] > (df["date"].astype("str") + " 06:30:00")
    before_dusk = df["datetime"] < (df["date"].astype("str") + " 18:30:00")
    df["during_business_hours"] = df["is_working_day"] & past_dawn & before_dusk
    return df
def day_range_to_week_numbers(timestamps_series):
    """
    Convert timestamps in a Series to their relative week number.
    - If first 790 timestamps happen in first seven days, they become "1"
    - If timestamps 791-1558 happen in second seven days, they become "2"
    We also return the day:week mapping dict in case it's needed elsewhere.
    :param timestamps_series: pandas Series containing timestamps
    :return week_number_series: pandas Series of mapped timestamps_series values
    :return day_week_map: Python dict map for distinct_date:week_number
    """
    timestamps_series = pd.to_datetime(timestamps_series)  # just in case
    first_day = timestamps_series.dt.date.min()
    last_day = timestamps_series.dt.date.max()
    days = pd.date_range(first_day,last_day,normalize=True).strftime("%Y-%m-%d")
    day_week_map = {}
    week_number = 0
    for i, day in enumerate(days):
        if i % 7 == 0:
            week_number += 1
        day_week_map[day] = week_number
    dates_series = timestamps_series.dt.date.astype("str")
    week_number_series = dates_series.map(day_week_map)
    return week_number_series, day_week_map
def detect_time_precision(date_series):
    """
    Use some logic to detect the time precision of a pandas Series.
    :param date_series: pandas Series containing datetime values
    :return interval_string: String to use in title/ylabel/legend (ex: "Daily")
    :return interval: String to use for discrete x axis (ex: "Day")
    """
    is_weekly, zero_hrs, zero_mins, zero_secs = False, False, False, False
    if date_series.dtype == "O":
        if date_series.str.isdigit().all(): 
            is_weekly = True
    if is_weekly == False:
        if date_series.dtype == "O":
            date_series = pd.to_datetime(date_series)
        zero_hrs  = (date_series.strftime("%H") == '00').all()
        zero_mins = (date_series.strftime("%M") == '00').all()
        zero_secs = (date_series.strftime("%S") == '00').all()
    if is_weekly: 
        interval_string, interval = "Weekly", "Week"
    elif zero_hrs and zero_mins and zero_secs: 
        interval_string, interval = "Daily", "Day"
    elif zero_mins and zero_secs: 
        interval_string, interval = "Hourly", "Hour"
    elif zero_secs: 
        interval_string, interval = "Minutely", "Minute"
    else: 
        return "Data interval unknown; agg the data using calculators.py", None
    return interval_string, interval
def determine_best_time_aggregation(datetime_series):
    """
    Calc duration of a series, determine best agg interval for trend analysis.
    :param datetime_series: pandas Series where each value is a pandas timestamp
    :return interval_list: Python list of strings indicating intervals to use
    :return logic: Single string giving context to the decision
    """
    # discover start and end datetimes
    earliest = datetime_series[datetime_series.index[0]]
    latest = datetime_series[datetime_series.index[-1]]
    # calculate duration
    duration = latest - earliest
    # choose interval for time aggregation
    if duration.days <= 2:      # max 2880 datapoints
        interval_list, logic = ["minute"], "Duration: < 2 days"
    elif duration.days <= 5:    # max 5760, 96 datapoints
        interval_list, logic = ["minute", "hour"], "Duration: 3-5 days"
    elif duration.days <= 14:   # max 336 datapoints
        interval_list, logic = ["hour"], "Duration: 6-14 days"
    elif duration.days <= 30:   # max 720, 30 datapoints
        interval_list, logic = ["hour", "day"], "Duration: 15-30 days"
    elif duration.days <= 180:  # max 180 datapoints
        interval_list, logic = ["day"], "Duration: 31-180 days"
    else:                       # minimum 181, 26 datapoints
        interval_list, logic = ["day", "week"], "Duration: > 180 days"
    return interval_list, logic
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Metrics of Time Series
- 
```
date1 = pd.to_datetime(single_date, format='%b:%d:%Y')
date2 = pd.Timedelta('14d') + pd.to_datetime('2017-11-07')
s1 = pd.to_datetime(df.date, format='%b:%d:%Y')
s2 = pd.date_range('start_date', freq='D', periods=num_of_days)
s3 = df.loc[date_start:date_end]
s4 = df.date.max() - df.date
s5 = df.date.dt.day   # .month, .year, .quarter, .day_name()
s6 = df.col.strftime('%b %D, %Y')
s7 = df.resample('W').sum()
s8 = df.date.fillna()
s9 = df.colname.diff(365)  # colwise, subtract 365-indices-before from current
s10 = s.ewm(alpha=.1).std()
s11 = df.colname.shift(30) # colwise, shift column 30 cells deeper
s12 = df.index.tz      # df.tz_localize(None), df.tz_localize('America/Chicago')
df3 = df.asfreq('D')
df1 = by_day.assign(ffill=lambda df: df.coffee_consumption.ffill())
df2 = by_day.assign(bfill=lambda df: df.coffee_consumption.bfill())
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Outcome Plotting
- 
```
df.resample('W').sum().colname.plot()  # lineplot of weekly sum
plt.vlines(up_out.index, *plt.ylim(), color='black', ls='--', label='Ups')
df[['high', 'low']].plot(color='black', alpha=.6, ls=':', figsize=(16, 6))
df["mid"].plot(color='black', alpha=.6, ls='--')
```
```
def bollinger_band_outliers(y, n, k, group_avgs=pd.Series(dtype="int")):
    """
    Calculate the Bollinger bands and outliers for a time-index pandas Series.
    Default behavior is to calculate mid band from self's trend.
    Set the group_avgs parameter to use a different value series for mid band.
    - Mid band is used to set upper/lower bands; those bands identify outliers
    - Using group average for mid band shows where activity differs from others
    :param y: pandas Series for count of events along a time interval index
    :param n: Integer for n_rolling on the given time interval
    :param k: Integer for STDEVs to tune outlier factor (usually 2 or 20)
    :param group_avgs: optional pandas Series to set mid band for comparison
    :return: Python dictionary for Bollinger calculation results
    """
    _, interval = detect_time_precision(y.index)  # get time interval of y
    cond1 = len(group_avgs) == len(y)
    cond2 = type(group_avgs)==type(pd.Series())
    using_group_avgs = cond1 and cond2   # group_avgs is specified and valid
    if using_group_avgs:
        mid_band = group_avgs.rolling(n).mean()
    else: 
        mid_band = y.rolling(n).mean()
    upper_band = mid_band + (k * mid_band.std())  # Bollinger upper band
    lower_band = mid_band - (k * mid_band.std())  # Bollinger lower band
    volatility = (y - lower_band) / (upper_band - lower_band)  # set %b
    upper_outliers = y[volatility > 1]  # exceeding %b
    lower_outliers = y[volatility < 0]  # exceeding %b
    results_dict = {"actuals":y,"group_averages":group_avgs,"n_rolling":n,"k":k,
                    "upper_band":upper_band, "upper_outliers":upper_outliers,
                    "lower_band":lower_band, "lower_outliers":lower_outliers, 
                    "mid_band":mid_band, "volatility":volatility, 
                    "time_interval":interval}
    if not using_group_avgs:
        del results_dict["group_averages"]
    return results_dict
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Time Series Modeling
- Seasonality, fluctuation cycles, and autocorrelation for forecasting
- **Last Observed Value**
- **Simple Average**
- **Moving/Rolling Average**
    * Average of a given period as the prediction; usually last 3 or last 7 days
- **Previous Cycle** 
    * Slice the last cycle and use it as the prediction; usually last year
- **Holt's Linear Trend**
    * Calculate regression line of previous cycles, snap-on as prediction
- **Facebook Prophet's Model**
    * Next cycle based on previous cycles; good, but hard to install/get working
### Strategy
1. Understand the nature of your data
    * Is it years of information? months? weeks? days? hours?
    * From visualizations, are there immediate noticeable trends or seasonality?
1. Fix the time field if necessary
1. Downsample (aggregate) or upsample (add rows) based on the analytic goal
    * EX: Downsample from minute-by-minute transactions to daily totals
    * EX: Upsample **patchy** minute-by-minute transaction data to fill gaps
1. Use rolling averages for seasonal data and autocorrelation (shifts and diffs)
    * For all time-series options
1. Visualize various metrics for insights
1. Split into train and test using seasonality (if possible), or by percentage
1. Train models using training split then predict the future
    * Predict test using train
1. Evaluate each model's RMSE, best model has lowest RMSE
1. Use best model for future forecasting
```
# basic diff and shift plotting
ax = df.resample('M').mean().diff().plot()                    # diff MM averages
df.resample('M').mean().plot(ax=ax, label='Monthly Average')  # MM average
df.resample('M').shift(12).plot(ax=ax, label='Last Year')     # MM YoY
# split time data for a percentage
train_end_index = round(df.shape[0] * train_size)
train = df.iloc[:train_end_index]
test = df.iloc[train_end_index:]
# apply Holt's linear trend
from statsmodels.tsa.api import Holt
model = Holt(train[col], exponential=)
model.fit(smoothing_level = .1, smoothing_slope=.1, optimized=False)
model.predict(start=test.index[0], end=test.index[-1])
```

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
- Calculate many time-based metrics and do clustering!
```
# SETUP
import pandas as pd
from numpy.random import seed, choice
from datetime import time
import holidays
offdays = holidays.UnitedStates(years=2022).keys()
seed(42)
d = pd.Series(choice(range(1,31), size=10_000)).astype("str")
h = pd.Series(choice(range(1,24), size=10_000)).astype("str")
m = pd.Series(choice(range(1,60), size=10_000)).astype("str")
s = pd.Series(choice(range(1,60), size=10_000)).astype("str")
t = pd.to_datetime("2022-01-" + d + "T" + h + ":" + m + ":" + s).rename("ts")
c1 = pd.Series(choice(["a","b"], p=[.97,.03], size=10_000), name="cat")
c2 = pd.Series(choice(["uncool","cool"], p=[.8,.2], size=10_000), name="tude")
df = pd.concat([t, c1, c2], axis=1).sort_values(by="ts").reset_index(drop=True)
df["cash"] = (df["cat"] == "a") & (df["tude"] == "cool")
```
```
# ACTION ANOMALIES
# DETECT SPECIFIC EVENTS
df["bad"] = df["cat"].isin(["b","c","d"])
df["good"] = df["cat"].isin(["a","e","f"])
# UNIQUE SEQUENCES OF EVENTS
s = df["cat"]
three_event_sequences = {(s[i],s[i+1],s[i+2]) for i in s.index if i+2 < len(s)}
# DETECT AN EVENT SEQUENCE
ng = ("a","b","b")
x = [(i,i+1,i+2) for i in s.index if i+2 < len(s) if (s[i],s[i+1],s[i+2]) == ng]
# EVENT1 THEN EVENT2
a_cool = (df["cat"] == "a") & (df["tude"] == "cool")
a_uncool = (df["cat"] == "a") & (df.act == "uncool")
cool_then_uncool = a_cool & a_uncool.shift(-1)
detected_i = cool_then_uncool[cool_then_uncool].index
df.loc[list(detected_i) + [i + 1 for i in detected_i]].sort_index()
# CHART: COUNTS OF CATEGORY GIVEN CATEGORY
df[["cat","tude"]].value_counts().unstack().plot.barh()
```
```
# TIME ANOMALIES
# OUTSIDE BUSINESS HOURS
off_hours = (df.ts.dt.time < time(9,0)) & (df.ts.dt.time > time(17,0))
weekends = df.ts.dt.weekday > 5
holidays = df.ts.dt.date.isin(offdays)
outside_hours = off_hours | weekends | holidays
# TOO MANY OF AN EVENT PER HOUR
df["hr"] = df["ts"].dt.to_period("h")
cpm = df.groupby(["cash","hr"])["cash"].count() > 10
# ROLLING AVERAGE OF EVENT COUNT PER DAY
tsdf = df.set_index("ts")
mean_cash = tsdf[["cash"]].resample("D").sum().rolling(3).mean()
# BOLLINGER BANDS
actuals = tsdf[["cash"]].resample("D").sum()
mid_band = actuals.ewm(alpha=0.2).mean()       # alpha: 0 is all vals, 1 is self
upper_band = mid_band + (2 * mid_band.std())   # 2 or 20 typically
lower_band = mid_band - (2 * mid_band.std())   # 2 or 20 typically
volatility = (actuals - lower_band) / (upper_band - lower_band)
upper_outliers = actuals[volatility > 1]
lower_outliers = actuals[volatility < 0]
plt.figure(figsize=(14,5))
sns.lineplot(x=actuals.index, y=actuals, color="red")
sns.lineplot(x=actuals.index, y=ewma_cash, color="blue", ls="-.", alpha=.3)
sns.lineplot(x=actuals.index, y=upper_band, color="black", ls="-.", alpha=.2)
sns.lineplot(x=actuals.index, y=lower_band, color="black", ls="-.", alpha=.2)
plt.vlines(upper_outliers.index, *plt.ylim(), alpha=0.3, ls="--", color="red")
plt.vlines(lower_outliers.index, *plt.ylim(), alpha=0.4, ls=":", color="gray")
```
### Actions: Overlapping Sessions
```
# Example:
# [start,   end, start,   end, start, start,   end,   end]  # Series
# [    1,    -1,     1,    -1,     1,     1,    -1,    -1]  # Map to 1 and -1
# [    1,     0,     1,     0,     1,     2,     1,     0]  # Cumulative Sum
# [ True, False,  True, False,  True,  True,  True, False]  # x > 0
# [ True, False,  True, False,  True,  True,  True,  True]  # Fix last overlap
# [False, False, False, False,  True,  True,  True,  True]  # Determinations
# ["Nrm", "Nrm", "Nrm", "Nrm", "Ovr", "Ovr", "Ovr", "Ovr"]  # Map to category
# use cumsum, mask, shift-comparison, and .loc to determine overlaps
s = pd.Series(start_end_series)               # Series
s = s.map({starter:1, ender:-1})              # Map to 1 and -1
s = s.cumsum()                                # Cumulative Sum
if s[len(s) - 2] == 0 and s[len(s) - 1] == 1: # Handle edge case
    flip_last = True
s = s > 0                                     # x > 0
s = s | s.shift(2)                            # Fix last overlap
s.loc[s[~s].index - 1] = False                # Determinations
if flip_last:                                 # Handle edge case
    s.loc[len(s) - 1] = False
s = s.map({True:"Overlap", False:"Normal"})   # Map to category
s = s.rename("overlap_status")
pd.concat([s, pd.Series(start_end_series)], axis=1)
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Getting to the Numbers
- Distance-based clustering is powerful, but needs continuous values to work
- Creating a ton of features with continuous values is a great approach!
- Fast plot of numerical interactions: `sns.pairplot`
```
# ID by bins
binned = pd.cut(s, bins=[0,2,5], labels=['low','high'], right=False)
# ID by inter-quantile rule
q1 = col.quantile(0.25)
q3 = col.quantile(0.75)
iqr = q3 - q1
lower_bound = q1 - k * iqr
upper_bound = q3 + k * iqr
# ID by z-score
stats.zscore(col)
```
```
# TIME SERIES NUMERICALS HERE
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Baselines and Deviation
- A user accessed/read/changed/copied files outside their normal routine
    * Categorize all files (encode)
    * Get each user's by-category access probabilities
    * Set threshold for alerting, apply threshold
- A user tried to access a system in a different access category
    * Categorize all systems (encode)
    * Get each user's access rights
    * Mask for access attempts not matching access rights
- A user copied files out of a specialized system
    * Set alerting on specific actions
- One user logged in from multiple endpoints at the same time
    * Check duplicate active states in system processes for a user (easiest)
    * Combine logs, set session start/end, check user duplication
- Two or more users logged in from a single endpoint
    * Depends entirely on the endpoint and how it captures/separates logins
- Too many manipulations of sensitive data in a given time span
    * Categorize sensitive/other actions in binary
    * Perform interval-count aggregation
    * Set limits on action manually or through Bollinger band outlier detection
- Old/unused accounts became active
    * Decide what makes an account old manually or through probabilities
    * Get last-login information for all accounts
    * Check login information against reporting criteria
```
# HOW TO BASELINE
```

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
- Good at nontabular/large data
    * It's not great for tabular/small data; slower, black-box
- Good cases for NNs: images, video, sound, NLP
- Can do "reinforcement learning" (evaluating itself)
### Neural Network Design
- Uses neural nodes for weighing patterns
- Neural nodes combine into a perceptron
    * Input is however many features you're feeding in (A0, A1, A2)
    * Output is the number of classification outcomes
    * One layer of perception is an in-parallel layer
        * Input weights
    * Single-layer perceptron: one step of perception between input and output
    * Multi-layer perceptron: multiple steps of perception between input/output
        * This is a "series of perception"
- A tensor is higher-dimensionality data than scalar, vector, or matrix
    * Scalar: 1D, vector: 2D, matrix: 3D
- Gradient Descent: seeking the minimum loss
    * Distance-based, optimizing connections to reach an answer
    * Backpropogation against feedforward
```
# NEURAL NETWORK WALKTHROUGH
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Image Classification
- 
```
# PYTORCH EXAMPLE
```
```
from tensorflow import keras     # TensorFlow is frontend, Keras is backend
from keras import models, layers
from keras.datasets import mnist # very popular image classification dataset
(train_images, train_labels), (test_images, test_labels) = mnist.load_data()
train_images = train_images.reshape((60000, 28 * 28)); 
train_images = train_images.astype('float32') / 255 # reshape data for model
test_images = test_images.reshape((10000, 28 * 28))
test_images = test_images.astype('float32') / 255
network = models.Sequential() # create the model
network.add(layers.Dense(512, activation='relu', input_shape(28*28,)))
network.add(layers.Dense(10, activation='softmax')) # add output layer
network.compile(
    optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
# compile the model
train_labels = keras.utils.to_categorical(train_labels)
test_labels = keras.utils.to_categorical(test_labels)
network.fit(train_images, train_labels, epochs=20, batch_size=128)
test_loss, test_acc = network.evaluate(test_images, test_labels)
print(f'accuracy of network on test set: {test_acc}')
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Deep Learning
- Similar methodology to NNs, but the network structure for learning is flexible
```
# ADD COMPUTER VISION EXAMPLE
```

[[Return to Top]](#table-of-contents)







<!--
 #####                                                           
#     # ###### #    # ###### #####    ##   ##### # #    # ###### 
#       #      ##   # #      #    #  #  #    #   # #    # #      
#  #### #####  # #  # #####  #    # #    #   #   # #    # #####  
#     # #      #  # # #      #####  ######   #   # #    # #      
#     # #      #   ## #      #   #  #    #   #   #  #  #  #      
 #####  ###### #    # ###### #    # #    #   #   #   ##   ###### 
                                                                 
   #    ### 
  # #    #  
 #   #   #  
#     #  #  
#######  #  
#     #  #  
#     # ### 
-->

# Generative AI

--------------------------------------------------------------------------------
<!-- Needs work -->
## Implementing LLMs
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Implementing Image Generation
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
## Pipelining a Model
```
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
from skelarn.pipeline import Pipeline
pipe = Pipeline([
    ("scaler", StandardScaler()),     # step 1
    ("reducer", PCA())])              # step 2
pc = pipe.fit_transform(num_df)
print(pc[:,:2])
df["PC 1"] = pc[:,0]
df["PC 2"] = pc[:,1]
sns.scatterplot(data=df, x="PC 1", y="PC 2", hue="cat_col", alpha=0.4)
pipe = Pipeline([
    ("scaler", StandardScaler()), 
    ("reducer", PCA(n_components=3)),  # choose between 0 and 1 for PCA to lift!
    ("classifier", RandomForestClassifier())])
print(pipe["reducer"])
pipe.fit(X_train, y_train)
print(pipe["reducer"].explained_variance_ratio_)
print(pipe["reducer"].explained_variance_ratio_.sum()) # current explained var
print(pipe.score(X_test, y_test)) # hopefully we did well!!
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Building a Flask App
- Web interfacing framework that uses Python; pretty neato stuff
- Tutorial: search "Flask mega tutorial miguen grinberg"
- Links for all things Flask: https://www.fullstackpython.com/flask.html
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
    return f'Predicted result for observation {input_array} is {predict_result}'
if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=port)
# Example call: http://localhost:5000/predict?srv_count=500&num_failed_logins=0
```
### Flask Basic Routing
- Typically uses views.py or app.py; this allows page nav from Python framework
    * Set param `methods=['GET','POST','PUT']` to choose what you can do
    * Use `if request.method == 'POST':` for maximum effect
    * Set route as `'/<int:year>/<int:month>/<title>'` to capture args from URL
        * Capture args: `def func(x,y,z):`
- `@app.before_request()` Run function on *every* page nav action 
- `@app.route('/cool_page')` Run function for specific page navigation
- `@app.errorhandler(404)` Run function for HTTP error codes
### Flask Post-Route Functions
- Overall: Generate page template, Provide response, or Redirect the user
```
# global variables
from flask import g
g.key_name = "value"
g.pop("value", None)
# templates
Flask(__name__, template_folder='templates')
    return render_template('index.html')
return_template(cool_page.html, global_var_thingy="cool")  # use JINJA in HTML
# responses
return make_response(APIstuff, HTTP_response_code, headers=headers_dict)
# redirects
return redirect('/cool_page_2.html')
return redirect(url_for('cool_page_2'))
# requests
request.method
request.args.func
request.data
request.form
request.headers
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Building a Django App
```
# CREATE DJANGO EXAMPLE
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Deploying the Model
- Containers: Easy replication and distribution of software solutions
- Sandboxing: Each container in a Docker daemon is **isolated** from one another
    * A container can replicate a computer in a safe state for testing
- Cloud Support: Install the Docker daemon on a virtual server, build image, run
- Scalable: Load balancers (like Kubernetes) control many daemons/containers 
- Lightweight: *Not* ran in a VM; runs directly from OS kernel (Docker mediates)
    * Docker daemon will initialize a VM if OS kernel does not match container 
- Base images for `docker pull` or `FROM`: https://hub.docker.com
- Official documentation: https://docs.docker.com/engine/reference/builder/
### Dockerfile
- Set of instructions to build a Docker image
- Starts with `FROM`, which takes a base image as a parameter
- Each instruction adds a layer or an intermediate layer to the image
    * NOTE: Instructions run to completion before proceeding
- Instructions are couched in the base layer
    * For example: `RUN` for the Ubuntu base image uses Linux commands
- **RUN:** Execute a command when building the image
    * `RUN ["python3", "my_setup_script.py"]` is same as `python3 myscript.py`
    * Can also use: `RUN python3 myscript.py`, but the other form is recommended
- **COPY:** Copy a local directory's files into image's specified directory
    * Use `COPY . /app` to copy the current directory into image's "app" folder
- **WORKDIR:** Specify the directory for the image to proceed to
    * Nav to the runtime folder and use ENTRYPOINT + CMD here to run scripts
- **ENTRYPOINT:** Set the command for the image to run *every time*
    * Can't be modified through command line
    * If an image is designed to use a python kernel, specify python here
- **CMD:** Sets the command for the image to use when the image is ran
    * Often used with ENTRYPOINT
        * ENTRYPOINT is great for selecting a kernel ("python3") to run a script
    * With `ENTRYPOINT ["python3"]`, use: `CMD ["image_runtime_script.py"]`
```
FROM ubuntu:latest
RUN apt-get update -y
RUN apt-get install -y python3-pip python3-dev build-essential
COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt    # specify python libraries to install
ENTRYPOINT ["python3"]
CMD ["app.py"]
```
### Initializing, Running Docker Containers
- Build image(s) from a Dockerfile, Run images from the Docker images folder
- Build: Specify the context where the Dockerfile + needed files live
    * Example: `docker build .`
    * `-t author/purpose:version`: add image tag (image name)
- Run: Specify which compiled image to use
    * Example: `docker run -d -p 80:80 --rm image_name`
        * (d)etach from terminal, specify (p)ort, (rm) container on exit
    * Run named image: `docker run author/purpose`
        * This assumes the latest image version if version isn't specified
    * Alias an image during the run command: `--name alias_name`

[[Return to Top]](#table-of-contents)







<!-- 
   #                                                               
  # #   #####  #####  #      #  ####    ##   ##### #  ####  #    # 
 #   #  #    # #    # #      # #    #  #  #    #   # #    # ##   # 
#     # #    # #    # #      # #      #    #   #   # #    # # #  # 
####### #####  #####  #      # #      ######   #   # #    # #  # # 
#     # #      #      #      # #    # #    #   #   # #    # #   ## 
#     # #      #      ###### #  ####  #    #   #   #  ####  #    # 
                                                                   
 #####                                       
#     #  ####    ##   #      # #    #  ####  
#       #    #  #  #  #      # ##   # #    # 
 #####  #      #    # #      # # #  # #      
      # #      ###### #      # #  # # #  ### 
#     # #    # #    # #      # #   ## #    # 
 #####   ####  #    # ###### # #    #  ####  
-->

# Application Scaling
```
When you've hit the big time, scaling your applications is required.
Kubernetes is a popular choice for scaling containerization schemes.
Apache Kafka is another popular choice for serving data via scaled architecture.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Kubernetes
- Alias for *nix: `alias k=kubectl`
- Alias for Windows: `Set-Alias -Name k -Value kubectl`
- Events: `kubectl get events -A`
    * `kubectl get events --sort-by=<JSONPath>` or `kubectl get events -o wide`
### Wipe Kubernetes
```
kubectl delete -f <file>
kubectl delete pod,service <name1> <name2>  # if pods/services have same names
kubectl delete pods,services -l <label_name>=<label_value>  # delete by label
```
### Kubernetes Configuration
```
kubectl config view
KUBECONFIG=~/.kube/config1:~/.kube/config2:~/.kube/config3
kubectl config view -o jsonpath='{.users[*].name}'
kubectl config view -o jsonpath='{.users[?{@.name=="admin"}].user.password}'
kubectl config current-context
kubectl config get-contexts
kubectl config use-context <cluster>
kubectl config set-credentials <username> [options]
kubectl config set-credentials <user> --client-key=~/.kube/admin.key
kubectl config set-credentials --username=<username> --password=<password>
kubectl config set-credentials <user> --client-certificate=<path/to/cert> --
    embed-certs=true
kubectl config --kubeconfig=<config/path> use-context <cluster>
kubectl config set-context gce --user=cluster-admin --namespace=foo \
    && kubectl config use-context gce
```
### Pods
```
kubectl explain pod
kubectl get pods -A
kubectl get pods -n <namespace>
kubectl get pod <pod> --watch
kubectl get pods -A --watch
kubectl get pods --sort-by='.status.containerStatuses[0].restartCount   # sroted
kubectl get pods -o json
kubectl get pods -o wide
kubectl get pods -o custom-columns='DATA:spec.containers[*].image'
kubectl get pods -o custom-columns='DATA:spec.containers[*].volumeMounts'
kubectl get pods -o custom-columns='DATA:metadata'
```
```
kubectl run <pod> --generator=run-pod/v1 --image=<image>
kubectl run nginx --generator=run-pod/v1 --image=nginx
kubectl run busybox --generator=run-pod/v1 --image=busybox
kubectl run -i --tty nginx --image=nginx -- sh
kubectl run busybox --image=busybox -- sleep 100000
kubectl exec <pod> --  <command>
kubectl exec -it <pod> -- <command>
kubectl exec -it nginx -- ls -lrth /app/
kubectl run <pod> --generator=run-pod/v1 --image=nginx --dry-run   # test
kubectl patch pod <pod> -p '<patch>'
kubectl patch pod <pod> -p '{"spec":{"containers":[{
    "name":"kubernetes-serve-hostname",
    "image":"new image"
}]}}'
kubectl patch pod valid-pod --type='json' -p='[{
    "op":"replace",
    "path":"/spec/containers/0/image",
    "value":"new image"
}]'
```
```
kubectl create -f pod.yaml
cat <<EOF | kubectl create -f -
apiVersion: v1
kind: Pod
metadata:
    name: nginx-pod
spec:
    containers:
    - name: nginx
      image: ngingx:latest
EOF
```
```
cat <<EOF | kubectl create -f -
apiVersion: v1
kind: Pod
metadata:
    name: nginx-pod
spec:
    containers:
    - name: nginx
      image: nginx:latest
---
apiVersion: v1
kind: Pod
metadata:
    name: busybox
spec:
    containers:
    - name: busybox
      image: busybox
      args:
      - sleep
      - "100"
EOF
```
```
kubectl run nginx --generator=run-pod/v1 --image=nginx -n <namespace>
kubectl create -f pod.yaml -n <namespace>
```
```
kubectl delete pod <pod>
kubectl delete -f pod.yaml   # if pod was created from pod.yaml
kubectl delete pod <pod> --grace-period=0 --force
```
```
kubectl logs <pod>
kubectl logs <pod> -c <container>
kubectl logs -f <pod>        # read tail of logs
kubectl logs -l <label_name>=<label_value>
kubectl logs -l env=prod
kubectl logs -l <label_name>=<label_value> -c <container>
kubectl logs -f -l <label_name>=<label_value> --all-containers
kubectl get pods --all-namespaces -o jsonpath='{range.items[*].status
    .initContainerStatuses[*]}{.containerID}{"\n"}{end}' | cut -d/ - f3
kubectl top pod <pod>
kubectl top pod <pod> --containers
```
### Deployments
```
kubectl run <deployment> --image=<image>
kubectl create deployment <deployment> --image=<image>
kubectl run <deployment> --image=<image> --replicas=<replicas> --port=<port>
kubectl run nginx --image=nginx --replicas=2 --port=80
kubectl run nginx --image=nginx --replicas=2 --port=80 --expose
kubectl get deploy <deployment>
kubectl get deployment <deployment> --watch
kubectl get deployments.apps <deployment> --watch
kubectl get deploy -n <namespace>
kubectl get deploy --all-namespaces
kubectl get deploy -A
kubectl get deploy -o yaml
kubectl get deploy -o wide
kubectl set image deployment/nginx nginx=nginx:1.9.1
kubectl set image deployment/backend api=image:v2
kubectl scale --replicas=5 deployment/<deployment>
kubectl scale --replicas=5 deploy/<deployment>
kubectl run nginx --image=nginx --replicas=2 --port=80 --dry-run -o yaml
kubectl apply -f deployment.yaml
```
```
kubectl port-forward deployment <deployment> <localhost-port>:<deployment-port>
kubectl port-forward pod <pod> <localhost-port>:<pod-port>
kubectl port-forward redis 8090:6379
kubectl port-forward pod <pod> <port>        # same port
kubectl port-forward pod nginx 8000 9000     # listen on two port:port things
kubectl port-forward pod <pod> :<pod-port>   # listen on random port
kubectl port-forward pod nginx :80
kubectl port-forward --address localhost,123.45.67.89 pod redis 8000:6379
kubectl port-forward --address 0.0.0.0 pod <pod> <hosts-port>:<pod-port>
```
```
kubectl edit deployment/<deployment>
kubectl rollout undo deployment <deployment>
kubectl rollout history deployment <deployment>
kubectl rollout history deployment nginx
kubectl rollout undo deployment nginx --to-revision=2
kubectl rollout status deployment <deployment>
kubectl rollout pause deployment <deployment>
kubectl rollout resume deployment <deployment>
```
### Namespaces
```
kubectl get namespaces
kubectl get ns
kubectl get namespace <namespace>
kubectl describe namespace <namespace>
kubectl create namespace <namespace>
kubectl create -f namespace.yaml
kubectl -n <namespace> delete pods,services --all
kubectl delete namespace <namespace>
kubectl delete -f namespace.yaml
```
```
cat <<EOF | kubectl create -f -
apiVersion: v1
kind: Namespace
metadata:
    name: mynamespace
EOF
```
### Nodes
```
kubectl describe nodes
kubectl get nodes
kubectl get nodes <node>
kubectl top node <node>
kubectl get nodes -o jsonpath='{.items[*].status.addresses[?
    {@.type=="ExternalIP"}].address}'
kubectl describe nodes <node>
JSONPATH='{range .items[*]}{@.metadata.name}:{range @.status.conditions[*]}
    {@.type}={@.status}:{end}{end}' && kubectl get nodes 
    -o jsonpath="$JSONPATH" | grep "Ready=True"
kubectl cordon <node>     # mark node as unschedulable
kubectl drain <node>      # "drain" a node for maintenance
kubectl uncordon <node>   # mark node as schedulable
```
### Clusters
```
kubectl cluster-info
kubectl cluster-info dump
kubectl cluster-info dump --output-directory=</file/path>
kubectl diff -f ./my-manifest.yaml  # compare cluster state to next edited state
kubectl get pods -A -o custom-columns='DATA:spec.containers[*].image'
```
### Services
```
kubectl explain service
kubectl create service clusterip myclusterip --tcp=5678:8080
kubectl create service loadbalancer myloadbalancer --tcp=80
kubectl describe service <service>
kubectl edit service <service>
KUBE_EDITOR="vim" edit service <service>
kubectl delete service myclusterip
kubectl delete svc myloadbalancer
kubectl delete service myclusterip myloadbalancer
```
### Service Accounts
```
kubectl get serviceaccounts
kubectl get sa
kubectl get serviceaccount <serviceaccount>
kubectl create serviceaccount <serviceaccount>
kubectl delete serviceaccount <serviceaccount>
kubectl describe serviceaccount <serviceaccount>
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Apache Kafka
- Distributed stream processing
- Kafka 'broker' listens on port 9092 for TCP connection by default
    * Distributed system has multiple 'brokers'
        * Each broker has full copy of 'topics', each listens on different ports
    * One 'broker' is 'leader' on a 'partition'/'topic'; others are 'followers'
- Kafka 'producer' publishes to a 'topic' in the Kafka 'broker'
    * Each publish action adds a row in the 'topic' marked by index
    * With 'partitions', the 'producer' selects the 'partition' to add a row to
- Kafka 'consumer' reads the topic and all its rows from index 0 onward
    * All consumers in a group "Queue"; separate groups "Pub/Sub" each other
        * "Queue": publish once, consume once (disappears after)
        * "Pub/Sub": publish once, consume many times (doesn't disappear)
    * Consume: Consumer groups send topic partitions evenly between consumers
    * The max number of consumers in a group == number of partitions in a topic

[[Return to Top]](#table-of-contents)







<!--
######         #####                              
#     # #   # #     # #####    ##   #####  #    # 
#     #  # #  #       #    #  #  #  #    # #   #  
######    #    #####  #    # #    # #    # ####   
#         #         # #####  ###### #####  #  #   
#         #   #     # #      #    # #   #  #   #  
#         #    #####  #      #    # #    # #    # 
-->

# PySpark
```

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

--------------------------------------------------------------------------------
<!-- Needs work -->
## PySpark Commands
- Check Spark's intentions before query: `df.explain()`
    * Used for diagnosing performance issues; operation order from bottom-upward
- Switch to SQL: `df.createOrReplaceTempView('df')`
    * Run SQL statements: `spark.sql(''' SELECT * FROM df ''')`
- Build schema: `schema = StructType([(StructField(...), StructField(...)),])`
    * StructField syntax: `Structfield("col1", StringType())`
### PySpark Wrangling Example
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
    [count(when(isnan(c) | col(c).isNull(), c)).alias(c) for c in df.columns]
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
### PySpark Aggregation Example
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

--------------------------------------------------------------------------------
<!-- Needs work -->
## PySpark Machine Learning
```
from pyspark.ml.stat import ...    # chi square / correlation testing
from pyspark.ml.feature import ... # imputation, encoding, scaling, vectorize...
from pyspark.ml.classification import ... # modeling
from pyspark.ml.regression import ...     # modeling
from pyspark.ml.clustering import ...     # modeling
from pyspark.ml.tuning import ...         # model cross-validation
from pyspark.ml.evaluation import ...     # model evaluation
```

[[Return to Top]](#table-of-contents)







<!--
####### #       #    #     #####                             
#       #       #   #     #     # #####   ##    ####  #    # 
#       #       #  #      #         #    #  #  #    # #   #  
#####   #       ###        #####    #   #    # #      ####   
#       #       #  #            #   #   ###### #      #  #   
#       #       #   #     #     #   #   #    # #    # #   #  
####### ####### #    #     #####    #   #    #  ####  #    # 
-->

# ELK Stack
```
Elasticsearch, Logstash, Kibana. Otherwise known as the ELK stack.
Elasticsearch is a storage architecture.
Logstash is a pipelining architecture.
Kibana is a user interface for accessing the data/pipelining in Elasticsearch.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Elasticsearch
- Popular SIEM system with querying and visualizations/dashboards (Kibana/API)
- Can use Kibana's UI to perform simple tasks, queries, and visualization
- Can use the console in Kibana Dev Tools to run powerful queries/indexing/etc
    * Painless scripting (Java-based language) overcomes KQL shortcomings
- Python interacts with the Elasticsearch REST API on port 9200 (default)
- To connect: create an account in Kibana and use those creds in Python queries
### cURL: Perform an Aggregation
- Note: this is meant to be pasted into Bash terminal
- In Kibana, you can draft/test your query JSON before you run it here
    * Consider making script that reads JSON into cURL command "--data" argument
```
curl -k --user username:password --header "Content-Type:application/json"      \
-X GET https://123.45.67.89:9200/index_pattern/_search                         \
--data "                                                                       \
{                                                                              \
  \"query\":{\"match_all\":{}},                                                \
  \"aggs\":{\"cool\":{\"terms\":{\"field\":\"agent.name\", \"size\":1000}}}    \
}"                                                                             \
> output.json
```
### Python: Stack Assessment
```
# DEFINITION BLOCK
def gather_fields_from_index(properties):
    output_list = []
    def walk_down(current, name=""):
        keys = list(current.keys())
        for key in keys:
            if "properties" in current[key].keys():
                walk_down(current[key]["properties"], f"{name}{key}.")
            else:
                output_list.append(f"{name}{key}")
    walk_down(properties)
    return set(output_list)
def gather_field_pnids(search_context, all_fields,\
                       pn_field="winlog.provider_name",\
                       eid_field="winlog.event_id", range_kwargs=None):
    field_count = len(all_fields)
    print(f"Getting all PN_ID options for {field_count} fields...",
          end="\r", flush=True)
    capture_dict = {}
    j = 0.0
    for i, new_field in enumerate(all_fields):
        if round((i / field_count) * 100) > j:
            j = round((i / field_count) * 100)
            print(f"Getting all PN_ID options for {field_count} fields: {j}%",
                  end="\r", flush=True)
        sc2 = search_context.query("exists", field=new_field)
        if type(range_kwargs) is dict:
            sc2 = sc2.filter("range", **range_kwargs)
        sc2.aggs.bucket("pn",  "terms", field=pn_field,  size=10_000)\
                .metric("eid", "terms", field=eid_field, size=10_000)
        response = sc2.execute()
        my_aggs = response.aggregations.to_dict()
        for pn_bucket in my_aggs["pn"]["buckets"]:
            pn = pn_bucket["key"]
            for eid_bucket in pn_bucket["eid"]["buckets"]:
                eid = eid_bucket["key"]
                pn_id = f"{pn}_{eid}"
                if pn_id not in capture_dict.keys():
                    capture_dict[pn_id] = {"event_cols":{"all":[]}}
                capture_dict[pn_id]["event_cols"]["all"].append(new_field)
    print(f"Parsed all {field_count} fields! Count of discovered PN_IDs:",
          len(capture_dict.keys()))
    output_dict = {}
    for key in sorted(list(capture_dict.keys())):
        col_list = sorted(capture_dict[key]["event_cols"]["all"])
        output_dict[key] = {"event_cols": {"all":col_list}}
    return output_dict
```
```
# EXECUTION BLOCK
output_findings_to_json = True
ip, user, password = "https://192.168.0.1:9200", "coolguy", "coolpassword"
index_pattern = "so-beats-*"
import warnings
warnings.filterwarnings("ignore")
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search
client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
indices = sorted(list(client.indices.get_alias(index_pattern).keys()))
index_count = len(indices)
for i, ind in enumerate(indices):
    if round((i / index_count) * 100) > j:
        j = round((i / index_count) * 100)
        print(f"Checking indices: {j}%", end="\r", flush=True)
    try:
        maps = client.indices.get_mapping(ind)[ind]["mappings"]["properties"]
        new_set = gather_fields_from_index(index_fields)
        all_fields.update(new_set)
    except Exception as error:
        print(ind, "---", error)
        print(f"Checking indices: {j}%", end="\r", flush=True)
all_fields = sorted(list(all_fields))
print("Check complete! Number of observed fields:", len(all_fields))
search_context = Search(using=client, index=index_pattern, doc_type="doc")
field_pnids = gather_field_pnids(
    search_context, all_fields, pn_field, eid_field, mission_window)
providers = {pn_id.split("_")[0] for pn_id in field_pnids.keys()}
provider_printout = "\n".join(sorted(list(providers)))
print(f"\nDiscovered Providers:\n{provider_printout}\n")
sample_val = "Microsoft-Windows-Security-Auditing_4624"
if sample_val in field_pnids.keys():
    print(f"Fields for sample: {sample_val}\n{field_pnids[sample_val]}\n")
if output_findings_to_json:
    with open("kb_specific.json", "w") as f:
        f.write(json.dumps(output_pnids, indent=2))
```
### Python: Record Pull
```
# DEFINITION BLOCK
def flatten_json(json_input, splitout_lists=False):
    output_dict = {}
    def flatten(current_structure, name=""):
        if type(current_structure) is dict:
            # loop vertically (key -> value)
            for element in current_structure:
                flatten(current_structure[element], name + element + ".")
        elif type(current_structure) is list:
            if splitout_lists in [True, "True", "true", "Yes", "yes", "sure"]:
                for i, element in enumerate(current_structure):
                    flatten(element, name + str(i) + "_")
            else: output_dict[name[:-1]] = current_structure
        else: output_dict[name[:-1]] = current_structure
    flatten(json_input)
    return output_dict
def print_progress(i):
    if i < 1_000_000 and i % 1_000 == 0 and i != 0:
        print(f"{i // 1_000}k records found...", end="\r", flush=True)
    elif i % 10_000 == 0 and i != 0:
        print(f"{i / 1_000_000}mil records found...", end="\r", flush=True)
def use_es_response(response, return_count=10, use_es_id=False):
    hits = response.__dict__["_d_"]["hits"]["hits"]
    rows = []
    for hit in hits[:return_count]:
        obj = hit["_source"]
        if use_es_id:
            obj["_id"] = d.meta.id
        row = flatten_json(obj)
        rows.append(row)
    if len(rows) == 0:
        return None
    df = pd.DataFrame(rows)
    return df
def query_the_stack(query_object, return_count=None):
    response = query_object.execute()
    if not response.success(): 
        print("Connection failed!")
        return None
    under10records = len(response.__dict__["_d_"]["hits"]["hits"]) < 10
    if return_count in range(1,11) or under10records:
        df = use_es_response(response, return_count, use_es_id)
        return df
    rows = []
    try:
        for i, d in enumerate(query_object.scan()):
            if i == return_count:
                break
            if shh is False:
                print_progress(i)
            obj = d.to_dict()
            if use_es_id:
                obj["_id"] = d.meta.id
            row = flatten_json(obj)
            del obj
            rows.append(row)
            del row
    except Exception as error:
        print("Something went wrong!! The query probably didn't complete.")
        print(f"Here's the error:\n{error}")
    try:
        if shh is False:
            print("Total records found:", "{:,}".format(i))
    except:
        pass
    if len(rows) == 0:
        return None
    df = pd.DataFrame(rows)
    del rows
    return df
```
```
# EXECUTION BLOCK
ip, user, password = "https://192.168.0.1:9200", "coolguy", "coolpassword"
index_pattern = "so-beats-*"
import warnings
warnings.filterwarnings("ignore")
import pandas as pd
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search
client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
search_context = Search(using=client, index=index_pattern, doc_type="doc")
s1 = search_context\
    .query("match", winlog__event_id=4624)\
    .filter("range", **{"@timestamp": {"gte": "now-1d"}})\
    .source(fields=["winlog.provider_name","winlog.event_id"])
df1 = elk_basics.query_the_stack(s1, 10_000)
s2 = search_context.query("exists", field="winlog.event_data.LogonType")
df2 = elk_basics.query_the_stack(s2, 10_000)
```
### Python: Advanced Querying
```
# DEFINITION BLOCK: NO DEFINITIONS!
```
```
# EXECUTION BLOCK
ip, user, password = "https://192.168.0.1:9200", "coolguy", "coolpassword"
index_pattern = "so-zeek-*"
import warnings
warnings.filterwarnings("ignore")
import pandas as pd
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search
client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
search_context = Search(using=client, index=index_pattern, doc_type="doc")
painless = """
boolean x = false;
def src_regex = /181\.18\.120\.\d{1,3}/.matcher(doc["source.ip"].value);
if (src_regex.matches()) {
    x = doc["client.ip_bytes"].value > doc["server.ip_bytes"].value;
}
return x;
"""
fields = ["source.ip","destination.ip","client.ip_bytes","server.ip_bytes"]
s = search_context\
    .query("bool", **{"must": [{"match": {"source.ip":"123.45.67.0/24"}}],
                      "filter": {"script": {"script": {"source": painless}}}})\
    .params(request_timeout=90)
s.aggs.bucket("src", "terms", field="source.ip", size=10_000)\
      .metric("dst", "terms", field="destination.ip", size=10_000)
print("Executing... please hold for a few seconds...", end="\r", flush=True)
response = s.execute()
print("Done!" + " "*100)
results = response.aggregations.to_dict()
output_set = set()
for bucket in results["src"]["buckets"]:
    src = bucket["key"]
    dsts = {bkt["key"] for bkt in bucket["dst"]["buckets"]}
    rows = {(src, dst) for dst in dsts}
    output_set.update(rows)
df = pd.DataFrame([{"source":os[0], "destination":os[1]} for os in output_set])
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Logstash
- 

--------------------------------------------------------------------------------
<!-- Needs work -->
## Kibana
### Kibana Dev Tools: Print to Console
```
# UNIQUE COMBINATIONS OF SOURCE IP FIRST-TWO OCTETS
# RUNTIME MAPPINGS ARE TEMPORARY FIELDS ADDED TO RECORDS
# WE CAN AGGREGATE THESE TEMPORARY FIELDS FOR COOL OUTCOMES
GET so-zeek-*/_search
{
"size": 0,   // Focusing on aggregations, so, show zero individual records
"runtime_mappings": {"srcip_firsttwo_octets": {
    "type": "keyword",
    "script": {"source": """
        boolean requiredfields_exist;
        String ip;
        String firsttwo_octets = '';
        requiredfields_exist = (
            doc.containsKey('source.ip') && !doc['source.ip'].empty;
        )
        if (requiredfields_exist) {
            ip = doc['source.ip'].value.toString();
            def octets = ip.splitOnToken('.');
            for (int i = 0; i < 2 && octets.length == 4; i++) {
                firsttwo_octets = firsttwo_octets + octets[i] + '.';
            }
            emit(firsttwo_octets);
        }
    """
}}},
"fields": ["source.ip", "srcip_firsttwo_octets"],
"_source": false,
"aggs": {
    "firsttwo": {"terms": {"field": "srcip_firsttwo_octets", "size": 10000}
}}}
```
### Kibana Dev Tools: Reindexing (ETL-like operation)
```
# CLONE MAPPINGS; CLOSE THE SOURCE INDEX FIRST! USE AN INDEX WITH LITTLE DATA!
POST so-beats-2023.10.15/_clone/my-exploration-index
# CLEAR THE IRRELEVANT DATA, LEAVING JUST THE MAPPINGS THAT WE NEED
POST my-exploration-index/_delete_by_query
{"query": {"match_all": {}}}
# RUN REINDEXING OPERATION
POST _reindex
{
"max_docs": 100,
"source": {
    "index": "so-beats-*",
    "query": {"bool": {
        "must": {"exists": {"field": "process.executable"}},
        "filter": {"script": {"script": {"source": """
            String col = 'process.executable';
            String cmd = '\\cmd.exe';
            boolean fp_cmd = doc[col].value.endsWith(cmd);
            return fp_cmd;
            """
        }}}}
    },
    "_source": ["@timestamp","agent.name","process.executable"]
},
"script": {"source": """
    ctx._source.investigation = 'early-1';
    ctx._source.norm_exec = ctx._source.process.executable.toLowerCase();
"""
},
"dest": {
    "index": "my-exploration-index"
}}
# IF _REINDEX TIMES OUT, YOU CAN CHECK RUNNING REINDEXING OPERATIONS...
GET _tasks?detailed=true&actions=*reindex
# ...THEN, CHECK THAT SPECIFIC TASK'S PROGRESS...
GET _tasks/Ovbg8nVuREaqV3INCO13Og:361012073
# ...AND IF YOU NEED, YOU CAN CANCEL THAT SPECIFIC TASK...
# NOTE: COPIED RECORDS REMAIN IN THE TARGET INDEX (PROCESSED RECORDS NOT UNDONE)
POST _tasks/Ovbg8nVuREaqV3INCO13Og:361012073/_cancel
# ...THEN YOU CAN DELETE THE RECORDS OUT IF NECESSARY...
POST my-exploration-index/_delete_by_query
{"query": {"match_all": {}}}
# ...OR, DELETE THE ENTIRE INDEX AND MAPPINGS!
DELETE my-exploration-index
```

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
- Requirements Stage: Talk with stakeholders about their requirements/timeline
- Decision Stage: Decide which requirements you will be able to complete
    * Goal is to complete *all* user requirements for this "sprint" (a timeline)
    * You choose how in-depth to go for each requirement

--------------------------------------------------------------------------------
<!-- Needs work -->
## Selecting the Framework
- Waterfall: takes it one step at a time, fully-complete each step then move on
    * All requirements defined ahead of time
    * Inflexible for new requirements/issues, must start over; finish is clear
- AGILE: deliver minimums, expand minimums with features iteratively
    * An iterations is a "spiral"; spiraling with new features
    * Flexible for new requirements/issues, but may be hard to say it's finished
### Systems Development Lifecycle (SDLC)
- Framework for delivering software
- Waterfall and AGILE both still in use; each follows same steps; AGILE repeats
- Step 1: Analysis - Selecting requirements to fulfill (final ones are in SRS)
    * UML: Use case diagram; user choices, choice result
- Step 2: Design - choosing the solutions to solve those requirements
    * UML: Class diagram; classes with vars, inheritance; "unfilled diamond"
- Step 3: Implementation - building the chosen solutions
    * UML: Activity diagram; typically a program's flowchart with actual code
- Step 4: Testing - ensuring the solutions are functional + satisfy requirements
    * UML: Sequence diagram; example is client-server communication sequence

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
- Absolute reference using hold_clickdrag + fn + F4
- Doubleclick bottomright of function cell to affect all rows in selected col(s)
```
# count
=COUNT(cells)
# conditions
=IF(AND(cond1, OR(cond2, cond3)), truth_value, false_value)
=COUNTIF(cells, cellwise_condition) | =SUMIF(cells, cellwise_condition)
=INDEX(range, MATCH(string_to_match, range)) | =IFERROR(value, truth_value)
# numbers
=B2-B3 | =B9+B12
=MOD(cells, 3) | =POWER(cells, 2) | =SUM(cells, cells) | =AVERAGE(cells, cells)
# strings
=CEILING(cells) | =FLOOR(cells)
=CONCATENATE(cells, cells, " ", cells, " ") | =SPLIT(cells, ",") | =LEN(cells)
=REPLACE(cells, index, length, new_text) | =SUBSTITUTE(cells, match, sub, times)
=LEFT(cells, numchars) | =MID(cells, start, steps) | =RIGHT(cells, numchars)
=UPPER(cells) | =LOWER(cells) | =PROPER(cells)
# times
=NOW() | =TODAY() | =TIME(HHcells, MMcells, SScells) | =DATEDIF(s1, s2, step)
# VLOOKUP: read columns vertically to discover match then return the column
=VLOOKUP(key, range_to_search(use fn+f4 to 'lock' it), col_to_return, FALSE)
# advanced features
=SPARKLINE(range, {'charttype','bar';'color','red';'max',max(range); etc})
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## PowerBI
- Can do reports in Jupyter! And you should!!
```
from powerbiclient import Report, models
# Import the DeviceCodeLoginAuthentication class to authenticate with Power BI
from powerbiclient.authentication import DeviceCodeLoginAuthentication
# Initiate device authentication
device_auth = DeviceCodeLoginAuthentication()
group_id=""
report_id=""
report = Report(group_id=group_id, report_id=report_id, auth=device_auth)
report
```
```
from powerbiclient import QuickVisualize, get_dataset_config, Report
from powerbiclient.authentication import DeviceCodeLoginAuthentication
import pandas as pd
df = ...
# Create a Power BI report from your data
PBI_visualize = QuickVisualize(get_dataset_config(df), auth=device_auth)
# Render the new report
PBI_visualize
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Tableau
- Excellent software for interactive visualizations and dashboards
- Regular Tableau requires a license, can save locally, autosaves enabled
- Tableau Public is free, but all work gets posted to https://public.tableau.com
### Tableau Resources
- The Superstore CSV is popular to learn and demo Tableau
- Faith Kane: https://public.tableau.com/app/profile/faith.kane
- Sean Oslin: https://public.tableau.com/app/profile/sean.oslin
### Tableau Usage
- Explore your data w/ Excel pivot tables first; exploration in Tableau is slow
    * Tableau Prep can assist with this
- Data Source: Used for changing files across the project
    * Adjust field types; Tableau relies on correct typing for simplifying work
    * Hide unnecessary columns from project using drop-downs in each column
    * Filter results at top-right (intuitive)
- Sheets: Used for building individual charts
    * Plot by rows and columns, use Marks for conditional formatting / tooltips
    * Set chart type in top right, change chart dimensions via top-mid dropdown
    * Adjust display options for numbers, add trend lines, annotations, and more
        * Everything-formatting: Context Menu > Format
    * Create: calculated fields for agg, level of detail (LOD) calculations, etc
    * Can build new file using Python/Pandas and add the new file to new sheet
- Dashboard: Show multiple sheets in one place
    * Add non-sheet elements from bottom left
    * Create multi-sheet filters
- Story: Used for presentation of sheets and dashboards

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
Python is my main language, so I'll just use the section to store odd snippets.
R is an alternative to Python and used especially in academia (use is waning).
C++ pointer manipulation is very fast, so C++ might play a role in development.
```
- TODO: Add decorators like `@staticmethod` to Python classes

--------------------------------------------------------------------------------
<!-- Needs work -->
## Python Oddities
- `import sys` --- `sys.path.append("..")` open relative links to parent dir
- `reload(coolutil)` Reload your imports (Uses: `from importlib import reload`)
- `help(coolfunc)` or `print(coolfunc.__doc__)`: Read function's docstring
- `if __name__ == '__main__': (code)` to run code when directly invoking script
- Look up character in unicode with Python: `ord('?')`
- Get character using its unicode "code point" in Python: `chr(63)`
- Variables: `dir()` ---> `x = 100` ---> `dir()` ---> `del x` ---> `dir()`
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
- `mylist[start:stop:step]`, especially backwards with `print("hello"[::-1])`
- `sorted(mylist)` returns sort, `mylist.sort()` performs and saves sort
    * Same with `reversed(mylist)` and `mylist.reverse()`
- `mylist.remove("f")` removes "f"; `mylist.insert(2, "m")` inserts at index 2
    * Remove has no gaps; Insert shifts old index 2 (and the rest) to the right
- `mylist[1] = "hi` direct assignment; can also `mylist[1:3] = ["sup","yo"]`
### Dicts
- Dict keys can be any immutable variable, like a tuple!
- `{"a":1, "b":2}.get("zzz", "doesn't exist!")` query for a key
- `x.update({"trees":["Oak"]})` add new key:value without reassignment
- `{ok:{ik:float(iv) for (ik, iv) in ov.items()} for (ok, ov) in d.items()}`
### Generators
- `x = iter(mylist)` creates iterable list, `next(x)` prints next item in x
    * Iterables track your spot if you use `next`, pretty cool with `os.walk()`
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
print(cool1 < cool2) # returns "Yup" (less-than is overloaded)
print(cool1)         # returns "Cool Guy costs only $15.00." (str is overloaded)
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
- SyntaxError and IndentationError are reported before *any* code runs
    * All other errors are reported during runtime
- SyntaxError: "illegal" code
    * EX: `print("hi") print("there!") print("all on one line?...")`
- IndentationError: didn't indent properly, ex: not indenting a `for` loop
- ValueError: can't perform operation on that data type, ex: `int("hi")`
- TypeError: similar to value error, ex: `"abc" + 42`
- NameError: didn't initialize a variable before its use, ex: `print(greeting)`
- NotImplementedError: function has no body
- AssertionError: `assert` statement fails
    * Or, `import unittest` unit test assertion fails
- RuntimeError: example is when recursion function runs 1,000 times
    * Can be adjusted via `sys.setrecursionlimit()`
- Logic error: the code ran, but the output is wrong
    * EX: `42 * 1` when you meant `42 * 10` (this is also called a bug)
- Capture all but logic errors via `try`-`except` statements
    * EX: `try: code` -> `except NameError: code`
    * Use `try` with `raise` to force errors/non-errors into `except` statement
        * EX: `raise TypeError("Not integer!")`
        * Can raise your own errors
            * `class CoolError(Exception): def __init__...`
            * `raise CoolError(...)`
    * Use `finally` after `except` statement to run code regardless of errors
        * EX: `finally: print("Terminated.")`
### Python from Terminal
- Capture passed args when calling python script from terminal
```
touch run.py; 
echo """
import sys
vars = sys.argv             # capture args
print('--- Args:', ', '.join(vars))
if len(vars[1:]) == 2:      # input validation
    cool1, cool2 = vars[1], vars[2]
    if cool2.isnumeric(): 
        print('----- 2 args; Add 42 to arg 2:', int(cool2) + 42)
    else:
        print(f'----- 2 args; "{cool1}", because arg 2 isn\'t an integer!')
else:
    print('----- Didn\'t pass 2 args to run.py')
""" >> run.py;
python3 run.py "yo";
python3 run.py "yo" 21
python3 run.py "yo" "sup"
rm run.py
```
### Terminal from Python
- Reach out over SSH and operate a specific terminal; output to LOCAL file
```
import subprocess
pipe = subprocess.PIPE
remote_terminal_command = """
sshpass -f pass.txt ssh user@123.45.67.89;
/bin/vbash -c "show config" > output.txt;
"""
subprocess.Popen(remote_terminal_command, shell=True, stdout=pipe, stderr=pipe)
with open("output.txt", "r") as f:
    config = f.read()
print(config)
```

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
### C++ Pointers
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
### C++ Libraries
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
### C++ Examples
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