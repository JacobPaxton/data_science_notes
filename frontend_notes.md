# Front-End Notes

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

I.    [HTML                          ](#html)
1.    [HTML Basics                   ](#html-basics)
2.    [HTML Examples                 ](#html-examples)

II.   [CSS                           ](#css)
1.    [CSS Basics                    ](#css-basics)
2.    [CSS Examples                  ](#css-examples)

III.  [JavaScript                    ](#javascript)
1.    [JavaScript Basics             ](#javascript-basics)
2.    [JavaScript Examples           ](#javascript-basics)

IV.   [Bootstrap                     ](#bootstrap)
1.    [Bootstrap 5                   ](#bootstrap-5)

V.    [jQuery                        ](#jquery)
1.    [jQuery Basics                 ](#jquery-basics)

<br>

<br>





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

<!-- Needs work -->
## HTML Basics
- Foundation of web pages
- Specifically elements, tags, and attributes
    - Element: start-tag + content + end-tag
    - Tags: the start and end of HTML elements
    - Attributes: additional information about element, located in start-tag
- `<head> </head>` element contains these options: title style meta link script base
    - meta: `charset`, `name="keywords" content="..."`, `name="description", author, viewport`, `http-equiv="refresh" content="30"`
- When there's no end-tag, it's considered an empty element (ex: line break)
- Attributes values are wrapped with double-quotes except when double-quotes are used inside the value
- Wrapping an img tag like this `<a href="site"><img ...></a>` makes the image into a clickable link to site
- Add small icon to browser tab: in head, `<link rel="icon" type="image/x-icon" href="filepath">`
### HTML Block-Level Elements
- Always starts on a new line + top-bottom margin; always extends fully left-right in view
- Most common: p div h1-h6 li ul ol table dl dt form
- Others: address article aside blockquote canvas dd fieldset figcaption figure footer header hr main nav noscript pre section tfoot video
- div: used to contain other HTML elements and style them, often takes: style, class, id
### HTML Inline Elements
- Does not start on a new line; takes up the minimum amount of room
- *Cannot contain a block-level element*
- Most common: a br button code img input label script select span textarea
- Others: abbr acronym b bdo big cite dfn em i iframe kbd map object output q samp small strong sub sup time tt var
- span: used to style portions of text. often takes: style, class, id
- select: dropdown menu, can use `size="3"` to show 3 options, can choose multiple with `<select ... multiple>`
    - All selection things use: `<option value="thing_to_select">` with no closing tag
    - To select multiple options in pure HTML, hold down Ctrl or Command
- datalist: attached to the value in: `<input list ...>`, write in box to filter options down
- output: calculations from inputs, use: `<output name="outputthing" for="a b"></output>` to run `id="a"` `id="b"`
- iframe: embed a webpage inside a webpage, ex: `<iframe src="url" title="sub_page_title"></iframe>`
#### Input Element
- Options: button checkbox color date datetime-local email file hidden image month number 
- More: password radio range reset search submit tel text time url week
- time or date or month or week: nice selection box for time or date, can set attributes for min and max
- file: select file for upload, can use `multiple` in element to allow multi-file upload
- hidden: pass information to `<submit>` that isn't visible to user, ex: customer ID
- number: same as `<text>` but only numbers are allowed
- range: slide bar that doesn't show value, ex: volume slider
- tel: telephone numbers, must set pattern ex: `pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"`
- `<input list="name_of_list_1234"><datalist id="name_of_list_1234">`
    - `<datalist> </datalist>` contains option elements like: `<option value="the_option">`
### HTML Attributes
- class: group together *any* HTML elements for common styling/javascript, ex: `class="city"` or `<span class="note city">`
    - `.city { CSS_here }` --- `.note { CSS_here }`
    - Javascript: `var x = document.getElementsByClassName("city");`
- id: unique value that is not shared anywhere else, uses `#` instead of `.` in styling, Javascript uses HTML id often
    - ex: `#specificElement { CSS_here }` then in Javascript: `document.getElementById("specificElement");`
    - can jump to specific element, ex: `<a href="#specificElement">` or `<href="page.html#specificElement">`
- text size: set box width for an input using text, ex: `<input type="text" size="50">` (default is 20)
    - `maxlength` specifies max number of enter-able characters
    - `pattern` uses REGEX to limit input, ex: `pattern="[A-Za-z]{3}"`
    - `placeholder` is background hint on what to input in field, ex: `placeholder="123-45-678"`
    - 'required' attribute prevents submission until field is filled
    - 'autofocus' attribute puts cursor in the input field when HTML is loaded
- img src: file path, includes the file name, ex: `<img src="/static/imgs/image.jpg">`
- img alt: text to display if `src` doesn't resolve
- (tag) style: add style to element like color, font, size, and more
    - `<h1 style="font-size:60px;">`
    - the above style value is CSS, always "property:value" format
- (tag) title: display the value of title as a tooltip when hovering over element with mouse
- a href: hyperlinks, use `target="_blank"` for new-tab open, `"_parent"` to move up in directory, `"_top"` for focus
    - Click to open email client: `<a href="mailto:email@site.com">text</a>`
    - Add `title="link title goes here"` to give tooltip text on link hover
    - Use `href="#uniqueidthing"` to jump to a specific id attribute on the page, to jump to other page: `page.html#id`
### Empty HTML Tags
- `<br>`: line break
- `<hr>`: horizontal line

<!-- Needs work -->
## HTML Examples
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
    <img src="filepath" alt="text_if_cant_open_img" style="width:300px;height:300px;">
  </body>
</html>
```
### HTML Table Example
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

<!-- Needs work -->
## CSS Basics
- Customization for HTML - "Cascading Style Sheets"
- Most common is linking external CSS files into HTML using the "link" tag, used to style many HTML pages
- Can be specified in its own element with tag "style" (internal), used to style entire HTML page from head
- Can be given inside HTML elements (inline) with `style="property:value"`
- External: `<link rel="stylesheet" href="filepath/file.css">` where file.css is formatted like Internal CSS
- Internal: `<style body {property:value; property:value; ...} h1 {property:value;} p {property:value;}></style>`
    - Can set style for multiple elements at once: `body {property:value} h1 a p {property:value}`
- Inline: `<p style="property:value;">`
### CSS Elements
- Formatting elements: b strong i em mark small del ins sub sup
- Citation elements: 
    - blockquote (with attribute `cite="website"`) 
    - q (normal quote) 
    - abbr (with attribute `title="full name of abbreviation"`) 
    - address (contents are contact information) 
    - cite (contents are the title of a reference)
    - bdo (used like this: `<bdo dir="rtl">` to see contents reversed)
- `img`, `map` (clickable spots), `area` (define click area), and `picture` (flexibility) are all useful things for pictures
### CSS Stylings
- Color formats: color name - rgb(255, 99, 71) - #ff6347 - hsl(9, 100%, 64%) - rgba(1, 2, 3, alpha) - hsla(., ., ., alpha)
    - Fun fact: HEX colors (#ff6347) are in #RRGGBB format where RR GG BB are hex value for each color
    - Another fun fact: setting RR GG BB as equal makes gray colors
    - HSL is hue - saturation - lightness where hue=0 is red, hue=120 is green, hue=240 is blue
- Link colors: in Internal CSS, unclicked is `a:link { property:value; }`, clicked is `a:visited`, hover is `a:hover`
- `"background-color:powderblue;"` `"color:red"` `"font-size:60px;"` `"font-family:verdana;"` `"text-align:center;"`
- `"border:2px solid Violet;"` `"padding:30px;"` (between content and element) `"margin:50px"` (buffer outside element)
- Float image on hover: `<p><img ... style="float:left;">text_here</p>`
- Background image to non-image element: `"background-image: url('image_url_here');"`
    - Can also set background image for entire page by setting in Internal CSS: `body { background-image...; }`
    - This defaults to repeating-fill, so set this: `background-repeat:no-repeat;`
    - Covering an element: `background-attachment:fixed;` `background-size:cover;` `background-size: 100% 100%;`

<!-- Needs work -->
## CSS Examples
### HTML Table Example - CSS
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
      #                       #####                               
      #   ##   #    #   ##   #     #  ####  #####  # #####  ##### 
      #  #  #  #    #  #  #  #       #    # #    # # #    #   #   
      # #    # #    # #    #  #####  #      #    # # #    #   #   
#     # ###### #    # ######       # #      #####  # #####    #   
#     # #    #  #  #  #    # #     # #    # #   #  # #        #   
 #####  #    #   ##   #    #  #####   ####  #    # # #        #   
-->

# JavaScript

<!-- Needs work -->
## Javascript Basics
- HTML into action!
- Initiated and closed in HTML by `<script>` and `</script>`
    - External Javascript is pulled in with this syntax: `<script src="folder/javascript_code.js"></script>`
    - External Javascript files do not have `<script>` nor `</script>`
- Display script-disabled content: `<noscript>text_here</noscript>` (common use: "Please enable Javascript")
- Javascript actions are always followed by semicolon (few exceptions, just use semicolon every time)
- Functions work just like in other languages but with this syntax (definition): `function nameHere() { action; }`
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
### Javascript in Action
- Modifying HTML element attributes: `<script>document.getElementById("identifier").attribute = "new value";</script>`
    - Can modify CSS style like this: `<script>document.getElementById("identifier").style.fontSize = "35px";</script>`
- Modifying HTML element contents: `<script>document.getElementById("identifier").innerHTML = "input me!";</script>`
- Output something as HTML: `<script>document.write(5 + 6)</script>`
    - Outputting after a document loads (ex: load page, await user) will overwrite all HTML
- Alert in window: `<script>window.alert(5 + 6)</script>`
    - "window" is optional, can just do `<script>alert(5 + 6)</script>`
- Display data for debugging: `<script>console.log(5 + 6)</script>`
- Print page (like print to PDF): `<button onclick="window.print()">Print this page</button>`
    - The `onclick` attribute is an HTML "event", and is very common
    - Other events: onchange onmouseover onmouseout onkeydown onload
- Create an object: `const person = {firstName="Dean", lastName="Watson", age=50, eye_color="blue"};`
    - Value as function: `const person = {... fullName=function() {return this.firstName + " " + this.lastName;}};`
    - Access object's key values: `person.firstName` or `person["firstName"]` or `person.fullName()`
- Example function definition: `function functionName(param1, param2) { statement1; statement2; }`
    - Reminder: using `let` inside a function makes the variable block-scope, as in can't be used outside function
- Example function call: `document.getElementById("selector").innerHTML = functionName();`
    - Can also be called like this (self-invoked): `(function () { statement1; statement2; })();`
    - Portions of functions can be called like this: `person.fullName.call(person3);`
    - apply() instead of call() does an array instead of separate function arguments

## Javascript Examples
- Put text into id'd element: script document.getElementById("identifier").innerHTML = "input!"; /script
    - set style: document.getElementById("identifier").style.color = "red"
- Concatenate strings: script var txt1 = "start"; var txt2 = "coding"; document.getElementById("demo").innerHTML = txt1 + " " + txt2; /script

[[Return to Top]](#table-of-contents)






<!--
######                                                        
#     #  ####   ####  #####  ####  ##### #####    ##   #####  
#     # #    # #    #   #   #        #   #    #  #  #  #    # 
######  #    # #    #   #    ####    #   #    # #    # #    # 
#     # #    # #    #   #        #   #   #####  ###### #####  
#     # #    # #    #   #   #    #   #   #   #  #    # #      
######   ####   ####    #    ####    #   #    # #    # #      
-->

# Bootstrap

<!-- Needs work -->
## Bootstrap 5
- HTML, CSS, and Javascript through pre-designed templates
- Designed to speed up front-end development

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

<!-- Needs work -->
## jQuery Basics
- Simplifies Javascript for web dev

[[Return to Top]](#table-of-contents)