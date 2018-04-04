# Object Oriented Programming

JavaScript supports Object-Oriented programming (OOP), and as of `ECMAScript 6` (finalised in 2016), features a few new features to make OOP easier - chiefly, the `class` keyword.

## Object Initialisers

Before we get into the ins-and-outs of OOP, let's take a small, related diversion into the shortcut syntax used for creating both arrays and simple *objects* with *properties*.
 
```javascript
let list1 = [];                         // This is an array
let list2 = [1, 2, 3];                  // This is an array containing the numbers: 1, 2 and 3
let list3 = ["Dave", "Pete", "John"];   // This is an array containing the strings: "Dave", "Pete" and "John"
``` 

So far, so easy.

Now in that third example (`list3`) we were storing names. What about if we wanted surnames? That's where creating simple objects comes in:
```javascript
let dave = {
    firstName:  "Dave",
    surname:    "Doolittle"
};
```

We just created a simple object that had the *properties*: `firstName` and `surname`. The values of those properties were: "Dave" (for `firstName`) and "Doolittle" (for `surname`);

We can also combine arrays and simple objects:
```javascript
let people = [ 
    {
        firstName:  "Dave",
        surname:    "Doolittle"
    },
    {
        firstName:  "Peter",
        surname:    "Piper"
    },
];
```

We created an array (`people`) which contained 2 entries - one with "Dave Doolittle" and the other with "Peter Piper".
 
This combination of arrays and simple objects is a convenient way of working or configuraing JavaScript programs. 

## What is Object Oriented Programming?

So far, everything we've done has be "functional" in that we've defined variables and functions which can all be used with each other, which is fine provided the *scope* of the application is small.

Programming in this way soon becomes tricky because any `function` can modify any `variable`. Once the *scope* gets larger (as is often the case on anything outside of a demo), things get trickier.

With OOP, you have the addition of: `classes`, `objects` - which have `properties` and `methods` (functions, but specific to a class of object).
  
## Why Object Oriented Programming?

The idea is that we *model* our program using things which relate to the real world - objects. 

Before we get into that, let's consider this *functional* example - we want to record the names and addresses of people registering for an event. We create code like this to cater for it:

```javascript
let list = [];

function addPerson(firstName, surname, address, postcode)
{
    let entry = {
        firstName: firstName,
        surname: surname,
        address: address,
        postcode: postcode
    };
    list.push(entry);
}

```

Here, we've used the simple object notation (see above) to create an entry (`entry`) which has the properties: `firstName`, `surname`, `address` and `postcode`.

We now want to add the date of birth to the list - to ensure, for example, that only adults are in the list.

```javascript
let list = [];

function addPerson(firstName, surname, address, postcode, dateOfBirth)
{
    var entry = {
        firstName: firstName,
        surname: surname,
        address: address,
        postcode: postcode,
        dateOfBirth: dateOfBirth
    };
    list.push(entry);
}

// Let's add someone to the list...
addPerson("Dave", "Doolittle", "12 High Street,Camden", "NW1 0JA", "26/7/2000");
```

We then realise that we might have more than one list, so rather than tie the `addPerson` function to the `list` variable, we accept an array as a parameter:

```javascript
let list = [];

function addPerson(toThisList, firstName, surname, address, postcode, dateOfBirth)
{
    var entry = {
        firstName: firstName,
        surname: surname,
        address: address,
        postcode: postcode,
        dateOfBirth: dateOfBirth
    };
    toThisList.push(entry);
}

// Let's add someone to the list...
addPerson(list, "Dave", "Doolittle", "12 High Street,Camden", "NW1 0JA", "26/7/2000");
```

Next we are told that we are told that we may need to be able to change the address of a given person, but: how do we identify a person? Firstname + surname? Firstname, surname and date of birth?
You can't really guarantee that for a very large database (e.g. a typical sales system) that the name + date of birth fields would be unique, so we'd need to add an ID for them:

```javascript
let list = [];

function addPerson(toThisList, id, firstName, surname, address, postcode, dateOfBirth)
{
    ... 
}

// Let's add someone to the list...
addPerson(list, 1, "Dave", "Doolittle", "12 High Street,Camden", "NW1 0JA", "26/7/2000");
```

Every time we need to make a change to `addPerson`, we need to amend **every** call to `addPerson`. And that function's parameter list is getting longer-and-longer (hence more complicated).

### The OOP Way

Using our example from above, we are dealing with *people* and *lists*. People are a class of "Person". "Dave" is an instance of Person (an object). 

To model this problem using OOP, we'd create a class called "Person" which would have the properties:  `firstName`, `surname`, `address`, `postcode` and `dateOfBirth`.

Like this:

```javascript
class Person
{
    constructor(firstName, surname, address, postcode, dateOfBirth)
    {
        this.firstName = firstName;
        this.surname = surname;
        this.address = address;
        this.postcode = postcode;
        this.dateOfBirth = dateOfBirth;
    }
}

let dave = new Person("Dave", "Doolittle", "12 High Street,Camden", "NW1 0JA", "26/7/2000");
console.log(dave);  // Show that it's worked
```

So, what's going on there, then? 
- line 1: declares the class `Person`
- line 3: `constructor` is something special that is called when construct-ing the object
- lines 5-9: use the special `this` keyword to declare and assign the properties: `firstName`, `surname`, `address`, `postcode` and `dateOfBirth`
- finally, we create an object (or "instance", if you like) called `dave` - initialised with the same values as in our functional example. We use `console.log` as a simple test to show it's working

It might be that we don't always have a person's address initially, so we could allow for the address to be added to the person later:

```javascript
class Person
{
    constructor(firstName, surname, dateOfBirth)
    {
        this.firstName = firstName;
        this.surname = surname;
        this.address = null;    // Initialise to null so that the property exists
        this.postcode = null;   // Initialise to null so that the property exists
        this.dateOfBirth = dateOfBirth;
    }
    
    setAddress(address, postcode)
    {
        this.address = null;
        this.postcode = null;
    }
}

let dave = new Person("Dave", "Doolittle", "26/7/2000");
dave.setAddress("12 High Street,Camden", "NW1 0JA");
console.log(dave);  // Show that it's worked
```

With our amended code, we were able to create `dave` and later add his address. 
