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
1.    [Bootstrap 5 Basics            ](#bootstrap-5)
2.    [Bootstrap 5 Example           ](#bootstrap-5)

V.    [jQuery                        ](#jquery)
1.    [jQuery Basics                 ](#jquery-basics)

VI.   [D3.js                         ](#d3.js)
1.    [D3 Basics                     ](#d3-basics)

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

<!-- Polished -->
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
    - use `<input type="range" step="10">` to add 10 ticks to range bar (default range is 0-100), slider can only tick onto the steps
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

<!-- Polished -->
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

<!-- Polished -->
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

<!-- Polished -->
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
    - Another version: `switch (input_me) { case first_match_input_try: statement; statement; case second_match_input_try: statement; ... }`
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

<!-- Needs work -->
## jQuery Basics
- Simplifies Javascript for web dev
- Big use is simplifying `document.getElementsByClassName("intro");` to `$(".intro")` and more
    - Classes: `$(".classname")`, elements: `$("elementtag")`, ID: `$("#identifier")`, drilling: `$("div p.classname")`

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