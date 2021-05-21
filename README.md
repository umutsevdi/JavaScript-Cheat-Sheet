# JavaScript-Cheat-Sheet
# JavaScript Essentials -1

# 1.0 - Declarations
In JavaScript values are hold in declarations which operates similar to pointers. Each of those declerations are made with the type name followed by an identifier. In JavaScript a declaration can be made by one of three operators which are : 
* var : function scoped definition
* const : block scoped definition, can not be changed once initialized
* let : block scopped definition

## 1.0.1 - Variable : 
Variable can be optionally initialized and can be used even before the initialization unlike most of the programming languages : 
```js
    var x;
    typeof(x); // undefined
    x=15;
    typeof(x); //number
```

## 1.0.2 - Constant : 
Constant is a value that can not be changed once initialized. 
```js
    const x = 20;
```

## 1.0.3 - Let : 
Let can be optionally initialized and can be used even before the initialization unlike most of the programming languages : 
```js
    let  x;
    typeof(x); // undefined
    x=15;
    typeof(x); //number
```

# 1.1 Data Types

The latest ECMAScript standard defines eight data types which are :
* undefined
* null
* boolean
* number
* string
* symbol
* function
* bigint

All values other than those primitives are referred as objects.

JavaScript is a dynamically typed language which means that the data types of the variables are specified during the execution of the code. 

Variables can be reassigned to another data type without restrictions.

Data Type of an object can be seen via `typeof` function. 
```js
var x = 15;
console.log(typeof(x)) //number
x = function(){
    //doSomething
}
console.log(typeof(x)) //function
```

## 1.1.1 - Data Type Conversion : 
* When a string and a number is used with `+` operator , number is converted to string.
    ```js
    var x = 50;
    x = 50 + " 10 " // x = " 5010 "
    ```
    However rest of the operators do not contain same feature.
    ```js
    var x  = "50";
    x = x - 7; // 43
    ```

* To convert string to a number we can use `parseInt()` , `parseFloat()` functions.

* Another way to convert a String to int is `Number()` function. 

    ```js
    parseInt("100"); // 100;
    parseInt("100" , 2); // 4;
    Number("16"); // 16;
    ```
### 1.1.1.1 - Data Type Conversion Values :
| Value     | Number | String      | Boolean |
| --------- | ------ | ----------- | ------- |
| 1         | 1      | "1"         | true    |
| 0         | 0      | "0"         | false   |
| "1"       | 1      | "1"         | true    |
| "0"       | 0      | "0"         | false   |
| "ten"     | NaN    | "ten"       | true    |
| true      | 1      | "true"      | true    |
| false     | 0      | "false"     | false   |
| null      | 0      | "null"      | false   |
| undefined | NaN    | "undefined" | false   |
| ""        | 0      | ""          | false   |
| " "       | 0      | " "         | true    |

Inside a function you can use this line of code to place a valid data type to a variable.
```js
b = typeof b !== 'undefined' ?  b : 1;
```
## 1.1.2 - Data Types : 
### 1.1.2.1 Strings 
* You can access an element of a string just like using arrays.
```js
    let myString="Hello World";
    console.log(myString[1]); //e
    console.log(myString.charAt(4)); //o
```
* However you can not change a character in string.
```js
    let myString="Hello World";
    myString[0]="h";
    console.log(myString); // Hello World
```

| Method                                       | Description                                             |
| -------------------------------------------- | ------------------------------------------------------- |
| concat()                                     | joins two or more strings                               |
| replace()                                    | replaces a string with another string                   |
| split()                                      | converts the string to an array of strings              |
| substr(start, length) / substring(start,end) | returns a part of a string                              |
| trim()                                       | removes whitespace from the strings                     |
| slice(start, end)                            | returns a part of a string                              |
| toLowerCase() / toUpperCase()                | returns the passed string in lower / upper case         |
| includes()                                   | searches for a string and returns a boolean value       |
| search()                                     | searches for a string and returns a position of a match |
| String()                                     | transforms given object to string                       |

```js
const text1 = 'hello';
const text2 = 'world';
const text3 = '     JavaScript    ';

// concatenating two strings
const result1 = text1.concat(' ', text2);
console.log(result1); // "hello world"

// converting the text to uppercase
const result2 = text1.toUpperCase();
console.log(result2); // HELLO

// removing whitespace from the string
const result3 = text3.trim();
console.log(result3); // JavaScript

// converting the string to an array
const result4 = text1.split();
console.log(result4); // ["hello"]

// slicing the string
const result5= text1.slice(1, 3);
console.log(result5); // "el"
```

#### 1.1.2.1.4.2 - Strings Commands	
| Code | Output               |
| ---- | -------------------- |
| \"   | include double quote |
| \\   | include backslash    |
| \n   | new line             |
| \r   | carriage return      |
| \v   | vertical tab         |
| \t   | horizontal tab       |
| \b   | backspace            |
| \f   | form feed            |

### 1.1.2.2 - Numbers
* There are certain definitions in numbers which are : 
  * NaN : not a number,  is a keyword that indicates that the value is not a number.
    ```js
    const value = "hello" - 2; // NaN
    ```
  * Infinity : In JavaScript, when calculation is done that exceeds the largest (or smallest) possible number, Infinity (or -Infinity) is returned. 
    ```js
    const value = 2 / 0; // Infinity
    ```
  * BigInt : In JavaScript, Number type can only represent numbers less than (253 - 1) and more than -(253 - 1). However, if you need to use a larger number than that, you can use the BigInt data type.

    A BigInt number is created by appending n to the end of an integer. For example,

    ```js
    const value = 900719925124740998n;
    ```

| Method                        | Description                                                           |
| ----------------------------- | --------------------------------------------------------------------- |
| isNaN()                       | determines whether the passed value is NaN                            |
| isFinite()                    | determines whether the passed value is a finite number                |
| isInteger()                   | determines whether the passed value is an integer                     |
| isSafeInteger()               | determines whether the passed value is a safe integer return          |
| parseFloat(string)            | converts the numeric floating string to floating-point number         |
| parseInt(string, [radix])     | converts the numeric string to integer                                |
| toExponential(fractionDigits) | returns a string value for a number in exponential notation           |
| toFixed(digits)               | returns a string value for a number in fixed-point notation           |
| toPrecision()                 | returns a string value for a number to a specified precision          |
| toString([radix])             | returns a string value in a specified radix(base)                     |
| valueof()                     | returns the numbers value                                             |
| toLocaleString()              | returns a string with a language sensitive representation of a number |


Constants : 
* EPSILON :	returns the smallest interval between two representable numbers
* MAX_SAFE_INTEGER :	returns the maximum safe integer
* MAX_VALUE	returns : the largest possible value
* MIN_SAFE_INTEGER :	returns the minimum safe integer
* MIN_VALUE :	returns the smallest possible value
NaN	represents 'Not-a-Number' value
* NEGATIVE_INFINITY :	represents negative infinity
* POSITIVE_INFINITY :	represents positive infinity
	
### 1.1.2.3 - Symbols
Symbols are immutable (cannot be changed) and are unique. For example : 
```js
const value1 = Symbol('hello');
const value2 = Symbol('hello');

console.log(value1 === value2); // false
```
Symbols are created with a description, to access it use;
`symbol.description`.

Unlike other data types, symbols are ignored in loops. And because of that symbols can be stored in objects without causing name issues.
```js
const id = Symbol("id");
let myObj={
    name:"Josh",
    id:123213,
    [id]:7
}
```
| Method     | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| for()      | Searches for existing symbols                                |
| keyFor()   | Returns a shared symbol key from the global symbol registry. |
| toSource() | Returns a string containing the source of the Symbol object  |
| toString() | Returns a string containing the description of the Symbol    |
| valueOf()  | Returns the primitive value of the Symbol object.            |
	
	
Symbol Properties
* asyncIterator	Returns the default AsyncIterator for an object
* hasInstance	Determines if a constructor object recognizes an object as its instance
* isConcatSpreadable	Indicates if an object should be flattened to its array elements
* iterator	Returns the default iterator for an object
* match	Matches against a string
* matchAll	Returns an iterator that yields matches of the regular expression against a string
* replace	Replaces matched substrings of a string
* search	Returns the index within a string that matches the regular expression
* split	Splits a string at the indices that match a regular expression
* species	Creates derived objects
* toPrimitive	Converts an object to a primitive value
* toStringTag	Gives the default description of an object
* description	Returns a string containing the description of the symbol	
	
### 1.1.2.4 - Functions

* A function is a block of code that performs a specific task.
* Functins can be defined in various ways : 
```js

// Default function definition
function myFunction(key){

}

// Function as an expression
const myFunction = function(key){

}

// Arrow Function definition
const myFunction = (key) => {

}
```
The difference : functions that are defined as an expressions can not be hoisted, meaning that calling them before the definition causes an error.

```js
myExpressiveFunction(); // causes error

const myExpressiveFunction = function(){
    console.log("expression");
}

myDefinitiveFunction(); // definition
function myDefinitionFunction(){
    console.log("definition");
}
```

Functions can return a value and it can be assigned to another variable.
```js
function sum( num1 , num2 ){return num1 + num2; };
let x = sum(3,5);
```
Functions can return multiple values at the same time by using objects.
```js
function returnExample(){
    return { name : "Max" , value : 15 };
}
let x = returnExample();
### 1.1.2.5 - Arrays

Arrays are a type of object that contains multiple objects. Unlike arrays in other programming 
languages they behave similar to lists. New values can be added or existing ones can be removed. 
Also arrays in javascript can contain different types of data.
```js
const myArray = [
   15,
   { name: 15, value: 7 },
  "text",
   function () { return -1; }
];
```
* As you see in the example constant myArray contains
a number, an object, a string and one function

* To add an element to an array use, `push()` or `unshift()` functions. 
  * `push()` places element to the end of the array.
  * `unshift()` adds an element to the beginning of the array.
```js
    var myArray=[1,2,3];
    myArray.push(4);
    myArray.push(5);
    myArray.unshift("numbers");
    console.log(myArray); // ["numbers",1,2,3,4,5];
```
* To change an element or use an element use `arrayName[index]`. This returns the element with given index.
* To remove an element from an array use `pop()` or `shift()`functions. 
  * `push()` removes the last element from the array.
  * `unshift()` removes the first element from the array.


```js
    var myArray=["a","b","c","d"];
    myArray.pop();
    console.log(myArray); // ["a","b","c"];
    myArray.pop();
    console.log(myArray); // ["a","b"];
    myArray.shift();
    console.log(myArray); // ["b"];

```
* To see the number of elements in the array use `arrayName.length`.
#### 1.1.2.1.1 - Other Array Functions : 

| Method                  | Description                                                                                                                    |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| concat()                | joins two or more arrays and returns a result                                                                                  |
| filter(function(key){}) | calls a function by placing each element as function property, returns an array of elements that are returned by the function. |
| indexOf()               | searches an element of an array and returns its position                                                                       |
| concat()                | joins two or more arrays and returns a result                                                                                  |
| find()                  | returns the first value of an array element that passes a test                                                                 |
| findIndex()             | returns the first index of an array element that passes a test                                                                 |
| forEach()               | calls a function for each element                                                                                              |
| includes()              | checks if an array contains a specified element                                                                                |
| sort()                  | sorts the elements alphabetically in strings and in ascending order                                                            |
| slice()                 | selects the part of an array and returns the new array                                                                         |
| splice()                | removes or replaces existing elements and/or adds new elements                                                                 |

```js
    let dailyActivities = ['sleep', 'work', 'exercise']
    let newRoutine = ['eat'];

    // sorting elements in the alphabetical order
    dailyActivities.sort();
    console.log(dailyActivities); // ['exercise', 'sleep', 'work']

    //finding the index position of string
    const position = dailyActivities.indexOf('work');
    console.log(position); // 2

    // slicing the array elements
    const newDailyActivities = dailyActivities.slice(1);
    console.log(newDailyActivities); // [ 'sleep', 'work']

    // concatenating two arrays
    const routine = dailyActivities.concat(newRoutine);
    console.log(routine); // ["exercise", "sleep", "work", "eat"]

    var newArray = myArray.filter(function (key) {
        return typeof (key) == "number"; //returns an array that that has true for each element that is number and false if otherwise
    })
```
#### 1.1.2.1.3 - Multidimensional Arrays	
* You can define multidimensional arrays like this : 
```js
    let studentsData = [['Jack', 24], ['Sara', 23], ['Peter', 24]];
```
* To access an element use `arrayName[indexRow][indexCol]`;
```js
    console.log(x[0]); // ["Jack", 24]
    console.log(x[0][0]); // Jack
```
* All array functions can be used here as well : 
```js
    studentsData.push(['Peter', 24]);
    studentsData[1][2] = 'hello';
    console.log(studentsData); //[["Jack", 24], ["Sara", 23,"hello"], ["Peter", 24]
```

### 1.1.2.2 - Objects
Will be added soon
console.log('newArray :>> ', newArray);

const myObj = { name: "name", id: 123213, testFunction: function (key) { return !(1 - key); } }
console.log('myObj.testFunction(15); :>> ', myObj.testFunction(15));

	
	
	
	
	
	
