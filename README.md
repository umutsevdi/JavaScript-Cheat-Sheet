# 1 - Declarations
In JavaScript values are hold in declarations which operates similar to pointers. Each of those declerations are made with the type name followed by an identifier. In JavaScript a declaration can be made by one of three operators which are : 
* var : function scoped definition
* const : block scoped definition, can not be changed once initialized
* let : block scopped definition

## 1.1 - Variable : 
Variable can be optionally initialized and can be used even before the initialization unlike most of the programming languages : 
```js
    var x;
    typeof(x); // undefined
    x=15;
    typeof(x); //number
```

## 1.2 - Constant : 
Constant is a value that can not be changed once initialized. 
```js
    const x = 20;
```

## 1.3 - Let : 
Let can be optionally initialized and can be used even before the initialization unlike most of the programming languages : 
```js
    let  x;
    typeof(x); // undefined
    x=15;
    typeof(x); //number
```

# 2 Data Types

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
## 2.0 - Data Type Conversion Values :
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
## 2.1 Strings 
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

### 2.1.1 - Strings Commands	
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

## 2.2 - Numbers
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


### 2.2.1 Constants : 
* EPSILON :	returns the smallest interval between two representable numbers
* MAX_SAFE_INTEGER :	returns the maximum safe integer
* MAX_VALUE	returns : the largest possible value
* MIN_SAFE_INTEGER :	returns the minimum safe integer
* MIN_VALUE :	returns the smallest possible value
NaN	represents 'Not-a-Number' value
* NEGATIVE_INFINITY :	represents negative infinity
* POSITIVE_INFINITY :	represents positive infinity
	
## 2.3 - Symbols
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
	
	
### 2.3.1 Symbol Properties
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
	
## 2.4 - Functions

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
The difference : functions that are defined as an expressions can not be hoisted, meaning that calling them before the definition causes an error. Arrow functions does not have binding entities which means keywords such as `this` and `super` can be called to get information from it's parent.

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

```

### 2.4.1 Function Defaults : 
In ES2015 ( ES6 ) `Function Defaults` was introduced to JavaScript which allows you to create default properties for functions in case they are not defined when the function is called.

```js
function printEventMessage( name = "Elise" , message = "Happy Birthday" ) {
    console.log(message +" "+ name + " !");
}

printEventMessage(); // Happy Birthday Elise !
printEventMessage("Jack"); // Happy Birthday Jack !
printEventMessage("Jack","How are you") // How are you Jack !
```

Function defaults can be used with each other : 

```js
function angle(x = 0.2, y = 1-x,  z = y-x) {
    return z*y*x;
}

angle(); // 0.096
```
#### 2.4.2 Functions with Rest Parameter : 
* Objects and arrays have a special `Spread Opearator(...)` that allows object properties to iterate. See `Spread Operator` in `Arrays` for more example.
* This operator can be used as an argument for functions.
```js
function printArgs(...args) {
    console.log(args); // 
}
printArgs(3,4,5); // [3 , 4 , 5]
printArgs(2); // [2]
```
### 2.4.3 Closures : 
In JavaScript functions are a data type just like any other primitives, which allows definition of functions within functions.
```js
function calculate(num1){
    function sum(num2){
        return num1+num2;
    }
    return sum(num1+num2);  
}

const result = calculate(4); 
console.log(result); // function sum(num2){return num1+num2}
console.log(result(5)); // 9
```
### 2.4.4 Function Shorthands :
When a function has an object parameter, a spesific part of that object can be called. In following example the HTTP function from `request` package has a parameter called `response`. However this object is complex and in most cases all we need is the `body` of the response. So instead of calling it and then pointing to body we can directly call body.
```js
request.get(
    'https:/www.example.com/',
    function (error, response) {
        if (!error) 
            console.log(response.body);
    }
);
//Second parameter is response so we can directly reach to the body
request.get(
    'https:/www.example.com/',
    function (error, {body}) { 
        if (!error) 
            console.log(body);
    }
); 
```
## 2.5 - Arrays

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
* Property values can be swapped with `Array Swapping`.
    ```js
    let x = 4;
    let y = 5;
    [x,y] = [y,x];
    console.log(x,y); // 5 4

    ```
* To see the number of elements in the array use `arrayName.length`.
* Arrays can be iterated with different ways : 
     ```js
    const fruits = ["apple", "orange", "cherry"];

     for (let i = 0; i < fruits.length; i++) {
        console.log(i,fruits[i]);
    }
    //0 apple
    //1 orange
    //2 cherry
    fruits.forEach(function(item,index){
        console.log(index,item)
    });
    //0 apple
    //1 orange
    //2 cherry

    for (const item of fruits) {
        console.log(item); 
    }
    //apple
    //orange
    //cherry
    ```
* Arrays have a special `Spread Opearator(...)` that allows array to iterate.
```js
const array = ["Hi ","How ","are ","you ","? "];
console.log(...array); // Hi How are you ?
```
  * `...` operator can be used to embed array in another array.
```js
const array = [1,3,5];
var arrayBig = [...arr, 2 , 4 , 6 ],
console.log(arrayBig); // [ 1 , 3 , 5 ,2 ,4 ,6]
```
### 2.5.1 - Other Array Functions : 

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
### 2.5.6 - Multidimensional Arrays	
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

## 2.6 - Objects
Unlike other programming languages, objects do not require a class to be created. They can be defined, assigned and changed freely.

```js
let Person={
    name: "Elise",
    age: 19,
    mail : "elise@example.com"    
};
``` 
In JavaScript an object can contain functions, variables and even other nested objects.
```js
const vector={
    x:10,
    y:7,
    findDistance: function(){ 
        return Math.sqrt( x**2 + y**2 ); 
    },
    end : {
        x:4,
        y:6
    }
}
```
Object properties are defined with key - value pairs. To reach one element you can use different methods.
* `object.key` is called the dot notation.
* `object["key"]` is called the bracket notation. Bracket notation requires a string which can be derived from another variable.
```js
const obj = {
    name : "objectName",
    id : 123,
    number : 7
};

obj.name="Object 123";

obj["id"]= 150;

const referance = "number";
obj[referance]=49;

console.log( obj.name + "\t" + obj.id + "\t" + obj.number ); //Object 123   150 49

```
* `this` keyword is used when we need to reach to a property within the same object.
* You can access object methods by calling the key. 
  * `object.functionName` allows you to access the function data. Which displays the function in string.
  * `object.functionName()` allows you to call the method.
```js
    const myObject = {
        name : "objectName",
        display : function () {
            return "Object is "+ this.name;
        }
    }
    console.log( myObject.display ); // f () { return "Object is " + this.name; }
    console.log( myObject.display() ); // Object is objectName
    
```
* To add a variable into an object simply add a key and a value.
```js
    const myObject = {};
    myObject.name = "student";
    myObject.hello = function () { console.log(" Hello World! "); }
    myObject.hello(); // Hello World!
```	
* Objects have a special `Spread Opearator(...)` that allows object properties to iterate. See `Spread Operator` in `Arrays` for more example.
```js
const obj1 = { x : 1, y : 2 };
const obj2 = {..obj1, z : 3};
console.log( ...obj2 ) // {x : 1 , y : 2 , z : 3}
```
* Literal objects can be iterated with their properties.
    ```js
    const myObject = {
        name : "objectName",
        age : 15,
        id : 123
    }
    for (let key in myObject) {
    console.log(key, yourobject[key]); 
    }
    //name objectName
    //age 15
    //id 123
    ```
    * After ES6(2015) a key,value pair version of for was added. This allows you to directly access to values.
    ```js
    for (let [key, value] of Object.entries(myObject)) {
        console.log(key, value);
    }
    //name objectName
    //age 15
    //id 123
    ```
    * `Object.keys(objectName).forEach(function)` is another way to iterate:
    ```js 
    Object.keys(myObject).forEach((key, value) => {
        console.log(key,value);
        
    });
    //name objectName
    //age 15
    //id 123
    Object.keys(myObject).forEach(function(key, value) {
        console.log(key,value);
    });
    //name objectName
    //age 15
    //id 123
    ```
### 2.6.0 Objects Destructuring and Property Shorthand
* Properties in JavaScript can be quickly assigned if their names are identical.
    ```js
        const name = "Elise";
        const userAge= 40;
        const user = {
            name,
            age: userAge,
            location: 'Philadelphia'
        }
        // 'name' was directly written to user because their names are matched. In other cases we still need ':' to define the object property.
    ```
* Destructuring is a way of accessing object properties without calling the object.
    ```js
    const person = {
        name: 'Sara',
        age: 25,
        gender: 'female'    
    }
    const name = person.name;
    ```
* Object Destructuring can be easily done with an anonymus `{}` object properties. 
    ```js
    const person = {
        name: 'Sara',
        age: 25,
        gender: 'female'    
    }
    let { name, age, gender } = person;
    ``` 
* Objects destructuring doesn't process doesn't require identical names. If you would like to pick different variable names it can be done with `:` operator. And also not all variables have to be mentioned.
    ```js
    const person = {
        name:"Sara",
        age:20,
        location: "United States of America",
    }
    const { age, location:address } = user;
    ```
* Object destructuring can be used in function arguments.
    ```js
    const product = {
        label: 'Red notebook',
        price: 3,
        stock: 201,
        salePrice: undefined,
        rating: 4.2
    }
    function transaction(type, { label, stock }){
        console.log(type, label, stock);
    }
    transaction('order', product);
    //In this example despite the fact that we send entire object, the function received only label and stock.
    ```
### 2.6.1 - Constructors :
* Constructor is used to define objects with predefined and reusable properties.

```js
function Person(name , job , age) {
    this.name = name;
    this.job = job;
    this.age = age;

    this.toString() = function () {
        return "Person = [ name = "name+" job = "+job+" age = "+age+" ] ";
    }
}

const person1 = new Person("Umut", "Student", 21);
const person2 = new Person("John", "Politician", 49);
console.log( person1.toString() ); // Person = [ name = Umut job = Student age = 21 ]
```
#### 2.6.1.1 Constructors vs Literal Objects : 
* Literal objects are generally used to define a single object. The constructors are used to defined multiple objects.
* Each object defined with constructor function is unique which means they can have different values for properties.
* Which means defining a spesific function or a property for an object created with a constructor means, it will be unique to that instance.
* However on literal objects it is different. Literal objects are clone of one other. They are just pointers to target the same object.

```js 
const object1 = {
    name : "object 1",
}
var object2 = object1;
object2.name = "object 2";
console.log(object1.name + object2.name ); // object2 object2
```

### 2.6.2 Adding Property to an Object :
 * Lets add a function or a property to person1 fromprevious example.
```js
function Person(name , job , age) {
    this.name = name;
    this.job = job;
    this.age = age;
}
const person1 = new Person("Umut", "Student", 21);
const person2 = new Person("John", "Politician", 49);

person1.myFunction = function() {
    console.log( "Hi!" );
}
person1.myFunction(); // Hi
person2.myFuntion(); // Uncaught TypeError: person2.myFunction is not a function
```
* As you see from the example constructors do not share properties added after the definition.
### 2.6.3 Prototypes :
* If you would like to add a function or a property to all previously created objects, you can use `prototype`. Prototype allows you to make additions and changes to the constructor function.

```js
function Person(name , job , age) {
    this.name = name;
    this.job = job;
    this.age = age;
}
const person1 = new Person("Umut", "Student", 21);
const person2 = new Person("John", "Politician", 49);

Person.prototype.myFunction = function() {
    console.log( "Hi!" );
}
person1.myFunction(); // Hi
person2.myFuntion(); // Hi

const person3 = new Person("test","test",13);
person3.myFunction(); // Hi
```

JavaScript has also built in constructors which are :
* Object();
* String(); 
* Number();
* Boolean(); 
  
However it is recommended to use primitive types instead of built-in constructors.

### 2.6.4 Classes :
In ES2015(ES6) `class` was added to JavaScript which behaves the same with `class` from `Java` programming language.
```js
class Person {
  constructor(name) {
    this.name = name;
  }
}
const person1 = new Person('John');
```  

#### 2.6.4.1 Getters & Setters :
Objects can not only provide properties but also can modify how user can interract with them.

However to access them, you must use them as a property rather than a function.

```js
const object = {

    id: '157',
    get getId() {
        return this.id;
    }
    set setId(id) {
        this.id = id;
    }
};
object.getId; // 157
object.id; // 157
object.getId(); // Error
object.setId = "110";
object.getId;  // 110
```

#### 2.6.4.2 Object Define Property : 
`Object.defineProperty()` method is also another way to define getter & setters.

```js
const object = {
    id: '157',
};
Object.defineProperty(object, "getId", {
    get : function () {
        return this.id;
    }
});
Object.defineProperty(object, "setId", {
    set : function (id) {
        this.id = id;
    }
});
```
#### 2.6.4.3 Class Inheritance :
```js
class User { 
    constructor(name) {
        this.name = name;
    }
}
class Student extends User {
 constructor(name,id) {
    console.log("Creating student class");
    this.id = id;
    super(name);
    }
}
``` 
## 2.7 - Maps : 
Maps behave similar to objects, the only difference is their keys have no type restriction.
* You can access map elements by using `mapName.get(key)` function.
* You can define or change map elements by using `mapName.set(key,value)` function.
```js
let myMap = new Map();
myMap.set("String Key", 15);
myMap.set(129,7);
let object = {};
myMap.set(object,"can be key");
```
* To remove an element use `mapName.delete(key)`. `delete(key)`returns `true` if given key has been found.
* To remove all elements use `mapName.clear()`.
* To get the size of a map use `mapName.size`.
* To iterate over a map use `forEach()` or `for of`.
```js
let map = new Map();
map1.set("Jack", {age : 40 , job : "web developer"});
map1.set("John", {age : 15 , job : "unemployed"});

for (let [key, value] of map) {
    console.log(key + '- ' + value);
} // Jack - {age : 40 , job : web developer}
  // John - {age : 15 , job : unemployed}

map.forEach(function(value, key) {
  console.log(key + '- ' + value)
}) // Jack - {age : 40 , job : web developer}
   // John - {age : 15 , job : unemployed}

for (let key of map.keys()) {
  console.log(key)
} //Jack
  //John
```
## 2.8 - Sets : 
Sets behave similar to arrays but unlike arrays, set values can not be duplicate.
Just like arrays, sets can store different data types.

```js
const set = new Set([1, 2, 3]);
console.log(set.values()); // Set Iterator [1, 2, 3]
```
* Sets have following functions to handle the data.

| Method       | Description                         |
| ------------ | ----------------------------------- |
| has(item)    | Checks if given item is in the set  |
| add(item)    | Adds given item to the set.         |
| values()     | Allows access to set elements.      |
| delete(item) | Removes given element from the set. |
| clear()      | Removes all elements from the set.  |

* To iterate over a set you can use `for..of` or `forEach()` similar to arrays.
```js
const set = new Set( [2, 4, 6] );
for (let i of set) {
    console.log(i);
}
//1
//2
//3
```
## 2.9 - WeakSets :
WeakSets are a type of set where all elements have to be an object. However WeakSets are not iterable.
## 2.10 - Proxy Objects :

```js
new Proxy(target, handler);
```

# 3 Loops : 

| for...of                                                                | for...in                                                                                                                    |
| ----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| The for...of loop is used to iterate through the values of an iterable. | The for...in loop is used to iterate through the keys of an object.                                                         |
| The for...of loop cannot be used to iterate over an object.             | You can use for...in to iterate over an iterable such arrays and strings but you should avoid using for...in for iterables. |

# 4 Asynchronous JavaScript Actions : 
Asynchronous functions can work seperately from the rest of the code. When they are in await status, compiler ignores them. Their code is performed once they are ready.
## 4.1 Timeout Functions : 
* `setTimeout(function,delay,...args)` : Calls a function after a delay. This function also returns a intervalID value. If function requires parameters they can be optionally written after delay.
* `clearTimeout(intervalID)` : Cancels a timeout event with given intervalID.
```js
function displayTime(){
    let dateTime= new Date();
    let time = dateTime.toLocaleTimeString();
    console.log(time);
}
let event = setTimeout(displayTime,1500); // Displays time after 1.5 seconds.
clearTimeout(event); // Display time function is cancelled.
```
## 4.2 CallBack Function : 
In JavaScript, we know that a function can be assigned to a value, which also means it can be send to a function.
```js
function doWhatISend(name, callBack){
    console.log("I am "+name);
    callBack();
}
function callMe(){
    console.log("function was called");
}
doWhatISend("Umut"+callMe());
// I am Umut
//function was called
```
The callback function is helpful when you have to wait for a result that takes time. For example, the data coming from a server because it takes time for data to arrive.
## 4.3 Promises : 
In JavaScript `asynchronous` operations can be completed easily with the help of `promises`. A promise starts at `pending` state. If it is successful, the process ends with `fullfilled` state. If an error occurs during pending state, it will enter to `rejected` state.

```js
let promise = new Promise(function (resolve,reject){});
```
A promise requires a function. Optionally requires functions for `resolve()` and `reject()` states.
* If the promise returns successfully, resolve function is triggered.
* If an error occurs, reject function is called.
```js
const state = false;
let promise = new Promise(function (resolve,reject){
    if(state){
        resolve("State is true");
    }else{
        reject("State is false");
    }
}) // Promise {<rejected>: "State is false."}
```

### 4.3.1 Promise Chaining : 
Promise may require more complex handling, because of that we have `then()` , `catch()` and `finally()`.

```js
let promise = new Promise(function (resolve,reject){
    resolve("State is true");
}); // Promise {<rejected>: "State is false."}
promise.then(function success(result){
    console.log(result);
})
.catch(function fail(result){
    console.log(result);
})
.finally(function doAnyway(){
    console.log("Do anyway");
});
```

### 4.3.2 Promise Chaining vs CallBack : 
Both promise chaining and callback can be use for asynchronous tasks. However promise chaining has easier syntax.
```js 
//Promise Chaining
api().then(function(result) {
    return api2() ;
}).then(function(result2) {
    return api3();
}).then(function(result3) {
    // do work
}).catch(function(error) {
    //handle any error that may occur before this point 
});
//CallBack
api(function(result){
    api2(function(result2){
        api3(function(result3){
             // do work
            if(error) {
                // do something
            }
            else {
                // do something
            }
        });
    });
});
```

### 4.3.3 Other Promise Methods : 

| Method               | Description                                                               |
| -------------------- | ------------------------------------------------------------------------- |
| all(iterable)        | Waits for all promises to be resolved or any one to be rejected           |
| allSettled(iterable) | Waits until all promises are either resolved or rejected                  |
| any(iterable)        | Returns the promise value as soon as any one of the promises is fulfilled |
| race(iterable)       | Wait until any of the promises is resolved or rejected                    |

	
	
	
## 4.4 async / await :
`async` is a keyword for a function to represent this function returns a `promise`.
```js
async function name(...args){
    console.log("Resolving");
    return Promise.resolve(true);
}
f().then(function(result){
    console.log(result)
});
// Resolving
//
// true
```
`await`is a keyword that is used inside a `async` function to wait asynchronous operation.

```js
// a promise
let promise = new Promise(function (resolve, reject) {
    setTimeout(function () {
    resolve('Promise resolved')}, 4000); 
});

// async function
async function asyncFunc() {

    // wait until the promise resolves 
    let result = await promise; 

    console.log(result);
    console.log('hello');
}

// calling the async function
asyncFunc();
```
* In the example first the promise was sent. Then the `asyncFunc()` was called. Then the function had waited until the arrival of `result`.
	
## 4.5 setInterval : 
`setInterval(function,delay)` behaves exactly like `setTimeout()`. Only difference is `setInterval()` repeats the process. setInterval returns an intervalID just like timeout function.

```js
setInterval(console.log("Hello"),5000); 
```
* In this example code prints "Hello" to console every 5 seconds.

* To cancel this repeating process, use `clearInterval(intervalID)`.

# 5 JSON
JSON stands for JavaScript Object Notation. It is a file format to store data. Similar to JavaScript objects, JSON uses key-value pairs. JSON objects can be directly used just like JavaScript objects. 
```js
    const data = {
        "name" : "Umut",
        "age" : 21,
        "university" : "Yildiz Technical University"
    }
    console.log(data.name); // Umut
```
* To convert JSON data to literal object, use `JSON.parse(jsonObject)` which returns a literal object from the parsed JSON.
* To convert a literal object to JSON, use `JSON.stringfy(javaScriptObject)`.

# 6 Strict Mode : 
Strict mode prevents a variable to be used before declaring. Strict mode must be defined on top of the code(or an object). Strict mode can be temporarily activated by defining it inside a function or object.
```js
'use strict';
```
* Strict mode prevents deleting an object with `delete`.
* Allows you to write more secure JavaScript.
* Prevents any form of bad syntax and unrecognizable code.

# Express : Back End Framework for NodeJS

* Express framework can be easily downloaded with `npm install express` command on a terminal that points to the directory of your project.
* To create a web application, you need a few lines of code for the initialization.
    ```js
        const express = require("express"); 
        const app = express(); // Express framework is originally a function itself.
        const port = 3000;
        app.listen(port, () => {
            console.log("Server is up on port " + port);
        }); //This command starts your server.
    ``` 

* To create a `path` on your server, you can use this line : 
    ```js
    app.get("/pathName", (request, response) => {
        response.send("Response Content");
    });
    ```
  * `send()` function can be used for various ways such as :
   
    ```js
        const jsonObject = {
            name : "Object Name",
            id : 123456789,
            phone : 53538512,
            location : "Istanbul"
        };

        app.get("/json", (req, res) => {
            res.send(JSON.stringify(jsonObject));
            }
        );

        app.get("/html", (req, res) => {
            res.send(" <h1>HTML Header</h1>");
            }
        );
    ```
* Express can also read and use `html` files in a directory. To do that :
    ```js
        const filePath = path.join(__dirname, "../public"))
        app.use(express.static(filePath);
    ```
## 1 Server Side Rendering : 
* When we would like to send static pages we can directly send the html file to the client. However it is not the case most of the times. Sometimes `server-side rendering` is preferred. Server-Side rendering is a method to create customized pages and send them to the client.
* One known method to do that is using `handlebars`. Handlebars are `html` rendering tools.
* You can use any handlebar to perform server side rendering. But to make things easier and compatible with `Express` we will be using `hbs library`. To install use `npm install hbs` command on your directory.
* You can use this file structure on your project something like this :
    ```js
    projectName
                ⌞node_modules
                ⌞public
                        ⌞css
                        ⌞js     //Front end JavaScripts
                        ⌞html
                        ⌞resources
                                    ⌞images
                ⌞src
                    ⌞app.js     // Your express scripts
                ⌞views
                    ⌞index.hbs  // Handlebars
                ⌞package-lock.json
                ⌞package.json             
    ```
* To render `handlebar views` use :
  ```js
    app.get( "/path", (res, req ) => {
        res.render("template")
    });
  ```
* `render()` function can receive a second parameter which is an object. So we can use those elements in our `template.hbs` file in views folder.
    ```js
    const object = {
        name : "My Web Page",
        author : "Umut"
    }
    app.get( "/path", (res, req ) => {
        res.render("template",object)
    });
    ```
* Those values can be accessed from our handlebar files.
    ```hbs
    <!DOCTYPE html>
    <html>
        <head>
            <link rel="stylesheet" href="./css/styles.css">
            <script src="/js/app.js"></script>
        </head>
        <body>
            <h1>This is {{name}} </h1>
            <h2>My name is {{author}} </h2>
            <img src="resources/1606043657721.jpg">
        </body>
    </html>
    ```
* Functions can be called from handlebar files too.
    ```js
    let num = 0
    const renderObject = {
            myFunction: function () {
                num+=10;
                return num;
            }
        }
    app.get("/handlebars_test/", (req, res) => {
        res.render("index", renderObject);
    })
    ```
    ```hbs
    <!DOCTYPE html>
    <html>

    <head></head>

    <body>
        <p>{{myFunction}}</p>
    </body>

    </html>
    ```
* `render()` looks up to `views` directory by default for the templates. But this can be changed with `set()` function. 
    ```js 
    app.set("views",path.join(__dirname,"../path/"));
    ```
    
