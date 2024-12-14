## Thoughts
- Generate many features, use factorization to slim back down onto useful ones
- Generative AI section
- Kubernetes section

<!-- Needs Work -->
### Marketing
```python
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

--------------------------------------------------------------------------------
<!-- Needs work -->
## Model Evaluation
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Environment Setup
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
### ***Data Formats***
- CSV
- XLSX
- SAS
- Stata
- Parquet
- HDF5
- MATLAB
### ***REST APIs***
- Application Programming Interface: a way to interact with 'owned' data
    * There's rules and defined mathods for interacting with APIs
    * Scraping is still possible, but APIs may be better in some cases
- REST, RESTful: a standardized structure for URLs
- RESTful JSON API: URLs follow REST comms w/ server are in JSON format
### RESTful JSON APIs
- Interfacing is done through HTTP requests
- Endpoints are typically: "/api/v1/items/1" with ["next_page"]/["max_page"]

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

--------------------------------------------------------------------------------
<!-- Needs work -->
## Natural Language Processing
- Designed for normalizing, analyzing, and modeling bodies of text
- Useful for keyword and sentiment analysis, classification, anomaly detection
- Often involves factorization of sparse matrices (decompose then approximate)
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
### WORK-IN-PROGRESS
- NEED: Bring in notes from https://github.com/lets-talk-codeup/github-guesser
- NEED: Add PCA example for TruncatedSVD
- Natural Language Toolkit (NLTK): https://www.nltk.org/index.html
- Fuzzy matching: `thefuzz.process.extract("matchme", listlikehere, limit=None)`
    * Return list of match score tuples like: [(string1, score, rank), ...]
- NEED: Vectorized method for performing this cleaning work
- Add ngram compilation to this

--------------------------------------------------------------------------------
<!-- Polished -->
## Performing NLP
- Python Unicode normalization: `doc = UNICODE.normalize().encode().decode()`
- Python NLTK: `from nltk import tokenize, porter, stem, corpus.stopwords`
    * Choose a specific method under each of these, ex: TweetTokenizer
    * Use `sent_tokenize` instead of `tokenize` for sentence tokenization
- Python text sentiment: `from nltk.sentiment import SentimentIntensityAnalyzer`
    * Score: `SentimentIntensityAnalyzer().polarity_scores(sentence_token)`
- Python Wordclouds: `import wordcloud.WordCloud, PIL.Image, matplotlib.pyplot`
    * See: https://github.com/amueller/word_cloud/blob/master/examples/parrot.py
- Python bag of words: `import sklearn.feature_extraction.text`
    * Count Vectorization and TF-IDF Vectorization
### Normalizing String Features
1. Perform Unicode normalization with one of the following: NFD, NFC, NFKD, NFKC
1. Encode from normalized text into ASCII
1. Decode from ASCII into UTF-8
1. Remove special characters using REGEX: replace /[^a-z0-9'\s]/ with ""
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
1. (Classification) Add cols for class-wise, word-wise proportions
1. (Classification) Sort data by proportion, plot stacked barchart (ex: best 25)
1. Plot a wordcloud with an optional black-white picture mask
### Sentiment Analysis
1. Perform cleaning steps from before (tokenize on sentences)
1. Instantiate a pre-trained sentiment analyzer
1. Calculate sentiment score per sentence, calc average sentiment across scores
1. (Classification) Group sentiment score averages by target class

--------------------------------------------------------------------------------
<!-- Polished -->
## Probability
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
- **Exponential**: probability of wait time for Poisson event (time between events)
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
### Python Dataframe Styling
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Classification
- Ultimately, classifiers always take an input and map it to a discrete output
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

--------------------------------------------------------------------------------
<!-- Polished -->
## Regression
- TODO: snippet about polynomial transformation of features to make more linear
- TODO: snippet about other transforms (log, exponent, etc) to better correlate
### Features for Regression
- Keep features that highly-correlate with the target: `df.corr()`
- Interactions are awesome! They can have better correlations; `s1 * s2`
    * Example: `df["cat1_col2"] = (df["col1"] == "cat1") * df["col2"]`
- Features that correlate with other features contribute to multicollinearity
    * Multicollinearity reduces model performance
    * Reduce multicollinearity by thresholding variance inflation factor (VIF)
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

--------------------------------------------------------------------------------
<!-- Needs work -->
## Time Series
- TODO: Resampling into consistent intervals, reducing precision, etc
- TODO: Filling forward/backwards by averaging, etc
- TODO: Creating tons of numerical features
### Timestamp Engineering
- VERY POWERFUL: `df.set_index("interval_ts").reindex([t1,t2,t3,t4]).fillna(0)`
- ALSO POWERFUL: `quadr_interp = ts_index_df.interpolate(method="quadratic")`
    * Options: "linear","quadratic","nearest"
    * `df["col1"].plot(title="figtitle",marker="o",figsize=(30,5))`
    * `quadr_interp["col1"].plot(color="red",marker="o",linestyle="dotted")`
- Consider timestamp amplification (col for hour, day, minute, etc)
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
- **Holt's Linear Trend**
    * Calculate regression line of previous cycles, snap-on as prediction
    * Use smoothing level and smoothing slope
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
## Neural Networks
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
### Deep Learning
- Similar methodology to NNs, but the network structure for learning is flexible
- Computer Vision

--------------------------------------------------------------------------------
<!-- Needs work -->
## Model Deployment
- Use `from skelarn.pipeline import Pipeline` and save trained pipe to PKL file
    * Access parts using layer names, ex: `("scaler", StandardScaler())`
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
### PySpark Commands
- Check Spark's intentions before query: `df.explain()`
    * Used for diagnosing performance issues; operation order from bottom-upward
- Switch to SQL: `df.createOrReplaceTempView('df')`
    * Run SQL statements: `spark.sql(''' SELECT * FROM df ''')`
- Build schema: `schema = StructType([(StructField(...), StructField(...)),])`
    * StructField syntax: `Structfield("col1", StringType())`
### PySpark Wrangling Example
```python
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
```python
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
### PySpark Machine Learning
```python
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
## Planning a Project
- Requirements Stage: Talk with stakeholders about their requirements/timeline
- Decision Stage: Decide which requirements you will be able to complete
    * Goal is to complete *all* user requirements for this "sprint" (a timeline)
    * You choose how in-depth to go for each requirement
### Selecting the Framework
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

--------------------------------------------------------------------------------
<!-- Needs work -->
## Business Tools
- Excel and Google Sheets: fast initial exploration
- PowerBI: if your company uses it already, use Jupyter with `powerbiclient`
- Tableau: if your company uses it already, or, if you have license/experience
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