# <center><strong>Data Science Notes, v4</strong></center>

<!-- The common man keeps the world turning. -->
<!-- Use your skills to help these people!!! -->

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
I.    [Tools                           ](#tools)
1.    [Environment Setup               ](#environment-setup)
1.    [Jupyter Notebooks               ](#jupyter-notebooks)
1.    [Analyst Tools                   ](#analyst-tools)
1.    [Git Workflow                    ](#git-workflow)

II.   [Projects                        ](#projects)
1.    [Project Management              ](#project-management)
1.    [Project Frameworks              ](#project-frameworks)
1.    [Project Tools                   ](#project-tools)
1.    [Stakeholders                    ](#stakeholders)

III.  [Computer Science                ](#computer-science)
1.    [Data Structures                 ](#data-structures)
1.    [Search and Sort Algorithms      ](#search-and-sort-algorithms)

IV.   [Databases                       ](#databases)
1.    [Databasing Overview             ](#databasing-overview)
1.    [Database Documentation          ](#database-documentation)
1.    [Database Operations             ](#database-operations)
1.    [Relational Databases            ](#relational-databases)
1.    [Managing a SQL Database         ](#managing-a-sql-database)

V.    [Query                           ](#query)
1.    [SQL                             ](#sql)
1.    [Spark                           ](#spark)
1.    [Elastic Suite                   ](#elastic-suite)

VI.   [Acquire                         ](#acquire)
1.    [Dataset Sources                 ](#dataset-sources)
1.    [Regular Expressions             ](#regular-expressions)
1.    [Python Web Scraping             ](#python-web-scraping)
1.    [Data Structure Normalization    ](#data-structure-normalization)

VII.  [Explore                         ](#explore)
1.    [Probabilities & Distributions   ](#probabilities-and-distributions)
1.    [Hypothesis Testing              ](#hypothesis-testing)
1.    [Geospatial                      ](#geospatial-analysis)
1.    [Clustering                      ](#clustering)
1.    [Anomaly Detection               ](#anomaly-detection)
1.    [Natural Language Processing     ](#natural-language-processing)

VIII. [Model                           ](#model)
1.    [Feature Reduction               ](#feature-reduction)
1.    [Model Training                  ](#model-training)
1.    [Classification                  ](#classification)
1.    [Regression                      ](#regression)
1.    [Time Series                     ](#time-series-ts)
1.    [Neural Networks                 ](#neural-networks-nn)
1.    [Reinforcement Learning          ](#reinforcement-learning-rl)

IX.   [Deploy                          ](#deploy)
1.    [Exports & Pipelines             ](#exports-and-pipelines)
1.    [Containers                      ](#containers)
1.    [Local Deployment                ](#local-deployment)
1.    [Scalable Deployment             ](#scalable-deployment)

X.    [Generate                        ](#generate)
1.    [Generative AI Resources         ](#generative-ai-resources)
1.    [Large Language Models           ](#large-language-models-llms)
1.    [Retrieval Augmented Generation  ](#retrieval-augmented-generation-rag)
1.    [Image Generation                ](#image-generation)
1.    [Audio Generation                ](#audio-generation)
1.    [Video Generation                ](#video-generation)

<br>

<br>







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
                    ####### ####### ####### #        #####  
                       #    #     # #     # #       #     # 
                       #    #     # #     # #       #       
                       #    #     # #     # #        #####  
                       #    #     # #     # #             # 
                       #    #     # #     # #       #     # 
                       #    ####### ####### #######  #####  
                                        
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# TOOLS


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

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup
- Python is managed by "pip" (PyPi), and optionally Anaconda, Mamba, VENV, etc
### Environment Setup on Windows
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
```batch
: CONDA ENV LAUNCH SCRIPT
cd %USERPROFILE%\zen
call activate mighty
%SystemRoot%\explorer.exe "%USERPROFILE%\zen"
code "" "%USERPROFILE%\zen" | exit
jupyter notebook
```
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
```bash
# CONDA ENV LAUNCH SCRIPT
cd ~/zen
conda activate mighty
open ~/zen
code "" "~/zen" | exit
jupyter notebook
```
### Environment Setup on JupyterHub
1. Log into JupyterHub UI with your account
1. Open a new terminal
1. `conda create -n env1 ipykernel`
1. `conda init bash`
1. `conda activate env1`
1. `conda install ...`
1. `python -m ipykernel install --user --name env1 --display-name "ENV1"`
1. Log out and log back in
1. Select the new Python kernel called "ENV1" and proceed as normal

[[Return to Top]](#table-of-contents)







<!--
      #                                         
      # #    # #####  #   # ##### ###### #####  
      # #    # #    #  # #    #   #      #    # 
      # #    # #    #   #     #   #####  #    # 
#     # #    # #####    #     #   #      #####  
#     # #    # #        #     #   #      #   #  
 #####   ####  #        #     #   ###### #    # 
                                                
#     #                                                        
##    #  ####  ##### ###### #####   ####   ####  #    #  ####  
# #   # #    #   #   #      #    # #    # #    # #   #  #      
#  #  # #    #   #   #####  #####  #    # #    # ####    ####  
#   # # #    #   #   #      #    # #    # #    # #  #        # 
#    ## #    #   #   #      #    # #    # #    # #   #  #    # 
#     #  ####    #   ###### #####   ####   ####  #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Jupyter Notebooks
### Notebook Niceties
- Command mode: dd for cell deletion, y for code cell, m for markdown cell
- TAB for autocomplete, Shift TAB for full context at cursor location
- Option Shift - to split cell into two cells at cursor
- Option Dragclick to drag multi-line cursor
- Run shell commands with `!` like this: `!echo "hi"`
    * I think the commands depend on what terminal program is running Jupyter
- Run ipython commands with `%` like this: `%ls`
- MD LaTeX: `$H_0$`, see: https://www.caam.rice.edu/~heinken/latex/symbols.pdf
- PLT LaTeX: https://matplotlib.org/stable/tutorials/text/mathtext.html
### iPyWidgets
```python
from IPython.display import display
import ipywidgets
from datetime import date
mydate = date(2023,1,1)
dateobject = ipywidgets.widgets.DatePicker(value=mydate)
display(dateobject)
# RUNNING NEXT CODE UPDATES ALL DISPLAYED OBJECTS IN REAL TIME
dateobject.value = date(2023,5,20)
```
### Python Chart Choices
- Inspiration: https://www.python-graph-gallery.com/all-charts
- Custom: https://matplotlib.org/stable/tutorials/introductory/customizing.html
    * Check out lines_bars_and_markers/bar_label_demo.html (one chart guide)
    * Check out lines_bars_and_markers/categorical_variables.html (multi-chart)
- Cheatsheet: "Python Seaborn Cheat Sheet PDF" on Google
- Use colorblind palettes as often as possible
- `import matplotlib.pyplot as plt, seaborn as sns, plotly.express as px`
- Figure-level plots for multiple sub-charts; axis-level plot for a single chart
- Continuous x-axis: `displot` (hist, kde, ecdf) or `relplot` (line, scatter)
    * ECDF is awesome! Plot it overlapping a histogram for very cool plots
- Categorical x-axis: `catplot` w/ `kind`: count,bar,box,violin,swarm,strip,more
- `pairplot`, `heatmap`, `regplot`(scatter+reg), `jointplot`(scatter+edge hists)
    * `pairplot` charts can be accessed/modified with `.axes`
    * `regplot` uses `line_kws={'color':'red'}`
- Normality: `statsmodels.api.qqplot`; x: theoretical quants, y: observed quants
### Python Pandas Dataframe Styling
```python
# STYLE DF: FORMAT/BAR NUMBERS, COLOR LEVELS, FORMAT STRINGS; PRINT TO HTML FILE
styler = df.head(10).style\
    .format({"money":"${:,.0f}", "category":str.upper})\
    .hide(axis="index")\
    .background_gradient(cmap="Oranges")\
    .highlight_max(subset="money", color="green")\
    .highlight_min(subset="money", color="red")\
    .bar(subset="money", color="#1f77b4")\
    .export()
html = df.head(10).style.use(styler).to_html()
display(HTML(html))
```

[[Return to Top]](#table-of-contents)







<!--
   #                                             #######                        
  # #   #    #   ##   #    #   #  ####  #####       #     ###   ###  #     #### 
 #   #  ##   #  #  #  #     # #  #        #         #    #   # #   # #    #     
#     # # #  # #    # #      #    ####    #         #    #   # #   # #     #### 
####### #  # # ###### #      #        #   #         #    #   # #   # #         #
#     # #   ## #    # #      #   #    #   #         #    #   # #   # #    #    #
#     # #    # #    # ####   #    ####    #         #     ###   ###  ####  #### 
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Analyst Tools
- Excel and Google Sheets: fast initial exploration
- PowerBI: if your company uses it already, use Jupyter with `powerbiclient`
- Tableau: if your company uses it already, or, if you have license/experience
- ArcGIS: geospatial analysis and third-party data enrichment
### Excel
- Absolute reference using hold_clickdrag + fn + F4
- Doubleclick bottomright of function cell to affect all rows in selected col(s)
```excel
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
### PowerBI
- 
### Tableau
- Excellent software for interactive visualizations and dashboards
- Regular Tableau requires a license, can save locally, autosaves enabled
- Tableau Public is free, but all work gets posted to https://public.tableau.com
    * Faith Kane: https://public.tableau.com/app/profile/faith.kane
    * Sean Oslin: https://public.tableau.com/app/profile/sean.oslin
    * The Superstore CSV is popular to learn and demo Tableau
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
### ArcGIS
- 

[[Return to Top]](#table-of-contents)







<!-- 
 #####             #     #                                                  
#     # # #####    #  #  #  ####  #####  #    # ###### #       ####  #    # 
#       #   #      #  #  # #    # #    # #   #  #      #      #    # #    # 
#  #### #   #      #  #  # #    # #    # ####   #####  #      #    # #    # 
#     # #   #      #  #  # #    # #####  #  #   #      #      #    # # ## # 
#     # #   #      #  #  # #    # #   #  #   #  #      #      #    # ##  ## 
 #####  #   #       ## ##   ####  #    # #    # #      ######  ####  #    # 
-->

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
### Git Troubleshooting
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
### Gitlab Setup
- Milestones: phases of project
- Labels: components of project
- Issues: work breakdown of components, can be tied to Milestones/Labels
    * Build in CSV; "Title"/"Description" cols, use 2 Alt+Enters to do a newline

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
        ######  ######  #######       # #######  #####  #######  #####  
        #     # #     # #     #       # #       #     #    #    #     # 
        #     # #     # #     #       # #       #          #    #       
        ######  ######  #     #       # #####   #          #     #####  
        #       #   #   #     # #     # #       #          #          # 
        #       #    #  #     # #     # #       #     #    #    #     # 
        #       #     # #######  #####  #######  #####     #     #####  
                                
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# PROJECTS


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

--------------------------------------------------------------------------------
<!-- Polished -->
## Project Management
- Project Sponsor: executive or senior that authorizes and champions the project
- Project Manager (PM): executes the project, reports to all stakeholders
### Project Initiation
- Projects are initiated and authorized with approval of the Project Charter
- Project Sponsor writes (and signs) charter in order to start business project
- Charter defines project objectives, high-level requirements, risk, assumptions
    * Also specifies stakeholders, timeline, budget, milestones, deliverables
- Signing the charter authorizes the project and use of organization resources
### Project Planning
- After project is authorized, next step is building the Project Management Plan
    * Contains all project planning documents (subsidiary plans)
- Scope/Schedule/Cost Management Plans: baselines, monitoring, change control
    * Work Breakdown Structure (WBS) decomposes work into hierarchy of tasks
    * Critical Path Method (CPM) sets core and optional components for timelines
    * Gantt charts visualize timeline (tasks/milestones vs time with progress)
    * Burn-down charts track progress and remaining tasks, helps control scope
    * Change management plan to define how to make changes to baselines
- Quality Management Plan: objectives, standards, control, assurance
- Communications Management Plan: who/how/what/frequency to inform stakeholders
- Risk Management Plan: identification, assessment, strategies, monitor/control
    * Avoidance: eliminate (bad/likely) risk or protect project from impacts
    * Mitigation: reduce (bad/likely) risk to acceptable level
    * Transfer: use insurance/outsourcing/contracts to pass (bad/likely) risk
    * Acceptance: don't do anything to proactively avoid/mitigate/transfer risk
    * Exploit: realize opportunity to its fullest potential (ex: discounts)
    * Enhance: increase probability/impact of opportunity
    * Share: give well-positioned third party the opportunity to max-capitalize
    * Contingency Planning: make plan for if risk occurs
- Procurement Management Plan: process, timelines, contracts, vendors, strategy
- Stakeholder Engagement Plan: who, how to engage, how to manage expectations
- Human Resource Management Plan: select members, define roles/responsibilities
    * Includes training/development strategies and team performance management
- Integration Management Plan: make sure all project components work together
### Project Execution
- Once the Project Management Plan is complete, kick off project, execute plan
- Assigned roles perform assigned tasks and deliver expected deliverables
- Performance, quality, scope, time, cost, and risk is monitored/reported out
- Issues that come up are resolved using planned mechanisms and/or reported
- Changes are coordinated/made as necessary in order to handle encountered risks
### Project Completion
- In some projects, the delivery may be completed and entirely handed off
    * Release project resources back to the organization and celebrate!
- In some projects, the delivery meets objectives and enters a support phase
- In some projects, the delivery is followed by another round of the project
- In each case, capture lessons learned and other valuable insights

[[Return to Top]](#table-of-contents)







<!-- 
######                                           
#     # #####   ####       # ######  ####  ##### 
#     # #    # #    #      # #      #    #   #   
######  #    # #    #      # #####  #        #   
#       #####  #    #      # #      #        #   
#       #   #  #    # #    # #      #    #   #   
#       #    #  ####   ####  ######  ####    #   
                                                 
#######                                                                
#       #####    ##   #    # ###### #    #  ####  #####  #    #  ####  
#       #    #  #  #  ##  ## #      #    # #    # #    # #   #  #      
#####   #    # #    # # ## # #####  #    # #    # #    # ####    ####  
#       #####  ###### #    # #      # ## # #    # #####  #  #        # 
#       #   #  #    # #    # #      ##  ## #    # #   #  #   #  #    # 
#       #    # #    # #    # ###### #    #  ####  #    # #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Project Frameworks
- Many frameworks with differing popularity
- Typically an organization will prefer one and its employees are made to use it
- Rarely, the opportunity to pick a framework will arise; choose carefully!
### Agile
- A template usually flavored into specific frameworks
    * Scrum, Kanban, and Extreme Programming are common Agile flavors
- Focused on development "sprints" lasting a few weeks where you iterate quickly
- Each sprint builds on the previous sprint with more features and development
- Flexible for new requirements/issues, but may be hard to say it's finished
### Scrum
- Good for fast-paced unpredictable environments with high amounts of feedback
- Has very specific roles
    * Product Owner: manage the Product Backlog, coordinate with stakeholders
    * Scrum Master: make sure team follows Scrum, remove blockers/distractions
    * Development Team: actually does the work
    * Stakeholders: customers, users, and other relevant parties
- Has very specific events
    * Sprint Planning: plan the next sprint, set the Sprint Goal, Sprint Backlog
    * Daily Scrum: quickly explain what work was completed and is up next
    * Sprint Review: demonstrate the sprint's completed work to stakeholders
    * Sprint Retrospective: analyze how the sprint went, improve processes
- Development Team self-organizes to take on items from Sprint Backlog
- Sprints last a set amount of time, typically two weeks, sometimes four or one
### Kanban
- Good for evolving-requirements projects and operations teams (visual tickets)
- Visualize the workflow; limit WIP; focus continuous delivery/improvement
- Uses a Kanban board with swim lanes marking tasks into phases of progress
- Can be merged with Scrum ("Scrumban") to help manage the flow of work (visual)
### Extreme Programming (XP)
- Good where developers are directly interacting/sitting with customers
- Pair programming; continuous integration; test-driven development; refactoring
- Follows Agile principles
### Lean
- Good for money/time efficiency, useful in manufacturing, customer relations
- Focused on minimizing waste, being efficient, streamlining processes
### Six Sigma
- Good for quality improvement projects (processes, products, etc)
- Define, Measure, Analyze, Improve, Control (or Design, Verify)
- Sometimes combined with Lean ("Lean Six Sigma") to control money/time/quality
### Scaled Agile Framework (SAFe)
- Good for large organizations that want to manage complex projects across teams
- Agile Release Trains (ARTs); Program Increments (PIs); coord across teams
- Complex/difficult and should only be used in orgs experienced with Agile
### PMBOK (Project Management Body of Knowledge)
- Good for large scale projects requiring detailed planning and documentation
- Uses the Project Charter, Project Management Plan, etc- all the best practices
### Waterfall
- Good for physical projects like construction of buildings/infrastructure
- Has specific phases that don't overlap and can't be reversed
    * Requirements Gathering
    * System Design
    * Implementation
    * Testing
    * Deployment
    * Maintenance
- Sometimes used in software development where delivery has complex dependencies
### PRINCE2 (Projects IN Controlled Environments)
- Good for large complex projects requiring a structured approach
- Has clear process and roles but is very bureaucratic/rigid (not dynamic)
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
######                                           #######                        
#     # #####   ###       # #####  ####  #####      #     ###   ###  #     #### 
#     # #    # #   #      # #     #    #   #        #    #   # #   # #    #     
######  #    # #   #      # ####  #        #        #    #   # #   # #     #### 
#       #####  #   #      # #     #        #        #    #   # #   # #         #
#       #   #  #   # #    # #     #    #   #        #    #   # #   # #    #    #
#       #    #  ###   ####  #####  ####    #        #     ###   ###  ####  #### 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Project Tools
### Tool Selection
- Speed and flexibility: lightweight cloud-based tools like Trello, Asana
- Enterprise support: big tech tools like MS Projects or Oracle Primavera
- User experience: consider doing user testing/piloting before going full scale
    * Users might hate a tool, this gives them a chance to choose a good tool
- Integrate with existing tech stack: reduce friction/silos/sprawl
- Cost-Benefit: hurt once by purchasing the right tool at the get-go
    * Scaling, automation, other integrations, communication/coordination, etc
- Scale/flex with org growth: avoid downroad refactor by good upfront buy
- Security and Compliance: handling sensitive data, prevent leaks, GDPR, HIPAA
### Tool Integration
- Central data/docs hub that integrates with other project management platforms
- Task/project management that integrates with comm platforms, dev repos, etc
- Comm/collab platforms that integrates with project management, can notify
- Reports/dashboarding to aggregate insights from project management platform
- Automation and workflow orchestration to propagate actions through everything
- Risk/issue tracking that can alert out into other platforms, perform actions
### Best Practices for Integration
- Use APIs/automation where possible to automatically sync/trigger across tools
- Represent information consistently across platforms (ex: name of task status)
- Review tools every once in awhile to see if they've become outdated/broken
- Train people to use the tools effectively and maximize their featureset

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                                          
#     # #####   ##   #    # ##### #   #  ####  #     #####  ###### #####   #### 
#         #    #  #  #   #  #     #   # #    # #     #    # #      #    # #     
 #####    #   #    # ####   ####  ##### #    # #     #    # #####  #    #  #### 
      #   #   ###### #  #   #     #   # #    # #     #    # #      #####       #
#     #   #   #    # #   #  #     #   # #    # #     #    # #      #   #  #    #
 #####    #   #    # #    # ##### #   #  ####  ##### #####  ###### #    #  #### 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Stakeholders
- The people involved in or impacted by projects
- Various levels of technical expertise, domain knowledge, interest
    * Stakeholders want just a report or dashboard: give them it
    * Stakeholders want the end product and a demo: give them it
    * Stakeholders want the models and technical details: give them it
    * Stakeholders want everything: give them everything
- A one-page writeup/summary is *always* welcome for any project or initiative
- Consider moving code/technicals out of a report and printing result to PDF
### Story Design
- Prepare to Create; Talk and Listen; Sketch; Prototype
    * Clear physical/mental room; Know your data; Understand audience, Big Idea
    * Use everything so far to sketch out your ideas (brainstorm)
    * Refine the sketches into presentation material
- Use a narrative approach that follows your goal and respects your audience
    * Determine which framework to use (persuasive, man-in-hole, story)
    * Determine context, challenge, and solution
- Put valuable work into visualizations, tables, etc as much as possible
    * A non-correlation can be more important than a correlation
- Tuck supporting information into appendices to reduce presentation complexity
    * This includes expert-level visualizations, and, statistical tests!
- Remove redundant/unimportant information to reduce story complexity
### Storytelling
- The story should be clear from the beginning, throughout, and at the end
- Start with answering the "why" directly and up front and keep answer simple
- Keep visualizations simple in the main presentation and avoid text walls
    * Use highlighting, arrows, etc to point out the key aspects of vizs
- Speak to understoods like business goals, responsible stakeholders, etc
    * Give credit to people and teams and technologies and data sources
- Present to yourself/team in a prebrief to make sure gaps get covered
- Use "we'll talk about that" as a way to hook people with questions
- Take down questions, regardless if they were answered, for postmortem
    * Correct/clarify presentation to address the question up front

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
              #####  ####### #     # ######   #####   #####  ### 
             #     # #     # ##   ## #     # #     # #     #  #  
             #       #     # # # # # #     # #       #        #  
             #       #     # #  #  # ######   #####  #        #  
             #       #     # #     # #             # #        #  
             #     # #     # #     # #       #     # #     #  #  
              #####  ####### #     # #        #####   #####  ### 
                                                    
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# COMPUTER SCIENCE


<!-- 
######                      
#     #   ##   #####   ##   
#     #  #  #    #    #  #  
#     # #    #   #   #    # 
#     # ######   #   ###### 
#     # #    #   #   #    # 
######  #    #   #   #    # 
                            
 #####                                                               
#     # ##### #####  #    #  ####  ##### #    # #####  ######  ####  
#         #   #    # #    # #    #   #   #    # #    # #      #      
 #####    #   #    # #    # #        #   #    # #    # #####   ####  
      #   #   #####  #    # #        #   #    # #####  #           # 
#     #   #   #   #  #    # #    #   #   #    # #   #  #      #    # 
 #####    #   #    #  ####   ####    #    ####  #    # ######  ####  
-->


--------------------------------------------------------------------------------
<!-- Polished -->
## Data Structures
- Linear data structures: Array, Stack, Queue, Linked list, Hash table
- Non-linear data structures: Class, Graph, Tree, Heap
### Linked List
- Linear data structure
- Many element+pointer combos where a combo's pointers reference prev/next combo
- Excellent at handling problemsets involving sorting long arrays
    * Just update two neighbor combos' pointers; no need to update entire array
- Compiled languages ex: C++ incorporate pointers natively, easy linked list
- Interpreted languages ex: Python don't incorporate pointers, avoid linked list
- The element+pointer combo (one item in the linked list) is a "head"
- The "head" is split into the data (a la payload) and the pointer(s)
- A linked list's pointers can be simply-linked, doubly-linked, and/or circular
    * Singly: link next, doubly: link next & prev, circular: last link to first
- Because there's no structure, a linked list is usually deleted by a function
### Hash Table
- A mapping of keys (hashes) to values
- Uses hashing function(s) to create the key for the value, ex: modulo
- Hashing functions range from very simple/DIY to highly complex/academic
- The key (the hashed value) is used as the index for the value
    * No collisions: "perfect hash function" (not really useful)
    * Two different values with same hashed key: a "collision"
- Collision resolution approach: store many values in one bucket, in array
    * This is one approach to handling collisions; it's called "chaining"
- Another approach: "Open addressing"/"Linear probing"; use next open bucket
    * These buckets use "empty since start" and "empty after removal" flags
    * Reason-why-empty flags are important for how the algorithm "walks" buckets
    * Finding an empty-since-start flag during a removal walk: done
    * Finding an empty-after-removal flag during a removal walk: keep going
- Another approach: "Quadratic probing"; if collision, use function to find spot
    * Function: `(hash_value + (c1 * i) + (c2 * i^2)) % table_size`
        * "Double hashing": `(hash1 + (hash2 * i)) % table_size`, two hashes!!
    * `i` is increased by 1 after each attempt; increasing/trying `i`: "probing"
    * Uses same empty-since-start and empty-after-removal flags as before
    * Table size of 16: hash value is `16 % 16 = 0`, try to place value at 0
    * Collision at 0: `(0 + (1 * 1) + (1 * 1)) % 16 = 2`, try placing at 2
    * Collision at 2: `(0 + (1 * 2) + (1 * 4)) % 16 = 6`, try placing at 6
    * Collision at 6: `(0 + (1 * 3) + (1 * 9)) % 16 = 12`, try placing at 12
    * Collision at 12: `(0 + (1 * 4) + (1 * 16)) % 16 = 4`, try placing at 4
    * Collision at 4: `(0 + (1 * 5) + (1 * 25)) % 16 = 14`, try placing at 14
- Buckets are fast!! Much faster to find values this way
    * No buckets: find the 3/8" wrench in a *pile* of wrenches, hammers, drills
    * Buckets: find the 3/8" wrench in the wrench bucket, ignoring other buckets
- Finding the value involves: hashing it -> going to the matching hash (bucket)
- Buckets are implemented efficiently via ["linked lists"](#linked-list)
    * Each bucket contains a linked list; linked lists have speedy appends/sorts
    * Create a linked list for each bucket, then append nodes to it (can sort!!)
#### Hash Functions
- Hash key: the parameter passed to a hash function, determines bucket choice
- Hash function: computes the bucket containing the row from the hash key
- Dynamic hash function: hash function but doesn't let buckets get too deep
- Modulo: 
    1. Convert the hash key by interpreting the key's bits as an integer value.
    2. Divide the integer by the number of buckets.
    3. Interpret the division remainder as the bucket number.
    4. Convert bucket number to physical address of the block that has the row.
- Mid-square hash:
    1. Square the (numeric) key
    2. Extracts R digits from the result's middle (R=2 for 205936: 59)
        * This is done using substrings when the key is variable-size
    3. Calculate `extracted_digits % table_size`
    * Note: For N buckets, this must be true: `R >= log(N)` to index all buckets
    * Note: "Mid-square hash base-2" uses `R >= log-base-2(N)` instead
        * Base-2 only requires a few shift and bitwise AND operations (faster!!)
- Multiplicative string hash:
    1. Start with initial value (academic value used is 5381)
    2. Loop each character in str: 
        * `new_value = (previous_value * multiplier) + ascii_of_current_char`
        * Academic multiplier value is 33 (performant??........)
    3. Calculate `final_value % 1000`
### Hash Tables and Linked Lists
- Hash tables are fast... especially with linked lists
- Each hash "bucket" contains a linked list
- Linked lists are appended to / sorted extremely quickly
- p1 EX: Buckets are [0,1,2,...] based on the alphabet (a = 0, b = 1, ...)
- p2 EX: Choose the bucket you know the value to be in ("a" are in bucket 0)
- p3 EX: `a[0] = ("A1", n1)`, `n1 = ("A2", n2)` --- `x[1] = ("B1", n3)`, ...
### Class
- The blueprints of an object
- Contains attributes (descriptors) and methods (functions)
- Blueprint is outlined in a class definition; classes are typically capitalized
- Is only a blueprint until the program "instantiates" it (creates an object)
- Instantiation creates the object and sets the default attributes and methods
- Defaults are set by the class's "constructor" on instantiation
- After creation, the object is modified using "attribute reference operators"
    * In Python, object modification looks like this: `book1.title = "Walden"`
- An object is highly flexible and its methods can instantiate other objects
- An object can also inherit attributes from another class
- A "derived class" inherits attributes from a "base class"
### Binary Tree
- Similar to linked list, but one node can point to TWO nodes (binary)
- "Parent" and "child" nodes here, with "root" node as topmost node in tree
    * Left child is less than parent; right child is greater than parent
    * Left child itself and its children are less than its parent
    * Right child itself and its children are greater than its parent
- Leaf: node with no children
- Internal node: node with one child
- Edge: Link between parent and child
- Depth: Edge count to root
- Level: Grouping of nodes all at a certain depth
- Height: Largest depth in tree
- Full tree: All nodes have zero or two children
- Complete tree: All levels "full" except maybe the last level
    * Last level must at least be fully-shifted left
- Perfect tree: All internal nodes have two children, all leaf nodes same level
- Printing a binary tree: descend left to end, print from end in left-cur-right
- Adding to a binary tree: navigate to right spot, do linked list things
- Deleting nodes: find next-highest node, replace node to be deleted, delete
### Heap
- Like a binary tree BUT parent node has larger or smaller value than its childs
    * It can be *any* tree, but it is typically a "complete" binary tree
    * Parent larger than childs: "max heap"; smaller: "min-heap"
- Typically stored using arrays (not pointers like a binary tree
    * [root, left, right, leftleft, leftright, rightleft, ...]
    * Percolate: append to array, swap index with parent if needed
    * Find parent's index for percolation: `parent_i = floor((i - 1) / 2)`
    * Child's index for percolation: `i = 2 * i + 1` or `i = 2 * i + 2`
- Turn array into a heap: "heapify"
    * Start with "internal node" having largest index (last internal node)
        * Largest node's index: `i = floor(len(array) / 2) - 1`
    * Swap with largest child if a child is larger
        * After, if child node is an internal node, repeat evaluation on it
    * Move to next internal node (the one having next-largest index)
    * Follow same swap procedure; swap with largest child if a child is larger
    * Continue evaluating internal nodes in this way
    * Finally, evaluate the root in this way; done!
#### Max Heap
- Insertion: maintain "complete" tree, add node at bottom, "percolate" upward
    * EX: value of 99 added to last layer, swap with parent having key of 21, ..
- Removal: heaps work with the largest value, so ROOT is the only node removed
    * Replace root with the last node in last layer (maintain complete tree)
    * Swap the rulebreaking root with its greatest child until rules met
#### Min Heap
- Same exact thing as max heap but parent is smaller than children

[[Return to Top]](#table-of-contents)







<!-- 
 ####                                        ##        ####                     
#    # #####   ##   #####   ####  #   #     #  #      #    #  ####  #####  #####
#      #      #  #  #    # #    # #   #      ##       #      #    # #    #   #  
 ####  ####  #    # #    # #      #####     ###        ####  #    # #    #   #  
     # #     ###### #####  #      #   #    #   # #         # #    # #####    #  
#    # #     #    # #   #  #    # #   #    #    #     #    # #    # #   #    #  
 ####  ##### #    # #    #  ####  #   #     ###  #     ####   ####  #    #   #  
                                                                            
   #                                                             
  # #   #       ####   ####  #####  # ##### #    # #    #  ####  
 #   #  #      #    # #    # #    # #   #   #    # ##  ## #      
#     # #      #      #    # #    # #   #   ###### # ## #  ####  
####### #      #  ### #    # #####  #   #   #    # #    #      # 
#     # #      #    # #    # #   #  #   #   #    # #    # #    # 
#     # ######  ####   ####  #    # #   #   #    # #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Search and Sort Algorithms
- Efficient computing can make or break the user experience
- Speedy searches and sorts can make a world of difference across all processing
    * Sorting is crucial for all storytelling; max/min values, large/small, etc
    * Searching is crucial for all analysis; find the data you need
    * Simple changes to slow code can speed it up immensely
- Knowing where algorithms are great / are useless informs excellent code design
    - Goal: decrease "computational complexity"; lower runtime + memory use
    - Goal: decrease "space complexity" lower memory use by itself
    - Goal: decrease "auxiliary space complexity"; lower data overhead
- Knowing where to be perfect / where to cut corners can secure victory
    * Heuristic algorithms: imperfect but good enough, much faster than perfect
- Runtime complexity and space complexity help distinguish algorithm performance
    * Runtime (in seconds) is different from runtime complexity (Big O)
### Runtime Complexity
- Runtime complexity: where input values change, how does program change?
    * Uses "Big O Notation", ex: `O(n)`, `O(1)`, `O(n^2)`
- Computation count is constant regardless of input values: `O(1)`
- Each computation divides & conquers the input values: `O(logn)`
    * "Time increases linearly while n increases exponentially"
    * EX: 1min does 10 values, 2min does 20 values, 3min does 40 values, ...
- Each new value requires a new calculation: `O(n)`
- Each new value requires a new calculation *and* divide & conquer: `O(n*logn)`
- Each new value requires a new calculation on *all other values*: `(n^2)`
- The number of total values is used for the loop count on all values: `O(n^n)`
### Recursion
- Function calling itself until goal achieved / no more work remains
    * Special term: "Base case", what is executed to end recursion
- Especially good at all-possible-outcomes problems
    * EX: Scramble words using string indexing/splits recursively
### Heuristic Algorithms
- Heuristic algorithms don't perfectly solve problems but are FAST
    * Being perfect and slow is sometimes necessary (sorting)
    * Being imperfect and speedy is sometimes preferred (solving problems)
    * Being imperfect and speedy is sometimes necessary (rounding decimals)
    * Accuracy requirements steer heuristic choices
- Knapsack problem is great example of where heuristic algorithms are useful
    * Goal: fit max amount of defined-size objects into bag
    * Perfect tries all possible combinations to get max (very slow, perfect)
    * Heuristic repeatedly chooses largest that fits (extremely fast, decent)
### Selection sort - Average speed of O(n^2)
- 1. Search the *entire* array for the smallest value and move it to the start
    * [4,2,9,7,6,3,1,8,5,0,10] -> [1,4,2,9,7,6,3,8,5,0,10]
- 2. The "start" moves forward as the smallest values are moved to the beginning
    * [1,4,2,9,7,6,3,8,5,0,10] -> [1,2,4,9,7,6,3,8,5,0,10]
- 3. Repeat until 100% sorted; this is easy to implement in code!
- Perfect sort, always O(n^2) (read all for each value)
### Insertion sort - Average speed of O(n^2)
- 1. Compare two values, swap them if second value is larger than first
    * [1,5,4,6,2,3] -> [1,4,5,6,2,3] (5 > 4, so swap occurs)
- 2. On a swap, comparison moves backward; second value compared to before-first
    * [1,4,5,6,2,3] (1 < 4, so no swap occurs)
- 3. On no swap (or index 0 reached when moving backward), compare moves forward
    * [1,4,5,6,2,3] -> [1,4,5,2,6,3] (move forward until find 6 > 2, swap)
- 4. Repeat insertion sorting until array is 100% sorted
    * [1,4,2,5,6,3] -> [1,2,4,6,5,3] (move backwards, swapping until find 1 < 2)
    * [1,2,4,6,5,3] -> [1,2,4,5,6,3] -> [1,2,4,5,3,6] -> 4,3,5 -> [1,2,3,4,5,6]
- Perfect sort, nearly-sorted list improve speed to `O(n)` (just reads each val)
### Shell sort - Average speed of O(n^1.5)
- Interleaved insertion sorts with a final regular insertion sort
- 1. Choose gap values for your array, ex: array with 15 values, use [5,3,1]
    * Gap value chooses based on index; 0-10 is [0,5,10],[1,6],[2,7],[3,8],[4,9]
- 2. Iterate gap values; for each value, use the value to split/sort the array
    * Gap value 5: [4,2,9,7,6,3,1,8,5,0,10] -> [4,3,10],[2,1],[9,8],[7,5],[6,0]
    * Insertion-sort each "interleaved list"; ex: [4,3,10] -> [3,4,10]
        * Insertion sort uses `i + gap_value` instead of `i + 1`, sort in-place
    * After gap value 5 shell sort: [3,1,8,5,0,4,2,9,7,6,10]
    * Gap value 3: [3,1,8,5,0,4,2,9,7,6,10] -> [3,5,2,6],[1,0,9,10],[8,4,7]
    * Insertion-sort each "interleaved list"; ex: [3,5,2,6] -> [2,3,5,6]
    * After gap value 3 shell sort: [2,0,4,3,1,7,5,9,7,6,10]
    * Gap value 1: just insertion sort here, but it's much faster now!!
        * Insertion sort works backwards; gapvalue 3 sort means only move back 3
    * After gap value 1 shell sort: [0,1,2,3,4,5,6,7,8,9,10]
- **Note: must use a gap value of 1 at some point to clean up the other sorts!**
- Worst-case is `O(n^(3/2))` (better than `O(n^2)`)
### Quicksort - Average speed of O(n*logn)
- From a midpoint index, split array in two, sort across the two parts
- 1. Select midpoint: [4,2,9,7,6,3,1,8,5,0,10] -> [3]
- 2. Move midpoint value to end of array temporarily: [4,2,9,7,6,1,8,5,0,10,3]
- 2. From left, find a value larger than the midpoint value: [4]
- 3. From right, find a value smaller than the midpoint value: [0]
- 4. Swap these two: [4,2,9,7,6,1,8,5,0,10,3] -> [0,2,9,7,6,1,8,5,4,10,3]
- 5. Repeat until fromleft has higher index than fromright
    * [0,2,9,7,6,1,8,5,4,10,3] -> [9],[1] -> [0,2,1,7,6,9,8,5,4,10,3]
    * [0,2,1,7,6,9,8,5,4,10,3] -> fromleft[7] is higher index than fromright[1]
    * Place midpoint between fromright and fromleft: [0,2,1,3,7,6,9,8,5,4,10]
- 6. First partitioning is done, midpoint is in correct spot now
    * Low partition: [0,2,1], high partition: [7,6,9,8,5,4,10]
- 7. Pick one partition, then repeat the process until that partition is sorted
    * [0,2,1] midpoint is [2], -> [0,1,2], no values higher than midpoint, done
- 8. Go to the other partition and start the partitioning process on that one
    * [7,6,9,8,5,4,10] midpoint is [8], -> [7,6,9,5,4,10,8]
    * [7,6,9,5,4,10,8] -> [9],[4] -> [7,6,4,5,9,10,8]
    * [7,6,4,5,9,10,8] -> fromleft[9] is higher index than fromright[5]
    * Place midpoint between fromright and fromleft: [7,6,4,5,8,9,10]
    * Second partitioning is done, midpoint is in correct spot
    * New partitions: [7,6,4],[8,9,10]; repeat the sorts on these
- Re-combine all sorted pieces; final array is [0,1,2,3,4,5,6,7,8,9,10]
- Perfect sort, worst case is O(n^2) but this is rare
### Merge sort - Average speed of O(n*logn)
- 1. Halve array repeatedly until all values are isolated
    * 1. [4,2,9,7,6,3,1,8,5,0,10]
    * 2. [4,2,9,7,6,3]                      ||| [1,8,5,0,10]
    * 3. [4,2,9]       || [7,6,3]           ||| [1,8,5]         || [0,10]
    * 4. [4,2]   | [9] || [7,6]   | [3]     ||| [1,8]   | [5]   || [0] | [10]
    * 5. [4],[2] | [9] || [7],[6] | [3]     ||| [1],[8] | [5]   || [0] | [10]
- 2. Work backwards in same order, sorting as you combine things back together
    * 5. [4],[2] | [9] || [7],[6] | [3]     ||| [1],[8] | [5]   || [0] | [10]
    * 4. [2,4]   | [9] || [6,7]   | [3]     ||| [1,8]   | [5]   || [0] | [10]
    * 3. [2,4,9]       || [3,6,7]           ||| [1,5,8]         || [0,10]
    * 2. [2,3,4,6,7,9]                      ||| [0,1,5,8,10]
    * 1. [0,1,2,3,4,5,6,7,8,9,10]
- Each recombine operation compares leftmost indices; append lower value to list
    * EX: [1,8],[5] -> (1 < 5) -> append [1] -> (5 < 8) -> append 5 -> append 8
- After halves sorted, take combined array and compare to another combined one
    * EX: recombine-sort [1,8],[5] ----> recombine-sort [1,5,8],[0,10]
- Perfect sort, slightly faster than the above sorts
### Bucket sort - DEPENDS!
- Intelligent split of array into buckets, sort each bucket, then recombine
    * Integer bucket sorting is called "radix sort"; sort 1s, then 10s, then ...
    * Signed radix sorting sorts as usual, then splits out negatives/reverses
    * Radix sort has average speed of O(n)!!!!!
- Many approaches for bucket choices; the choice makes/breaks the sort speed
    * Values between zero and one: 10 buckets (0.1xx, 0.2xx, 0.3xx, ...)
    * Alphabetical: 26 buckets (Axx, Bxx, Cxx, ...)
- Too many buckets is too slow; too few buckets is also too slow (careful!)
    * Elbow method to determine best combo?...
- Best choice for bucket internals is the [linked list](#linked-list)
### Heapsort
- Sorting an array, ASC; heapify array into max heap, then "remove" root node
- Remember, removing a root node involves putting the last node as root
- "Removing" the root here actually means setting last index of array as root
    * Last index is no longer considered available to the sort when "removed"
- When last node is moved to root, it is percolated down as necessary
    * Max-Heap rules are still in place
- Keep going until entire array sorted
### Quickselect - Average speed of O(n^1.5)
- Find the kth-smallest number using a modified Quicksort
### Linear Search - O(n)
- From the first value, iterate forward until the value is found
- No requirements except for data to be iterable in some way
- Traditional way to search; boring and slow
### Binary Search - O(log n)
- Split in half repeatedly while playing marco polo
- Requires data to already be sorted
### Hash Table - O(n)
- Look for values using its hash
### Other Algorithms
- Longest common substring
- Dijkstra's shortest path
### NP-Complete (lacking algorithms)
- NP-Complete: impossible to "solve" via algorithm
    * "Cliques", finding any subset of vertices where each is connected to every
- Knowing NP-complete problems saves mental cycles trying to find a solution
- Use heuristic algorithms for best-possible solution at speed to "solve"!

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
    ######     #    #######    #    ######     #     #####  #######  #####  
    #     #   # #      #      # #   #     #   # #   #     # #       #     # 
    #     #  #   #     #     #   #  #     #  #   #  #       #       #       
    #     # #     #    #    #     # ######  #     #  #####  #####    #####  
    #     # #######    #    ####### #     # #######       # #             # 
    #     # #     #    #    #     # #     # #     # #     # #       #     # 
    ######  #     #    #    #     # ######  #     #  #####  #######  #####  
                                                                        
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# DATABASES


<!-- 
######                                                           
#     #   ##   #####   ##   #####    ##    ####  # #    #  ####  
#     #  #  #    #    #  #  #    #  #  #  #      # ##   # #    # 
#     # #    #   #   #    # #####  #    #  ####  # # #  # #      
#     # ######   #   ###### #    # ######      # # #  # # #  ### 
#     # #    #   #   #    # #    # #    # #    # # #   ## #    # 
######  #    #   #   #    # #####  #    #  ####  # #    #  ####  
                                                                 
#######                                             
#     # #    # ###### #####  #    # # ###### #    # 
#     # #    # #      #    # #    # # #      #    # 
#     # #    # #####  #    # #    # # #####  #    # 
#     # #    # #      #####  #    # # #      # ## # 
#     #  #  #  #      #   #   #  #  # #      ##  ## 
#######   ##   ###### #    #   ##   # ###### #    # 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Databasing Overview
- Database: file system with query engine, generally structured or unstructured
- Most structured databases use relational database management systems (RDBMS)
- Relational databases follow set theory and handle tabular data
- Most unstructured databases use NoSQL, or "not only SQL"
- NoSQL databases handle "big data" - Veracity, Volume, Velocity, Variety
- Info about databases, database rankings: https://db-engines.com/en/
### Database Roles
- Database Administrator: specifically securing databases, making them available
- Database Designer: focused on database structure and staying within limits
- Database Programmer: scripting queries using general purpose programming langs
- Database User: query runner (allowed by DB admin, aided by DB programmer)
### Database Architecture
- Query processor: interpret/streamline queries for the storage manager
- Storage manager: translate queries into low-level filesystem commands
- File system: the simple storage of data, coordinated by storage manager
- Transaction manager: handles sets of queries, deconflicts overlaps
- Log: complete record of every processed insert/update/delete (ignoring reads)
    * Used for database recovery (ex: mid-transaction quits, complete DB loss)
- Catalog: directory of tables, columns, indexes, and other database objects
### Database Design Process
- Three phases of database design: Analysis, Logical Design, and Physical Design
- Often expressed via entity-relationship (ER) diagrams and table diagrams
    * Analysis uses ER diagrams, Logical Design uses table diagrams
- Analysis: define requirements for entity/attributes/relationships
    * 1- Discover entities, relationships, and attributes (investigation)
    * 2- Determine cardinality (aspects of relations, ex: many-to-one, min-zero)
    * 3- Distinguish independent/dependent entities (room depends on building)
    * 4- Create supertype/subtype entities (building has foyer, rooms, closets)
- Logical Design: implement the discovered requirements as a database
    * 1- Implement entities (create tables in the database)
    * 2- Implement relationships (connect tables using foreign keys/etc)
    * 3- Implement attributes (add columns to the tables)
    * 4- Normalize tables (reduce/remove redundancy, etc)
- Physical Design: add indexes to tables (indexes speed up queries)
    * 1- Use the database systems to do this

[[Return to Top]](#table-of-contents)







<!-- 
#####                                                  
#    #   ##   #####   ##   #####    ##    ####  ###### 
#    #  #  #    #    #  #  #    #  #  #  #      #      
#    # #    #   #   #    # #####  #    #  ####  #####  
#    # ######   #   ###### #    # ######      # #      
#    # #    #   #   #    # #    # #    # #    # #      
#####  #    #   #   #    # #####  #    #  ####  ###### 
                                                        
#####                                                                           
#    #  ####   ###  #   # #    # ##### #    # #####   ##   ##### #  ####  #    #
#    # #    # #   # #   # ##  ## #     ##   #   #    #  #    #   # #    # ##   #
#    # #    # #     #   # # ## # ####  # #  #   #   #    #   #   # #    # # #  #
#    # #    # #     #   # #    # #     #  # #   #   ######   #   # #    # #  # #
#    # #    # #   # #   # #    # #     #   ##   #   #    #   #   # #    # #   ##
#####   ####   ###   ###  #    # ##### #    #   #   #    #   #   #  ####  #    #
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Database Documentation
- Two main kinds: Entity-Relationship (ER) diagram and table diagram
- ER diagrams show requirements, table diagrams show requirement implementation
- ER diagrams map easily to table diagrams; Analysis maps to Logical Design
- ER diagrams have entities, their attributes, and entity-entity relationships
- Table diagrams have database tables, their columns, and table-table relations
### ER Diagram
- Charting entities, their attributes, and entity-entity relationships
    * E/A/R types (blueprint) and instances (created)
- This typically precedes database design; it helps structure requirements
- Usually combined with a glossary (elaborates on entity/attribute/relationship)
- Entity: one "thing", even entity names follow this non-plural rule
- Attributes: descriptive aspects of an element, ex: thing's name, date, etc
- Entity relationships: a truck (thing) relates to the truck depot (thing)
- Cardinality: maxima, minima (modality), and require (applies to entity/attr)
### Entities
- The building block of ER diagrams, and the future tables of a database
- An entity is singular (even in name) and contains attributes and/or entities
- Supertype entity: an entity containing other entities (Car: DieselCar/GasCar)
- Subtype entity: an entity contained by another entity (DieselCar)
- Super/Sub relationships are called "IsA relationships" (DieselCar-IsA-Car)
- Subtype entity pri-key must match supertype's pri-key and be foreign key to it
- Partition: a grouping of subtypes linked to a supertype's attribute
    * Subtypes inside a partition must be mutually-exclusive (no double dipping)
    * Subtypes of one partition can share values w/ subtype of another partition
    * EX: Card: TypeAttr:[CreditCard/DebitCard], CompanyAttr:[VISA/Mastercard]
### Attributes
- The descriptive elements of an entity
- Attributes are singular and names are clearly expressed in the glossary
    * For car entity's "FuelType" attribute, "Type" is defined in dictionary
- Attributes have maxima/minima/require cardinality in both ER & table diagrams
- EX: [Employee] FullName M-1(1), PassportNumber 1-M(0), SkillCode M-M(0)
### Relationships
- The link between entities
- Relationships are named as Entity-Relationship-Entity, ex: "Person-Owns-Car"
- Relationships happen between entities including supertype/subtype entities
- Super/Sub have dependent relationship; regular entities may be independent
- Dependence: one thing only exists when another thing does, ex: person - nose
    * Dependence is expressed via arrows/diamonds; "A depends on B" is B -> A
    * Dependent entities usually have composite primary key (foreign + primary)
- Independence: either thing can exist or not, ex: car, garage
- Dependence can be "existence dependence" (ER) or "functional dependence" (R)
- Relationships have maxima/minima/require cardinality; format is max(min)
    * Other formats use symbols; crow's foot is many, dash is one, o is zero
- EX: [Flight] 1(1) --Includes-- M(0) [Booking] exactly one flight, any bookings
### Table Diagram
- Converted version of the ER diagram
- Entity -> Table; Attribute -> Column; Relationship -> Foreign Key
- Much more specific than ER diagrams, meant to directly describe DB schema
- Attributes now have type declarations, ex: VARCHAR(100)
- Foreign keys now have a line directly connecting them to their primary key
### Glossary
- Glossary: data dictionary/repository, explains ER/table diagram words
#### Example Glossary Entry
```
* [entity/relationship/attribute] Name: [name] 
* Synonyms: [syn1], [syn2]
* Description: A [name] is ... [name] includes... but excludes...
```

[[Return to Top]](#table-of-contents)







<!-- 
######                                                  
#     #   ##   #####   ##   #####    ##    ####  ###### 
#     #  #  #    #    #  #  #    #  #  #  #      #      
#     # #    #   #   #    # #####  #    #  ####  #####  
#     # ######   #   ###### #    # ######      # #      
#     # #    #   #   #    # #    # #    # #    # #      
######  #    #   #   #    # #####  #    #  ####  ###### 
                                                        
#######                                                          
#     # #####  ###### #####    ##   ##### #  ####  #    #  ####  
#     # #    # #      #    #  #  #    #   # #    # ##   # #      
#     # #    # #####  #    # #    #   #   # #    # # #  #  ####  
#     # #####  #      #####  ######   #   # #    # #  # #      # 
#     # #      #      #   #  #    #   #   # #    # #   ## #    # 
####### #      ###### #    # #    #   #   #  ####  #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Database Operations
### Primary Key
- Primary key: the column(s) that uniquely identify each row in a table
- Can be simple (one column) or composite (multiple columns)
- Primary key must be minimal-complexity (least columns)
    * Choose a car's VIN instead of the composite of year/make/model/owner/plate
- Each entry in the primary key must be unique, and no single value can be null
- Primary keys should be as simple as possible
    * Choose auto-incrementing integers instead of 256-bit hash
- Can create an artificial key if primary key assembly is complex/not possible
    * Artificial key is generally auto-incrementing integers
### Queries
- Query: a database operation, includes data retrieval and insert/update/delete
- Queries are CRUD operations; Create, Read, Update, and Delete data
- "Create" queries add brand new table(s) to a database
- "Read" queries display data from a database
- "Update" queries modify existing table(s) in a database
- "Delete" queries remove table(s) from a database
- Queries can be grouped into multi-query "transactions"
- Funds transfer is a transaction; remove money from one account, add to other
- Transactions are *not* allowed to partially-execute, ex: only removing money
    * Database systems ensure either entire or none of transaction is performed
### Joins
- Join: bringing tables together into one table
- Many types of joins; inner/outer, equijoin/non-equijoin, self-join, cross-join
- "Outer" join: bring tables together while allowing unmatched rows
- "Inner" join: bring tables together while dropping unmatched rows
- "Equijoin": using a matching key to join tables
- "Non-equijoin": use conditional evaluation to join tables
- "Self-join": join the same table onto a copy of itself
- "Cross-join": all possible row combinations of two or more tables
### Storage
- Speed: measured as access time and transfer rate
    * Access time: time to access the first byte in a read or write operation
    * Transfer rate: read/write speed following initial access
- Block: chunk of data in standardized size, ex: 2kb, for storage
    * Standardized size is enforced; partial-fill is still sent as a full block
    * Typical range for block size is 2kb to 64kb
- Magnetic disk: disk drives, use "sectors", 512 bytes to 4 kb per sector
- Flash memory: solid state, use "pages", 2 kb to 16 kb per page
- Storage controller: converts data from main memory (RAM) to magnetic/flash
- Table clusters: interleave rows of two or more tables in the same storage area
    * Cluster key: common key from all tables, determines order
#### Row-Oriented Storage
- Row-oriented storage: packaging row-wise for storage on disks or flash memory
- Most common storage form for relational databases
- Iterates rows and reads all cells in the row (fast at row's attributes)
- Great when individual cells have small data, not documents/images/etc
- Heap table: unordered rows; track open space in blocks; linked list refill
- Sorted table: ordered rows; pure linked list work to keep order in changes
- Hash table: buckets of linked blocks; hash key is column(s); fast changes
#### Column-Oriented Storage
- Column-oriented storage: packaging column-wise for storage on disks/flash
- Reads all cells in column (fast at a column's values)
- Great for column-based work + compression, terrible at multi-column
- Used by: PostgreSQL, Vertica, NoSQL
### Index
- I am so bored by database indices
- They are copies of one or more columns from one or more tables
- They are sorted
- They don't have to be unique
- They have pointers that point to the specific rows they refer to
- You can use table scans (reading tables) or index scans (reading indices)
    * Decision made from "hit ratio"; high hit ratio -> table scan, low -> index

[[Return to Top]](#table-of-contents)







<!-- 
######                                                           
#     # ###### #        ##   ##### #  ####  #    #   ##   #      
#     # #      #       #  #    #   # #    # ##   #  #  #  #      
######  #####  #      #    #   #   # #    # # #  # #    # #      
#   #   #      #      ######   #   # #    # #  # # ###### #      
#    #  #      #      #    #   #   # #    # #   ## #    # #      
#     # ###### ###### #    #   #   #  ####  #    # #    # ###### 
                                                                 
######                                                         
#     #   ##   #####   ##   #####    ##    ####  ######  ####  
#     #  #  #    #    #  #  #    #  #  #  #      #      #      
#     # #    #   #   #    # #####  #    #  ####  #####   ####  
#     # ######   #   ###### #    # ######      # #           # 
#     # #    #   #   #    # #    # #    # #    # #      #    # 
######  #    #   #   #    # #####  #    #  ####  ######  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Relational Databases
- Two-dimensional tables, connected, queryable
### Relational DB Model Basics
- Domain: named **set** of possible database values, ex: integers, strings, ...
- Tuple: collection of domains, ex: `(Integers, DictionaryWords, LogicalValues)`
- Relation: named **set** of tuples (each tuple must have the same sequence)
- Relational rules: general term for structural, business, ref. integrity rules
- Structural rules: governs data universally for all databases
    * Unique primary key, unique column names / rows, only one value in a cell
- Business rules: "local rules" enforced by the database system / requirements
    * Unique column values, no missing values, deletion cascade
- Referential integrity rules: foreign key constraints
    * Must match a value in primary key, if composite can't be partially null
- Constraints: Column-level (one column) vs Table-level (more than one column)
### Foreign Key
- Column of one table referencing another table's primary key
- Foreign key typically adopts the name of the primary key it references
- Values in foreign key must exist in the referred-primary key (ref. integrity)
- Values in foreign key can be null unless the primary key is marked "required"
    * If all foreign key values are null, then zero connections to pri-key (bad)
- Values in foreign key can be duplicates unless reference to pri-key is 1-to-1
    * Foreign key may also be marked "unique" to disallow duplicates
- 1-to-1 / 1-to-M has foreign key; M-to-M has new table w/ composite foreign key
    * Use CASCADE/RESTRICT constraints to assist DB management during CRUD ops
### Relational Algebra
- Relational algebra is table operations (uses set theory)
- Select: selects a subset of rows of a table
- Project: eliminates one or more columns of a table
- Product: lists all possible combinations of rows of two tables
- Join: a product operation followed by a select operation
- Union: combines two tables by selecting all rows of both tables
- Intersect: combines two tables by selecting only rows common to both tables
- Difference: combines two tables by selecting not-in-common rows
- Query optimizers rely on relational algebra
    * Convert query to rel. algebra expressions and create alternate expressions
    * Compare processing times of all rel. algebra expressions, pick fastest

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                                       
##   ##   ##   #    #   ##    ####  # #    #  ####       ##   
# # # #  #  #  ##   #  #  #  #    # # ##   # #    #     #  #  
#  #  # #    # # #  # #    # #      # # #  # #         #    # 
#     # ###### #  # # ###### #  ### # #  # # #  ###    ###### 
#     # #    # #   ## #    # #    # # #   ## #    #    #    # 
#     # #    # #    # #    #  ####  # #    #  ####     #    # 
                                                              
 #####   #####  #         ######                                                
#     # #     # #         #     #   ##   #####   ##   #####    ##    ####  #####
#       #     # #         #     #  #  #    #    #  #  #    #  #  #  #      #    
 #####  #     # #         #     # #    #   #   #    # #####  #    #  ####  #### 
      # #   # # #         #     # ######   #   ###### #    # ######      # #    
#     # #    #  #         #     # #    #   #   #    # #    # #    # #    # #    
 #####   #### # ######    ######  #    #   #   #    # #####  #    #  ####  #####
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Managing a SQL Database
### SQL Data Types
- DATE (YYYY-MM-DD), TIME (hh:mm:ss), DATETIME (YYYY-MM-DD hh:mm:ss), TIMESTAMP
- TINYINT(255), SMALLINT(65_535), MEDIUMINT(16_777_215), 
- INT/INTEGER(4_294_967_295), BIGINT(2e64 - 1)
- DECIMAL(digits,decimalplaces), FLOAT (6.8e38), DOUBLE (1.8e308)
- CHAR (255), VARCHAR (65_535)
- BLOB, BINARY, VARBINARY, IMAGE (0101011101)
- POLYGON, POINT, GEOMETRY (coordinate-related; POINT is a tuple (x,y))
- XML, JSON (documents)
- Any of the above column data types can have: NULL
### SQL Constraints
- Either follows this syntax: `..., ColName INTEGER constraint_here, ...`
- Or this syntax: `constraint_here (ColName)` / `constraint_here (C1, C2, ...)`
- Or this syntax: `CONSTRAINT name_here AS constraint_here (ColName, ...)`
- Primary key (unique, non-null): `PRIMARY KEY (c1)`
    * See also: `c1 INTEGER PRIMARY KEY AUTO_INCREMENT` (ignore c1 on insert)
- Foreign key (choose vals from pri key): `FOREIGN KEY (c1) REFERENCES t1 (c1)`
- No duplicates: `UNIQUE (c1)`
- Handle nulls: `c1 INTEGER NOT NULL` / `c1 INTEGER DEFAULT 42`
- Positive/Negative: `SIGNED` (positive or negative), `UNSIGNED` (positive only)
- Match condition: `CHECK (cond1)` / `CHECK (cond1, cond2)` / `CHECK (a > 100)`
#### SQL Referential Integrity Violation Constraints
- Used for handling updates to a primary key being referenced by foreign key(s)
    * EX: `... FOREIGN KEY c1 REFERENCES t1(c1) ON DELETE CASCADE` / `ON UPDATE`
- Reject key changes: `RESTRICT` 
- Allow key changes, set foreign keys' changed values to null: `SET NULL`
- Allow key changes, set default for foreign keys' changed values: `SET DEFAULT`
- Allow key changes, pass them on to foreign keys' changed values: `CASCADE`
### SQL Database Architecture Work
- `CREATE DATABASE db_name;`
- `CREATE TABLE Employee (ID INT, Name VARCHAR(60) NOT NULL, PRIMARY KEY (ID));`
    * `DROP TABLE Employee` (if other table references Employee, this fails)
- `ALTER TABLE Employee...` (specifically column-based changes)
    * `... ADD ColumnName DataType;`
    * `... CHANGE CurrentColumnName NewColumnName NewDataType;`
    * `... DROP ColumnName;`
- `CREATE INDEX index_name ON table (column)` / `... ON table (c1, c2, c3, ...)`
- `CREATE VIEW viewtable AS SELECT ...`
    * Views are convenient versions of raw tables and can protect sensitive info
    * Restrict certain changes to view: `WITH CHECK OPTION (a > 0);`
### SQL Database Content Work
- `INSERT INTO account VALUES (290, 'Ethan Carr', 5000);`
- `INSERT INTO names VALUES (1, 'John'), (2, 'Joan'), ...;`
- `UPDATE Account SET Balance = 4500 WHERE ID = 831;`
- `DELETE FROM Account WHERE ID = 572;`
- `TRUNCATE TABLE Account` (drop all rows and reset auto-increment)

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
                      #####  #     # ####### ######  #     # 
                     #     # #     # #       #     #  #   #  
                     #     # #     # #       #     #   # #   
                     #     # #     # #####   ######     #    
                     #   # # #     # #       #   #      #    
                     #    #  #     # #       #    #     #    
                      #### #  #####  ####### #     #    #    
                                        
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# QUERY


<!--
 #####   #####  #       
#     # #     # #       
#       #     # #       
 #####  #     # #       
      # #   # # #       
#     # #    #  #       
 #####   #### # ####### 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## SQL
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
    * `SHOW`:`\l`, `USE`: `psql -d mydb`, `DESCRIBE`: `\d` or `\dt`, quit: `\q`
        * `SHOW`, `USE`, and `DESCRIBE` don't work
    * Select distinct: `SELECT DISTINCT ON (c1) c1, c2, c3 FROM t ORDER BY c1;`
    * `CREATE OR REPLACE PROCEDURE p(IN a, ..) BEGIN .. END; $ LANGUAGE plpgsql`
    * Invoke a stored procedure: `CALL procedure_name(10000, 429);`
    * `\copy` used with ETL copy instructs, ex: `\copy (SELECT * FROM table)...`
    * `pg_dump` to export a table as SQL; `pg_dumpall` exports all tables as SQL
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
### SQL Pull Records
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
### SQL Calculate Aggregates
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
### SQL Subquerying
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
### SQL Temp Table Creation
```sql
USE employees;
CREATE TEMPORARY TABLE germain_1457.employees_with_departments AS
    SELECT first_name, last_name, departments.dept_name
    FROM employees
    JOIN dept_emp USING(emp_no)
    JOIN departments USING(dept_no);
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Spark
- Computational clustering solution for big data processing
- Non-clustered compute fails in four specific "big data" scenarios, w/ extreme:
    * Velocity (throughput); gather or stream data quickly to/from many sources
    * Volume (static size); handle data that exceeds memory or storage
    * Veracity (data quality); prevent normal corruption of storage/transmission
    * Variety (formats); handle data edge cases and unstructured data
- Spark clusters are designed to solve these "big data" scenarios
    * Java Virtual Machine (JVM) coordinates computational clusters using Scala
    * Singular actions propagate efficiently across clusters to perform tasks
    * Uses "lazy execution" which optimizes a given task before execution begins
    * Can iteratively build and preview a task before running the full task
- Can initialize a Spark cluster on a single computer; this is sometimes useful!
    * The default behavior here parallelizes (clusters) every core of the CPU
    * Multi-core tasks leverage more processing power than single-core tasks
    * Proper use of multi-core tasking can yield significant performance boosts
- Spark has overhead that makes it less competitive on small data, flexibility
    * There's latency with initializing the Spark cluster, booting the JVM, etc
    * Any non-Spark processing (pandas) requires dumping data out of the cluster
- Rule of thumb: use Spark when data is at least 1GB and processing is defined
    * Skip use of Spark when dataset is smaller or when you need flexibility
    * Explore large data w/ comfort tools, then move work to multi-core pipeline
    * Use Spark to crunch numbers, then export the result numbers into insights
- Alternatives: Hadoop, Dask
### PySpark
- Official Python library for working with Spark computational clusters
- Translates Python actions into Scala actions and operates the JVM as normal
- Check Spark's intentions before query: `df.explain()`
    * Used for diagnosing performance issues; operation order from bottom-upward
- Switch to SQL: `df.createOrReplaceTempView('df')`
    * Run SQL statements: `spark.sql(''' SELECT * FROM df ''')`
- Build schema: `schema = StructType([(StructField(...), StructField(...)),])`
    * StructField syntax: `Structfield("col1", StringType())`
```python
import pyspark
from pyspark.sql.functions import *  # overwrites py funcs; fine when Spark-only
spark = pyspark.sql.SparkSession.builder.getOrCreate()  # CREATE A LOCAL CLUSTER
df = spark.read.csv('data.csv', header=True, schema=schema_struct)  # INGEST CSV
# WRANGLING (LAZY EXECUTION)
df = df.join(df2, "joincol", "left").drop(df.joincol).drop(df2.joincol)  # JOIN
df.select(
    [count(when(isnan(c) | col(c).isNull(), c)).alias(c) for c in df.columns]
).show(vertical=True)  # PRINT NULL COUNTS
df = df.na.fill(0, subset=['x', 'y']).na.drop()  # FILL, DROP NULLS
df.printSchema()  # CHECK DTYPES
df = df.withColumn('cool', df.x.cast('string')).withColumnRenamed("b4", "aftr")
df = df.withColumn("ts_to_month", month(to_timestamp("col1", "M/d/yy H:mm")))
df = df.withColumn("datediff", datediff(current_timestamp(), "datecol"))
df = df.withColumn('repl', regexp_replace(df.x, re, repl))   # REGEX REPLACE
df = df.withColumn('substr', regexp_extract(df.col, re, g))  # REGEX SUBSTR
df = df.withColumn("c1", trim(lower(df.c1)))  # LOWERCASE AND TRIM
df = df.withColumn("c1", format_string("%03d", col("c1").cast("int")),) # FORMAT
df = df.withColumn('c2', concat(lit('x:', df.x)))  # CONCAT STRINGS
df = df.select(*, expr(df.x + df.y).alias('z'))  # ADD X + Y AS COLUMN Z
df = df.selectExpr('*', 'x + y as z')            # ADD X + Y AS COLUMN Z
df = df.withColumn('ten', when(df.x > 10, '>10').otherwise('<=10'))  # IF/ELSE
df = df.where((df.x > 5) | (df.y < 5)).where(df.z ==7)  # WHERE, OR + AND
df = df.sample(fraction=0.01, seed=42)  # SMALL SAMPLE
trn, val, test = df.randomSplit([0.6, 0.2, 0.2], seed=42) # SPLIT FOR MODELING
# EXECUTE ALL ABOVE WRANGLING STEPS, SAVE RESULTS TO FILE
df.write.json("df_json", mode="overwrite")
trn.write.format("csv").mode("overwrite").option("header", "true").save("t.csv")
val.write.format("csv").mode("overwrite").option("header", "true").save("v.csv")
tst.write.format("csv").mode("overwrite").option("header", "true").save("h.csv")
# EXPLORATION (LAZY EXECUTION)
x_y = df.select(sum(df.x)), df.select(mean(df.x))  # COLUMN MATH
mean_min = df.groupBy('gb').agg(mean(df.x), min(df.y))  # AGG GROUPBY
crosstab = df.crosstab('g1', 'g2')  # CROSSTAB
mean_x_given_g1_g2 = df.groupBy('g1').pivot('g2').agg(mean('x'))  # PIVOT TABLE
value_counts = df.groupBy('col','target').count().sort('count',ascending=False)\
.withColumn('proportion', round(col('count') / df.count(), 2)) # COUNTS/NORMALS
# MODELING
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
#######                                         #####                        
#       #        ##    ####  ##### #  ####     #     # #    # # ##### ###### 
#       #       #  #  #        #   # #    #    #       #    # #   #   #      
#####   #      #    #  ####    #   # #          #####  #    # #   #   #####  
#       #      ######      #   #   # #               # #    # #   #   #      
#       #      #    # #    #   #   # #    #    #     # #    # #   #   #      
####### ###### #    #  ####    #   #  ####      #####   ####  #   #   ###### 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Elastic Suite
- The Elastic suite is a powerful solution for data transform/storage, analytics
    * Elasticsearch: database; directly accessible, can use inbuilt pipelines
    * Kibana: user interface; insights/viz, database management, task runner
    * Beats: ingest agents; many preconfigured agents, can build custom agents
    * Logstash: optional ingest pipeline layer with full customization
- Elasticsearch database is extremely well-documented and has many useful APIs.
    * Uses typical HTTP requests, ex: `PUT url/new-index`, `DELETE url/goodbye`
    * `_search`: Querying records, allows aggregation and temp field creation
    * `_delete_by_query`: Deleting records, uses a query to select for deletion
    * `_reindex`: Copy records from one index to another, can transform the copy
    * `_bulk`: Perform a bulk of actions including ingest, delete, change, etc
### API Calls
- Use Kibana's console to draft API calls for scripting, run one-off tasks
    * Guaranteed connection to Elasticsearch, no worries about creds/network/etc
    * Simplifies API syntax, ex: `GET _cat/indices?h=index&expand_wildcards=all`
- Use cURL to run the API calls from a command line interface or script
    * `curl -k --user U:P -H ... -XGET "url/index/_search" -d @q.json > o.json`
    * JSON use `-H "Content-Type: application/json" -d @q.json`
    * NDJSON use `-H "Content-Type: application/x-ndjson" --data-binary @q.json`
- Use Python to parse JSON to CSV, or, perform scan, index management, etc
    * `elasticsearch-py` and `elasticsearch-dsl` libraries simplify tasks
### Example _search API Request Body
```json
{
  "size": 0,
  "query": {"bool": {
    "must": [
        {"exists": {"field": "source.ip"}},
        {"query_string": {"query": "network.transport: (tcp OR udp)"}}
    ],
    "must_not": [
      {"match": {"source.ip": "123.45.67.89"}}
    ],
    "filter": [
      {"range": {"@timestamp": {"gte":"2001-01-01T00:00:00", "lte":"now-3d"}}},
      {"script": {"script": {"source": "return doc['first2'].value != '0.0';"}}}
    ]
  }},
  "runtime_mappings": {
    "first2": {"type": "keyword", "script": """
    String ip_address = doc['source.ip'].value.toString();
    String firsttwo_octets = '';
    def octets = ip_address.splitOnToken('.');
    for (int i = 0; i < 2 && octets.length == 4; i++) {
      firsttwo_octets = firsttwo_octets + octets[i] + '.';
    }
    if (firsttwo_octets != '') { emit(firsttwo_octets); }
    """},
    "sentmore_192_168": {"type": "boolean", "script": """
    String srcip = doc['source.ip'].value;
    int total_sent = doc['source.bytes'].value;
    int total_rcvd = doc['destination.bytes'].value;
    def myregex = /192\\.168\\.\\d{1,3}\\.\\d{1,3}/.matcher(srcip);
    if (myregex.matches()) {emit(total_sent > total_rcvd) && (total_rcvd > 0);}
    """}
  },
  "aggs": {
    "unique_first2": {"terms": {"field": "first2", "size": 1000}},
    "rare_first2": {"rare_terms": {"field": "first2"}},
    "most_sent"
  }
}
```
### Scan Records in Python
```python
# -- DEFINITION BLOCK -- #
def pull_records(query_object, pullcount_limit=None, shh=False, add_id=False):
    response = query_object.execute()
    if not response.success():
        print("Connection failed!")
        return None
    rows, i = [], 0
    try:
        for i, record in enumerate(query_object.scan()):
            if i == pullcount_limit:
                i = i - 1
                break
            if shh is False and i % 1_000 == 0:
                print_progress(i)
            obj = record.to_dict()
            if add_id:
                obj["_id"] = record.meta.id
            row = flatten_json(obj)
            del obj
            rows.append(row)
            del row
    except Exception as error:
        print(f"Something went wrong! The query likely failed. Error:\n{error}")
    if shh is False:
        print(f"Total records pulled: {i + 1}")
    if len(rows) == 0:
        return None
    df = pd.DataFrame(rows)
    del rows
    return df
def flatten_json(json_input, keyout_lists=False):
    output_dict = {}
    def flatten(current_structure, name=""):
        if type(current_structure) is dict:
            for element in current_structure:
                flatten(current_structure[element], name + element + ".")
        elif type(current_structure) is list:
            if keyout_lists:
                for i, element in enumerate(current_structure):
                    flatten(element, name + str(i) + "_")
            else:
                output_dict[name[:-1]] = current_structure
        else:
            output_dict[name[:-1]] = current_structure
    flatten(json_input)
    return output_dict
def print_progress(i):
    if i < 1_000_000 and i % 1_000 == 0 and i != 0:
        print(f"{i // 1_000}k records pulled...", end="\r", flush=True)
    elif i % 10_000 == 0 and i != 0:
        print(f"{i / 1_000_000}mil records pulled...", end="\r", flush=True)
# -- EXECUTION BLOCK -- #
ip, user, password = "https://192.168.0.1:9200", "coolguy", "coolpassword"
index_pattern = "winlogbeat-*"
import pandas as pd
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search
client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
search_context = Search(using=client, index=index_pattern, doc_type="doc")
s1 = search_context\
    .query("match", winlog__event_id=4624)\
    .filter("range", **{"@timestamp": {"gte": "now-1d"}})\
    .source(fields=["winlog.provider_name","winlog.event_id"])
df1 = pull_records(s1, 21_000)
s2 = search_context.extra(**{
    "query": {"match": {"event.code": 4624}},
    "fields": ["event.code", "winlog.event_data.LogonType", "related.user"]})
df2 = pull_records(s2, 192_168_010)
```
### Copy Existing Index's Config for Use in New Index
```python
def copy_existing_index_config(client, alias="winlogbeat-*"):
    """Grab mappings/settings from index in pattern for the new custom index"""
    mappings = client.indices.get_mapping(index=alias) # GRAB INDEX MAPPINGS
    ind_name = list(mappings.keys())[-1]        # CHOOSE NEWEST INDEX IN PATTERN
    put_body = mappings[ind_name]               # SAVE NEWEST INDEX'S MAPPINGS
    ind_sets = client.indices.get_settings(index=ind_name) # GRAB INDEX SETTINGS
    settings = ind_sets[ind_name]["settings"]   # ISOLATE NEWEST INDEX SETTINGS
    del settings["index"]["uuid"]               # THIS DEL TO PREVENT CONFLICT
    del settings["index"]["creation_date"]      # THIS DEL TO PREVENT CONFLICT
    del settings["index"]["provided_name"]      # THIS DEL TO PREVENT CONFLICT
    del settings["index"]["version"]["created"] # THIS DEL TO PREVENT CONFLICT
    put_body["settings"] = settings             # SAVE NEWEST INDEX'S SETTINGS
    return put_body                             # CUSTOM INDEX'S FULL 'PUT' BODY
elastic_backend = "https://localhost:9200"
ssl_cert = "C:\\Users\\coolguy\\ca.crt"
login_creds = ("elastic", "elastic")
client = ES([elastic_backend], ca_certs=ssl_cert, http_auth=login_creds)
winlogbeat_index_definition = copy_existing_index_config(client)
response = client.indices.create(index="new", body=winlogbeat_index_definition)
print(f"INDEX CREATION:\n{response}\n------------")
```

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
                 #     #####   #####  #     # ### ######  ####### 
                # #   #     # #     # #     #  #  #     # #       
               #   #  #       #     # #     #  #  #     # #       
              #     # #       #     # #     #  #  ######  #####   
              ####### #       #   # # #     #  #  #   #   #       
              #     # #     # #    #  #     #  #  #    #  #       
              #     #  #####   #### #  #####  ### #     # ####### 
                                                    
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# Acquire


<!--
######                                          
#     #   ##   #####   ##    ####  ###### ##### 
#     #  #  #    #    #  #  #      #        #   
#     # #    #   #   #    #  ####  #####    #   
#     # ######   #   ######      # #        #   
#     # #    #   #   #    # #    # #        #   
######  #    #   #   #    #  ####  ######   #   
                                                
 #####                                            
#     #  ####  #    # #####   ####  ######  ####  
#       #    # #    # #    # #    # #      #      
 #####  #    # #    # #    # #      #####   ####  
      # #    # #    # #####  #      #           # 
#     # #    # #    # #   #  #    # #      #    # 
 #####   ####   ####  #    #  ####  ######  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Dataset Sources
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
### Data Formats
- CSV
- XLSX
- SAS
- Stata
- Parquet
- HDF5
- MATLAB
### REST APIs
- Application Programming Interface: a way to interact with 'owned' data
    * There's rules and defined mathods for interacting with APIs
    * Scraping is still possible, but APIs may be better in some cases
- REST, RESTful: a standardized structure for URLs
    * Interfacing is done through HTTP requests
- RESTful JSON API: URLs follow REST, comms w/ server are in JSON format
    * Endpoints are typically: "/api/v1/items/1" with ["next_page"]/["max_page"]

[[Return to Top]](#table-of-contents)







<!-- 
######                                            
#     # ######  ####  #    # #        ##   #####  
#     # #      #    # #    # #       #  #  #    # 
######  #####  #      #    # #      #    # #    # 
#   #   #      #  ### #    # #      ###### #####  
#    #  #      #    # #    # #      #    # #   #  
#     # ######  ####   ####  ###### #    # #    # 
                                                  
#######                                                                  
#       #    # #####  #####  ######  ####   ####  #  ####  #    #  ####  
#        #  #  #    # #    # #      #      #      # #    # ##   # #      
#####     ##   #    # #    # #####   ####   ####  # #    # # #  #  ####  
#         ##   #####  #####  #           #      # # #    # #  # #      # 
#        #  #  #      #   #  #      #    # #    # # #    # #   ## #    # 
####### #    # #      #    # ######  ####   ####  #  ####  #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Regular Expressions
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
### REGEX Capture Group Examples
- Note these examples are Python REGEX using `re.findall(regexp, string)`
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
- `^.+(\S+)!$` *Only last non-whitespace before "!"; leftmost greedy runs first*
    * "Hello, Sam!" -------------> ["m"]
    * "Hello, Sam Witwicky!" ----> ["y"]
- `^.+?(\S+)!$` *Non-greedy leftmost means greedy rightmost takes precedence*
    * "Hello, Sam!" -------------> ["Sam"]
    * "Hello, Sam Witwicky!!!" --> ["Witwicky"]
    * "f7g?3.rb3%79h&2398dh!" ---> ["f7g?3.rb3%79h&2398dh"]
- `([a-zA-Z]+)\s*?([a-zA-Z]+){,1}!` *Two capture groups, second is optional*
    * "Hello, Sam!" -------------> [("Sam", "")] (two capture groups -> tuple)
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello!" ------------------> [("Hello", "")]
- `Hello,\s([a-zA-Z]+)\s*?([a-zA-Z]+){,1}!` *Best solution of above*
    * Same as above example but with "Hello,\s" at the beginning
    * "Hello, Sam!" -------------> [("Sam", "")]
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello, Sam    Witwicky!" -> [{"Sam", "Witwicky"}]
    * "Hello!" ------------------> []
- `Hello,\s([a-zA-Z]+)(?:\s([a-zA-Z]+)){,1}!` *Use match group w/ capture in it*
    * Optional match group w/ capture in it is proper design for optional parts
    * "Hello, Sam!" -------------> [("Sam", "")]
    * "Hello, Sam Witwicky!" ----> [("Sam", "Witwicky")]
    * "Hello, Sam    Witwicky!" -> []
    * "Hello!" ------------------> []

[[Return to Top]](#table-of-contents)







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

--------------------------------------------------------------------------------
<!-- Polished -->
## Python Web Scraping
- `[url].com/robots.txt` ----- see if a site is OK with scraping or not
- Keep timestamps on your work, websites change!!
### Python Pandas Direct-Read
- Use this method if you're working with *HTML tables*; it's easy and effective
- Sample HTML tables (testing): https://www.w3schools.com/html/html_examples.asp
- `df = pd.read_clipboard()` makes a dataframe from your clipboard's content
    * Sometimes the fastest solution is the best!!
```python
import pandas as pd
url = "https://www.w3schools.com/html/tryit.asp?filename=tryhtml_table_headings"
df1 = pd.read_html(url)[0]   # read HTML tables from URL, set first table as df1
myhtml = "<table><tr><th>hi</th></tr><tr><td>12</td></tr></table>"
df2 = pd.read_html(myhtml)[0]   # read HTML tables from string, set first as df2
```
### Python Requests
- Use this method if you need to scrape the contents of *static* HTML tags
- Requests grabs the page HTML, BeautifulSoup does the tag scraping
    * Note that any post-HTML loading (ex: Javascript) is not grabbed...
- To build a dataframe: use a sequence of `request.get` calls and build each row
- Beautiful Soup dive: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
    * Consider: `BeautifulSoup(df.loc["page", 1318], "html.parser")`
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
### Python Selenium
- Use this method to handle pages w/ Javascript (JS) or do advanced nav actions
- Selenium drives a browser; browser runs JS like normal and we can task browser
    * Requests (raw HTTP GET) only pull pre-JS-loaded content (not all content)
    * Selenium runs JS, making it possible to pull all page content
    * Selenium-driven browsers can click/hover/etc to execute more JS for pull
- We can use BeautifulSoup to store page content at various stages of JS
    * Selenium can wait until certain page elements have loaded
    * On detection of loaded elements, we can punch page content into a Soup
    * Then we can analyze that Soup like normal
- Setting up Selenium requires downloading a relevant browser webdriver
    * Firefox, Chrome, and more are supported
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
### Python Walk Images
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

[[Return to Top]](#table-of-contents)







<!-- 
######                      
#     #   ##   #####   ##   
#     #  #  #    #    #  #  
#     # #    #   #   #    # 
#     # ######   #   ###### 
#     # #    #   #   #    # 
######  #    #   #   #    # 
                            
 #####                                                        
#     # ##### #####  #    #  ####  ##### #    # #####  ###### 
#         #   #    # #    # #    #   #   #    # #    # #      
 #####    #   #    # #    # #        #   #    # #    # #####  
      #   #   #####  #    # #        #   #    # #####  #      
#     #   #   #   #  #    # #    #   #   #    # #   #  #      
 #####    #   #    #  ####   ####    #    ####  #    # ###### 
                                                              
#     #                                                                         
##    #  ####  #####  #    #   ##   #      # ######   ##   ##### #  ####  #    #
# #   # #    # #    # ##  ##  #  #  #      #     #   #  #    #   # #    # ##   #
#  #  # #    # #    # # ## # #    # #      #    #   #    #   #   # #    # # #  #
#   # # #    # #####  #    # ###### #      #   #    ######   #   # #    # #  # #
#    ## #    # #   #  #    # #    # #      #  #     #    #   #   # #    # #   ##
#     #  ####  #    # #    # #    # ###### # ###### #    #   #   #  ####  #    #
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Data Structure Normalization
### Database Normal Forms
- Goal is to represent data in a non-redundant, clear, and simple architecture
- Zero Normal Form (0NF): Data has not been normalized
    * Getting to 0NF means structuring data where it can be retrieved from DB
    * DB is stuck in 0NF if has duplicate rows/columns, or cell vals have arrays
- First Normal Form (1NF): No duplicate rows/columns, one value per cell
    * Going 0NF -> 1NF means de-duplicating rows/columns and splitting arrays
    * DB is stuck in 1NF if it has composite key *and* partial-key dependencies
        * Partial-key dependency: part of composite key alone drives non-key col
- Second Normal Form (2NF): No partial dependencies on any composite keys
    * Going 1NF -> 2NF means splitting composite key, put key:non-keys in tables
    * DB is stuck in 2NF if non-key col is driven by other non-key (transitive)
- Third Normal Form (3NF): All cols are not dependent on other non-key cols
    * Going 2NF -> 3NF means keeping subkeys, but put subkey:non-keys in tables
    * DB is stuck in 3NF if any non-keys can't be the table's key
- Boyce-Codd Normal Form (BCNF): All cols in all tables can be their table's key
    * Going 3NF -> BCNF means moving can't-key cols to can-key:can't-key table
    * ***Typical stopping point in normalization for most database admins***
    * DB is stuck in BCNF if a key's dependent cols are unrelated to each other
- Fourth Normal Form (4NF): One key drives one set of all-related values
    * Going BCNF -> 4NF means splitting a key's independent non-keys to tables
    * DB is stuck in 4NF if joining tables can produce more information
- Fifth Normal Form (5NF): All many:many relationships are in their own tables
    * Going 4NF -> 5NF means putting all many:many relations in their own tables
    * DB is stuck in 5NF if a time-based row addition includes unchanged info
- Sixth Normal Form (6NF): All time-based changes only add a row of changed info
    * Going 5NF -> 6NF means putting each possible change in its own table
    * Nothing really higher than this point in traditional DB normalization
* Some database normalization decisions are specific to the data itself
    * Domain-Key Normal Form (DKNF) means all keys/values in DB have constraints
    * Object-Relational, NoSQL, and Denormalization intentionally violate NFs
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
### Normalization Drafting
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

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
            ####### #     # ######  #       ####### ######  ####### 
            #        #   #  #     # #       #     # #     # #       
            #         # #   #     # #       #     # #     # #       
            #####      #    ######  #       #     # ######  #####   
            #         # #   #       #       #     # #   #   #       
            #        #   #  #       #       #     # #    #  #       
            ####### #     # #       ####### ####### #     # ####### 
                                                        
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# EXPLORE


<!--
######                                                                 ##    
#     # #####   ####  #####    ##   #####  # #      # ##### #   #     #  #   
#     # #    # #    # #    #  #  #  #    # # #      #   #    # #       ##    
######  #    # #    # #####  #    # #####  # #      #   #     #       ###    
#       #####  #    # #    # ###### #    # # #      #   #     #      #   # # 
#       #   #  #    # #    # #    # #    # # #      #   #     #      #    #  
#       #    #  ####  #####  #    # #####  # ###### #   #     #       ###  # 
                                                                             
######                                                                     
#     # #  ####  ##### #####  # #####  #    # ##### #  ####  #    #  ####  
#     # # #        #   #    # # #    # #    #   #   # #    # ##   # #      
#     # #  ####    #   #    # # #####  #    #   #   # #    # # #  #  ####  
#     # #      #   #   #####  # #    # #    #   #   # #    # #  # #      # 
#     # # #    #   #   #   #  # #    # #    #   #   # #    # #   ## #    # 
######  #  ####    #   #    # # #####   ####    #   #  ####  #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Probabilities and Distributions
- Probability of outcome: P(outcome) = (count_get_outcome) / (count_get_any)
    * P(heads flip) = (1) / (2) -> (1) / (2) -> ... (independent events)
    * P(name drawn) = (1) / (4) -> (1) / (3) -> ... (dependent events)
- Probability distribution: chart of outcomes and their chances
    * Get probability from distribution: area under the curve (AUC) with slicing
    * Chance of rolling 1 or 2 from 6: 2/6 of the distribution (1/3)
- Total Probability Law: For the same event in separate samples, sum probability
    * Batch1: 50% of product; Batch2: 25% of product; Batch3: 25% of product
    * Batch1: 1% defect rate; Batch2: 2% defect rate; Batch3: 3% defect rate
    * Total defect probability: (1% * 50%) + (2% * 25%) + (3% * 25%) = 1.75%
- Bayes Theorem: P(A|B) = (P(B|A) * P(A)) / P(B)
    * Probability that A is true given B is true: P(A|B)
    * Probability that you survived if you had a gun: P(lived|gun)
    * Probability that you had a gun if you survived: P(gun|lived)
    * Observed numbers: P(lived) = 6/10, P(gun) = 3/10, P(gun|lived) = 2/6
    * Bayes: P(lived|gun) = ((2/6) * (6/10)) / (3/10) -> (2/10) / (3/10) -> 2/3
- A/B Testing: Given a customer has seen/done/bought B, will they do/buy A
    * Decide experiment duration, date, and the change (keep change small)
        * Design the change before proceeding; if not possible, can't continue
    * Decide the number of users for Control group and Treatment group
    * Decide the key performance indicators (KPIs) that will provide the answer
    * Perform the split randomly and control for various bias (ex: time of day)
    * Do not change the experiment mid-way or else you'll contaminate/bias it
    * At experiment conclusion, draw up findings report and recommendations
- Get P(A|B) of dataset: `(df["A"] & df["B"]).sum() / (df["B"].sum() / len(df))`
    * Get P(A) given 2+ cols: `(df["A"] & mask).sum() / (mask.sum() / len(df))`
    * Low probability here indicates "A" outcomes are anomalous!
### Theoretical Distributions
- "Law of Large Numbers": larger sample brings sample mean closer to theoretical
- **Uniform**: equal likelihood of all outcomes (dice rolls)
    * Not very useful for our purposes
    * Recipe: `stats.randint.rvs(gte_val, lt_val, size=(10,10))`
    * P(A) = 1 / len(Options)
- **Binomial**: two outcomes (coin flips)
    * Not very useful for our purposes
    * Recipe: `stats.binom.rvs(tries, chance_to_win, size=(10,10))`
    * P(A) = `stats.binom.pmf(wintarget, tries, chance_to_win)` (discrete)
- **Normal**: outcomes congregating on one value (bell curve)
    * Very useful if we expect a normal distribution for something
    * Recipe: `stats.norm.rvs(center, size_one_stdev, size=(10,10))`
    * P(A) = `stats.norm.pdf(mark, center, size_one_stdev)` (continuous)
    * Between points: `stats.norm.cdf(0) - stats.norm.cdf(-1)` (AUC)
    * Strategy: Identify mean and stdev, build distribution
    * Central Limit Theorem: increase sample size, stats metrics get more normal
- **Poisson**: events over time (probability of an outcome in a time interval)
    * Useful for time-related events; mu is average events per time interval
        * With Poisson, lambda and mu are the same value
    * Recipe: `stats.poisson.rvs(mu, size=(10,10))`
    * P(A) = `stats.poisson.pmf(x, mu)` (discrete)
    * Between counts: `stats.poisson.cdf(5, 2) - stats.poisson.cdf(3, 2)` (AUC)
        * "3 to 5 events when the average is 2 events for that time interval"
    * Strategy: Identify avg event count for time interval, build distribution
    * Peak of distribution is always the lambda value (average count)
- **Exponential**: wait time probability for Poisson event (time between events)
    * Useful for time-related events; lambda is average events per time interval
    * Recipe: `stats.expon.rvs(scale=events_per_interval, size=(10,10))`
    * P(A) = `stats.expon.pdf(x, scale=events_per_interval)` (continuous)
    * Between times: `stats.expon.cdf(4, scale=2) - stats.expon.cdf(1, scale=2)`
        * "Between minute 1 and minute 4 when events are (avg) twice per minute"
    * Strategy: Identify avg event count for time interval, build distribution
- **Geometric**: probability of consecutive failures (failed attempts)
    * Useful when calculating probability of failing x times (CDF)
    * Recipe: `stats.geom.rvs(success_chance, size=(10,10))`
    * P(A): `stats.geom.pmf(attempt_when_successful, fail_chance)`
    * Between attempts: `stats.geom.cdf(4, 0.3) - stats.geom.cdf(2, 0.3)`
        * "2 to 4 attempts when the success chance is 30%"
    * Strategy: Groupby each actor, avg successful attempt #, build distribution
- **t-Distribution**: Wider normal distribution (sharper peak, wider flanges)
    * Increasing degrees of freedom makes it look more like normal distribution
- **Log-Normal**: right-skewed for normal (0 to infinite, normal)
    * When you can't go below a number, but the distribution is basically normal
    * Lots of real-world examples for this
- Lots more distributions... check scipy documentation for stats module
### Methods for Distributions
- Probability from theoretical distribution: `dist.method()`
    * Chance of specific outcome: `dist.pmf(discrete)`, `dist.pdf(continuous)`
    * Area larger than a mark: `dist.sf(num)`, `dist.isf(proportion)`
    * Area less than or equal to a mark: `dist.cdf(num)`, `dist.ppf(proportion)`
- Probability from discrete records: `vc = s.value_counts(normalize=True)`
    * Chance of specific outcome: `vc.loc[x] if x in vc.index else "Not found"`
    * CDF and SF: `cdf = vc.loc[(vc.index <= x)].sum()`, `sf = 1 - cdf`
    * P(Between Marks): `vc.loc[(vc.index > left) & (vc.index < right)].sum()`
- Probability from continuous records: `t = s.rank(method='average', pct=True)`
    * Chance of specific outcome: draw density and plot point? hmm. thinking...
    * Compare to value: `cdf = (s <= x).mean()`, `sf = 1 - cdf`
- Proportions of outcomes: `vc = df[["A","B"]].value_counts(normalize=True)`
    * `vc.loc[("lived","gun")]` (previous step orders multi-index as "A","B")

[[Return to Top]](#table-of-contents)







<!-- 
#     #                                                         
#     # #   # #####   ####  ##### #    # ######  ####  #  ####  
#     #  # #  #    # #    #   #   #    # #      #      # #      
#######   #   #    # #    #   #   ###### #####   ####  #  ####  
#     #   #   #####  #    #   #   #    # #           # #      # 
#     #   #   #      #    #   #   #    # #      #    # # #    # 
#     #   #   #       ####    #   #    # ######  ####  #  ####  
                                                                
#######                                     
   #    ######  ####  ##### # #    #  ####  
   #    #      #        #   # ##   # #    # 
   #    #####   ####    #   # # #  # #      
   #    #           #   #   # #  # # #  ### 
   #    #      #    #   #   # #   ## #    # 
   #    ######  ####    #   # #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Hypothesis Testing
- Testing normality, independence, difference of means, correlation, etc
- Involves setting null and alternate hypothesis, then conducting test
- Parametric tests (strict requirements) vs non-parametric tests (loose)
    * Each test has assumptions that must be met for the test to be valid
- Errors: Type I (falsely-reject null), Type II (falsely-accept null)
    * False Positive Rate: probability of a Type I error
    * False Negative Rate: probability of a Type II error
### Metrics
- Consider applying all of the following in a metrics pivot table
- Sum of Squares: `sum((col - col.mean()) ** 2)`
- Variance: `(Sum of Squares) / col.count()`
- Standard Deviation (STD): `(Variance) ** 0.5`
- Mean Absolute Deviation (MAD): `mean(abs(col - col.mean()))`
- Z-Scores: `(col - col.mean()) / (Standard Deviation)`
- Quartiles: `index = 0.25 * (len(col) - 1); col[index]`
    * First, second, third quartiles (cutpoints): 0.25 (Q1), 0.5 (Q2), 0.75 (Q3)
    * Use interpolation if index not an int; 1.25 is 25% of the diff between 1,2
- Interquartile Range (IQR): `Q3 - Q1`
- IQR Outliers: `(col < (Q1 - (1.5 * IQR))) | (col > (Q3 + (1.5 * IQR)))`
### Tests
- The following tests come from Python's stats library, `from stats import ...`
- Anderson-Darling: test normality, `anderson(col)`
- Chi Square: independence of samples, `chi2_contingency(observedvals_crosstab)`
- One-Way ANOVA: compare samples for mean, `f_oneway(samp1.y, samp2.y, ...)`
    * Non-parametric: Kruskal-Wallis H test, `kruskal(samp1.y, samp2.y, ...)`
- T-Test: compare means of independent samples, `ttest_ind(samp1.y, samp2.y)`
    * Non-parametric: Mann-Whitney U test, `mannwhitneyu(samp1.y, samp2.y)`
- T-Test: compare means of sample vs population, `ttest_1samp(samp.y, pop.y)`
    * Non-parametric: Mann-Whitney U test, `mannwhitneyu(samp1.y, samp2.y)`
- T-Test: compare means of sample before vs after, `ttest_rel(past.y, future.y)`
    * Non-parametric: Wilcoxon signed-rank, `wilcoxon(past.y, future.y)`
- Pearson Correlation: correlation coefficient of linear vars, `pearsonr(x, y)`
    * Non-parametric: Spearman Correlation, `spearmanr(x, y)`
### Situations
- X categoricals against y categorical: chi2; independent cells, cells are > 5
    * Degree of Freedom: `(num_cols - 1) * (num_rows - 1)`
- X categoricals against y continuous: t-test; 1samp/2samp, normality, variance
    * One-sample t-test: when comparing a sample to a general population mean
    * Two-sample t-test: when comparing a distinct sample to another sample
- X conts against X conts or the y cont: corr; linearity, normality / monotonic
    * Correlation statistic: strength and direction of correlation (-1.0 to 1.0)
    * Strength indicators: similar rate of change, both monotonic / polytonic
    * Always plot correlations to check for linearity
    * Can transform one or both: logarithmic, square root, inverse (1/col), more

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                           
#     # ######  ####   ####  #####    ##   ##### #   ##   #      
#       #      #    # #      #    #  #  #    #   #  #  #  #      
#  #### #####  #    #  ####  #    # #    #   #   # #    # #      
#     # #      #    #      # #####  ######   #   # ###### #      
#     # #      #    # #    # #      #    #   #   # #    # #      
 #####  ######  ####   ####  #      #    #   #   # #    # ###### 
                                                                 
   #                                               
  # #   #    #   ##   #      #   #  ####  #  ####  
 #   #  ##   #  #  #  #       # #  #      # #      
#     # # #  # #    # #        #    ####  #  ####  
####### #  # # ###### #        #        # #      # 
#     # #   ## #    # #        #   #    # # #    # 
#     # #    # #    # ######   #    ####  #  ####  
-->

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
```python
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
```python
import geopandas as gpd
# initialize two geodataframes and join the plots
d1 = gpd.sjoin(gdf1, gdf2, op="contains")  # gdf2 entirely inside gdf1 boundary
d2 = gpd.sjoin(gdf1, gdf2, op="intersect") # gdf2 is inside or on gdf1 boundary
d3 = gpd.sjoin(gdf2, gdf1, op="within")    # backwards "contains"
print(len(d1))                             # number of gdf2 things inside gdf1
```
```python
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
    legend_name="Schools per km squared by School District"
).add_to(m)
```
### Shapely
- Set correct coord reference system for Geopandas for max accuracy

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

--------------------------------------------------------------------------------
<!-- Polished -->
## Clustering
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Anomaly Detection
- Detect a bad action
- Detect a normal action at a bad time
- Detect a normal action which is too big or too small
- Detect normal actions that are overlapping when they should be separate
- Detect normal actions that combine into a bad chain
- Detect normal actions that happen too quickly or too slowly
- Detect normal actions that deviate from a baseline of actions
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
### Actions: Overlapping Sessions
```python
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
flip_last = False                             # Handle edge case
if s[len(s) - 2] == 0 and s[len(s) - 1] == 1:
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
### Unsupervised Techniques
- Isolated Forest: score observations for how anomalous they are from neighbors
    * Good when anomalies expected in train, good at high-dimensionality data
    * Specify assumed amount of contamination (ex: 20% anomalous)
- One-Class Support Vector Machine (SVM): train on normal, classify normal/not
    * Good when train is entirely normal (don't contaminate train with anomaly)
    * Regularization (C), anomaly boundary (Nu), choose kernel function
- Autoencoders: train neural network on normal, anomaly: high reconstruct error
    * Good when data is images/etc and when train is entirely normal

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

--------------------------------------------------------------------------------
<!-- Polished -->
## Natural Language Processing
- Designed for normalizing, analyzing, and modeling bodies of text
- Useful for keyword and sentiment analysis, classification, anomaly detection
- Often involves factorization of sparse matrices (decompose then approximate)
- Natural Language Toolkit (NLTK): https://www.nltk.org/index.html
### Bag of Words (BoW)
- NLP preprocessing; turn words into numerical values for model training
- Sparse matrix for each document (index) and a vector of each word (column)
- Count Vectorization (CV); Term Frequency * Inverse Document Frequency (TFIDF)
    * CV: fast/explainable; word counts; doesn't consider word importance
    * TFIDF: slow/complex; word weights; keeps importance and filters stopwords
### Cosine Similarity
- Compare one document's similarity to another using a mathematical measure
    * `dot_product(doc1, doc2) / (sqrt(sum(doc1 ** 2)) * sqrt(sum(doc2 ** 2)))`
- Result is between -1 and 1; 1 means identical, -1 means entirely opposite
### Normalizing String Features
1. Perform Unicode normalization with one of the following: NFD, NFC, NFKD, NFKC
1. Encode from normalized text into ASCII
1. Decode from ASCII into UTF-8
1. Remove special characters using REGEX: replace /[^a-z0-9'\s]/ with ""
1. Replace newline characters with single space to flatten text
1. Perform tokenization using a tokenizer
1. Delete stopwords (words that need to be deleted or that aren't useful)
1. Perform stemming or lemmatization to reduce word variations to their root
1. Rejoin the resulting roots into a single document and/or corpus (if required)
### Keyword Analysis
1. Perform cleaning steps from before (tokenize on words)
1. Calculate character count and word count for every document
1. Plot scatterplot of charcount vs wordcount (Classification: color by target)
1. Create a corpus of all cleaned documents
1. (Classification) Also split docs by class and create a corpus for each subset
1. Get word counts per corpus (index is each word, cols are counts per corpus)
1. Perform N-Gram value counts on each corpus and concat to the above dataframe
1. (Classification) Add cols for class-wise, word-wise proportions
1. (Classification) Sort data by proportion, plot stacked barchart (ex: best 25)
1. Plot a wordcloud with an optional black-white picture mask
### Sentiment Analysis
1. Perform cleaning steps from before (tokenize on sentences)
1. Instantiate a pre-trained sentiment analyzer
1. Calculate sentiment score per sentence, calc average sentiment across scores
1. (Classification) Group sentiment score averages by target class
## Python NLP Libraries
- NLTK: `from nltk import tokenize, porter, stem, corpus.stopwords`
    * Choose a specific method under each of these, ex: TweetTokenizer
    * Use `sent_tokenize` instead of `tokenize` for sentence tokenization
- NLP at speed (faster than NLTK): spaCy, `import spacy`
- Unicode normalization: `doc = UNICODE.normalize().encode().decode()`
- N-Grams: `bigrams = nltk.ngrams(corpus_listlike, 2)`
- Text sentiment: `from nltk.sentiment import SentimentIntensityAnalyzer`
    * Score: `SentimentIntensityAnalyzer().polarity_scores(sentence_token)`
- Wordclouds: `import wordcloud.WordCloud, PIL.Image, matplotlib.pyplot`
    * Plotfreq: `img = WordCloud().generate_from_frequencies({"hi":29,"yo":8"})`
    * See: https://github.com/amueller/word_cloud/blob/master/examples/parrot.py
- Topic modeling: `from gensim import corpora, models, similarities, downloader`
- Fuzzy matching: `thefuzz.process.extract("matchme", listlikehere, limit=None)`
    * Return list of match score tuples like: [(string1, score, rank), ...]
- Bag of words: `import sklearn.feature_extraction.text`
    * Count Vectorization and TF-IDF Vectorization
- Read text from PDFs: `from pdfminer.high_level import extract_text`

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
                    #     # ####### ######  ####### #       
                    ##   ## #     # #     # #       #       
                    # # # # #     # #     # #       #       
                    #  #  # #     # #     # #####   #       
                    #     # #     # #     # #       #       
                    #     # #     # #     # #       #       
                    #     # ####### ######  ####### ####### 
                                        
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# MODEL


<!--
#######                                          
#       ######   ##   ##### #    # #####  ###### 
#       #       #  #    #   #    # #    # #      
#####   #####  #    #   #   #    # #    # #####  
#       #      ######   #   #    # #####  #      
#       #      #    #   #   #    # #   #  #      
#       ###### #    #   #    ####  #    # ###### 
                                                 
######                                                    
#     # ###### #####  #    #  ####  ##### #  ####  #    # 
#     # #      #    # #    # #    #   #   # #    # ##   # 
######  #####  #    # #    # #        #   # #    # # #  # 
#   #   #      #    # #    # #        #   # #    # #  # # 
#    #  #      #    # #    # #    #   #   # #    # #   ## 
#     # ###### #####   ####   ####    #   #  ####  #    # 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Feature Reduction
- Get rid of features that contain only one unique value
- Get rid of features that are duplicates or otherwise match other features
- Get rid of features that have nulls not worth handling (or drop rows)
    * Python: `df.dropna(axis=1, thresh=(len(df.columns)*0.9))`
- Get rid of features that strongly correlate with others (multicollinearity)
    * Variance Inflation Factor (VIF); features with >10 VIF should be dropped
- Select features using linear regression coefficients (furthest vals from zero)
- Select features using SelectKBest, Recursive Feature Engineering (RFE), RFECV
    * SelectKBest: evaluate estimator once with n features
    * RFE: evaluate estimator, drop worst feature, repeat until n features left
    * RFECV: same as RFE but also with crossvalidation (best across row subsets)
- Can do feature reduction with LassoCV regularization (increases bias/underfit)
    * Pass `sum(lcv.coef_ != 0)` as n_features parameter for SelectKBest or RFE
- Get rid of features that have no analytic value (ex: observation identifiers)
- Apply matrix factorization like PCA, TruncatedSVD, or NMF
    * Matrix factorization: decompose a matrix, use results for approximation
    * Matrix decomposition: express one matrix as multiple smaller matrices
    * Matrix approximation: use small imprecise matrices to predict large matrix
### Linear Algebra for Feature Reduction
- Tensor: any-dimensional mathematical object, ex: 1D tensor is a vector
- Vector: one-dimensional array describing an observation in multiple dimensions
- Vector Space: a collection of vectors that can be added/multiplied, with rules
- Rank: dimensions of the vectors in a vector space (describes rows and columns)
- Matrix: two-dimensional array that maps actions on vectors or vector spaces
- Inverse Matrix: multiplying this and a matrix results in the identity matrix
    * Not all matrices are "invertible" like this
- System of Linear Equations: grouping of equations like `2x + y = 5; x - y = 3`
    * Explicitly not polynomial, should only have one solution for variable vals
- Linear Transformations: a function that linearly maps one matrix to another
- Eigenvalues/Eigenvectors: scaling one matrix to another using scalar/vector
    * Explained variance ratio: `eigenvalue / total_variance` (between 0 and 1)
- Determinant: getting the area of a 2D matrix, the volume of a 3D matrix, etc
- Inner Product Space: describing shape (length, angles, etc) of a vector matrix
- Orthogonality: where two vectors have an inner product of zero
- Diagonalization: convert original matrix to a diagonal matrix: `[[5,0],[0,3]]`
    * Diagonal matrix is eigenvalues; apply to eigenvector matrix
- Singular Value Decomposition (SVD): decompose matrix into eigen vectors/values
    * This reveals the "intrinsic dimension" / "information" of a matrix
- Covariance: how two vectors change together (checking linear correlation)
- Covariance Matrix: how every vector changes with every vector in a matrix
    * 3D version: [[COVxx,COVxy,COVxz],[COVyx,COVyy,COVyz],[COVzx,COVzy,COVzz]]
### Principal Component Analysis (PCA)
- Feature reduction strategy, designed for wide non-sparse datasets
    * Also useful for de-correlating features due to non-linear transformation
- Involves eigenvectors/eigenvalues of a dataset's covariance matrix
    * Principal Component (PCs) are eigenvectors; original data becomes this
    * Eigenvalues describe how valuable a PC is (larger eigenvalue is better)
- Select some of the eigenvectors based on eigenvalue (how much they contribute)
    * Descending-sort eigenvectors by their eigenvalue, scree plot, elbow method
    * Calc each's explained variance ratio, cumsum, plot, choose using threshold
### Truncated Singular Value Decomposition (TruncatedSVD)
- Feature reduction strategy, especially designed for sparse matrices
    * PCA starts with calculating a covariance matrix, destroying "sparsity"
    * SVD multiplies the original data, preserving "sparsity" and zeroing data
- SVD itself is not a data reduction strategy; TruncatedSVD uses SVD for that
    * SVD exactly-decomposes the original matrix into three smaller matrices
    * Original Matrix = Column Eigenvectors * Eigenvalues * Row Eigenvectors
- TruncatedSVD follows the same eigenvalue/eigenvector selection process as PCA
    * Cumulative explained variance threshold or elbow method to reduce features
    * You can also use the count of nonzero eigenvalues for component count
### Non-Negative Matrix Factorization (NMF)
- Feature reduction strategy, meant for **non-negative** sparse matrices
    * Like TruncatedSVD, also better than PCA due to PCA's flaws with "sparsity"
    * Outperforms TruncatedSVD on non-negative data (explicit non-negative rule)
    * Slower than TruncatedSVD due to use of loss function and training steps
- Decomposes to parts-based "metafeatures" matrix and an activation-mask matrix
    * Imagery: *parts* of a face, *activated* for smile, *deactivated* for frown
    * Text: *parts* of sentences, *activated* for happy, *deactivated* for angry
- NMF approximates a V matrix by two smaller matrices, W and H; V ~= W * H
    * V matrix: original data; each column is observation, each row is feature
    * W matrix: key parts of original data; each column is "basis vector"
    * H matrix: activation mask for W matrix; each column is "weights"/"gains"
    * All three matrices must have non-negative values
- NMF follows the same eigenvalue/eigenvector selection process as PCA
    * Cumulative explained variance threshold or elbow method to reduce features

[[Return to Top]](#table-of-contents)







<!-- 
#     #                            #####                                        
##   ##  ####  #####  ##### #        #    #####    ##   # #    # # #    #  #### 
# # # # #    # #    # #     #        #    #    #  #  #  # ##   # # ##   # #    #
#  #  # #    # #    # ####  #        #    #    # #    # # # #  # # # #  # #     
#     # #    # #    # #     #        #    #####  ###### # #  # # # #  # # #  ###
#     # #    # #    # #     #        #    #   #  #    # # #   ## # #   ## #    #
#     #  ####  #####  ##### #####    #    #    # #    # # #    # # #    #  #### 
-->

--------------------------------------------------------------------------------
<!-- Polished -->
## Model Training
- Epoch: a round of data shuffle/split, model fit, evaluation, parameter update
    * Use epochs to control training time, prevent overfit, "reach" convergence
- Convergence: error improvement between epochs slows down, or error is accepted
    * Early stopping: when error improvement between epochs slows, halt training
    * Some models reach hyperparameter limits and stop (ex: tree max depth)
    * Other models like KNN and Naive Bayes have no iterative training process
- Adaptive learning rate: improve model past plateau even if it may not converge
    * Upon reaching plateau before convergence/epochs, throw a wrench in random
- Stochastic Gradient Descent (SGD): optimization for iterative model fitting
    * Tweaks model parameters in opposite direction of loss gradient
    * Uses small random subset/batch of the training data (stochastic)
### Encoding
- Models require numerical values; we can convert text to numbers with encoding
- Change string values to one-hot representation, ex: `x="cat"` -> `is_cat=True`
    * Python: `pd.get_dummies(df[["col1","col2]], drop_first=True)`
- Change string values to ordinal values, ex: `cold, warm, hot` -> `0, 1, 2`
    * Python: `df["col3"].replace({"cold":0, "warm":1, "hot": 2})`
### Scaling
- Some models rely on raw distances; scaling numerical values is very important
    * Always scale for KNN and K-Means (distance-based); no need for tree-based
- This is quietly very important in certain machine learning models
    * Without scaling, expressing height in inches vs feet will affect model
    * With scaling, different units are equalized; improves model performance
    * Scaling "equalizes density of continuous features for machine learning"
    * Normalizes Euclidian Distance calcs: `d = sqrt((x1 - x2)^2 + (y1 - y2)^2)`
    * Split data before scaling; fit on train; transform all splits
- Example: make 1-10 mean the same to a machine learning model as 1-1000
    * A model simply sees a value shift of 1->400 as more significant than 1->4
    * But, going from 1->4 in 1 (minimum) to 10 (maximum) is 40% shift in range
    * Going from 1->400 in 1 (minimum) to 1000 (maximum) is also 40% shift
    * So, shifting 1->400 and 1->4 should be considered equally; hence, scaling!
    * Scaling converts both 1-1000 and 1-10 to a consistent expression like 0-1
    * In 0-1 scale (MinMaxScaler), 4 and 400 are now both 0.4; no numerical diff
    * This is practically required in distance-based models
    * There are other scaling methods, each with their own considerations!
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
### Cross-Validation (CV)
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
### Grid Search CV
- Grid Search mixes cross validation with your hyperparameter tuning
- We pass the hyperparameter grid and K folds, and it trains/evals each model
- Set `n_jobs = -1` to use multi-core processing! Speed gains!
- For even more speed gains: try `RandomizedSearchCV`
    * Doesn't try out the entire grid; "hones in" on the best, faster
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Classification
- Supervised machine learning, predict which category something belongs to
- Ultimately classifiers always take an input and map it to a discrete output
- Different classification algorithms use different mapping methodologies
### Features for Classification
- Convert continuous/ordinal columns to categorical ones, ex: binning
    * Can use histograms to determine these groupings
- Use chi-square tests to find which categorical features are related to target
    * Can use heatmaps/mosaic plots to visualize these crosstabs
- One-hot encode all selected columns for modeling
- Features that correlate with other features contribute to multicollinearity
    * Multicollinearity reduces model performance
    * Reduce multicollinearity by thresholding variance inflation factor (VIF)
- You can always train a model first and evaluate which features were best!
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
- **Voting Classifier**
    * Train multiple classifiers separately, have them vote on each row's class
- **Bagging Classifier**
    * Train classifiers with data bootstraps (random rows w/ replacement)
    * Can enable "out of bag" subset for validation split
### Evaluating Classifiers
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
- **Cumulative Gains:** How many samples required to get certain amount of class
    * `scikitplot.metrics.plot_cumulative_gain(actuals, preds)`
- **Lift Curve:** How many samples required for model to beat random guessing
    * Good model has steep rise on left of lift curve (with fewer samples)
    * `scikitplot.metrics.plot_lift_curve(actuals, preds)`

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

--------------------------------------------------------------------------------
<!-- Polished -->
## Regression
- Supervised machine learning, predict the numerical value of something
- Ultimately regressors always take an input and plot it on a line to get output
- Different regression algorithms plot different lines and use different loss
### Features for Regression
- Keep features that highly-correlate with the target: `df.corr()`
- Interactions are awesome! They can have better correlations; `s1 * s2`
    * Example: `df["cat1_col2"] = (df["col1"] == "cat1") * df["col2"]`
- Features that correlate with other features contribute to multicollinearity
    * Multicollinearity reduces model performance
    * Reduce multicollinearity by thresholding variance inflation factor (VIF)
    * Can transform features by taking log, exponent, PCA, etc of the values
- Scatterplots can show outliers; consider removing outlier datapoints
    * Removing outliers can improve model performance
- You can always train a model first and evaluate which features were best!
### Training Regressors
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
### Evaluating Regressors
- Residuals, MSE, RMSE, SSE, ESS, TSS, r2
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Time Series (TS)
- Time-focused exploration and modeling, sometimes involving machine learning
- Leverage TS if your analytic goal involves the time component of your data
    * Forecast what a numerical value will be after a certain amount of time
    * Identify anomalies in how a numerical value changed over a given period
    * Put certain behaviors of a moving numerical value into specific categories
### Interpolation and Resampling
- Fixing or adjusting TS data in order to meet various objectives
- Interpolation: filling gaps in TS data, like sensor downtime in hourly temps
    * Forward-propagate previous value, backward-propagate next value across gap
    * Take the value of the nearest non-null value into the null values in gap
    * Draw line across gaps and plot values along the line (linear or quadratic)
- Upsampling: up the precision/observations of TS data, ex: from daily to hourly
    * Involves creating synthetic data; synthetic values require interpolation
- Downsampling: decrease the precision of TS data, ex: from hourly to daily
    * Involves aggregating values using mean, sum, etc depending on situation
### Stationarity
- Important concept for TS modeling which commonly requires addressing
- TS data is typically not stationary (has trends over time) which is not ideal
    * Non-stationary TS data: predictability issues, violates model assumptions
    * Stationary TS data: focuses on measurable drivers for better modeling
- Stationary definition: TS data has constant mean, variance, and autocovariance
    * Constant mean: average value shouldn't have a systematic (up/down) trend
    * Constant variance: spread of values shouldn't grow/shrink systematically
    * Constant autocovariance: pattern of inter-value correlations is consistent
- Establish stationarity with differencing, transformation, seasonal adjustment
    * Differencing: every value has its previous value subtracted
    * Transformation: take square root, logarithm, Box-Cox, etc of values
    * Seasonal differencing: a season of values has previous season subtracted
    * Overdifferencing: when you remove valuable trends and relationships
- Test for stationarity using Augmented Dickey-Fuller (ADF) test or KPSS test
    * Also check visually, or use (Partial) Autocorrelation Function (ACF/PACF)
### Features for Time Series
- Timestamp decomposition to create observation's day, hour, minute, etc fields
- Seasonal decomposition to create month-in-year, day-of-week, etc features
- One-hot encoding for opening-hour, closing-hour, lunch-hours, etc
### Bollinger Bands
- Outliers from a rolling average (mid band) using upper/lower band cutoffs
    * Outliers shown by tuning k value (usually 2 or 20 standard deviations)
- Upper band: `mid_band + (k * std(mid_band))`
- Lower band: `mid_band - (k * std(mid_band))`
- Volatility (%b): `(actuals - lower_band) / (upper_band - lower_band)`
- Outliers: actuals where (volatility > 1) or (volatility < 0)
### Time Series Modeling
- Seasonality, fluctuation cycles, and autocorrelation for forecasting
- **Last Observed Value**
- **Simple Average**
- **Moving/Rolling Average**
    * Average of a given period as the prediction; usually last 3 or last 7 days
- **Previous Cycle** 
    * Slice the last cycle and use it as the prediction; usually last year
- **Autoregressive Integrated Moving Average (ARIMA)**
    * Forecast using an adjusted moving average
    * Use ACF/PACF to get lag values for AR (p) and MA (q), get differencing (d)
    * Seasonal ARIMA also includes valuable seasonal decomposition
- **Holt's Linear Trend**
    * Calculate linear regression line of previous cycles, snap-on as prediction
    * Use smoothing level and smoothing slope
    * Holt-Winters Seasonal Method also includes valuable seasonal decomposition
- **Autoregressive Conditional Heteroskedasticity (ARCH)**
    * Focuses on modeling non-constant variance (heteroskedasticity)
    * Generalized ARCH addresses complex dependencies causing heteroskedasticity
- **Vector Autoregression (VAR)**
    * Draw regression line onto two different TS valuesets (regress scatterplot)
    * Goal is to draw new conclusions with multiple TS integrated
    * Use Granger Causality Test to check if one TS can predict another TS
    * Cointegration: 2+ TS produce stationary TS when combined (Engle-Granger)
    * Error correction model (ECM) corrects for short deviations in cointegrated
- **Facebook Prophet's Model**
    * Next cycle based on previous cycles; good, but hard to install/get working
    * See also RNNs like LSTM or even random forests / gradient boosting
### Strategy
1. Understand the nature of your data
    * Is it years of information? months? weeks? days? hours?
    * From visualizations, are there immediate noticeable trends or seasonality?
1. Fix the time field if necessary
1. Downsample (aggregate) or upsample (add rows) based on the analytic goal
    * EX: Downsample from minute-by-minute transactions to daily totals
    * EX: Upsample **patchy** minute-by-minute transaction data to fill gaps
1. Use rolling averages for seasonal data and autocorrelation (shifts and diffs)
    * Differencing to try to get stationarity
1. Visualize various metrics for insights
1. Split into train and test using seasonality (if possible), or by percentage
1. Train models using training split then predict the future
    * Predict test using train
1. Evaluate each model's RMSE, best model has lowest RMSE
1. Use best model for future forecasting

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

--------------------------------------------------------------------------------
<!-- Polished -->
## Neural Networks (NN)
- Design neuron lattice and set randomization/evaluation; result is "black box"
- NN is different from traditional ML approaches
    * Traditional supervised ML training results in feature weights (readable)
    * Traditional unsupervised ML models shapes using set algorithms (readable)
    * NN model training involves auto-creating features in epochs (unreadable)
    * Both traditional ML and NN still use normal metrics like accuracy, r2
- Good cases for NNs: images, video, sound, NLP (large non-tabular data)
- Stick with traditional modeling where possible for interpretability
### Neural Network Design
- Neural node: basic building block of neural networks
    * A node receives a value and performs a weighted mathematical operation
    * Weights are auto-adjusted during NN training and can be exported/imported
- Layer: a processing step in a neural network, can be dense or sparse
    * Dense layer: every neuron in layer connects to every neuron in other layer
    * Sparse layer: when a layer is not dense, ex: CNN convolutional layers
- Input layer: simply receive individual, multiple, or entirety of observations
- Output layer: simply output for task, ex: classification, regression, etc
- Hidden layer(s): contains weighted neural nodes to model complex patterns
    * Activation: non-linear modification of hidden layer to assist in modeling
    * Weighted neural node: essentially an engineered feature
- Compilation: set loss function, optimizer, eval metric, and model update plan
    * Evaluation metrics are largely the same between NN and non-NN modeling
- When training, NNs use backpropagation to calc gradients, optimizer to update
    * Backpropagation works backward to calculate loss gradient between layers
    * Optimizers use these gradients to update weights to try to decrease error
### Layer Activations
- Activations put non-linearity into NN to enable learning complex patterns
- Sigmoid (Logistic): Map to between 0 to 1; binary-class; vanish; unoptimal
- TanH (Hyperbolic Tangent): Map to between -1 to 1; vanish; more optimal
- Rectified Linear Unit (ReLU): prevents reducing gradients to small values
    * Fixes vanishing gradients, but might cause exploding gradients
    * Use He weight intialization to also help prevent exploding gradients
    * Use LeCun weight initialization to manage activation/gradient variance
- Leaky ReLU: prevents dead neurons by force-applying activation to `x <= 0`
- Parametric ReLU (PReLU): Leaky ReLU but learn activation during training
- Softmax: all values between 0 to 1 and their outputs sum to 1; multi-class
- Swish: Sigmoid multiplied by input value; similar to ReLU but smoother
- Exponential Linear Unit (ELU): similar to ReLU but smoother
- Hard Sigmoid: simple version of sigmoid due to being "piecewise linear"
- Mish: mix TanH and Softplus; similar to ReLU but smoother
### Neural Network Loss Functions
- Cross-Entropy: binary-class
- Categorical Cross-Entropy: multi-class
- Sparse Categorical Cross-Entropy: multi-class but memory efficient
- Weighted Cross-Entropy Loss: imbalanced multi-class
- Mean Squared Error (MSE): regression using MSE
- Mean Absolute Error (MAE): regression using MAE
- Huber: regression with condition for outliers and for non-outliers
- Triplet: metric learning
- Contrastive: verifying match
- Custom loss is also possible, ex: using MSE with L1 or L2 regularization
### Training Optimizers
- Stochastic Gradient Descent (SGD): uses loss gradient between small batches
    * Simple, fast, common; great where simple optimizer is fine
    * Tune learning rate carefully (or else slow convergence/oscillations)
- SGD with Momentum: use moving average of previous gradients
    * All the benefits of SGD with accelerated convergence
- Adaptive Gradient (AdaGrad): use historical gradient, lessen large gradients
    * Good for sparse data or when parameters have varying importance
    * Learning rate may become too small over time
- Root Mean Square Propogation (RMSprop): AdaGrad plus prevent small learn rate
    * Good for sequential datasets
- Adadelta: RMSprop but remove the learning rate hyperparameter (auto-adjust it)
- Adaptive Moment Estimation (Adam): Combine SGD+Momentum and RMSprop
    * Good for pretty much everything and is typically the default option to use
    * Can be somewhat expensive and may lead to overfitting
- Nesterov-Accelerated Adaptive Moment Estimation (Nadam): add Adam and Nesterov
    * Improves convergence rate compared to Adam with few additional downsides
- Limited-Memory Broyden–Fletcher–Goldfarb–Shanno (L-BFGS): if need then read!
- Vanishing gradient problem: gradients shrink to zero in long backpropogation
    * Opposite is exploding gradient problem, too-large gradients; same issues
    * Slows down model learning because earlier layers receive smaller/no update
    * Destroys/forgets long-term dependencies in sequential and deep FNN models
    * Fix: certain activation functions, weight initializations, gates, batches
### Available Neural Networks
- **Feedforward (FNN)**
    * Most basic NN; pass each input independently into hidden layers to output
    * Mainly used for classification or regression tasks on tabular data
    * Processes each input independent of other inputs
    * Typically uses backpropagation to minimize the loss function
    * Single-Layer Perceptron (SLP) is an FNN with no hidden layers
    * Multi-Layer Perceptron (MLP) is an FNN with at least one hidden layer
- **Radial Basis Function Network (RBFN)**
    * Uses one hidden layer containing "radial basis neurons"
- **Recurrent Neural Network (RNN)**
    * Take previous output as part of a new input
    * Mainly used when data has a logical sequence, ex: video, sound, language
    * Processes inputs sequentially (order of inputs matters, ex: time series)
- **Long Short Term Memory (LSTM)**
    * Uses memory cells to keep info, uses input gate, forget gate, output gate
    * Sequential model like RNN/GRU, gates address vanishing gradient problem
    * Employs attention mechanisms to focus on most relevant parts of input
- **Gated Recurrent Unit (GRU)**
    * Uses update gate and reset gate to control how info flows through network
    * Sequential model like RNN/LSTM, gates address vanishing gradient problem
    * Similar to LSTM but simpler (fewer gates) and therefore more efficient
- **Convolutional (CNN)**
    * Apply filters or kernels to detect patterns (edges, textures, shapes, etc)
    * Specialized for grid-like data like images/videos (ex: object detection)
    * Processes each input independent of other inputs
- **Capsule Networks (CapsNets)**
    * Use capsules to assist generalizing to new viewpoints
    * Improves on CNN for image recognition with important spatial relationships
- **Autoencoder (AE)**
    * Uses an encoder to compress input and decoder to reconstruct from compress
    * Great for dimensionality reduction, denoising, and anomaly detection
- **Self-Organizing Map (SOM)**
    * Unsupervised dimensionality reduction into typically 2-D grid
    * Used for visualizations, clustering, and feature extraction
- **Siamese Networks**
    * Uses two or more identical sub-networks to compare one thing to another
    * Used for verification of faces and signatures
### Image Classification
1. Split the dataset into train, validate, test as usual
1. Reshape image pixels to be a one-dimensional vector
    * NumPy: `X.reshape(len(X), pixels_wide * pixels_tall)`
1. Normalize all image pixels to decimal value by dividing their value by 255
1. Create Sequential model
1. Add input layer with input shape of pixelcount, choose neurons/activation
1. Add any additional hidden layers with any preferred neuron counts, activation
1. Add output layer with activation and neuron count of unique classes count
1. Compile the model with an optimizer, loss function, and evaluation metric
1. Fit the model on the reshaped training images set
1. Evaluate the model on the validation images set
1. Tune model as necessary (repeat above layer choice steps)
1. When satisfied, run on test images set to see if you've overfitted or not

[[Return to Top]](#table-of-contents)







<!-- 
######                                                                          
#     # ##### # #    # #####  ####  ####   ####  ##### #    # ##### #    # #####
#     # #     # ##   # #     #    # #   # #    # #     ##  ## #     ##   #   #  
######  ####  # # #  # ####  #    # #   # #      ####  # ## # ####  # #  #   #  
#   #   #     # #  # # #     #    # ####  #      #     #    # #     #  # #   #  
#    #  #     # #   ## #     #    # #  #  #    # #     #    # #     #   ##   #  
#     # ##### # #    # #      ####  #   #  ####  ##### #    # ##### #    #   #  
                                                                                
#                                                   
#       #####   ##   ####  #    # # #    #  ####  
#       #      #  #  #   # ##   # # ##   # #    # 
#       ####  #    # #   # # #  # # # #  # #      
#       #     ###### ####  #  # # # #  # # #  ### 
#       #     #    # #  #  #   ## # #   ## #    # 
####### ##### #    # #   # #    # # #    #  ####   
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Reinforcement Learning (RL)
- A combination of modeling with actions and specific rewards and penalties
- Combined system self-trains using rewards and penalties to hone actions
- Often involves neural network modeling with key differences
    * May swap backpropagation with temporal difference learning or Q-learning

[[Return to Top]](#table-of-contents)







<!-- 
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
                ######  ####### ######  #       ####### #     # 
                #     # #       #     # #       #     #  #   #  
                #     # #       #     # #       #     #   # #   
                #     # #####   ######  #       #     #    #    
                #     # #       #       #       #     #    #    
                #     # #       #       #       #     #    #    
                ######  ####### #       ####### #######    #    
                                                
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# DEPLOY


<!--
#######                                               ##    
#       #    # #####   ####  #####  #####  ####      #  #   
#        #  #  #    # #    # #    #   #   #           ##    
#####     ##   #    # #    # #    #   #    ####      ###    
#         ##   #####  #    # #####    #        #    #   # # 
#        #  #  #      #    # #   #    #   #    #    #    #  
####### #    # #       ####  #    #   #    ####      ###  # 
                                                            
######                                                
#     # # #####  ###### #      # #    # ######  ####  
#     # # #    # #      #      # ##   # #      #      
######  # #    # #####  #      # # #  # #####   ####  
#       # #####  #      #      # #  # # #           # 
#       # #      #      #      # #   ## #      #    # 
#       # #      ###### ###### # #    # ######  ####  
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Exports and Pipelines
- Use `from skelarn.pipeline import Pipeline` and save trained pipe to PKL file
    * Access parts using layer names, ex: `("scaler", StandardScaler())`

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                           
#     #  ####  #    # #####   ##   # #    # ###### #####   ####  
#       #    # ##   #   #    #  #  # ##   # #      #    # #      
#       #    # # #  #   #   #    # # # #  # #####  #    #  ####  
#       #    # #  # #   #   ###### # #  # # #      #####       # 
#     # #    # #   ##   #   #    # # #   ## #      #   #  #    # 
 #####   ####  #    #   #   #    # # #    # ###### #    #  ####  
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Containers
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
```docker
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
### Docker Compose
- 

[[Return to Top]](#table-of-contents)







<!-- 
#                                   
#        ####   ####    ##   #      
#       #    # #    #  #  #  #      
#       #    # #      #    # #      
#       #    # #      ###### #      
#       #    # #    # #    # #      
#######  ####   ####  #    # ###### 
                                    
######                                                               
#     # ###### #####  #       ####  #   # #    # ###### #    # ##### 
#     # #      #    # #      #    #  # #  ##  ## #      ##   #   #   
#     # #####  #    # #      #    #   #   # ## # #####  # #  #   #   
#     # #      #####  #      #    #   #   #    # #      #  # #   #   
#     # #      #      #      #    #   #   #    # #      #   ##   #   
######  ###### #      ######  ####    #   #    # ###### #    #   #   
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Local Deployment
### Python Flask
- Web interfacing framework that uses Python; pretty neato stuff
- Tutorial: search "Flask mega tutorial miguen grinberg"
- Links for all things Flask: https://www.fullstackpython.com/flask.html
- Typically uses views.py or app.py; this allows page nav from Python framework
    * Set param `methods=['GET','POST','PUT']` to choose what you can do
    * Use `if request.method == 'POST':` for maximum effect
    * Set route as `'/<int:year>/<int:month>/<title>'` to capture args from URL
        * Capture args: `def func(x,y,z):`
- `@app.before_request()` Run function on *every* page nav action 
- `@app.route('/cool_page')` Run function for specific page navigation
- `@app.errorhandler(404)` Run function for HTTP error codes
- Overall: Generate page template, Provide response, or Redirect the user
### Python Django
- 
### Python Svelte
- 
### Deploying the Model
- 

[[Return to Top]](#table-of-contents)







<!-- 
 #####                                                   
#     #  ####    ##   #        ##   #####  #      ###### 
#       #    #  #  #  #       #  #  #    # #      #      
 #####  #      #    # #      #    # #####  #      #####  
      # #      ###### #      ###### #    # #      #      
#     # #    # #    # #      #    # #    # #      #      
 #####   ####  #    # ###### #    # #####  ###### ###### 
                                                         
######                                                               
#     # ###### #####  #       ####  #   # #    # ###### #    # ##### 
#     # #      #    # #      #    #  # #  ##  ## #      ##   #   #   
#     # #####  #    # #      #    #   #   # ## # #####  # #  #   #   
#     # #      #####  #      #    #   #   #    # #      #  # #   #   
#     # #      #      #      #    #   #   #    # #      #   ##   #   
######  ###### #      ######  ####    #   #    # ###### #    #   #   
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Scalable Deployment
### Kubernetes
- Scalable container architecture
### Apache Kafka
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
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
                                                                                
                                                                                
         #####  ####### #     # ####### ######     #    ####### ####### 
        #     # #       ##    # #       #     #   # #      #    #       
        #       #       # #   # #       #     #  #   #     #    #       
        #  #### #####   #  #  # #####   ######  #     #    #    #####   
        #     # #       #   # # #       #   #   #######    #    #       
        #     # #       #    ## #       #    #  #     #    #    #       
         #####  ####### #     # ####### #     # #     #    #    ####### 
                                                                
                                                                                
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
####### ####### ####### ####### ####### ####### ####### ####### ####### ####### 
  # #     # #     # #     # #     # #     # #     # #     # #     # #     # #   
 #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #   #  
-->


# GENERATE


<!--
 #####                                                                 #    ### 
#     # ###### #    # ###### #####    ##   ##### # #    # ######      # #    #  
#       #      ##   # #      #    #  #  #    #   # #    # #          #   #   #  
#  #### #####  # #  # #####  #    # #    #   #   # #    # #####     #     #  #  
#     # #      #  # # #      #####  ######   #   # #    # #         #######  #  
#     # #      #   ## #      #   #  #    #   #   #  #  #  #         #     #  #  
 #####  ###### #    # ###### #    # #    #   #   #   ##   ######    #     # ### 
                                                                                
######                                                          
#     # ######  ####   ####  #    # #####   ####  ######  ####  
#     # #      #      #    # #    # #    # #    # #      #      
######  #####   ####  #    # #    # #    # #      #####   ####  
#   #   #           # #    # #    # #####  #      #           # 
#    #  #      #    # #    # #    # #   #  #    # #      #    # 
#     # ######  ####   ####   ####  #    #  ####  ######  ####  
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Generative AI Resources
- Open source models and tutorials: Hugging Face
### Available Generative Models
- **Boltzmann Machine (BM)**
    * Uses probability to learn a distribution over a set of inputs
    * Good at dimensionality reduction, feature learning
    * Restrictive version only connects visible layers to hidden layers (faster)
- **Generative Adversarial Network (GAN)**
    * Uses Adversarial loss with discriminator, generator, and latent variable
- **Variational Autoencoder (VAE)**
    * Uses Kullback-Leibler Divergence loss, measure diff in prob distributions
- **Transformer Networks**
    * Uses self-attention mechanisms to capture relationships
    * Foundation of BERT and GPT, good at NLP and language translation
    * Employs attention mechanisms to focus on most relevant parts of input
    * All data is processed simultaneously

[[Return to Top]](#table-of-contents)







<!-- 
#                                   
#         ##   #####   ####  ###### 
#        #  #  #    # #    # #      
#       #    # #    # #      #####  
#       ###### #####  #  ### #      
#       #    # #   #  #    # #      
####### #    # #    #  ####  ###### 
                                    
#                                                        
#         ##   #    #  ####  #    #   ##    ####  ###### 
#        #  #  ##   # #    # #    #  #  #  #    # #      
#       #    # # #  # #      #    # #    # #      #####  
#       ###### #  # # #  ### #    # ###### #  ### #      
#       #    # #   ## #    # #    # #    # #    # #      
####### #    # #    #  ####   ####  #    #  ####  ###### 
                                                         
#     #                                    
##   ##  ####  #####  ###### #       ####  
# # # # #    # #    # #      #      #      
#  #  # #    # #    # #####  #       ####  
#     # #    # #    # #      #           # 
#     # #    # #    # #      #      #    # 
#     #  ####  #####  ###### ######  ####  
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Large Language Models (LLMs)
- Open source models and tutorials: Hugging Face
### Methodology
- 
### Training
- 
### Scaling Down
- Transformers

[[Return to Top]](#table-of-contents)







<!-- 
######                                                    
#     # ###### ##### #####  # ###### #    #   ##   #      
#     # #        #   #    # # #      #    #  #  #  #      
######  #####    #   #    # # #####  #    # #    # #      
#   #   #        #   #####  # #      #    # ###### #      
#    #  #        #   #   #  # #       #  #  #    # #      
#     # ######   #   #    # # ######   ##   #    # ###### 
                                                          
   #                                                           
  # #   #    #  ####  #    # ###### #    # ##### ###### #####  
 #   #  #    # #    # ##  ## #      ##   #   #   #      #    # 
#     # #    # #      # ## # #####  # #  #   #   #####  #    # 
####### #    # #  ### #    # #      #  # #   #   #      #    # 
#     # #    # #    # #    # #      #   ##   #   #      #    # 
#     #  ####   ####  #    # ###### #    #   #   ###### #####  
                                                               
 #####                                                           
#     # ###### #    # ###### #####    ##   ##### #  ####  #    # 
#       #      ##   # #      #    #  #  #    #   # #    # ##   # 
#  #### #####  # #  # #####  #    # #    #   #   # #    # # #  # 
#     # #      #  # # #      #####  ######   #   # #    # #  # # 
#     # #      #   ## #      #   #  #    #   #   # #    # #   ## 
 #####  ###### #    # ###### #    # #    #   #   #  ####  #    # 
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Retrieval Augmented Generation (RAG)
- Adding context to existing model
### Design
- 
### Implementation

[[Return to Top]](#table-of-contents)







<!-- 
###                             
 #  #    #   ##    ####  ###### 
 #  ##  ##  #  #  #    # #      
 #  # ## # #    # #      #####  
 #  #    # ###### #  ### #      
 #  #    # #    # #    # #      
### #    # #    #  ####  ###### 
                                
 #####                                                           
#     # ###### #    # ###### #####    ##   ##### #  ####  #    # 
#       #      ##   # #      #    #  #  #    #   # #    # ##   # 
#  #### #####  # #  # #####  #    # #    #   #   # #    # # #  # 
#     # #      #  # # #      #####  ######   #   # #    # #  # # 
#     # #      #   ## #      #   #  #    #   #   # #    # #   ## 
 #####  ###### #    # ###### #    # #    #   #   #  ####  #    # 
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Image Generation
- 

[[Return to Top]](#table-of-contents)







<!-- 
   #                           
  # #   #    # #####  #  ####  
 #   #  #    # #    # # #    # 
#     # #    # #    # # #    # 
####### #    # #    # # #    # 
#     # #    # #    # # #    # 
#     #  ####  #####  #  ####  
                               
 #####                                                           
#     # ###### #    # ###### #####    ##   ##### #  ####  #    # 
#       #      ##   # #      #    #  #  #    #   # #    # ##   # 
#  #### #####  # #  # #####  #    # #    #   #   # #    # # #  # 
#     # #      #  # # #      #####  ######   #   # #    # #  # # 
#     # #      #   ## #      #   #  #    #   #   # #    # #   ## 
 #####  ###### #    # ###### #    # #    #   #   #  ####  #    # 
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Audio Generation
- 

[[Return to Top]](#table-of-contents)







<!-- 
#     #                        
#     # # #####  ######  ####  
#     # # #    # #      #    # 
#     # # #    # #####  #    # 
 #   #  # #    # #      #    # 
  # #   # #    # #      #    # 
   #    # #####  ######  ####  
                               
 #####                                                           
#     # ###### #    # ###### #####    ##   ##### #  ####  #    # 
#       #      ##   # #      #    #  #  #    #   # #    # ##   # 
#  #### #####  # #  # #####  #    # #    #   #   # #    # # #  # 
#     # #      #  # # #      #####  ######   #   # #    # #  # # 
#     # #      #   ## #      #   #  #    #   #   # #    # #   ## 
 #####  ###### #    # ###### #    # #    #   #   #  ####  #    # 
-->

--------------------------------------------------------------------------------
<!-- Needs work -->
## Video Generation
- 

[[Return to Top]](#table-of-contents)












# TO-DO
1. Sveltekit app on a local deployment just to render this notes file in webapp
1. Github Pages hosting the Sveltekit app with CI/CD pipeline
    * https://www.okupter.com/blog/deploy-sveltekit-website-to-github-pages
1. Geospatial project with OpenStreetMap and geo modeling in Jupyter
1. Add Jupyter project to the Github Pages and relevant CI/CD
1. Reinforcement learning project in pipeline, containerized scaled deployment
1. Add RL project to Sveltekit and to the Github Pages and relevant CI/CD
1. LLM with RAG in pipeline, containerized scaled deployment
1. Add the LLM with RAG to Sveltekit and to the Github Pages and relevant CI/CD
1. Add StableDiffusion following same containerized scaled deployment
1. Add audio/video generations as well
### Sections to Polish (mark what is planned in above steps)
- [x] Tools > Enterprise Tools > ArcGIS
- [x] Explore > Geospatial Analysis
- [x] Model > Reinforcement Learning
- [x] Deploy > Exports and Pipelines
- [x] Deploy > Containers
- [x] Deploy > Local Deployment
- [x] Deploy > Scalable Deployment
- [x] Generate > Generative AI Resources
- [x] Generate > Large Language Models
- [x] Generate > Retrieval Augmented Generation
- [x] Generate > Image Generation
- [x] Generate > Audio Generation
- [x] Generate > Video Generation