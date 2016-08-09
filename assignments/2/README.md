# What Is This?

The intention of this guide is to provide a simple introduction to programming with JavaScript to **absolute beginners**. If you have used the language before and have a reasonable understanding of internet technologies this is probably not for you.

## Basics

### JavaScript can be Front-end or Back-End

What we're covering is **front-end**.

Front-end = the browser (e.g. Chrome, FireFox, Safari etc) do the work. So, if you have something very processor-intensive (e.g. lots of complex calculations) and your *host machine* is slow, then the processing may take some time, slowing your computer down.

Back-end = the code runs on a server/ collection of servers. 
E.g. this search for "Spongebob" on Amazon: https://www.amazon.co.uk/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=spongebob

A technology called [Node.js](https://nodejs.org/) allows you to run JavaScript on a server, meaning that Amazon could have been written using Node.js (but it probably wasn't).

#### Front-End

When running JavaScript in a browser, you'll view a page which has **HTML**, **CSS** and, of course, **JavaScript**.

**HTML** contains the content of the page you are viewing, including any structures like tables, lists etc. It's *not a programming language*, it's a *markup language*.

**CSS** (Cascading Style Sheets) is a set of rules that define how the HTML looks.

**JavaScript** is why we're all here!

##### How It's All Connected

Here's some sample HTML. Note: ```<!--``` and ```-->``` are start and end tags for comments.

    <html>
    <head>
        <script type="text/javascript" src="/js/main.js"></script>  <!-- this is a link to the JavaScript -->
        <link rel="stylesheet" href="/css/main.css" />              <!-- this is a link to the CSS -->
    </head>
    <body>
        <script type="text/javascript">                             <!-- this is JavaScript embedded in the page -->
            var count = 1;
        </script>
        <style type="text/css">                                     <!-- this is CSS embedded in the page -->
            P {
                font-weight: bold;
            }
        </style>
        <p>This is the main page</p>
    </body>
    </html>

**DO THIS:**

Right-click the page you are viewing and select the *View Source* option. That will show you the HTML, CSS and JavaScript (if any) needed to make that page.

#### The Language

Keeping things simple, JavaScript consists of:

- constants
- variables
- assignments
- conditions
- blocks
- functions
- statements
- loops
 
|What|JavaScript Example|
|---|---|
|constant|```12``` or ```"some words"```. They are both constants. 12 will always be 12.|
|variable|```var count = 1;``` *count* is a variable. It's value may change.|
|assignment|```count = 2``` Assigns the variable *count* with the value 2. **Note:** single =|
|condition|```count == 2``` Checks whether the variable *count* is equal to 2. **Note:** double =|
|block|```{ var count = 1; var x = 2; }```. *count* and *x* are only available between the *{* and *}*|
|function|```function celsiusToFahrenheit(celsius)```. Defines the function *celsiusToFahrenheit* which takes one parameter, *celsius*|
|statement|```if (count == 2) { alert("it's two!"); }```. Checks the variable count and if it's equal to 2 displays a message|
|loop|```for (var count = 1; count < 10; ++count) { alert(i); }```. Will display the messsage 1, then 2, then 3, until 9|
|loop|```while (count < 10) { alert(count); ++count;  }```. Will display the messsage 1, then 2, then 3, until 9|

##### Execution Order

JavaScript is processed top-down, looping where necessary. When the code gets to the last line, it has typically finished.

###### Loops


##### Types
|Type|Description|
|---|---|
|String|e.g. ```"hello"```, ```'hello'``` etc|
|Number|e.g. ```1```, ```3.1415972```|
|Boolean|e.g. ```true``` or ```false```|
|Undefined|A special value when a value is not specified. More on this later.|
|Null|A value representing "no value". E.g. a value of ```NULL``` has actually specified, typically to initialise a variable. *Not the same as undefined*.|
|Object|An instance of an object which may be your own object (when using Object-Oriented techniques) or one of the in-built classes (e.g. RegExp).|
|Array|A collection of values - which may be of any type, but will typically be of the same type. E.g. a list of names ```["Dave", "Pete", "John"];```|

###### Reserved Words

There is a lengthy list of [reserved words](http://www.w3schools.com/js/js_reserved.asp) which you may not use for variable names - mainly because they would cause ambiguity. Many words on that list will not yet be familiar to you, but as you progress you will understand why you are not allowed to use them for anything other than their defined purpose.

Consider this for example:

    var true = false;
    if (true == true)
    {
        console.log("It's true");
    }
    
We are trying to find out whether a variable named *true* is "true". It makes the code ambiguous and is not allowed.    
