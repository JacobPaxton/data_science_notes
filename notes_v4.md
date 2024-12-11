




<!-- 
#######                                                                 
#       #    # #    # # #####   ####  #    # #    # ###### #    # ##### 
#       ##   # #    # # #    # #    # ##   # ##  ## #      ##   #   #   
#####   # #  # #    # # #    # #    # # #  # # ## # #####  # #  #   #   
#       #  # # #    # # #####  #    # #  # # #    # #      #  # #   #   
#       #   ##  #  #  # #   #  #    # #   ## #    # #      #   ##   #   
####### #    #   ##   # #    #  ####  #    # #    # ###### #    #   #   
                                                                        
 #####                             
#     # ###### ##### #    # #####  
#       #        #   #    # #    # 
 #####  #####    #   #    # #    # 
      # #        #   #    # #####  
#     # #        #   #    # #      
 #####  ######   #    ####  #      
-->

# Environment Setup
```
It's nice having a step-by-step reference for setting up Anaconda environments.
Env setup can probably be copied over as-is; I use it fairly often.
I have Windows and MacOS instructions, I intend to add Linux instructions.
I also have instructions for JupyterHub with room to cover other tools' setup.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup on Windows
1. Regedit: `Computer\HKEY_CLASSES_ROOT\Directory\Background\shell\cmd`
    * Change reg key owner to Administrators and add Full Control in principals
    * Rename "HideBasedOnVelocityId" to "ShowBasedOnVelocityId"
    * Restart File Explorer in Task Manager and try Shift+Rightclick to open CMD
    * Undo Full Control change then undo owner change for reg key
1. Download and install Anaconda: https://www.anaconda.com/products/distribution
1. CMD: `setx PATH "%PATH%;%USERPROFILE%\AppData\Local\anaconda3"`
1. CMD: `setx PATH "%PATH%;%USERPROFILE%\AppData\Local\anaconda3\condabin"`
1. Start Menu > Manage App Execution Aliases > Uncheck python.exe, python3.exe
1. Restart CMD
1. Any: `conda config --append channels conda-forge`
1. Any: `conda create -n env1`, `conda env list`, `conda env remove -n ...`
1. Choose your preferred terminal and `conda init` it: `conda init cmd.exe`
    * Can auto-activate an env on terminal open via .bash_profile, .zshrc, etc
1. `conda activate env1`, `conda install pip`, `conda install ...`, `conda list`
    * `conda search xyz`, `conda install xyz=1.0.0`, `conda update xyz`
1. Install VSCode with defaults (consider "Open with Code" for context menus)
1. Any: try `code test.md`, if failed, VSCode command palette, "code", install
1. Install VSCode extensions for Python, Jupyter, etc
1. 80/120 char width code lines: Settings -> editor.rulers -> set to [80,120]
1. Create a Github/Gitlab/etc account if you don't have one (it's free!)
1. Download and install Git: https://git-scm.com/downloads
    * Keep Git Bash, add Git Bash profile to Windows Terminal, VSCode as editor
1. Git Bash: `git config --global user.name "git_username"`
1. Git Bash: `git config --global user.email "git_email`
1. (Option 1) Establish SSH auth for Gitlab or Github or other remote
    * (Github) https://github.com/settings/ssh/new (Other) add account SSH key
    * `ssh-keygen -t rsa -b 4096 -C "git_email_here"`
    * `cat ~/.ssh/id_rsa.pub | clip` which copies the SSH key to clipboard
    * Paste the key into the account SSH key box, title the key, save
    * Create a new test repository in the remote or select an existing one
    * Click the colored "Code" or "Clone" dropdown and copy the SSH link
        * SSH link, EX: git@github.com:JacobPaxton/data_science_notes.git
    * `git clone paste_link_here` to test the auth, should work
1. (Option 2) Establish HTTPS auth for Gitlab or Github or other remote
    * Create an access token for your account in the remote system
    * Use this token as your account password when prompted during Git actions
    * Create a new test repository in the remote or select an existing one
    * Click the colored "Code" or "Clone" dropdown and copy the HTTPS link
        * HTTPS link, EX: https://github.com/JacobPaxton/data_science_notes.git
    * `git clone paste_link_here` to test the auth, should work
### Windows Environment Launch Script
```batch
: CONDA ENV LAUNCH SCRIPT
cd %USERPROFILE%\zen
call activate mighty
%SystemRoot%\explorer.exe "%USERPROFILE%\zen"
code "" "%USERPROFILE%\zen" | exit
jupyter notebook
```

--------------------------------------------------------------------------------
<!-- Polished -->
### Environment Setup on MacOS
1. Open terminal
1. Create a Github/Gitlab/etc account if you don't have one (it's free!)
1. `git` (will install X-Code which contains Git)
1. `git config --global user.name "git_username_here"`
1. `git config --global user.email "git_email_here`
1. (Option 1) Establish SSH auth for Gitlab or Github or other remote
    * (Github) https://github.com/settings/ssh/new (Other) add account SSH key
    * `ssh-keygen -t rsa -b 4096 -C "git_email_here"`
    * `cat ~/.ssh/id_rsa.pub | pbcopy` which copies the SSH key to clipboard
    * Paste the key into the account SSH key box, title the key, save
    * Create a new test repository in the remote or select an existing one
    * Click the colored "Code" or "Clone" dropdown and copy the SSH link
        * SSH link, EX: git@github.com:JacobPaxton/data_science_notes.git
    * `git clone paste_link_here` to test the auth, should work
    * `echo "Host *\n  UseKeychain yes" >> ~/.ssh/config`
1. (Option 2) Establish HTTPS auth for Gitlab or Github or other remote
    * Create an access token for your account in the remote system
    * Use this token as your account password when prompted during Git actions
    * Create a new test repository in the remote or select an existing one
    * Click the colored "Code" or "Clone" dropdown and copy the HTTPS link
        * HTTPS link, EX: https://github.com/JacobPaxton/data_science_notes.git
    * `git clone paste_link_here` to test the auth, should work
1. Install VSCode with defaults
1. `code test.md`
    * If this fails, VSCode command palette, "code", install in PATH
1. Install VSCode extensions for Python, Jupyter, etc
1. Add 80/120 char vertical lines: Settings -> editor.rulers -> set to [80,120]
1. If required, download Homebrew
1. Download and install Anaconda: `brew install --cask anaconda`
1. `conda init`
1. `source ~/.zshrc`
1. Restart terminal
1. `conda config --append channels conda-forge`
1. `conda create -n env1`, `conda env list`, `conda env remove -n ...`
1. `echo "conda activate env1" >> ~/.zshrc`
    * This will auto-launch the conda env each time you open the terminal
1. `conda activate env1`, `conda install pip`, `conda install ...`, `conda list`
    * `conda search xyz`, `conda install xyz=1.0.0`, `conda update xyz`
### MacOS Environment Launch Script
```bash
# CONDA ENV LAUNCH SCRIPT
cd ~/zen
conda activate mighty
open ~/zen
code "" "~/zen" | exit
jupyter notebook
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup on Other Platforms
- Sometimes you are using a unique or proprietary system with its own steps
### JupyterHub
1. Log into JupyterHub UI with your account
1. Open a new terminal
1. `conda create -n env1 ipykernel`
1. `conda init bash`
1. `conda activate env1`
1. `conda install ...`
1. `python -m ipykernel install --user --name env1 --display-name "ENV1"`
1. Log out and log back in
1. Select the new Python kernel called "ENV1" and proceed as normal

[[Return to Top]]()







<!-- 
 #####          
#     # # ##### 
#       #   #   
#  #### #   #   
#     # #   #   
#     # #   #   
 #####  #   #   
-->

# Git
```
It's nice having a step-by-step reference for Git work.
There's a general workflow you should follow in order to work with Git.
When that workflow encounters problems, it's troubleshooting time!!
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Git Workflow
1. Make sure you've followed the environment setup steps to get Git working
1. Create the new project in Github/Gitlab or navigate to the existing repo
1. Click the colored "Code" or "Clone" dropdown and copy the SSH or HTTPS link
    * Depends on which auth method you went with in the environment setup steps
1. `git clone paste_link here`
1. `cd gitclone_created_folder`
1. `git branch -c mynewbranch`
1. `git branch mynewbranch`
1. Do the things with the files until you're ready to make a new commit
1. `git remote update`
1. Perform work in the branch: `git status`, `git add ...`, `git commit -m ...`
    * Add tag `git tag -a v1.0 -m "Version 1.0"` or remove tag `git tag -d v1.0`
    * Push with added tag (doesn't push by default): `git push remote v1.0`
1. (Option 1) push branch to remote: `git push origin mynewbranch:mynewbranch`
    * Can then submit a merge request in the Github/Gitlab/etc UI
1. (Option 2) merge branch locally into another branch like "main"
    * `git checkout main`, `git pull origin main`, `git merge mynewbranch`
    * Stage/commit/push the branch's changes to the main branch like normal
### After a Teammate Merges a Branch
1. If you accept these changes run `git pull`, this does not fix your local git
1. To delete the merged-in branch locally, run `git branch -d merged_branch`
1. To clean up the deletion you just performed, run `git fetch --prune`
1. Done! Merged-in branch has now been deleted locally.


--------------------------------------------------------------------------------
<!-- Polished -->
## Git Troubleshooting
- When the normal workflow encounters problems, there are ways to find solutions
### Resolving Merge Conflicts
1. Pull the Github repo down to a new folder using `git clone`
1. Copy the changed files / changes manually to the clone
1. Run `git add filename` `git commit -m "message"` `git push` as normal
1. Delete the old folder after successfully pushing your work
1. Move the new folder to where the old folder was- good as new!!
### Undoing Commits
1. Copy the commit hash you intend to go back to
    * You can simply use ^HEAD for previous commit, ^^HEAD for grandparent, etc
1. Decide if you want to keep post-commit changes (mixed) or fully reset (hard)
1. `git reset --mixed commit_hash_here`
1. (CAUTION) Apply the changes to remote: `git push origin branch_name --force`
    * This sets the remote repo's commit history to your local repo's commits
    * Maybe you just want to remove a tag from a push? `git push remote :v1.0`
### Git Command Trivia
- Compare any two files: `git diff --no-index file1.txt file2.txt`
- Forsee merge: `git diff --color-words receivingbranch..givingbranch file.txt`
- Compare remote vs local: `git diff @{u} --name-only`, `git diff @{u}`
- See commit history: `git log --oneline -5`, `git log --oneline -5 branch_name`
    * `git log --graph --all --oneline --decorate`
- Look at list of commit tags: `git tag -l`, `git tag -l "v1.*"`
- Stash: `git stash save "stash1"`, `git stash list`, `git stash pop stash@{1}`
    * `git stash apply stash@{3}`, `git stash drop stash@{3}`, `git stash clear`


[[Return to Top]]()







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
This should cover data types too like CSV, SAS, Parquet, and HDF5 files.
API notes should be structured in API request examples, with options explained.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## ***Datasets***
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
### Python-Importable Datasets
- `openml`: Many datasets; keyword search on https://www.openml.org and use IDs
- `tensorflow_datasets`: Many datasets; `mnist`, `imdb`, `boston_housing`
    * Or just use `tensorflow.keras.datasets` for various NN datasets
- `torchvision.datasets`: Image datasets; `MNIST`, `CIFAR10`, `FashionMNIST`
- `ucimlrepo.fetch_ucirepo`: UCI data; https://github.com/uci-ml-repo/ucimlrepo
- `sklearn.datasets`: Common datasets; `iris`, `digits`, `wine`
- `statsmodels.api`: Stats-related datasets; `adni`, `fair`, `flight`
- Other noteworthy imports for dataets: `pydataset`, `vega_datasets`

--------------------------------------------------------------------------------
<!-- Needs work -->
## ***Data Formats***
- CSV
- XLSX
- SAS
- Stata
- Parquet
- HDF5
- MATLAB

--------------------------------------------------------------------------------
<!-- Needs work -->
## ***REST APIs***
- Application Programming Interface: a way to interact with 'owned' data
    * There's rules and defined mathods for interacting with APIs
    * Scraping is still possible, but APIs may be better in some cases
- REST, RESTful: a standardized structure for URLs
- RESTful JSON API: URLs follow REST comms w/ server are in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests
- Endpoints are typically: "/api/v1/items/1" with ["next_page"]/["max_page"]

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
Capture is awesome and it's also a great way to express REGEX examples.
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## REGEX Metacharacters
- Language for parsing and slicing strings to capture substrings
- Uses a mixture of string literals and metacharacters for multiple objectives
- REGEX varies depending on the programming language you're using
    * REGEX by language: https://www.regular-expressions.info/tools.html
    * Test your REGEX in a specific language: https://regex101.com/
- Go deep into learning REGEX: http://www.rexegg.com/regex-disambiguation.html
- Flags: IGNORECASE, MULTILINE (run line-by-line), VERBOSE (ignore whitespace)
```re
| Zero or more (optional): *  | One or more: +        | Optional: ?            |
| Any character: .            | Choices: [a12qx]      | Anything-but: [^a12qx] |
| Alphanumeric: \w \W         | Whitespace: \s \S     | Digit: \d \D           |
| {5} Repeat exactly 5 times  | {3,6} Min 3, Max 6    | {3,} At least 3 times  |
| Anchor front: ^             | Anchor back: $        | Word boundary: \b      |
| Capture group: So (cool)!   | Match group: (?:yooo) |
| Case insensitive: (?i)(?-i) | Ignore spaces: (?x)   | Single line mode: (?s) |
```
### REGEX Metacharacter Explanation
- `\.`: a period; the backslash escapes the metacharacter so it is just "."
- `.+`: infinite amount of characters in sequence, but at least one: "?q9 -aAr!"
- `.+?`: same as above, but not greedy
- `.*`: infinite amount of characters in sequence, can be none (optional): "?q9"
- `.*?`: same as above, but not greedy
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
- `(?:ho)+`: match a repeating sequence of "ho", "hoho", "hohoho", "hohohoho"...

--------------------------------------------------------------------------------
<!-- Needs work -->
## REGEX Examples
- Maybe the best way to learn REGEX is to see a bunch examples of it in action!
### REGEX Capture Group Examples
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
    * "Hello, Sam!" -------------> [("Sam", "")] (two capture groups -> tuple)
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello!" ------------------> [("Hello", "")]
- `Hello,\s([a-zA-Z]+)(?:\s([a-zA-Z]+))*!` *Best solution of above*
    * Same as above example but with "Hello,\s" at the beginning
    * "Hello, Sam!" -------------> [("Sam", "")]
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello!" ------------------> []

[[Return to Top]]()







<!-- 
######                                   
#     # #   # ##### #    #  ####  #    # 
#     #  # #    #   #    # #    # ##   # 
######    #     #   ###### #    # # #  # 
#         #     #   #    # #    # #  # # 
#         #     #   #    # #    # #   ## 
#         #     #   #    #  ####  #    # 
                                         
#     #                   #####                                              
#  #  # ###### #####     #     #  ####  #####    ##   #####  # #    #  ####  
#  #  # #      #    #    #       #    # #    #  #  #  #    # # ##   # #    # 
#  #  # #####  #####      #####  #      #    # #    # #    # # # #  # #      
#  #  # #      #    #          # #      #####  ###### #####  # #  # # #  ### 
#  #  # #      #    #    #     # #    # #   #  #    # #      # #   ## #    # 
 ## ##  ###### #####      #####   ####  #    # #    # #      # #    #  ####  
-->

# Python Web Scraping
```
This is the rebel approach to data; not downloading it or registering for APIs.
Three main methods: pd.read_html, requests/beautifulsoup, selenium/beautifulsoup
- pd.read_html should be used to read HTML tables into dataframes
- requests should be used to pull specific files like images, video, etc
- selenium should be used to capture full page content
- beautifulsoup will parse HTML soup from requests, selenium, or otherwise
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Pandas Read-HTML
- Use this method if you're working with *HTML tables*; it's easy and effective
- Sample HTML tables (testing): https://www.w3schools.com/html/html_examples.asp
```python
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
- `df = pd.read_clipboard()` makes a dataframe from your clipboard's content

--------------------------------------------------------------------------------
<!-- Polished -->
## Requests
- Use this method if you need to scrape the contents of *static* HTML tags
- Requests grabs the page HTML, BeautifulSoup does the tag scraping
    * Note that any post-HTML loading (ex: Javascript) is not grabbed...
- To build a dataframe: use a sequence of `request.get` calls and build each row
- Beautiful Soup dive: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
```python
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
<!-- Polished -->
## Selenium
- Use this method if you need to scrape the contents of a *dynamic* page
- Selenium drives a browser that executes Javascript which affects page content
    * Running GET commands gets content before Javascript is run (before loaded)
    * Need to download the relevant webdriver like chromedriver.exe
- Selenium stores all loaded page elements, BeautifulSoup does the tag scraping
```python
from selenium import webdriver
from selenium.webdriver.common.by import By               # allow By.ID, etc
from selenium.webdriver.common.keys import Keys           # allow Keys.TAB, etc
from selenium.webdriver.support import expected_conditions as EC # detect tag
from selenium.webdriver.support.ui import WebDriverWait   # wait until tag loads
from selenium.webdriver.common.action_chains import ActionChains # script action
# BASIC PAGE PULL
chromepath = "C:\\Users\\CoolGuy\\chromedriver.exe"
chrome = webdriver.Chrome(chromepath)
url = "https://imgur.com"
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
```python
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

[[Return to Top]]()







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
```
Querying a database is just as important as establishing one.
Each database format has its own syntax/peculiarities which should be explained.
Query differences should be demo'd thoroughly on a common dataset, if possible.
The end state should be a dataframe that matches across query formats.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## SQL General
- SQL is maybe the most important programming language in the world
    * Decades-old, used everywhere, most systems support some SQL commands
- SQL databases are usually hosted on beefy systems; use SQL as much as possible
- SQL is five languages: Definition, Manipulation, Query, Control, Transaction
    * Data Definition Language (DDL): creating database objects (tables, users)
    * Data Manipulation Language (DML): database contents work ("CUD" of CRUD)
    * Data Query Language (DQL): "SELECT" statements (DML handles FROM/WHERE)
    * Data Control Language (DCL): controls account accesses
    * Data Transaction Language (DTL): governs transactions (multi-queries)
### SQL Tools
- SQLite: Lightweight SQL database; https://www.sqlite.org/
    * ALTER TABLE can't rename, remove, or constrain columns in a table    
    * `TRUNCATE t1;` is instead `DELETE FROM t1;` (can specify `WHERE`)
    * Use PRAGMA to find table indices
- PostgreSQL: Powerful SQL database; https://www.postgresql.org/
    * PGAdmin is awesome; view and manage everything, can generate your commands
    * `SHOW` is `\l`, `USE` is `psql -d mydb`, `DESCRIBE` is `\d` or `\dt`
    * Invoke a stored procedure: `CALL procedure_name(10000, 429);`
- Sequel ACE: Excellent GUI for SQL database reads and querying
- SQLAlchemy: Python library for interaction with SQL databases
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
<!-- Polished -->
## SQL Pull Records
```sql
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

--------------------------------------------------------------------------------
<!-- Polished -->
## SQL Calculate Aggregates
- `COUNT`, `MIN`, `MAX`, `RAND`
- `SUM`, `AVG`, `ABS`, `LOG`, `POW(x, y)`, `ROUND(n, decimal_places)`, `SQRT(n)`
```sql
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

--------------------------------------------------------------------------------
<!-- Polished -->
## SQL Subquerying
- Typically done with either an operator (`>`, `<`, `=`, etc), `IN`, or `EXISTS`
    * Consider these your three options for subqueries
```sql
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

--------------------------------------------------------------------------------
<!-- Polished -->
## SQL Temp Table Creation
```sql
USE employees;
CREATE TEMPORARY TABLE germain_1457.employees_with_departments AS
    SELECT first_name, last_name, departments.dept_name
    FROM employees
    JOIN dept_emp USING(emp_no)
    JOIN departments USING(dept_no);
```

[[Return to Top]]()







<!-- 
#     #                                                                          
##    #  ####  #####  #    #   ##   #      # ######   ##   ##### #  ####  #    #
# #   # #    # #    # ##  ##  #  #  #      #     #   #  #    #   # #    # ##   #
#  #  # #    # #    # # ## # #    # #      #    #   #    #   #   # #    # # #  #
#   # # #    # #####  #    # ###### #      #   #    ######   #   # #    # #  # #
#    ## #    # #   #  #    # #    # #      #  #     #    #   #   # #    # #   ##
#     #  ####  #    # #    # #    # ###### # ###### #    #   #   #  ####  #    #
-->

# Normalization
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
<!-- Polished -->
## Normalization Concepts
### Database Normal Forms
- Goal is to represent data in a non-redundant, clear, and simple architecture
- Zero Normal Form (0NF): Data has not been normalized
- First Normal Form (1NF): No duplicate rows/columns, one value per row
- Second Normal Form (2NF): No partial dependencies on any composite keys
- Third Normal Form (3NF): No multi-table (transitive) dependencies
- Boyce-Codd Normal Form (BCNF): User/State/City -> User/State, City/State
    * Typical stopping point in normalization for most database admins
- Fourth Normal Form (4NF): No list-like values (split to individual rows)
- Fifth Normal Form (5NF): Nothing useful can be gained from joining tables
### Data Content Normalization
- Goal is to express values in the correct format and drive analytic value
- Split a string field into multiple key-value pairs of various types
- Ensure integers are integers, floats are floats, strings are strings
- Can perform actions before ingest, during ingest, or after data is processed
    * Depends entirely on what system you're using and existing restrictions
    * Usually best to handle as much as possible during ingest (beefy systems)
- Best approach is to explore data, draft changes, move changes to proper system
    * Start with Python's `pandas` library, use a data subset if not enough RAM
    * Use `pandas` library's synergy for stats/viz/etc, identify changes needed
    * Model the changes in the proper system for compatibility/speed/simplicity
    * Test the changes before making any permanent changes for data surety
### Null Strategy
- Before thinking about null handling, consider the Minimum Viable Product (MVP)
    * Dropping columns with any nulls might be useful to get to MVP quickly
    * Can improve the approach post-MVP if time allows for it
- Check for nulls and consider whether to drop columns or impute values
    * Column-wise counts, class-wise null pattern hashing, etc
    * Highly-null columns might be worth dropping entirely
    * Highly-null rows might be worth dropping entirely
    * Sometimes can estimate the values for nulls, like measurements over time
    * Sometimes you can guess the value of nulls based on other columns' values
    * Domain expertise suffers from bias; consider handling first and evaluating
    * Python: can use `msno` library for null heatmaps, dendrograms, matrices
- Evaluate the effects of your chosen imputation method on value distributions
    * Python: can use `sklearn.impute` and `fancyimpute` (KNN, MICE) libraries

--------------------------------------------------------------------------------
<!-- Polished -->
## Normalization Drafting
- Subset the data if required and get it into a `pandas` DataFrame
- Initial values: `df.describe()`, `df.describe(exclude="number")`
- Initial duplicates: `df.duplicated(subset=["col1","col2",...], keep="first")`
- Initial nulls: `df.isna().sum()`, null pattern characterization (see below)
- Initial outliers: `df[df["num"] > 100]`, `df[df["string"].apply(len) > 100]`
- Logic to adjust field: `df["num_col"].apply(lambda x: x - 1)`
- Logic to explode field: `df["x"].apply(lambda x: pd.Series({"y":1,"z":2}))`
- Logic to combine fields: `df.apply(lambda row: row["a"] + row["b"], axis=1)`
- Logic to extract text via REGEX: `df["text"].str.extract("\w+\s(\w+)")`
- Logic to flag text: `df["text"].str.contains("hi|yo")`, `.startswith()`, ...
### Null Pattern Characterization
- Scenario: five data sources in a dataset, many nulls across several columns
- Approach: check each data source's nulls (group by)
- Method: Flag each null; subset on source; hash each row of flags; value counts
- Result: four sources are mostly one hash; one source is spread across hashes
- Findings: one data source is the cause of most of the nulls
- Recommendation: drop all rows from the one source; fix the data source's issue
```python
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
# PRINT PATTERN HASH ASSESSMENT RESULTS (INSIDE EXPANDABLE TEXT IN JUPYTER)
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

[[Return to Top]]()







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
<!-- Polished -->
## Data Reduction
### Feature Reduction
- Get rid of features that contain only one unique value
- Get rid of features that are duplicates or otherwise match other features
- Get rid of features that have nulls not worth handling (or drop rows)
    * Python: `df.dropna(axis=1, thresh=(len(df.columns)*0.9))`
- Get rid of features that strongly correlate with others (multicollinearity)
    * Variance Inflation Factor (VIF); features with >10 VIF should be dropped
- Select features using linear regression coefficients (furthest vals from zero)
- Select features using SelectKBest or Recursive Feature Engineering
- Can do feature reduction with LassoCV regularization (increases bias/underfit)
    * Pass `sum(lcv.coef_ != 0)` as n_features parameter for SelectKBest or RFE
- Get rid of features that have no analytic value (ex: observation identifiers)
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
- X-axis: Component Count
- Y-axis: Cumulative Explained Variance (as components increase, more explained)
- Only use PCA if need data reduction; component expression obfuscates insights
- Choose component # based on elbow method or a explained variance threshold

--------------------------------------------------------------------------------
<!-- Polished -->
## Model Training
### Encoding
- Change string values to one-hot representation, ex: `x="cat"` -> `is_cat=True`
    * Python: `pd.get_dummies(df[["col1","col2]], drop_first=True)`
- Change string values to ordinal values, ex: `cold, warm, hot` -> `0, 1, 2`
    * Python: `df["col3"].replace({"cold":0, "warm":1, "hot": 2})`
### Scaling
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
    * Same as StandardScaler but de-weighs outliers using IQR
- **QuantileTransformer**
    * Transform features into uniform or normal dist; de-weighs outliers
    * Get ECDF line -> discretize to uniform dist -> plot on dist
    * Complex; if you really want your data to be normal, then use this
- Not shown (yet): MaxAbsScaler, Normalizer
- Python: `from sklearn.preprocessing import RobustScaler`
### Resampling Classes for Model Training
- Classifiers have trouble modeling imbalanced-class datasets; so, resample!!
- Can oversample the minority class and undersample the majority class
    * AKA: Add artificial rows to smaller class, remove rows from larger class
    * This is only performed on the training split for model training
- Add rows with SMOTE (Synthetic Minority Oversampling TEchnique)
- Remove rows with Tomek Links
    * Delete from majority class the records that majority/minority overlap on
- Result is balanced classes in the training split, model may perform better
- Can do this in Python with SMOTETomek from imbalanced-learn library
```python
from imblearn.combine import SMOTETomek
def resampler(X_train, y_train):
    """ Use SMOTE+Tomek to eliminate class imbalances for train split """
    smtom = SMOTETomek(random_state=42)
    X_train_res, y_train_res = smtom.fit_resample(X_train, y_train)
    print("Before SMOTE+Tomek applied:", X_train.shape, y_train.shape)
    print("After SMOTE+Tomek applied:", X_train_res.shape, y_train_res.shape)
    return X_train_res, y_train_res    # return resampled train data
```

[[Return to Top]]()







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
<!-- Polished -->
## Clustering in General
- Cluster for Exploration: discover groupings in data in multi-dimensional space
- Cluster for Feature engineering: combine features into a brand new feature
- Cluster for Classification: predict if an observation belongs to a grouping
- Cluster for Anomaly detection: find datapoints outside of main clusters
- Cluster for Sub-modeling: subset data by cluster, train model on each subset
### Considerations
- Should only involve continuous features (don't include categorical features)
    * There's no such thing as numerical distance between "red" and "blue"
    * There's no such thing as numerical distance between "cold", "warm", "hot"
    * We should use category features to subset data then cluster inside subsets
- Requires careful decisions on how to handle outliers
    * Clustering with data that contains unaddressed outliers lowers performance
    * If goal is anomaly detection, keep outliers in the validation/test split
    * If goal is classification/regression, create pipeline to remove outliers
- Requires careful decisions on how to scale data
    * Scaling is practically required for distance-based clustering approaches
    * Some scaling approaches may be rendered ineffective if outliers are kept
    * Other scaling approaches account for outliers but may weaken prediction
        * Example: using RobustScaler when MinMaxScaler would've marked outliers
    * Scaling with RobustScaler is usually a safe option to scale with outliers
### Real-World Examples of Clustering
- Text: Document classification, summarization, topic modeling, recommendations
    * Hierarchical using Cosine Similarity
- Geographic: Distance from store, crime zones, housing prices
- Marketing: Customer segmentation, market research
- Anomaly Detection: Account takeover, security risk, fraud
- Image Processing: Radiology, security

--------------------------------------------------------------------------------
<!-- Polished -->
## Clustering Approaches
### t-SNE
- **Purely for visualization use (not modeling)**, helps show potential clusters
- Transforms multi-dimensional data into a 2D representation (easily plotted)
- Stochastically modifies the dataset to spread tight data, condense sparse data
    * Set hyperparameters for learning-rate, number of iterations, metric, etc
- Stochastic nature means unseen data will be changed differently than training
    * This is why t-SNE should not be used as a preprocessing step for modeling
- Python: `from sklearn.manifold import TSNE`
### KMeans
- Using euclidean distances (straight lines) to group points into n clusters
- ML plots centroids randomly, assigns nearest points, calcs inertia, moves plot
    * Inertia (one cluster): `sum([distance(xy,centroid)**2 for xy in cluster])`
    * Sum all cluster inertia values to get the total inertia metric for a model
- Cluster into target classes: choose cluster count matching target class count
    * Typical classification metrics apply to the result of this assignment
- Cluster into feature: try multiple cluster-count numbers, select the best one
    * Choose a range of cluster counts using domain knowledge, visualizations
    * Loop: Pick a cluster count, fit KMeans for it, calculate resulting inertia
    * After loop: Plot cluster-count selection (x-axis) versus inertia (y-axis)
    * Use elbow method to choose a balance of low-cluster-count and low-inertia
    * ANOVA test can check if clusters are statistically distinguishable
- Python: `from sklearn.cluster import KMeans`
### Hierarchical (Agglomerative)
- Group datapoints into clusters by plotting a dendrogram and choosing a cutoff
    * Dendrogram: represents distances between datapoints as vertical lines
    * Typical cutoff: draw horizontal line at base of longest-unmerged line
    * Intersections of cutoff line and vertical lines are the cluster result
- https://stackabuse.com/hierarchical-clustering-with-python-and-scikit-learn
    * Each record is a cluster; group clusters until only one cluster remains
    * Agglomerative moves closest two clusters into one cluster, repeatedly
    * This operation walks vertically; long-unmerged clusters become candidates
    * Draw horizontal line at base of longest-unmerged line, count intersections
    * Count of horizontal line's vertical intersections is the cluster count.
- Python: `from scipy.cluster.hierarchy import linkage, dendrogram, fcluster`
    * Linkage performs clustering, dendrogram visualizes it, fcluster is cutoff
    * For pipelining, use: `from sklearn.cluster import AgglomerativeClustering`
### DBSCAN
- Set a proximity on all datapoints, cluster the chain of overlapping proximity
- Excellent at mapping shapes in data; search "DBSCAN visualization" online
- Excellent at finding anomalies because non-overlapping points get reported
- Computationally-expensive compared to other clustering methods, but effective
- Python: `from sklearn.cluster import DBSCAN`
    * For anomalies, look for values assigned to cluster `-1`

[[Return to Top]]()







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
- Fuzzy matching: `thefuzz.process.extract("matchme", listlikehere, limit=None)`
    * Return list of match score tuples like: [(string1, score, rank), ...]
- NEED: Vectorized method for performing this cleaning work
- Add ngram compilation to this

--------------------------------------------------------------------------------
<!-- Needs work -->
## Normalizing String Features
1. Perform Unicode normalization with one of the following: NFD, NFC, NFKD, NFKC
1. Encode from normalized text into ASCII
1. Decode from ASCII into UTF-8
1. Remove special characters using REGEX: replace /[^a-z0-9'\s]/ with ""
1. Perform tokenization using a tokenizer
1. Delete stopwords (words that need to be deleted or that aren't useful)
1. Perform stemming or lemmatization to reduce word variations to their root
1. Rejoin the resulting roots into a single document and/or corpus (if required)
```python
import nltk
for dataset in ["stopwords","vader_lexicon","punkt","wordnet","omw-1.4"]:
    nltk.download(dataset)
def cleanup(doc, tokenizer, stopword_list, lemmatizer=None, stemmer=None):
    doc = doc.lower()
    doc = UNICODE.normalize('NFKD',doc).encode('ascii','ignore').decode('utf-8')
    doc = re.sub(r"[^a-z0-9'\s]","",doc)          # remove special characters
    words = tokenizer.tokenize(doc)               # tokenize words
    filtered = [word for word in words if word not in stopwords]
    if wnl is not None:  chopped = [wnl.lemmatize(word) for word in filtered]
    elif ps is not None: chopped = [ps.stem(word) for word in filtered]
    else:                chopped = filtered
    clean_text = " ".join(chopped)
    return clean_text
tokenizer = nltk.tokenize.TweetTokenizer()
stemmer = nltk.porter.PorterStemmer()
lemmatizer = nltk.stem.WordNetLemmatizer()
stopword_list = nltk.corpus.stopwords.words("english")
```

--------------------------------------------------------------------------------
<!-- Needs work -->
## Keywords and Sentiment
### Keyword Analysis
- Cool: https://github.com/amueller/word_cloud/blob/master/examples/parrot.py
```python
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
```python
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
```python
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
```python
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
```python
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