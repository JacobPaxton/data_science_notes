# Front-End Notes

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

I.    [The Internet                  ](#the-internet)
1.    [History of The Internet       ](#history-of-the-internet)

II.   [HTML                          ](#html)
1.    [HTML Basics                   ](#html-basics)
2.    [HTML Specifics                ](#html-specifics)
3.    [HTML Examples                 ](#html-examples)

III.  [CSS                           ](#css)
1.    [CSS Basics                    ](#css-basics)
2.    [CSS Examples                  ](#css-examples)

IV.   [XML                           ](#xml)
1.    [XML Basics                    ](#xml-basics)

IV.   [JavaScript                    ](#javascript)
1.    [JavaScript Basics             ](#javascript-basics)
2.    [JavaScript Examples           ](#javascript-examples)

V.    [Bootstrap                     ](#bootstrap)
1.    [Bootstrap 5 Basics            ](#bootstrap-5-basics)
2.    [Bootstrap 5 Example           ](#bootstrap-5)

VI.   [jQuery                        ](#jquery)
1.    [jQuery Basics                 ](#jquery-basics)

VII.  [D3.js                         ](#d3.js)
1.    [D3 Basics                     ](#d3-basics)

VIII. [PHP                           ](#php)
1.    [PHP Basics                    ](#php-basics)

<br>

<br>






<!-- 
#######                  ###                                                
   #    #    # ######     #  #    # ##### ###### #####  #    # ###### ##### 
   #    #    # #          #  ##   #   #   #      #    # ##   # #        #   
   #    ###### #####      #  # #  #   #   #####  #    # # #  # #####    #   
   #    #    # #          #  #  # #   #   #      #####  #  # # #        #   
   #    #    # #          #  #   ##   #   #      #   #  #   ## #        #   
   #    #    # ######    ### #    #   #   ###### #    # #    # ######   #   
-->

# The Internet

## Internet Basics
- Web development should be tested across all major browsers
- Page types: HTML, ASPX
### History of The Internet
- Commercialization of UNIX -> Hypertext Markup Language / CSS -> Javascript
- Browsers: Mosaic -> Netscape Navigator | Internet Explorer -> Modern ones
- Internet Service Providers -> Web Hosting -> Websites -> Search | E-Commerce
### Uniform Resource Locators (URLs)
- URL structure: `https://www.w3.org/Consortium`
    * `https:`: the protocol definition
    * `//www.w3.org`: the resource name (host machine names preceded by `//`)
        * `www`: subdomain (the folder containing the website)
            * Server admin can create as many different subdomains as they want
            * "www" is default and nowadays optional, ex: "bing.com" works fine
        * `w3`: domain name (can be separated by periods, ex: my.webmail.com)
        * `org`: top-level domain (web server searches this domain for "w3")
        * Not case sensitive
    * `/Consortium`: web page location as a filename and/or path
        * Usually case sensitive
- URL structure: `https://www.wgu.edu/online-it-degrees.html`
    * `online-it-degrees.html`: web page location as a filename
    * The main ones are just "index.htm" or "default.htm"
- URL structure: `https://www.youtube.com/watch?v=coolvideo&t=1m51s`
    * `watch`: web page location
    * `?v=coolvideo&t=1m51s`: query string


[[Return to Top]](#table-of-contents)






<!-- 
#     # ####### #     # #      
#     #    #    ##   ## #      
#     #    #    # # # # #      
#######    #    #  #  # #      
#     #    #    #     # #      
#     #    #    #     # #      
#     #    #    #     # #######
-->

# HTML

<!-- Polished -->
## HTML Basics
- Hypertext Markup Language; the foundation of web design
- The structure of web pages; specifically elements, tags, and attributes
    * Element: start-tag + content + end-tag
    * Tags: the start and end of HTML elements
    * Attributes: additional information about element, located in start-tag
- The HTML "tree" of tags is called the Document Object Model
- Use CSS to stylize the structure and Javascript to animate it
- Semantic HTML (the point of HTML): page structure, ex: headers, paragraphs
    * Presentational HTML (font, bold, etc) should not be used; use CSS instead
- Excellent HTML/CSS debugger: **Firebug** (Firefox extension)
### General HTML Usage
- Terminate a tag without a separate tag: `<a/>` instead of `<a></a>`
- Consider using an HTML editor to help spot errors; HTML will display w/ errors
- All tags should have termination, ex: `<title>Cool Page</title>`, `<meta />`
- Tags can have attributes, ex: `<div class="c1">`, `<div class="c1 c2 c3">`
- Comments: `<!-- Comment here, this won't displayed but user can still see -->`
- Special characters: for `<`, use this instead if you need to show `<`: `&lt;`
    * Other special characters: `>`:`&gt;` || `&`:`&amp;` || ` `:`&nbsp;`
    * More: `euro`:`&eur;` || `copyright`:`&copy;` || `trademark`:`&reg;`
    * More: `&eacute;`, `&egrave;`, `&ecirc;` (accented "e")
### HTML Block-Level Elements
- Always starts on a new line + top-bottom margin
- Always extends fully left-right in view
- Most common: `p` `div` `h1`-`h6` `li` `ul` `ol` `table` `dl` `dt` `form`
- Others: `address` `article` `aside` `blockquote` `canvas` `dd` `fieldset`
- More: `figcaption` `figure` `footer` `header` `hr` `main` `nav` `noscript`
- Even more: `pre` `section` `tfoot` `video`
### HTML Inline Elements
- Does not start on a new line
- Takes up the minimum amount of room
- *Cannot contain a block-level element* (but can contain other inline elements)
- Most common: `a` `br` `button` `code` `img` `input` `label` `script` `select`
- More: `span` `textarea` `abbr` `acronym` `b` `bdo` `big` `cite` `dfn` `em` `i` 
- Even more: `iframe` `kbd` `map` `object` `output` `q` `samp` `small` `strong`
- Even more: `sub` `sup` `time` `tt` `var`
### HTML Form Elements
- Surrounded by `<form>` (block-level element)
- Most common: `button` `checkbox` `color` `date` `datetime-local` `email` 
- More: `file` `hidden` `image` `month` `number` `password` `radio` `range` 
- More: `reset` `search` `submit` `tel` `text` `time` `url` `week`
### Jinja
- `{% block page_content %}` and more of these python-work-in-HTML is from Jinja

<!-- Polished -->
## HTML Specifics
- `<!DOCTYPE html>`: Document type declaration, required; "html" indicates HTML5
- `<html>`: The element that encompases the whole document (DOCTYPE precedes it)
    * Attribute: `lang="en"`
### General Attributes
- `id`: Tag ID; unique, important for many things including Javascript and CSS
    - Reference it in CSS: `#specificElement { CSS_here }` 
    * Reference it in Javascript: `document.getElementById("specificElement");`
    * Jump page to it: `<a href="#specificElement">`
    * Jump page to it (another way): `<href="page.html#specificElement">`
- `name`: Tag name; important for many things, especially Javascript and CSS
- `class`: Tag class; important for many things, especially Javascript and CSS
    * Reference it: "city": `.city { CSS_here }` || "note" `.note { CSS_here }`
    * Reference it in JS: `var x = document.getElementsByClassName("city");`
- `href`: Link; can link to URL, site files, or other tags via "name" attribute
    * URL: `href="google.com"`, site files: `href="coolpages/index.html"`
    * Tag reference ex: `<a name="top"/>` -> `<a href="#top">Back to top</a>`
- `target`: Perform a movement action, ex: open a new tab
    * Use: `"_blank"` (new tab), `"_self"`, `"_top"`, `"_parent"` (up in dir)
- `src`: Location of the file (similar to href), ex: `src="images/mountain.jpg"`
- `style`: Add CSS inline for an element, ex: `style="font-size:60px;"`
    * Always use "property:value" format
### Head
- `<head>`: Page header information (as opposed to body); not displayed to user
    * Tags: title style meta link script base
- `<title>`: Page title; browsers use these to name browser tabs
- `<style>`: Raw CSS to apply to the page (internal)
    * CSS file import: `<link rel="stylesheet" href="filepath_here/styles.css">`
- `<meta>`: Page metadata
    * Attribute: `charset="utf-8"`
    * `name="keywords" content="..."`
    * `name="description", author, viewport`
    * `http-equiv="refresh" content="30"`
- `<link>`: Link to something
    * Add company logo: `<link rel="icon" type="image/x-icon" href="filepath">`
- `<script>`: Javascript
- `<base>`: Not sure...
### Body
- `<body>`: Page content (as opposed to head); this is what the user sees
- `<div>`: Block; rectangular section, probably the most important element
    * Used for containing other elements
- `<h1>`: Page headers; there are 6 options (h1, h2, h3, h4, h5, h6)
- `<p>`: Paragraphs; holds text blocks (browsers add top/bottom margins for it)
- `<pre>`: Exastly as-is block; nice for code block formatting (think: indents)
- `<code>`: Code block; this sits inside another element like `<p>`
- `<a>`: Anchor tag; used for links, ex: `<a>Click here!</a>`
    * FTP, mailto, local files, page anchors, web links
    * Add `title` attribute to display something when link is hovered-over
- `<img>`: Image; use CSS to set height/width of image (default is full size)
    * Always ended by shorthand `<img src="bg.jpg" alt="bg" />`
    * Make it into a clickable link by surrounding it with `<a>`
    * Attribute: `alt="image didn't load :("`, text to display as placeholder
- `<iframe>`: embed a webpage inside a webpage
    * EX: `<iframe src="url" title="sub_page_title"></iframe>`
- `<dl>`: Data list; contains `<dt>` (data term) and `<dd>` (data definition)
    * `<dl> <dt>1</dt><dd>First Item</dd> <dt>2</dt><dd>Second Item</dd> </dl>`
- `<ul>`: Unordered list; usually bulletpoints
- `<ol>`: Ordered list; usually numbered points (like instructions)
- `<li>`: List element; contains the text, is surrounded by `<ul>`,`<ol>`
- `<span>`: Surround text to allow styling (has no other effect)
- `<br>`: Line break; HTML ignores non-specific whitespace
- `<hr>`: Horizontal line
- `<strong>`: Emphasize a portion of text; usually means making text bold
- `<button>`: Perform actions, ex: `<button type="button" onclick=[javascript]>`
### Forms
- `<form>`: Submission form; wraps submission fields
    * Attribute: `action` specifies the script file to process the form
    * Attribute: `method` specifies "get" or "post" for what you'd expect
        * "get" adjusts the URL: `<input...name="v1">` -> `script.php?v1="hi"`
        * "post" sends data securely; use "get" for bookmark-able inputs
    * Should always have an `<input>` tag with "submit" type
    * Can have an `<input>` tag with "reset" type
- `<label>`: Input labels; surrounds an input area or refers to it using `for`
    * `<label for="title">Title</label>` -> `<input type="text" id="title" />`
- `<input>`: Input section; use `type="text"` to use a text box
    * Types: text, hidden, radio, checkbox, password, button, submit, file
    * Assign a name attribute! This name will be the variable used by backend
    * Use `value` attribute to set a default input; checkboxes use `checked`
    * Gray-out options using the `readonly` attribute
- `<textarea>`: Larger text box than "text", set dimensions using `row`, `cols`
- `<select>`: Dropdown list, used with `<option value="c1">Pickme!</option>`
    * Pseudocode: SELECT OPTION1 OPTION2 OPTION3 /SELECT
    * Can specify `disabled` attribute for options that the user can't select
    * Can specify `selected` attribute to preselect a default option
    * Can specify `multiple` attribute to allow multi-choice selecton
        * In pure HTML, need to hold Shift or Ctrl to select multiple; USE CSS!
- `<datalist> </datalist>` contains options like: `<option value="the_option">`
#### Form Selection/Input Options
- "text": Text box; use `size` attribute to set box size
    * `maxlength`: Specifies max number of enter-able characters
    * `pattern`: Uses REGEX to limit input, ex: `pattern="[A-Za-z]{3}"`
    * `placeholder`: Background hint on what to input in field
        * EX: `placeholder="123-45-678"`
    * `required`: Prevents submission until field is filled
    * `autofocus`: Puts cursor in the input field when HTML is loaded
- "time" or "date" or "month" or "week": nice selection box for time or date
    * Can set attributes for min and max
- "file": select file for upload; multi-file upload uses `multiple` attribute
- "hidden": pass info to `<submit>` that isn't visible to user, ex: customer ID
- "number": same as `<text>` but only numbers are allowed
- "range": slide bar that doesn't show value, ex: volume slider
    * use `<input type="range" step="10">` to add 10 ticks to range bar 
    * Default range is 0-100; slider can only tick onto the steps
- "tel": telephone numbers; use ex: `pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"`
- List: `<input list="name_of_list_1234"><datalist id="name_of_list_1234">`
### Tables
- `<table>`: Table; wraps table fields
- `<thead>`: Table headers; uses `<th>` for these
- `<tbody>`: Table content; uses `<tr>` (rows) to wrap `<td>` (cells)
- `<tr>`: Table row; holds one row of `<td>`
- `<td>`: Table cell; holds one datapoint, try `colspan`/`rowspan` attributes
### New to HTML5
- `<header>`: Headline; typically company logo and nav elements
- `<footer>`: Footer; links, "contact us", etc that you'd see at the page bottom
- `<nav>`: Navigation container; main navigation portion for the site
- `<aside>`: Place element to the left of other elements
- `<article>` and `<section>` are used for page organization


<!-- Polished -->
## HTML Examples
### HTML Basic Page
```
<!DOCTYPE html> 
<html lang="en">
  <head>
    <title>HTML Example</title>
    <meta charset="utf-8">
  </head>
  <body>
    <h1>Large Heading</h1>
    <h6>Smallest Heading</h6>
    <br>
    <p>Paragraph</p>
    <pre>
        <code>
            x + y + 5 = 11;
            y - 2 - x = 4;
            x = 0;
            y = 6;
        </code>
    </pre>
    <a href="url_here">Link</a>
    <img src="filepath" alt="image" style="width:300px;height:300px;">
  </body>
</html>
```
### HTML Table #1
```
<table style="width:100%">
    <caption>Table Caption Here</caption>
    <colgroup>
        <col span=2 style="background-color: #D6EEEE">
    </colgroup>
    <tr>
        <th style="width:70%">FirstNameColumnHeader</th>
        <th>LastNameColumnHeader</th>
    </tr>
    <tr style="height:200px">
        <td>person1 firstname</td>
        <td>person1 lastname</td>
    </tr>
    <tr>
        <td>person2 firstname</td>
        <td>person2 lastname</td>
    </tr>
</table>
```
### HTML Table #2
```
<table> 
<thead> 
    <tr> <th>First</th> <th>Last</th> <th>Organization</th> <th>Type</th> </tr>
</thead>
<tbody> 
    <tr> <td>John</td> <td>Muir</td>  <td>Yosemite</td>     <td></td>      </tr> 
    <tr> <td colspan="2">Bob T. Till</td><td>KC Jazz</td>   <td>4</td>     </tr>
    <tr> <td>J</td><td>K</td><td rowspan="2">NJ</td><td rowspan="2">7</td> </tr> 
    <tr> <td>Bill</td> <td>Lueth</td>                                      </tr> 
</tbody>
</table>
```

[[Return to Top]](#table-of-contents)






<!-- 
 #####   #####   #####  
#     # #     # #     # 
#       #       #       
#        #####   #####  
#             #       # 
#     # #     # #     # 
 #####   #####   #####  
-->

# CSS

## CSS Basics
- Cascading Style Sheets; customizing HTML elements to look better
- Follows HTML load to adjust elements based on class, ID, name, etc definition
- CSS inside tags (inline), inside `<head>` (internal), or via file (external)
    * External CSS is most common; much more maintainable by simply editing file
### General CSS Usage
- **Consider using Inline CSS colors to troubleshoot HTML!**
- Internal/External CSS use a different format from Inline CSS
- Precedence: External overwritten by Internal overwritten by Inline
- Internal/External ordering: later styles overwrite earlier styles
- Ultimate style choice (from overlaps) is determined mathematically... not fun
- Comments: `/* Comment here, this won't displayed but user can still see */`

## CSS Specifics
- External CSS: `<link rel="stylesheet" type="text/css" href="style.css">`
- Internal CSS: `<style type="text/css"> body {property:value;} </style>`
    * `body {property:value; property:value; ...} p {property:value;}` 
    * Nested elements: `p.cool .big {property:value;} p#car48 {property:value;}`
    * More nested: `a > img.mountain {property:value;} h2 + p {margin-top:0px;}`
- Inline CSS: `<p style="property:value;">`
### CSS Elements
- Format elements: `b` `strong` `i` `em` `mark` `small` `del` `ins` `sub` `sup`
- Cite elements: 
    * `blockquote` (with attribute `cite="website"`) 
    * `q` (normal quote) 
    * `abbr` (with attribute `title="full name of abbreviation"`) 
    * `address` (contents are contact information) 
    * `cite` (contents are the title of a reference)
    * `bdo` (used like this: `<bdo dir="rtl">` to see contents reversed)
- Picture elements: 
    * `img`, `map` (clickable spots)
    * `area` (define click area)
    * `picture` (flexibility)
### CSS Coloration
- RGB set: `rgb(255, 99, 71)`
- Hex: `#ff6347` (note: this is `#RRGGBB`, each portion is hex)
    * Setting all three hex values equal will make gray
- Hue-Saturation-Lightness: `hsl(9, 100%, 64%)`
    * Hue: 0 is red, 120 is green, 240 is blue, goes to 359
- RGB + Alpha: `rgba(1, 2, 3, alpha)`
- Hue-Saturation-Lightness + Alpha: `hsla(., ., ., alpha)`
- Adjust CSS of unvisited link: `a:link {color: blue;}`
- Adjust CSS of visited link: `a:visited {color: pink;}`
- Adjust CSS of hovering-over link: `a:hover {color: orange;}`
- Adjust CSS of active link (link was just clicked): `a:active {color: red;}`
### CSS Random
- Background color: `"background-color:powderblue;"`
- Background image for entire page: `body { background-image...; }`
- Background image for non-image element: `"background-image: url('url_here');"`
    * Default is repeat-fill; use this: `background-repeat:no-repeat;`
    * P1 Try: `background-attachment:fixed;` 
    * P2 Try: `background-size:cover;` `background-size: 100% 100%;`
- Font: `"font-family:baskerville, cambria, serif;"` 
- Font size: `"font-size:60px;"`
- Font style: `"font-style: italic;"`
- Text alignment: `"text-align:center;"`
- Element border: `"border:2px solid Violet;"`
    * Also try: `border-width`, `border-style`, `border-color`
    * Border style can be: "none", "solid", or "double"
- Padding between content and element: `"padding:30px;"`
    * Also try: `padding-top`, `padding-right`, `padding-left`, `padding-bottom`
- Padding outside element: `"margin:50px"`
    * Also try: `margin-top`, `margin-right`, `margin-left`, `margin-bottom`
    * Auto-set margins: `margin: 40px auto;` (auto sets the margins if needed)
    * Margins don't add when they touch (70 + 40); larger margin wins (70 + 0)
- Set max width of an element: `max-width:980px;`
- Float image on hover: `<p><img ... style="float:left;">text_here</p>`
- Edge against an element: `float:left;` or `float:right;`
- Move from current location: `position:relative;` with whatever `left:5px;` etc
- Reset to window location and move: `position:absolute` with `right:100px;` etc
- Change list style: `list-style-type` (none, square, circle, or disc), 
    * `list-style-image`: use your own image for the bullet
    * `list-style-position`: bullets "outside" or "inside" (far-left, near-left)

<!-- Polished -->
## CSS Examples
### HTML Table Example
```
<style>
table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
    border-radius: 10px;
    border-style: dotted; <!-- many options for style here -->
    border-color: #96D4D4;
}
table {
    border-spacing: 30px
}
th {
    text-align: left;
    padding-top: 10px;
    padding-left: 10px;
    border-bottom: 1px solid #ddd
}
tr:hover {background-color: #D6EEEE;}
tr:nth-child(even) {background-color: #D6EEEE;}
</style>
```

[[Return to Top]](#table-of-contents)






<!-- 
#     # #     # #       
 #   #  ##   ## #       
  # #   # # # # #       
   #    #  #  # #       
  # #   #     # #       
 #   #  #     # #       
#     # #     # #######
-->

# XML

## XML Basics
- eXtensible Markup Language
- Used for storing structured data
- Uses custom tags to define elements
    * Check out XML Schema for standardization: http://www.w3.org/2001/XMLSchema
    * Tags are case-sensitive
- Textastic, Dreamweaver (XML editors), and text editors
### XML Example
```
<?xml version="1.0" encoding="utf-8"?>
<?xml-stylesheet type="text/css" href="cars.css"?>
<!— A list of cars in inventory —>
<cars>
    <car_id> 10001
        <make>Chevy</make>
        <model>Corvette</model>
        <package>
            <trim>LS</trim>
            <wheels>Stock</wheels>
            <engine>V6</engine>
        </package>
    </car_id>
    <car_id> 10002
        <make>Chevy</make>
        <model>Corvette</model>
        <package>
            <trim>Sport</trim>
            <wheels>Performance</wheels>
            <engine>V8</engine>
        </package>
    </car_id>
</cars>
```
### XML CSS
```
@charset "utf-8"; 
body { background-color:#FFDEAD; margin-top:10px; color: teal; } 
#overview h1 { text-align:center; } 
div.simage img { border:3px white solid; align:center; } 
#mysite { margin:auto; width:980px; } 
div.smallmat { width:300px; float: left; } 
div.scaption { padding:5px; } 
div.story { width:500px; float: left; } 
div.storybook { width:850px; float:left; margin:20px; }
```
### XML Schema
- Sets available elements/attributes and their order
- Also in XML format, editable
```
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"> 
<xs:element name="californiapeople"> 
    <xs:complexType> 
        <xs:sequence> 
            <xs:element name="person" maxOccurs="unbounded"> 
                <xs:complexType> 
                    <xs:sequence> 
                        <xs:element type="xs:string" name="name"/> 
                        <xs:element type="xs:string" name="first"/> 
                        <xs:element type="xs:string" name="profession"/> 
                        <xs:element type="xs:string" name="born"/> 
                        <xs:element type="xs:string" name="photograph"/> 
                    </xs:sequence> 
                    <xs:attribute type="xs:byte" name="id" use="optional"/> 
                </xs:complexType> 
            </xs:element> 
        </xs:sequence> 
    </xs:complexType> 
</xs:element>
```
### SimpleXML
```
<?php 
    $xml = simplexml_load_string('<photocollection></photocollection>'); 
    $xml->addChild("title", "June Lake"); 
    $xml->addChild("overview", "The June Lake Loop begins just..."); 
    $photo = $xml->addChild("photo"); 
    $photo->addChild("scaption", "June Lake in the Fall"); 
    $photo->addChild("caption", "June Lake and Carson Peak"); 
    $photo->addChild("story", "Each time that unfortunate day ..."); 
    $photo->addChild("smallimg", "imagessmall/junelakefall.jpg"); 
    $photo->addChild("largeimg", "imagespng/junelakeinthefall.png"); 
    $xml->asXML("xmlfiles/new.xml"); 
?>
```
### jQuery Ajax for XML
```
<!doctype html> <html lang="en"> 
<head> 
    <meta charset="utf-8" /> 
    <title>June Lake Gallery</title> 
    <link href="styles/p1.css" rel="stylesheet" type="text/css" media="screen"/> 
</head> 
<script src="./js/jquery-1.10.1.js"></script> 
<body> 
    <div id="mysite"> </div> 
</body> 
</html> 

$(document).ready (function () { 
    $.get( "practical.xml", function( xml ) { 
        var jQueryxml = $(xml); // Turn XML object into a jQuery object 
        var html = '<div id="ov"><h1>' + jQueryxml.find('ttl').text() + '</h1>'; 
        html += '<p>' + jQueryxml.find('ov').text() + '</p></div>'; 
        html += '<div id="gallery">'; 
        jQueryxml.find('photo').each(function(){ 
            html += '<div class="bk"><div class="sm"><div class="si"><a href="'; 
            var scaption = $(this).find('scaption').text(); 
            var caption = $(this).find('caption').text(); 
            var largeimg = $(this).find('largeimg').text(); 
            var smallimg = $(this).find('smallimg').text(); 
            var story = $(this).find('story').text(); 
            html += largeimg; 
            html += '"><img class="sphoto" src="'; 
            html += smallimg; 
            html += '" title="'; 
            html += caption; 
            html += '"></img></a></div><div class="scaption">'; 
            html += scaption; 
            html += '</div></div><div class="story">'; 
            html += story; 
            html += '</div></div>'; 
        }); //close each() 
        html += '</div>'; 
        $('#mysite').html(html); 
    }, "xml"); 
});
```
### XSLT
- eXtensible Stylesheet Language Transformation
- Translate an XML file into another XML file using mapping file / programming
```
<?xml version="1.0"?> 
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"> 
    <xsl:output method="html"/> 
    <xsl:template match="/"> 
        <div id="overview"> 
            <xsl:apply-templates select="/photocollection"/> 
        </div> 
        <div id="gallery"> 
            <xsl:apply-templates select="/photocollection/photo"/> 
        </div> 
    </xsl:template> 
    <xsl:template match="photocollection"> 
        <h1> <xsl:value-of select="title"/> </h1> 
        <p> <xsl:value-of select="overview"/> </p> 
    </xsl:template> 
    <xsl:template match="photo"> 
        <div class="storybook"> 
            <div class="smallmat"> 
                <div class="simage"> 
                    <a> 
                        <xsl:attribute name="href"> 
                            <xsl:value-of select="largeimg"/> 
                        </xsl:attribute>  
                        <img class="sphoto"> 
                            <xsl:attribute name="src"> 
                                <xsl:value-of select="smallimg"/> 
                            </xsl:attribute> 
                            <xsl:attribute name="title"> 
                                <xsl:value-of select="caption"/> 
                            </xsl:attribute> 
                        </img> 
                    </a> 
                </div> 
                <div class="scaption"> 
                    <xsl:value-of select="scaption"/> 
                </div> 
            </div> 
            <div class="story"> <xsl:value-of select="story"/> </div> 
        </div> 
    </xsl:template> 
</xsl:stylesheet>

<!DOCTYPE html> <html> 
<head> 
    <meta charset="utf-8" /> 
    <title>June Lake Gallery</title> 
    <link href="styles/p1.css" rel="stylesheet" type="text/css" media="screen"/> 
</head> 
<body> 
    <div id="mysite"> 
        <?php 
            $xslt = new XSLTProcessor; 
            $xmlfile = "p1.xml"; 
            $xslfile = "p1.xsl"; 
            if (!file_exists($xmlfile)) { exit('Failed to open p1.xml.'); } 
            $xml = new DOMdocument; 
            $xml->load($xmlfile); 
            $xsl = new DOMdocument; 
            $xsl->load($xslfile); 
            $xslt->importStyleSheet($xsl); 
            printf("%s",$xslt->transformToXML($xml)); 
        ?> 
    </div> 
</body> 
</html>
```

[[Return to Top]](#table-of-contents)






<!-- 
      #                       #####                               
      #   ##   #    #   ##   #     #  ####  #####  # #####  ##### 
      #  #  #  #    #  #  #  #       #    # #    # # #    #   #   
      # #    # #    # #    #  #####  #      #    # # #    #   #   
#     # ###### #    # ######       # #      #####  # #####    #   
#     # #    #  #  #  #    # #     # #    # #   #  # #        #   
 #####  #    #   ##   #    #  #####   ####  #    # # #        #   
-->

# JavaScript

<!-- Polished -->
## Javascript Basics
- HTML into action!
- Best practices: https://www.w3schools.com/js/js_conventions.asp and https://www.w3schools.com/js/js_best_practices.asp
    - Also: https://www.w3schools.com/js/js_mistakes.asp and https://www.w3schools.com/js/js_performance.asp
- Initiated and closed in HTML by `<script>` and `</script>`
    - External Javascript is pulled in with this syntax: `<script src="folder/javascript_code.js"></script>`
    - External Javascript files do not have `<script>` nor `</script>`
- Display script-disabled content: `<noscript>text_here</noscript>` (common use: "Please enable Javascript")
- Javascript actions are always followed by semicolon (few exceptions, just use semicolon every time)
- Functions work just like in other languages but with this syntax (definition): `function nameHere() { action; }`
    * Curly brackets are called "statement blocks"; these should be used almost always!
    - Can simplify functions like this: `newfunc = () => { statements_here; }` or even simpler: `newfunc = () => returned_thing`
### Javascript Specifics
- Javascript restricted keywords: var let const if switch for function return try
    - `var`, `let`, and `const` declare variables, can just do: `var a;` and assign value later like `a = 12`
    - `let` is "block scope" meaning it holds value inside a block but not outside- var is global scope
    - Always use `const` unless the value is expected to change, ex: `const pi = 3.14159265358`
- Logical operators: && is AND, || is OR, ! is NOT
- Type operators: typeof returns the type of a variable, instanceof returns `true` if object matches compared type
- Increment a variable by itself: `x++;` or decrement: `x--;` and these work: `+=` `-=` `*=` `/=` `%=` `&=` `|=` `**=`
    - NOTE: *Hyphens are restricted for subtraction, use camelCase or under_scores instead of hyphen-ated*
- Python dict format in Javascript is an object, works the same, and same case for Python lists and Javascript arrays
- Python lambda is supported in simpler terms, like this: `const x = function (a, b) {return a * b};`
- Use `numbervalue.toFixed(2)` to round to two decimal points, use `.toPrecision(2)` to ex: simplify 9.71 to 9.7
- Use `Number(thing)` to convert a thing to a number
    - Doing `Number(new Date("2017-09-30"))` returns number of milliseconds from 1970-01-01 to 2017-09-30
    - Can do parseInt(thing) to only return an integer
- `const car = carlist[0]` is fine, so is `carlist[0] = 'Chevy'`, so is persondict.firstname
- Most math-related functions are used through methods of `Math`, like `Math.PI`, `Math.round(13.268);`,  and more
    - Math methods: https://www.w3schools.com/jsref/jsref_obj_math.asp
    - `Math.random();` generates a random number between 0 (include) and 1 (exclude), multiply/floor the random gen to get moar numbers
- Useful comparison operator in addition to usual ones: with x = 5, `x === "5";` returns false, `x !== "5"` returns true (value *and* type)
- If/Else: `if (condition) {run_statements} else if (condition) {run_statements} else {run_statements}`, no semicolon ending needed
- Cases: `switch (cond) { case v1: code break; case v2: code break; ... }`
- Try/Catch: works as usual with `try { statements_here; } catch(err) { document.getElementById("demo").innerHTML = err.message; }`
    - Add on code to execute regardless of error or no-error: `try ... catch (err) ... finally { statements_here }`
- Send out your own error, pretty much anywhere: `throw "error";`, not limited to strings for output
- `this`: The object called `this` can refer to many things and helps with changing aspects of whatever contains `this`
    - Tutorial on `this`: https://www.w3schools.com/js/js_this.asp
- Class: only used as a template for objects, syntax: `class Car {constructor(name, year) {this.name = name; this.year = year;}}`
    - After building a class, create objects using it as the template: `let myCar1 = new Car("Ford", 2014);` `let myCar2 = new Car("Audi", 2019);`
    - Class methods run functions to create class properties: `class Cat {constructor(name, year) {...} age() { statements_here; }};`
- Imports/Exports: Used for files and syntax is: "person.js" contains `export {name, age};` and call with `import { name, age } from "./person.js";`
- JSON (Javascript Object Notation) syntax is: `"employees": [{"firstName":"John", "lastName":"Doe"}, {"firstName":"Anna", "lastName":"Smith"}]`
    - Can create a JSON object from a string: `const obj = JSON.parse(text);` and call the contents with `obj.employees[1].firstName`
- Debugging: `console.log(thingy);` (print to console), `debugger;` (halt code to examine current state), browser console
### Javascript String Work
- Expected methods: `.length`, `.toUpperCase()` and `toLowerCase()`, `.trim()`, `.split("")` and `.split(",")`
- Slicing: `.slice(start, end)`, `.substring(start, end)`, `.substr(start, count)`
    - slice does start and end, substring is slice but can't do negative values, substr does count-from start
    - Includes start, doesn't include end, first character is at index 0, omit second argument to get rest of string
- Replace: `.replace("replaceme", "withme")` --- return a copy, only replace case-sensitive first match
    - Replace case-sensitive and all instances with "withme": `.replace(/replaceme/gi, "withme")`
- Index: `.charAt(index)`, `.charCodeAt(index)`, `str[index]`
- Addition: `str1.concat(" ", str2)`, `str.padStart(42, "?")` or padEnd()
- Locate index: `.search("first_index_of_me")`, `.indexOf("first_index_of_me", startpos)`, `lastIndexOf("string", startpos)`
    - returns -1 if string not found; looks for first character of string, so if startpos inside string, continues through
    - Only .search can use REGEX, it can't use startpos though
- REGEX: `.match(/regexhere/gi)` --- /g for match-all, /i for case-insensitive
    - Can test your REGEX like this: `/e/.test("The best things in life are free!");` which returns true
- Return true/false: `.includes("string")`, `startsWith("string")` or endsWith(), 
- Use "template literals" to do cool string stuff, ex: `hello (\n) how are you`
    - Span multiple lines with a string; can also use `blahblah $(var1 * var2) blahblah` to put vars / expressions in string
    - Great for putting HTML into variables
- Dates: `const d = new Date(year, month, day, hour, minute, second, and millisecond);` or `const d = new Date("January 29th, 2017 11:13:00");`
    - Month specifically uses the month indices, so January: 0, February: 1 and more- rest are normal
    - Only one parameter in `Date(parameter);` is milliseconds, including more goes to the year-month-day formula
    - Date objects have methods like `d.toDateString();` and more for outputs specifically
        - Main use: `d.getFullYear();` and similar date-get methods, look here for them: https://www.w3schools.com/jsref/jsref_obj_date.asp
        - Can set portions of date object after creation using: `d.setFullYear();` and more methods
    - More formats for creating a date object like "2015-06-12", look up stuff
### Javascript Array Work
- Javascript arrays work like Python lists with `array.sort()`, `array.reverse()`, `array.length`, `array[0]`, `array[array.length - 1]`
    - Sorting numbers is funky, use: `numeric_array.sort(function(a, b){return a - b});`, for more sorting just look up a solution (don't bother)
    - To only house unique elements, use: `const letters = new Set(["a", "b", "c", ...])`, "Set" has several methods for add/remove/etc work
    - To create (better) objects, use `Map`, ex: `const fruits = new Map([ ["apples", 500], ["bananas", 300], ["oranges", 200] ]);`, has methods
- Detect if an object is an array: `object.isArray();` or `myarray instanceof Array;`
- Make an array from something: `array.from(something)`
- Perform element-wise operations: `array.map(myfunction);`
- Combine all elements using a function: `array.reduce(myfunction); function myFunction(total, value, index, array) { return total + value; }`
    - Can start with a total value by adding a second parameter to reduce, ex: `array.reduce(myfunction, starttotal);`
    - Can work from right to left (default is left to right): `.reduceRight()`
- Mask (filter elements): `array.filter(myfunction);`
- Check if all elements or some elements pass a conditional: `array.every(myfunction);` and `array.some(myfunction);`
- Search an array using an element: `array.indexOf("element")` return first index of found-element, `.lastIndexOf()` for last index, `.includes(elem)`
- Search an array using a function: `array.find(myfunction")` to return first found-element, `.findIndex(func)` for index of found-element
- Add element to end of array: `array.push(newelement);` or `array[array.length] = newelement;`
    - For `.push()`, when you set the output to a variable, it returns the length of the array
- Add element to beginning of array: `array.unshift(newelement);` 
    - Unshift itself returns new length of array (like with push)
- Add element(s) anywhere in array: `array.splice(startindex, deletecountfromstartindex, newelement, newelement, newelement, ...);`
    - EX: ["apple","banana","orange"] for `array.splice(2,0,"grape","lemon");` returns ["apple,"banana","grape","lemon","orange"]
    - Changing 0 to 1 in above example yields: ["apple","banana","grape","lemon"] because 2,1 indicates removing 1 element starting from index 2
        - Returning a splice with removed items will return those returned items
    - Adding no new elements and a index,delete combo (ex: `array.splice(15,3);`) will remove elements but leave no gaps like `delete array[15]`
- Remove last element of array: `array.pop();` or RETURN last element of array after popped: `const lastelement = array.pop();`
- Remove first element of array: `array.shift();`, can also return removed first value like above
- Delete element and leave a gap in that spot: `delete array[42];`
- Loop through array: `let text = "<ul>"; for (let i = 0; i < arraylength; i++) { text += "<li>" + fruits[i] + "</li>"; } text += "</ul>";`
    - Above is while looping the array, add list elements to an unordered list. Pretty simple.
    - Can also use `array.forEach(myfunction);` to do the same
- Convert array to one string with comma-separation: `array.toString();` or `array.join(',');`
### Javascript Loop Work
- Loop kinds: `for`, `for/in`, `for/of`, `while`, `do/while`, also the `break;` and `continue;` work as expected
    - Cool aspect: put Javascript statements in a block like `l420: { statements_here; }` then put in the statements `break l420;` or `continue l420;`
- For (by itself): `for (execute_initial; condition_while_true_continue_loop; execute_when_complete_iteration) { statements_here; }`
    - Generally used like this: `for (let i = 0; i < 100; i++) { statements_here; }`
    - Can put multiple variable declarations in first statement (comma-separated)
    - Each statement is optional! be careful of course, syntax is: `for ( ; ; ) { statements_here }` to use no initial statements
- For/in: `for (key in object) { statements_here }`, only used for looping properties of an object or an array
    - "key" is just a placeholder variable, often `let x`, works for keys or variables
    - Don't use this when the object/array has an important order to it
- For/of: similar syntax to for/in, but is used to loop values not keys (Arrays, Strings, Maps, NodeLists, and more)
- For Each: `array.forEach(myfunction);`, following this syntax (where function is declared elsewhere), and applies function to each element
- While: `while (condition) { statements_here }`, variant of this is `do { statements_here } while (condition);`
### Javascript in Action
- Modifying HTML element attributes: `<script>document.getElementById("identifier").attribute = "new value";</script>`
    - Can modify CSS style like this: `<script>document.getElementById("identifier").style.fontSize = "35px";</script>`
- Modifying HTML element contents: `<script>document.getElementById("identifier").innerHTML = "input me!";</script>`
- Output something as HTML: `<script>document.write(5 + 6)</script>`
    - Outputting after a document loads (ex: load page, await user) will overwrite all HTML
- Alert in window: `<script>window.alert(5 + 6)</script>`
    - "window" is optional, can just do `<script>alert(5 + 6)</script>`
- User input: `var response = prompt ("Enter your first name:");`
- User confirmation: `var response = confirm ("Do you confirm?");`
- Display data for debugging: `<script>console.log(5 + 6)</script>`
- Print page (like print to PDF): `<button onclick="window.print()">Print this page</button>`
    - The `onclick` attribute is an HTML "event", and is very common
    - Other events: onchange onmouseover onmouseout onkeydown onload
- Create an object: `const person = {firstName="Dean", lastName="Watson", age=50, eye_color="blue"};`
    - Value as function: `const person = {... fullName=function() {return this.firstName + " " + this.lastName;}};`
    - Access object's key values: `person.firstName` or `person["firstName"]` or `person.fullName()`
- Example function definition: `function functionName(param1, param2) { statement1; statement2; }`
    - Reminder: using `let` inside a function makes the variable block-scope, as in can't be used outside function
    - Async/Await are used for things like the bulk-submit button, waits for file upload then does success-fail operation
- Example function call: `document.getElementById("selector").innerHTML = functionName();`
    - Can also be called like this (self-invoked): `(function () { statement1; statement2; })();`
    - Portions of functions can be called like this: `person.fullName.call(person3);`
    - apply() instead of call() does an array instead of separate function arguments
### Ajax
- Asynchronous JAvascript XML
- USed for async retrieval of data from the server
- Relies on the XMLHttpRequest (XHR) object in Javascript
- Commonly combined with jQuery
- Drawback: page changed but no new one (back button skips changes to last page)
- Load HTML from file: `$('element_here').load(file_to_overwrite_element_here)`
- Run serverside work: `$.post("./filepath.php", { nav: nav}, func(data){code})`
    * PHP file in above would need to correctly-receive output of `func`
- Do any Ajax: `$.ajax({name:value, name:value, ...})`
    * Try names: `data`, `dataType`, `url`, `type`
    * Also try: `error(xhr, status, error)`, `success(result, status, xhr)`
    * EX: `$.ajax({type:"POST", url:"./file", success:function(data){code}})`

<!-- Needs work -->
## Javascript Examples
- Put text into id'd element: script document.getElementById("identifier").innerHTML = "input!"; /script
    - set style: document.getElementById("identifier").style.color = "red"
- Concatenate strings: script var txt1 = "start"; var txt2 = "coding"; document.getElementById("demo").innerHTML = txt1 + " " + txt2; /script

[[Return to Top]](#table-of-contents)






<!--
######                                                           ####### 
#     #  ####   ####  #####  ####  ##### #####    ##   #####     #       
#     # #    # #    #   #   #        #   #    #  #  #  #    #    #       
######  #    # #    #   #    ####    #   #    # #    # #    #    ######  
#     # #    # #    #   #        #   #   #####  ###### #####           # 
#     # #    # #    #   #   #    #   #   #   #  #    # #         #     # 
######   ####   ####    #    ####    #   #    # #    # #          #####  
-->

# Bootstrap

<!-- Polished -->
## Bootstrap 5 Basics
- HTML, CSS, and Javascript through pre-designed templates
- Designed to speed and standardize up front-end development
- Default HTML gets customized when Bootstrap is included
- Requires `<!DOCTYPE html></html>` because it uses HTML5 elements and CSS
- Allow mobile-device rendering and touch zooming: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- div: use `class="container-fluid"` or less-commonly `class="container"` for foundational display settings
    - Use padding with containers: `<div class="container pt-5"></div>`, also: `p-5` (pad div <-> contained), `my-5` (document <-> div)
    - Allow containers to resize to small, large, etc: `<div class="container-sm">` or `<div class="container-xxl">` and more
- Works off grid system, up to 12 columns in width, where span=1 is one column alone and span=4 is four columns combined into one
    - Use this: `<div class="col-sm-1">` when expecting small device and you want the div element to span 1 column; `col-sm-5` spans 5 columns
    - `col-sm-*` sizing sets the minimum-allowable width in pixels, important for screen size considerations, each size is kinda designed for screen orientation and device so look up stuff
    - div columns should always be nested in div rows
### Bootstrap 5 Specifics
- Importing BS5 stylesheet: `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">`
- Importing BS5 scripts: `<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js"></script>`
- background colors via `class="bg-dark"` and other bg classes
    - `bg-success`, `bg-warning`, `bg-danger` for green, yellow, and red text background coloring
    - for alerting outcomes, use `alert` instead
- alerting: like `class="alert-success"`
    - inside a div with an alert class, `<a href="link" class="alert-link">` keeps div alert color
    - dismiss alert: add to class `alert-dismissable`, then inside the div, `<button type="button" class="btn-close" data-bs-dismiss="alert"></button>`
    - fade-away animation with dismiss button: add `fade` and `show` to div class
    - use a "toast" for auto-fadeaway alerts
- button formatting inside `<button>` element: `class="btn"` and more like `btn-outline-primary`, `btn-sm` or `btn-lg`
    - active button uses `class="active"` and deactivated button uses the *attribute* "disabled"
    - spinner icon in button (loading): inside `<button></button>` element, add `<span class="spinner-border spinner-border-sm"></span>` and Loading...
    - buttons side-by-side: `btn-group` in div class with buttons inside div element, also `btn-group-lg` or `btn-group-sm`, also `btn-group-vertical`
    - dropdown button: `<div class="dropdown-menu"></div>` with an `<a class="dropdown-item" href="link">Button Label<a>` for each dropdown item
- text colors via `class="text-white"` and other text classes
    - `text-success`, `text-warning`, `text-danger` for green yellow and red text coloring
- font size via usual `class="h1"` thru `h6` but also `class="display-1` thru `display-6`, "display" does larger and skinnier than headings
    - `class="lead"` is used for first paragraph of article, slightly bigger for emphasis (lead into content)
- text location-ing: use class= for `text-start`, `text-center`, or `text-end` for left, center, and right alignment
    - `text-break` breaks up long text, `text-nowrap` does opposite
- table formatting via `class="table` and additional table classes like `table-striped` and `table-hover`
    - `table-sm` cuts cell padding in half, `table-responsive` adds horizontal scrollbar when needed (can indicate `table-responsive-sm` and more)
    - color row in table using class in `<tr>` element, for cell coloring add class to `<td>`, pretty simple
- round edges of image: `class="rounded"` or `class="rounded-circle"`
- aligning images: `class="float-start"` (left) or `float-end` (right) or `mx-auto d-block` (center)
    - resize based on device: throw in a `class="img-fluid"`
- progress bar for user: `<div class="progress"><div class="progress-bar" style="width:50%"></div></div>` where width is manual indication of progress
    - outside-div is used for progress bar's container while inside-div is used for the bar itself
    - can add text to inside-div to put text on the bar like percentage
    - can add background color like normal
    - animated stripe is done using iside-div class `progress-bar-striped progress-bar-animated`
- pagination: `<ul class="pagination"> <li class="page-item"><a class="page-link" href="link">1</a></li> ...more li elements... </ul>`
    - active-page is indicated using `<li class="page-item active"><a>2</a><li>`
    - when first page is selected, can't go previous, so use `class="page-item disabled"` for Previous button
    - pagination heirarchy (navigate to root folder(s)): `<ul class="breadcrumb"><li class-"breadcrumb-item"><a>topfolder</a></li><li><a>middle</a></li>`
        - indicate current location and disable link to it: don't include `<a></a>` routing and use `<li class="breadcrumb-item active">`
    - indicate pagination block size: `pagination-sm`
    - indicate pagination location: `class="pagination justify-content-center"` or `justify-content-end`
- list groups are nice in some cases, smash rows together vertically and do stuff inside `<ul class="list-group">`
- cards (yes, like trading cards, businessman profile cards, etc) is done using `<div class="card">`
- collapsible element via button: `<button data-bs-toggle="collapse" data-bs-target="#element_id_here">Button's Text</button>`
    - the content to collapse/reopen is indicated in raw `<div id="element_id_here" class="collapsible">Text to collapse or reopen</div>` using id target
    - default is text initially collapsed, to show text first use `class="collapse show"`
- list group with collapsible-text on each list item: just use w3schools lol, it's in BS5 Collapse section
- page navigation section: `<ul class="nav">` with `<li class="nav-item"><a class="nav-link" href="link">Link Name</a></li>`
    - set page nav formatting in `<ul>` like you'd expect
- navigation bar: `<nav class="navbar navbar-expand-sm bg-light">` with div for portions of nav bar and ul for nav section
    - delete out `navbar-expand-sm` to make nav vertical, there's a lot more customization with this too just look it up
    - overlay-side nav on click is "offcanvas"
- sliding images: `<div class="carousel slide">`
- show dialog box / popup window: just look at w3schools BS5 Tooltip
    - Popover is a more flexible version
- utilities: border - float - shadow - ratio - visibile or invisible - btn-close - color or bg-color
    - Bootstrap 5 uses flexboxes instead of float
### Bootstrap 5 Forms
- text input: `form-label` for label padding, `form-control` for the text boxes
- single-selection input: `form-check-label` for label padding, `form-check` for the selection element
    - Use: `<select class="form-select"><option>1></option><option>2</option>...</select>`
    - Sizing: `form-select-lg`, disable: add attr "disabled"
- multi-selection input (ctrl+click) and radio: `form-check-label` for label padding, `form-check-input` for the multi-select element
- data lists (type to filter): `form-label` and `form-control`
- toggle switches: `<div class="form-check form-switch"><input class="form-check-input" type="checkbox">` and uses `form-check-label` with `for`
- input group (text plus button as example): `<div class="input-group"><input type="text" class="form-control"><button class="btn btn-success" type="submit">Go</button></div>`
- use rows and columns for input sections: `<div class="row"><div class="col"><input></div><div class="col"><input></div></div>`
- change input section sizes: `class="form-control form-control-sm"`
- disable field: add attribute "disabled" or "readonly"
- floating stuff in inputs (looks nice): `<div class="form-floating"><textarea class="form-control"></textarea><label>Floating Label (always after input box)</label></div>`
- throw red shit at user when they're missing inputs: `<form class="was-validated"></form>`
    - field: `<input type="text" class="form-control" id="uname" placeholder="Enter username" name="uname" required>`
    - field still empty: `<div class="valid-feedback">Valid.</div>`
    - field has input: `<div class="invalid-feedback">Please fill out this field.</div>`
#### Bootstrap 5 Form Example
```
<form action="/nav_here_on_submit" method="POST">
    <div class="form-floating mb-3 mt-3">
        <input type="text" class="form-control" id="email" placeholder="Enter email" name="email">
        <label for="email">Email</label>
    </div>
    <div class="mb-3">
        <label for="pwd" class="form-label">Password:</label>
        <input type="password" class="form-control" id="pwd" placeholder="Enter password" name="pswd">
    </div>
    <div class="form-check mb-3">
        <label class="form-check-label">
            <input class="form-check-input" type="checkbox" name="remember">Remember me
        </label>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

[[Return to Top]](#table-of-contents)






<!--
        #####                             
     # #     # #    # ###### #####  #   # 
     # #     # #    # #      #    #  # #  
     # #     # #    # #####  #    #   #   
     # #   # # #    # #      #####    #   
#    # #    #  #    # #      #   #    #   
 ####   #### #  ####  ###### #    #   #   
-->

# jQuery

<!-- Polished -->
## jQuery Basics
- Simplifies Javascript for web dev
- Main syntax: `$("#elementID").action(callback_function);` or `$("elementID").action(function() { $(this).hide(); functions_here; });`
    - The `$("selector");` syntax is a simplified version of `document.getElement[...options_here]("selector");`
    - Selector formatting: `$(".classname")`, `$("elementtag")`, `$("#elementID")`, `$("div p.classname")`
        - More selections here: https://www.w3schools.com/jquery/jquery_selectors.asp
    - jQuery has many actions that you can chain to your selection
- Often put in an await-page-ready function using this syntax: `$(document).ready(function () { functions_awaiting_ready; });`
    - Shorter version: `$(function () { functions_awaiting_ready; });`
### jQuery Actions
- List of user-based actions: https://www.w3schools.com/jquery/jquery_ref_events.asp
- Common actions: `$("p").click();`, `dblclick`, `mouseenter`, `mouseleave`, `mousedown`, `mouseup`, `hover`, `focus`, `blur`
- Attach multiple actions on one selection: `$("p").on({ mouseenter: function(){$(this).css("color", "green");}, mouseleave: function, ... })`
### jQuery Effects
- List of action-resultant effects: https://www.w3schools.com/jquery/jquery_ref_effects.asp
- Common effects: `$("p").hide();`, `show`, `toggle`, `delay`, `fadeIn`, `fadeOut`, `fadeToggle`, `slideDown`, `slideUp`, `slideToggle`
    - Set speed of effect: `$("p").toggle(1000, callback_function)` where 1000 is duration in milliseconds to perform "toggle"
- Change multiple CSS properties (animate): `(selector).animate({styles},speed,easing,callback)`
    - EX: `$("button").click(function() { $("div").animate({height: '300px', opacity: 'toggle', left: '+=10px'}, "slow"); } ); `
    - Callback is done after animation is performed
- Chaining effects: `$("#p1").css("color", "red").slideUp(2000).slideDown(2000);`
- Reading content of HTML: `$("#id").text()` (plaintext content), `.html()` (text + `<b>` and similar), `.val()` (contents of value attribute)
    - EX: `alert("Text: " + $("#test").text());` or `alert("Text: " + $("#test").text("change contents to this!"));`
    - Can use a function to set contents, ex: `.text(function_here)`, works with `html` and `val` too
- Contents of other attributes: `$("p").attr("href")`
    - Can set/change attributes and values, ex: `$("#id").attr("href":"link", "title":"title_here", ...)` or use functions: `"href": function`
- Contents of CSS: `$("p").css("background-color");` would return what background-color is set for `<p>`, `"background-color", "yellow"` sets it
    - Can set multiple CSS at once: `$("p").css({"background-color": "yellow", "font-size": "200%"});`
    - Simpler reads: `$("#test").width()`, `.outerHeight()`, and more
### jQuery HTML Editing
- List of possible edits for HTML/CSS: https://www.w3schools.com/jquery/jquery_ref_html.asp
- Adding to HTML: `$("p").append("The End!");`, `.prepend("The Beginning!);`, `.after("After p!");`, `.before("Before p!");`
- Removing from HTML: `$("p").remove();` (removes p and any child elements), `$("p").empty();` (removes child elements from p)
    - Can be specific with removal: `$("p").remove(".classofp1, .classofp2")` removes only `<p class="classofp1">` or `classofp2`
- Adding/Removing CSS Classes: `$("p").addClass("cool");`, `removeClass("notcool")`, `toggleClass("maybecool")`
- Traversing up/down HTML elements: `$("span").parent()`, `parents`, `parentsUntil("elementtag")`, `children()`, `children("p.first")`, `find("span")`
    - Sideways traversal: `siblings(optional_tag)`, `next()`, `nextAll()`, `nextUntil("tag")`, `prev()`, `prevAll()`, `prevUntil("tag")`
    - More: `first()`, `last()`, `eq(pos_in_group)`, `filter(".intro")` (whitelist), `not(".intro")` (blacklist)
    - Traversal is awesome, see: https://www.w3schools.com/jquery/jquery_ref_traversing.asp

[[Return to Top]](#table-of-contents)






<!--
######   #####                      #     #                                      
#     # #     #         #  ####     #     # #  ####  #    #   ##   #       ####  
#     #       #         # #         #     # # #      #    #  #  #  #      #      
#     #  #####          #  ####     #     # #  ####  #    # #    # #       ####  
#     #       #         #      #     #   #  #      # #    # ###### #           # 
#     # #     #    #    # #    #      # #   # #    # #    # #    # #      #    # 
######   #####      ####   ####        #    #  ####   ####  #    # ######  #### 
-->

# D3.js

<!-- Needs work -->
## D3 Basics
- Data-Driven Documents (D3) for interactive JavaScript visualizations
- Foundation for Plotly.js and more
- Uses Scalable Vector Graphics (SVG) rendering
    - SVG is an image that is text-based, similar in structure to HTML
    - SVG is initialized in HTML as the `<svg></svg>` element, SVG elements go inside this tag
    - The `<svg></svg>` element itself requires width and height declaration, ex: `<svg width="500" height="500"></svg>`
- D3.js script import: `<script src="https://d3js.org/d3.v4.min.js"></script>`
- Download the "minified" script for offline use at https://d3js.org
    - This script contains the "d3" object that we use for all D3 work
- First step is to attach the d3 object to an element using `d3.select("#element_id")`
    - can use `d3.selectAll("element")` to attach one d3 object to multiple elements
- After attaching, you can use method chaining to adjust d3 object
- If you see "d" in places like `function (d) {};`, "d" is usually just referring to data
### D3 Select Methods
- Add text to first-found `<p>` element: `d3.select("p").text("Text here")`, same as doing `<p>Text here</p>`
- Add element just before end of `<body></body>` element: `d3.select("body").append("p").text("Text here")` (method chaining used here)
- Add element to specific position inside `<body></body>` element: `d3.select("body").insert("p", "button")`
    - Puts `<p></p>` inside `<div></div>` and right before `<button></button>`, or: `<div><p></p><button></button></div>`
- Remove element: `d3.select("p").remove()` for first found, or `d3.selectAll("p").remove()` for all
- Edit inner HTML: `d3.select("p").html("<span>Add me!</span>")`, same as changing `<p></p>` to `<p><span>Add me!</span></p>`
- Add attribute to element: `d3.select("p").attr("class","error")`, same as changing `<p></p>` to `<p class="error"></p>`
    - Can also do this using: `d3.select("p").classed("error", true)` or remove the property by setting `"error", true` to `"error", false`
- Add "required" property to text input box: `d3.select("input").property("required",true)`, same as `<input type="..." required>`
- Change styling of an element: `d3.select("p").style("color","red")`, same as `<p style="color:red"></p>`
- Run function on d3 object: `d3.select("body").data(data_var).text(function (d,i) {statements_here; return d;});`
    - `.text` is passing data_var (provided by `.data`) into function as "d" variable and returning "d" into body as text
    - Can put functions in a lot of places, ex: `d3.selectAll("p").style("color", function(d,i) { if (true) {return "green";} });`
- Events: `d3.select("p").on("mouseover", function() {d3.select(this).style("background-color", "orange");}).on("mouseout", function() {...});`
    - Check if click, mouseover, or mouseout: `d3.select("p").dispatch()`
    - Access aspects of event object: d3.event
    - Mouse/element coordinates: `d3.mouse(this)` (returns x and y of mouse pointer when mouseover this), `d3.touch()` (container coords)
- Animation: "scheduled" via `d3.select("p").transition(store_transition_as_this_var_here).style("background-color", "red")`
    - Usually put `.style` or `.attr` etc after the following animation config settings (duration, ease, delay)
    - Add `.duration(milliseconds)` to specify how long animation will take
    - Change transition style: `.easeElastic()`, `.easeBounce()`, and several more
    - Delay transition beginning: `.delay(milliseconds)`
- Data ingest from var: `d3.selectAll("p").data(mydata)` will element-wise add to each found `<p></p>` element
    - EX: `const mydata = [11,22,33,44]; d3.selectAll("p").data(mydata).text(function(d,i){return d;});`
    - Typically add "enter" and append" like: `d3.selection.data(mydata).enter().append("span").text(function ...);`
        - `.enter().append("span")` creates enough additional "span" elements to get all of mydata's elements a spot
        - No enter() for THREE p tags will add 11 to first p, 22 to second, 33 to third- "44" will not be added because there's no fourth p tag
    - "mydata" needs to be an array (or a function returning an array-like result) or else `.data()` won't work
    - Can ascribe single static value to element(s) by using `.datum(value)` instead of `data(values)`
- Data ingest from file: `d3.csv(url)`, `d3.json(url)`, `d3.tsv(url)`, `d3.xml(url)`
    - Each of these can take a function as a second argument for what to do with the data (called a "callback")
    - When using a callback function, two arguments are passed: `error` (containing whether ingest succeeded or not) and `data`, 
        - EX: `d3.csv("filepath", function (error, data) {statements;});`
- Schedule data for removal: create a variable with d3 work and add `.exit()`, then to actually remove, chain `.remove()` to the variable
    - `var p = d3.selection.methods.exit()` then `p.remove();`
### D3 SVG Work
- Proper way to initialize SVG is with variable declaration of width, height, and svg
    - EX: `<script>var width = 500; var height = 500; var svg = d3.select("body").append("svg").attr("width",width).attr("height",height);</script>`
- Proper way to create SVG elements is by appending a new element to the svg variable and method-chaining its attributes/other
    - Non-standard: `<line x1="100" y1="100" x2="500" y2="500" stroke="green"/>` --- ending "/" is a quick way to do `</line>`
    - Standard: `svg.append("line").attr("x1", 100).attr("y1", 100)...`
- Styling SVG elements is done in CSS: `<style>svg rect { fill: orange; } svg text { fill: white; }</style>`
- Grouping elements: use `var g = svg.append("g").attr("transform", function(d,i) {return "translate(0,0)";});`
    - "transform" indicates all elements transform (move coords) together
    - Create the grouped-object like this: `var ellipse = g.append("ellipse").attrs.append("text")` and then `g.append("text").attrs.text("words");`
    - Move around: `<g transform="translate(0,20)"><rect ... /><text .../></g>` --- move 20 pixels down (increasing numbers = further from top-left)
    - Append "g" elements for each datapoint: `var bar = graph.selectAll("g").data(data).enter().append("g").attr("transform", function ...)`
        - Can do: `.attr("transform", function (d,i) { return "translate(0," + i * barHeight + ")"; });`
- SVG element styling is done using: `.attr("fill", "green")` syntax with fill, stroke, stroke-width, opacity, font-family, font-size
- SVG Line: `.append("line")` with attr: x1, x2, y1, y2, stroke
- SVG Rectangle: `.append("rect")` with attr: x, y, width, height (x and y are coords for top-left corner)
- SVG Circle: `.append("circle")` with attr: cx, cy, r (cx and cy are coords of center of circle, r is radius)
- SVG Ellipse: `.append("ellipse")` with attr: cx, cy, rx, ry (rx is x-radius, ry is y-radius)
- SVG Text: `.append("text")` with attr: x, y (top-left for x and y)

## D3 Examples
```
Examples here... eventually...
```

[[Return to Top]](#table-of-contents)






<!--
######  #     # ######  
#     # #     # #     # 
#     # #     # #     # 
######  ####### ######  
#       #     # #       
#       #     # #       
#       #     # #       
-->

# PHP

## PHP Basics
- Server-side programming language to perform actions on web browsers
- Served via an "Application Server"; content is not static-printed like HTML
    * Popular one is Apache
- Starts with `<?php` and ends with `?>`
- Statements are terminated with semicolon
- Variables initialized with $var_name syntax, ex: `$first_word = "Hello";`
- Print the value of a variable: `<?php  echo $helloheader; ?>`

## PHP Examples
```
<?php 
    $hello = "Hello World Example"; 
    $helloheader = '<h1 class="green" id="hello">Hello, World</  h1>';  
?> 
<!DOCTYPE html> 
<html lang="en"> 
    <head> 
        <meta charset="utf-8">  
        <title><?php echo $hello; ?></title> 
        <link href="hello.css" type="text/css" rel="stylesheet" ></link> 
    </head> 
    <body> 
        <?php  echo $helloheader; ?> 
    </body> 
</html>
```
```
<!DOCTYPE html> <html xmlns="http://www.w3.org/1999/xhtml"> 
<head> 
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" /> 
    <title>June Lake Gallery</title> 
    <link href="styles/p1.css" rel="stylesheet" type="text/css" media="screen"/> 
</head> 
<?php 
    $xmlfile = "p1.xml"; 
    if (!file_exists($xmlfile)) { exit('Failed to open p1.xml.'); } 
    $xml = simplexml_load_file($xmlfile); ?> 
<body>
    <div id="mysite">
        <div id="overview">
            <h1> <?php echo $xml->title; ?> </h1>
            <p> <?php echo $xml->overview; ?> </p>
        </div>
        <div id="gallery"> 
            <?php 
                $photos = $xml->xpath("//photo"); 
                $photocount = count($photos); 
                $count = 0; 
                while ($count < $photocount) { 
                    $htmlstring = ('
                        <div class="storybook">
                        <div class="smallmat">
                        <div class="simage">
                        <a href="
                    '); 
                    $htmlstring .= $photos[$count]->largeimg; 
                    $htmlstring .= '"><img class="sphoto" src="'; 
                    $htmlstring .= $photos[$count]->smallimg; 
                    $htmlstring .= '" title="'; 
                    $htmlstring .= $photos[$count]->caption; 
                    $htmlstring .= '"></img></a></div><div class="scaption">'; 
                    $htmlstring .= $photos[$count]->scaption; 
                    $htmlstring .= '</div></div><div class="story">'; 
                    $htmlstring .= $photos[$count]->story; 
                    $htmlstring .= '</div></div>'; 
                    echo $htmlstring; $count++; 
                } 
            ?> 
        </div>
    </div>
</body>
</html>
```