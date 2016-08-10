# The Language

Keeping things simple, JavaScript consists of:

- constants
- variables
- operators
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
|operator|```5 + 5``` or ```20 / 3``` or ```3 * 6``` or ```++``` (add one) or ```--``` (subtract one) and more. ```=``` is an **assignment** operator (see below)|
|assignment|```count = 2``` Assigns the variable *count* with the value 2. **Note:** single =|
|assignment|```count += 2``` Adds 2 to the variable *count*. ```count -= 2``` Takes 2 away from the variable *count*|
|condition|```count == 2``` Checks whether the variable *count* is equal to 2. **Note:** double =|
|block|```{ var count = 1; var x = 2; }```. *count* and *x* are only available between the *{* and *}*|
|function|```function celsiusToFahrenheit(celsius)```. Defines the function *celsiusToFahrenheit* which takes one parameter, *celsius*|
|statement|```if (count == 2) { alert("it's two!"); }```. Checks the variable count and if it's equal to 2 displays a message|
|loop|```for (var count = 1; count < 10; ++count) { alert(i); }```. Will display the messsage 1, then 2, then 3, until 9|
|loop|```while (count < 10) { alert(count); ++count;  }```. Will display the messsage 1, then 2, then 3, until 9|

## Execution Order

JavaScript is processed top-down, looping where necessary. When the code gets to the last line, it has typically finished.

### Loops


### Types
|Type|Description|
|---|---|
|String|e.g. ```"hello"```, ```'hello'``` etc|
|Number|e.g. ```1```, ```3.1415972```|
|Boolean|e.g. ```true``` or ```false```|
|Undefined|A special value when a value is not specified. More on this later.|
|Null|A value representing "no value". E.g. a value of ```NULL``` has actually specified, typically to initialise a variable. *Not the same as undefined*.|
|Object|An instance of an object which may be your own object (when using Object-Oriented techniques) or one of the in-built classes (e.g. RegExp).|
|Array|A collection of values - which may be of any type, but will typically be of the same type. E.g. a list of names ```["Dave", "Pete", "John"];```|

### Reserved Words

There is a lengthy list of [reserved words](http://www.w3schools.com/js/js_reserved.asp) which you may not use for variable names - mainly because they would cause ambiguity. Many words on that list will not yet be familiar to you, but as you progress you will understand why you are not allowed to use them for anything other than their defined purpose.

Consider this for example:

    var true = false;
    if (true == true)
    {
        console.log("It's true");
    }
    
We are trying to find out whether a variable named *true* is "true". It makes the code ambiguous and is not allowed.    
