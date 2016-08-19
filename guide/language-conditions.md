# Conditions and Statements

Conditions allow you to check the state (condition) of variables. To check condition you use logical operators, like: ```==``` (is equal to), ```<``` and ```>``` (less than and greater than) and more.

The result of a condition is always a *boolean* - ```true``` or ```false```.

E.g.

    var age = 18;
    var olderThan18 = age > 18;    // == false
    var youngerThan18 = age < 18;  // == false
    var isAnAdult = age >= 18;     // == true
    var is18 = age == 18;          // == true

## Logical Operators

Keeping things simple, we have AND (```&&```), OR (```||```), NOT (```!```) and NOT EQUAL (```!=```).

E.g.

    var age = 18;
    var ageBetween18And21 = age >= 18 && age <= 21;  // true
    var doesntNeedToWork = age <16 || age >= 65;     // false
    var isNot21 = age != 21;                         // true
