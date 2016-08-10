# Introduction

The intention of this guide is to provide a simple introduction to programming with JavaScript to **absolute beginners**. If you have used the language before and have a reasonable understanding of internet technologies this is probably not for you.

It will focus on the *functional* aspect of JavaScript, ignoring (for now) the various [Object-Oriented](https://en.wikipedia.org/wiki/Object-oriented_programming) features. 

See the [resources](/guide/javascript-resources.md) page for more information on some of the basic principles of JavaScript and the web. It is recommended that you take the *JavaScript* as well as *HTML* track on [Codecademy](https://www.codecademy.com).

## JavaScript can be Front-end or Back-End

What we're covering is **front-end**.

**Front-end** = the browser (e.g. Chrome, FireFox, Safari etc) do the work. So, if you have something very processor-intensive (e.g. lots of complex calculations) and your *host machine* is slow, then the processing may take some time, slowing your computer down.
When you see an animation on a web page, that is typically the front-end. Like [this](http://anime-js.com/).

**Back-end** = the code runs on a server/ collection of servers. 
E.g. this search for "Spongebob" on Amazon: https://www.amazon.co.uk/s/ref=nb_sb_noss_2?url=search-alias%3Daps&field-keywords=spongebob

A technology called [Node.js](https://nodejs.org/) allows you to run JavaScript on a server, meaning that Amazon could have been written using Node.js (but it probably wasn't).

## Front-End


When running JavaScript in a browser, you'll view a page which is in **HTML**, containing **CSS** and, of course, **JavaScript**. Like this:

<table>
<tr>
<td style="border:1px solid black;text-align:center;background-color:#EEE;">
<strong>HTML</strong>
    <table>
    <tr>
    <td style="border:1px solid black;width:25ex;text-align:center;background-color:white;">
    JavaScript
    </td></tr>
    </table>
    <table>
    <tr>
    <td style="border:1px solid black;width:25ex;text-align:center;background-color:white;">
    CSS
    </td></tr>
    </table>
</td></tr>
</table>


| |What it does|
|---|---|
|**HTML**|contains the content of the page you are viewing, including any structures like tables, lists etc. It's *not a programming language*, it's a *markup language*|
|**CSS**|(Cascading Style Sheets) is a set of rules that define how the HTML looks|
|**JavaScript**|A scripting language and the reason you are here!|

## How It's All Connected

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

## Do this:

You are currently viewing a web page. Right-click it and select the *View Source* option. That will show you the HTML, CSS and JavaScript needed to make this page.

## The Language

[Keep reading](/guide/language-basics.md)