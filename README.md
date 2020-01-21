# Beginners Guide to PHP Syntax


## Commenting
---

```
// This is a single line comment

/* This is a multiple line comment */
```

## Defining Variables 
---

```
<?php
    $NewVariable = "This is a variable";
?>
```

- Variable names are case sensitive.
- Variable names must start with a letter or an underscore, and cannot start with a number
- Variable names can only contain alpha-numerica characters and underscores.
- Variable names cannot contain spaces.

## Echo & Print Statements
---

_**Echo** and **print** are both used to output data to the screen_

Echo can accept multiple parameters, and has no return value.  Echo is faster than print.

Print can only accept one argument, and has a return value of 1, making it useful in expressions.  

## Echo 

```
<?php
    $variable = "You can include variables in echo statements.";

    echo $variable;
    echo "This outputs a string.";
    echo "<p>You can also include HTML in an echo statement.</p>"
?>
```

## Print

```
<?php
    $variable = "You can print variables too.";

    print $variable;
    print "This outputs a string.";
    print "<p>Print statements also allow HTML markup.</p>";
?>
```

## Data Types 
---

The following data types are supported in PHP:

- Integers
- Strings
- Floating Point Numbers
- Booleans
- Arrays
- Objects
- NULL 
- Resource

## Integers

Integers are non-decimal whole numbers between -2,147,483,648 and 147,483,647.  Numbers can be in decimal, hexadecimal, or octal.

```
<?php
   echo 789;
?>
```

## Strings

Strings are sequences of characters enclosed in single or double quotes.

```
<?php
    echo "This is a string";
?>
```

## Floating Point Numbers

A floating point number is a number in exponential form, or a number with a decimal point.

## Booleans

Booleans are true/ false statements where 1 = true and 0 = false.

```
<?php
    $x = true;
?>
```

## Arrays

Arrays are variables that hold several values.

```
<?php
    $cities = array("Vancouver", "Toronto", "Montreal", "Calgary");
    
    echo $cities;
?>
```

## Objects

Objects store data and information on how the data should be processed.  

Objects are created by first declaring the parent class of the object, then creating objects that belong to the class with its own properties and methods.

```
<?php
    class Animal {
        // Empty class Animals has been defined
        public $family;
        
        function animalFamily($family) { // Properties
            $this->family = $family;
            
        }
        
         function getFamily() { // Methods
            return $this->family;
            
         }
    }



    $Elephant = new Animal(); // New object is created
    $Elephant->animalFamily('Elephantidae');
    echo "The Elephant is a member of the " . $Elephant->getFamily() . " family.";
?>
```

## NULL Values

NULL values represent empty variables that have no data assigned to them.  The value of NULL can only be NULL.  If a variable has not been assigned a value, it will automatically be considered a NULL value.

```
<?php
    $y = NULL;
    echo $y; // This will have no output
?>
```

## Resources

Resources are not a data type in the traditional sense.  A resource references an external source such as a database. 

```
<?php
// Check database connection
if($database = mysqli_connect('localhost','user','password','database')){
    echo "Successfully Connected";
}
?>
```

## Strings & String Functions
---

## Strings

Strings are sequences of characters enclosed in single('') or double ("")quotations.

Strings within single quotations are unable to process special characters, making it impossible to interpret the $ sign at the beginning of the variable name.  

```
<?php

    // single quoted string

    $firstName = 'Clementine';
    echo 'Hello $firstName!'; // outputs "Hello $firstname"
?>
```

Double quoted strings, on the other hand, can interpret variables and can also recognize special characters by using Escape Sequences.

```
<?php

    // double quoted string

    $firstName = "Clementine";
    echo "Hello $firstName!"; // outputs "Hello Clementine"
?>
```

## Escape Sequences

|    	|                 	|
|----	|-----------------	|
| \n 	| Linefeed        	|
| \r 	| Carriage Return 	|
| \t 	| Horizontal Tab  	|
| \v 	| Vertical Tab    	|
| \e 	| Escape          	|
| \f 	| Form Feed       	|
| \\ 	| Backslash       	|
| \$ 	| Dollar Sign     	|
| /' 	| Single Quote    	|
| \" 	| Double Quote    	|


## String Functions

Below are some commonly used string functions.

## strlen()
strlen() displays the number of characters within a string, including spaces.

```
<?php
    echo strlen("What is the length of this string?"); 
?>

// outputs "34"
```

## str_word_count()
str_word_count() displays the number of words within a string, including spaces.

```
<?php
    echo str_word_count("How many words are in this string?"); 
?>

// outputs "7"
```

## strrev()
strrev() displays the string in reverse.

```
<?php
    echo strrev("Go backwards"); 
?>

// outputs "sdrawkcab oG"
```

## strpos()
strpos() makes it possible to search the text within a string.  If the search is successful, it returns the position of the result (starting position is 0).  Otherwise, it will return "False".

```
<?php

    // search for the world "string" in the string "This is a string"

    echo strpos("This is a string", "string"); 
?>

// outputs "10"
```

## str_replace

str_replace is used for replacing certain text within a string.

```
<?php

    // replace the word "Clementine" with "Lola" inside the string "Good morning Clementine"

    echo str_replace("Clementine", "Lola", "Good morning Clementine"); 
?>

// outputs "Good morning Lola"
```

## Numbers
---

## Integers

As discussed above, Integers are non-decimal whole numbers between -2,147,483,648 and 147,483,647.  Numbers can be in decimal, hexadecimal, or octal.

### Integer Rules

- Integers must contain atleast one digit
- Integers cannot contain decimal points
- Integers can be either positive or negative
- Integers be in decimal, hexadecimal, or octal format.

### 3 Ways to Check if a Variable is an Integer

- is_int()
- is_integer()
- is_long()
 
*All three functions return true(1) if the variable is an integer, false(nothing) is returned otherwise.*

```
<?php
    $a = 1234;
    echo is_int($a); // returns 1, integer

    $b = 1.234;
    echo is_integer($b); // returns nothing, not an integer

    $c = "abc";
    echo is_long($c); // returns nothing, not an integer
?>
```

## Floating Point Numbers (Floats/Doubles)

Floating point numbers are numbers in exponential form or numbers with a decimal point. By default, floating point numbers print with the minimum number of decimal places needed.

Floats can store values up to 1.7976931348623E+308, depending on the platform.  They also have a maximum precision of 14 digits.

### 2 Ways to Check if a Variable is a Floating Point Number

- is_float()
- is_double()

*Both functions return true(1) if the variable is a float, false(nothing) is returned otherwise.*

```
<?php
    $a = 1234;
    echo is_float($a); // returns nothing, not a float

    $b = 1.234;
    echo is_integer($b); // returns 1, float

    $c = 1.e7;
    echo is_long($c); // returns 1, float
?>
```

## Infinite Numbers

In PHP, infinite numbers are numeric values that are larger than PHP_FLOAT_MAX.  

### 2 Ways to Check if a Variable is Infinite

- is_finite()  --- *returns true(1) if the variable is infinite, false(nothing) is returned otherwise.*
- is_infinite()  --- *returns true(1) if the variable is finite, false(nothing) is returned otherwise.*


```
<?php
    $a = log(0);
    echo is_infinite($a); // returns 1, infinite value

    $b = 1.234;
    echo is_infinite($b); // returns nothing, value is finite

    $c = 1.e7;
    echo is_finite($c); // returns 1, finite value
?>
```

## NaN

NaN stand for Not a Number, and is used for impossible mathematical operations.

### How to Check if a Variable is Not a Number

- is_nan()

*returns true(1) if the variable is not a number, false(nothing) is returned otherwise.*

```
<?php
    $a = acos(8);
    echo is_nan($a); // returns 1, not a number

    $b = 1.234;
    echo is_nan($b); // returns nothing, value is a number

?>
```

## Constants
---

A constant is a variable like identifier, but unlike variables, a constant cannot be changeD.  Constants are globally scoped.

Constant names must begin with a letter or underscore, no $ is required at the beginning of the name.

### Defining a Constant:
- define("constantName", "constantValue") 


```
<?php
    define("favouriteColour", "Orange");
    echo favouriteColour; // outputs "Orange"
?>
```

## Operators
---

### Arithmetic Operators

Arithmetic Operators are used to perform arithmetical operations with numeric values.

*For the following examples, assume $x = 2 and $y = 4*


| Operator 	| Name           	| Example                	|
|----------	|----------------	|------------------------	|
| +        	| Addition       	| $x + $y //returns 6    	|
| -        	| Subtraction    	| $x - $y //returns -2   	|
| *        	| Multiplication 	| $x * $y //returns 8    	|
| /        	| Division       	| $y / $x //returns 2    	|
| %        	| Modulo         	| $y % $x // returns 0   	|
| **       	| Exponentiation 	| $y ** $x // returns 16 	|

### Assignment Operators

Assignment Operators are used to write values to variables.

| Assignment 	| Same as   	|
|------------	|-----------	|
| a += b     	| a = a + b 	|
| a -= b     	| a = a - b 	|
| a *= b     	| a = a * b 	|
| a /= b     	| a = a / b 	|
| a %= b     	| a = a % b 	|

### Comparison Operators

Comparison Operators are used to compare two values.

| Operator 	| Name                                 	|
|----------	|--------------------------------------	|
| ==       	| Equal                                	|
| ===      	| Not Equal                            	|
| !=       	| Not Identical                        	|
| <>       	| Less Than                            	|
| !==      	| Greater Than                         	|
| <        	| Less Than                            	|
| >        	| Greater Than                         	|
| <=       	| Less Than or Equal To                	|
| >=       	| Greater Than or Equal To             	|
| <=>      	| Less Than, Equal To, or Greater Than 	|

### Logical Operators

Logical Operators are used to combine conditional statements.

| Operator 	| Name                                 	|
|----------	|--------------------------------------	|
| and      	| And                                	|
| or      	| Or                            	    |
| xor      	| Exclusive Or                        	|
| !       	| Not                                  	|
| &&      	| And                                  	|
| ||       	| Or                                	|

### Increment/Decrement Operators 

The increment/decrement operators are used to increment/decrement a variables value.

| Operator 	| Description                                 	|
|----------	|--------------------------------------	|
| ++$v      | Increments a variable by one, then returns it                                	|
| $v++      	| Returns a variable, then increments it by one                            	    |
| --$v      	| Decrements the variable by one, returns it afterward                         	|
| $v--       	| Returns the variable then decrements it by one                                   	|

### String Operators


| Operator 	| Description                                 	|
|----------	|--------------------------------------	|
| .      	| Used to concatenate arguments                                	|
| .=      	| Used to append the argument on the right to the left argument                            	    |

## Conditional Statements
---

### If Statement

Executes code if one condition is met.

```
if (condition) {
 // code to execute if condition is met
} 
```

### If.. Else

Executes one piece of code if a condition is met, and different piece of code if not.

```
if (condition) {
 // code to execute if condition is met
} else {
 // code to execute if condition is not met
} 
```

### If.. Elseif.. Else

Executes different code for more than two conditions.

```
if (condition) {
 // code to execute if condition is met
} elseif (condition) {
 // code to execute if this condition is met
} else {
 // code to execute if none of the conditions are met
} 
```

## Functions
---

### Built In Functions

PHP has a large collection of built in functions that can be easily called from directly within your php script.  These functions allow you to perform specific tasks.  There are a ton of great lists of built in functions out there.

### User-Defined Functions

You can also create your own functions within PHP.  Building functions can save you a lot of time and effort by automating things.

### Creating a Function

```
function function_name(){
    executable code;
}
```

### Function Parameters or Arguments

```
function function_name($first_parameter, $second_parameter) {
    executable code;
}
```

## Arrays
---

Arrays are variables that hold several values of a similar data type.

### 3 Types of Arrays

| Name 	| Description                               	|
|----------	|--------------------------------------	|
| Indexed Arrays     	|     Arrays that have a numeric index                          	|
| Associative Arrays     	| Arrays where the keys are named                           	    |
| Multidimensional Arrays      	| Arrays that contain one or more other arrays                       	|

### Declaring an Array

```
<?php
    $colours = array("Red", "Blue", "Yellow");

    echo "What is your favorite Colour? Is it " . $colours[0] . ", " .
    $colours[1] . " or " . $colours[2] . "?";
?> 

// outputs "What is your favorite Colour? Is it Red, Blue or Yellow?"
```

## Loops
---

Loops are used to execute the same code over and over again, if a certain condition has been met.

### While Loop

Loops through a block of code if condition is met

```
while (condition that must apply) {
 // code to execute goes here
} 
```

### Do.. While Loop

The block of code is executed once before the condition is evaluated.  If the condition is met, the statement repeats forever as long as the condition stays true.

```
do {
 // code to execute goes here;
} while (condition that must apply); 
```

### For Loop

Loops through a block of code until the counter reaches a specified number.

```
for (starting counter value; ending counter value; increment by which
to increase) {
 // code to execute goes here
} 
```

### Foreach Loop

Loops through a block of code once for each element within an array.

```
foreach ($InsertYourArrayName as $value) {
 // code to execute goes here 
}
```