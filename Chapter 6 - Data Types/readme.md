# What are Javascript Datatypes?

Data types in javascript refer to the attribute associated with the kind of data we are storing or working on. It associates the declared variable (or item) with a particular type so that the compiler can perform operations in an organized manner.

**There are mainly two types of data types in javascript:**

1.  Primitive data types
2.  Non-primitive data types

---

---

# Primitive Data Types

Primitive data types in javascript refer to those data types that are defined on the most basic level of the language. These Javascript data types cannot be de-structured further, nor do they have any pre-defined properties or methods. They are only used to store the items of *their type*.

**Following are the 7 primitive data types in javascript:**

- Numbers
- BigInt
- String
- Boolean
- Undefined
- Null
- Symbol

---

## Numbers

_Everyday, we encounter numbers in multiple forms. Be it sharing our phone number with someone or calculating the square root of a value in a math problem, and all these include numbers in integer, decimal, fraction, or any other form._

In javascript, the integers, float values (or decimals), and all the other numeric values are represented by the **_number datatype_**.

Unlike other languages (like C++), javascript doesn't define separate data types for integers, decimals, long integers, etc.

**Declaration:**

Numbers can be declared by using *var*, *let*, or *const* keyword followed by the *variable name*, and the number is assigned to it.

**Syntax:**

```javascript
var x = 1;
```

**Example:**

```javascript
let num1 = 10; //number with integer of value 10
var num2 = 9753123568; //number with integer of value 9753123568
const num3 = 3.14; //number with decimal of value 3.14
```

> - **Note:** The Javascript number type is a double-precision 64-bit binary format, i.e., it occupies 64 bits and ranges between a dynamic range (-2<sup>53</sup> - 1 to 2<sup>53</sup> - 1).
> - The numbers that overflow this range are handled by **BigInt** datatype.

Due to the existence of this range, there is an upper limit as well as a lower limit to storing numbers in javascript. Also there are some certain keywords related to numbers in javascript. *Following are some of these keywords related to numbers in javascript:*

**Largest safe Integer:** It represents the largest integer value that can be represented by javascript without any overflow.

*Representation:* `Number.MAX_SAFE_INTEGER` *Value:* 2<sup>53</sup> - 1 or 9007199254740991

**Largest value:** Represents the largest possible value that can be stored by javascript.

*Representation:* `Number.MAX_VALUE` *Value:* 2<sup>1024</sup> - 1

> Note: The *largest safe integer* refers to the largest value that can be **represented** while *largest value* refers to the largest value that can be **stored**.

**Smallest value:** It represents the smallest *positive* value in javascript.

_Representation:_` Number.MIN_VALUE` *value:* 2<sup>-1074</sup> or 5e-324

**Epsilon:** It represents the difference between 1 and the least number greater than 1.

*Representation:* `Number.EPSILON` *value:* 2<sup>-52</sup>

**Infinity:** It is a symbolic value that occurs in the case of an overflow.

To check whether a number has reached infinity (or -infinity): `Number.isFinite`

**NaN:** It represents anything that is *not a number* in javascript. The `NaN` case usually occurs during type conversion of the number or due to its concatenation with a string.

`Number.isNaN` can be used to verify whether a number is `NaN` or not.

---

## BigInt

_We often encounter cases where the number to be represented is really large, for example, the population of the world or the total number of stars in the sky. Though it is possible to represent these huge numbers on paper but certain data types come with memory constraints._

The **BigInt** data type in javascript is used to represent numeric values that exceed the *largest safe integer limit*. It is basically used to represent numbers greater than 2^53^-1.

> note: Unlike *number*, the *BigInt* data type doesn't represent decimal values. It only represents whole numbers.

**Declaration:**

BigInt values can be declared by two methods:

1.  By appending **_n_** at the end of the numeric value.
2.  By passing the number as an **_argument_** to the **_BigInt()_** constructor.

- **By appending *n* at the end of the numeric value:**

  BigInt can be declared by appending n at the end of the numeric value that we are assigning to our variable.

  **Syntax:**

  ```javascript
  var num = 9007199254740991n;
  ```

- **By passing the number as an *argument* to the *BigInt()* constructor.**

  BigInt can be declared by calling the BinInt constructor and passing the numeric value as an argument. *We do not need to append n at the end of the argument.*

  > note: the **new** keyword is not used while calling the BigInt() constructor.

  **Syntax:**

  ```javascript
  var num = BigInt(9007199254740991);
  ```

**Example:**

```javascript
const num1 = 112233445566778899233445566778894556646n; //BigInt number declared by appendening n.
const num2 = BigInt(112233445566778899233445566778894556646); //Bignint number declared by calling constructor
const num3 = BigInt("112233445566778899233445566778894556646"); //BigInt number declared by calling constructor where argument passed is a string.
```

> In the last example, the argument passed is a string. In the constructor calling method, we can even pass the string of a number, and it would return a BigInt number.

The output of the BigInt numbers will always be appended with n.

**Example:**

```javascript
console.log(num1);
// output: 112233445566778899233445566778894556646n

console.log(num2);
// output: 112233445566778899233445566778894556646n

console.log(num3);
// output: 112233445566778899233445566778894556646n
```

The BigInt operator acts as Number with +, -, \*, \*\*, % operators but acts as a boolean entity with if, ||, &&, Boolean, ! operators.

---

## String

_We often encounter elements that are presented in a textual manner, be it our name or a paragraph in the textbook. These elements are different from the numbers and have specific operations and constraints. In javascript, these kinds of texts are represented by **strings**_.

String type is used to store elements in a textual form. The elements are stored in *16-bit integer form.*

**Declaration:**

Strings are declared by assigning the text to the declared literals. The literal can be declared by either *const*, *var* or *let*. In Javascript, a string can be declared by the following three ways:

- **Single tick declaration:**

  _Strings are declared by enclosing the text between two single ticks (**''**)_

  **Syntax:**

  ```javascript
  var str = "Javascript";
  ```

- **Double tick declaration:**

  _Strings are declared by enclosing the text between two double ticks (**""**)_

  **Syntax:**

  ```javascript
  var str = "Javascript";
  ```

- **Backticks declaration:**

  _Strings are declared by enclosing the text between two backticks ticks (**``**)_

  **Syntax:**

  ```javascript
  var str = `Javascript`;
  ```

**Example:**

```javascript
const str1 = "This is String"; // single tick declaration
const str2 = "Javascript"; // double tick declaration
const str3 = `This is an example`; //backtick declaration
```

---

### String properties

The string type has various properties that assist in its operations. Following are some of the properties of strings:

**Indexing:**

Strings in javascript follow 0-based indexing, i.e., the first element of the string is considered at the 0th position, the second in the 1st position, and so on.

_Example:_

```javascript
const str = "This is a string";

console.log(str[0]);
//output: T

console.log(str[6]);
//output: s
```

> Thus, in order to access the elements of the string, we need to provide the string name follower by a square bracket ([]) and its index inside it.

**Immutability:**

In javascript, once the string is created, it cannot be further manipulated.

_Example:_

```javascript
let name = "Scaler";
name.toLowerCase(); // INVALID OPERATION
```

In the above example, the 'Scaler' string wouldn't change as the reference string object is immutable.

Although we can assign a new string to an existing string object.

```javascript
let newName = name.toLowerCase();

console.log(newName);
// output: scaler
```

**Concatenation:**

We can concatenate two strings using the + operator.

_Syntax:_

```javascript
var str1 = "java";
var str3 = "script";

var str3 = str1 + str2;

console.log(str3);
//output: javascript
```

> **note:** In strings that are declared using *backticks* we can include external variables using **${}**

_Example:_

```javascript
var str1 = "Javascript";
var str2 = `This is ${str1}`;

console.log(str2);
//output: This is Javascript
```

---

## Boolean

_We often encounter situations where there are two possible values, either true or false. For example, imagine logging into your social media account; the website takes your password and compares it with the one stored in their database. If it matches, i.e., the result of the comparison is true, it proceeds; otherwise, it terminates._

In javascript, the *boolean* data type is used to check the truthy or falsy condition. It is also known as *logical data type*.

**Declaration:**

It can be declared by using the **bool** keyword followed by the variable name. It can be assigned only *two* values, true or false.

**Syntax:**

```javascript
bool flag = false;
```

The boolean data type is generally used in conditional statements or at places where authentication is required.

**Example:**

```javascript
function boolExample(flag){
    if(flag1){
        console.log('Hello world');
    }else{
        console.log('Hey there!');
    }
}


bool x = true;
bool y = false;

boolExample(x);
//output: Hello world

boolExample(y);
//output: Hey there!
```

> Note: The statement flag is equivalent to flag == true, similarly !flag is equivalent to flag == false

---

## Undefined

_Sometimes, we encounter things that are obscure. For eg, the mode of communication of a recently discovered reptile in the amazon forests. Thus it cannot be put under any pre-defined set. In that case, the mode of communication remains undiscovered or undefined._

In javascript, undefined is a primitive data type in javascript that gets assigned to *variables* or *function arguments* when their values aren't initialized.

**Declaration:**

*undefined* Javascript data types can be declared by simply declaring a literal by using *var*, *let*, or *const* keyword. *We don't assign anything to the literal.*

**Syntax:**

```javascript
var undefinedValue;
```

**Example:**

```javascript
function example(x) {
  console.log("The user has entered: " + x);
}

var a;
var b = 10;
var c = "Javascript";

example(a);
//output: The user has entered: undefined

example(b);
//output: The user has entered: 10

example(c);
//output: The user has entered: Javascript
```

In the above example, the first function call will give out the output as *undefined* as the argument that is passed has been declared but not assigned any value.

*note:* Even if we call the function without passing ay value ti would output *undefined* as the parameter isn't assigned any value.

```javascript
function example(x) {
  console.log("The user has entered: " + x);
}

example();
//output: The user has entered: undefined
```

---

## Null

_We often encounter certain elements that do not hold any value, for e.g., as simple as the no signal message on the TV during rains to the vacuum in the space. These elements do not hold any value. In Javascript, these kinds of values are represented by null._

The *null* type in javascript refers to an empty object pointer. It holds only one value. It is used to represent **intentional absence** of any object.

**Declaration:** It is declared by declaring a variable using *var*, *let* or *const* keyword and it is assigned the value null.

**Syntax:**

```javascript
var a = null;
```

**Example:**

```javascript
function example(x) {
  console.log(x);
}

var a = 10;
var b = null;

example(a);
//output: 10

example(b);
//output: null
```

In the above example the output of b is null as the argument passed is a null value.

> If no value is passed to the function as parameter, then the output will be undefined only.

***null* properties:**

- **null is considered as falsy:**

  Which means that under conditional situaltion null will return false result.

  ```javascript
  function example(x) {
    if (x) {
      console.log("Not false");
    } else {
      console.log("false");
    }
  }

  example(null);
  //output: false

  example(true);
  //output: Not false
  ```

- **The typeof null is object.**

---

## Symbol

The symbol is a primitive data type in javascript that returns a unique symbol upon being called. Symbols do not have a literal form and are unique.

**Declaration:**

The symbol is declared by calling the **Symbol()** function. The parameter field doesn't default; thus it can be called either by passing an argument or empty.

> Note: the Symbol() isn't a constructor thus, if it is called with the **new** keyword, it will throw an error.

**syntax:**

```javascript
let s1 = Symbol();
let s2 = Symbol("javascript");
```

The Symbol() creates a new symbol every time it is called and the symbol has nothing to do with the *key* passed.

**Example:**

```javascript
let s1 = Symbol("x");
let s2 = Symbol("x");

console.log(s1 === s2);
// output: false
```

In the above example, even though the key passed is same still the symbols *s1* and *s2* will be different.

---

---

# Non-primitive Javascript Data Types

Non-primitive data types in javascript are those data types that aren't defined at a basic level but are complex data type are formed upon operations with the primitive data types. The non-primitive data types in javascript refer to objects and can perform multiple functions using their methods.

There are mainly three type of non-primitive (or complex) data types in javascript:

- **Object**
- **Array**
- **RegExp**

---

## Object

_During school, all of us were provided identity cards. This used to contain fields like our name, class, section, roll no, etc. These were used to identify students according to multiple attributes. In reality, we often encounter such situations where we need to associate one identity with different attributes. In javascript, such identities are stored using objects_

Object in javascript is a collection of data that is kept in a *key-value* pair manner.

**Declaration:**

Objects in javascript can be created by two methods:

- **Literal method:**

  In this method, a literal is created using *var*, *let* or *const* keyword, and we assign a set of key-value pairs to it, which is wrapped inside braces {}.

  **Syntax:**

  ```javascript
  let obj = {
    key: "value",
  };
  ```

- **By calling the constructor:**

  In this method we can declare the object by calling Object() constructor using new keyword and then add the *key-value* pair using the . operator.

  **Syntax:**

  ```javascript
  let obj = new Object();
  obj.name = "Javascript"; //here a key 'name' is added and it is assigned the value 'Javascript'.
  ```

**Example:**

```javascript
//By literal method
let car = {
  name: "Maruti",
  model: "Swift",
  color: "red",
  price: 550000,
};

//By constructor method
let bike = new Object();
bike.name = "Pulsar";
bike.model = "Dominar";
bike.color = "red";
bike.price = 200000;
```

> In a literal declaration, the key-value pair is separated by commas ,

> Two keys can not be the same in an object.

**Accessing objects items:**

Object items can be accessed by two ways:

- **By using dot operator:**

  Object items can be accessed by calling the *object name* followed by a *dot* operator followed by the *key* name.

  **syntax:**

  ```javascript
  objectName.key;
  ```

  **example:**

  ```javascript
  let car = {
    name: "Maruti",
    model: "Swift",
    color: "red",
    price: 550000,
  };

  console.log(car.name);
  // output: Maruti

  console.log(car.color);
  // output: red

  console.log(car.price);
  // output: 550000
  ```

- **By array method:**

  Objects can also be accessed by the array method. In this method, we state the name of the object and pass the key inside [] as a string.

  **Syntax:**

  ```javascript
  objectName[key];
  ```

  **Example:**

  ```javascript
  let car = {
    name: "Maruti",
    model: "Swift",
    color: "red",
    price: 550000,
  };

  console.log(car["name"]);
  // output: Maruti

  console.log(car["color"]);
  // output: red

  console.log(car["price"]);
  // output: 550000
  ```

**Using functions as a key-value:**

Inside the objects, functions can also be stored as a value for a key.

*Declaration:* Inside the object definition, the function is declared after the key.

_Syntax:_

```javascript
let obj = {
    key: function(){...}
}
```

_Example:_

```javascript
let car = {
  name: "Maruti",
  model: "Swift",
  color: "red",
  price: 550000,
  about: function () {
    return `This is a ${this.name}, of ${this.color} color.`;
  },
};

console.log(car.about);
// output: This is a Maruti, of red color.
```

> note: Here, the this keyword refers to the parent object.

---

## Array

_All of us have made to-do lists (though we never complete the tasks mentioned on it_

_). We keep adding or removing tasks on it. Similarly, we do often use to store a collection of items under one hood. For example, the grocery list or semester scores. In javascript, we do use **containers** to store these kinds of things._

Arrays in javascript are abstract data types that are used to store a set of elements. These can be multiple elements of the same or different types. Arrays are basically containers in javascript.

**Declaration:**

Javascript arrays can be declared by three methods:

- **By array literal:**

  In this method, arrays are declared using *const*, *let*, or *var* keyword, and the values are assigned to them using [].

  **Syntax:**

  ```javascript
  let ar = ["1", "2", "3"];
  ```

- **Constructor method:**

  Arrays can be declared by calling Array() constructor using the *new* keyword.

  **Syntax:**

  ```javascript
  let ar = new Array();
  ```

**Example:**

```javascript
// By literal
let X = ["Red", "Yellow", "Orange"];

//By constructor
let Y = new Array("Apple", "Orange", "Grapes", "Banana");

console.log(X);
// 'Red', 'Yellow', 'Orange'

console.log(Y);
// 'Apple', 'Orange', 'Grapes', 'Banana'
```

> Note: In javascript, the elements of an array can be of different types

**Example:**

```javascript
let ar = [1, "Pen", false, "Text"];
```

**Array properties:**

Following are some important properties of an array:

- **Indexing**

The array in javascript follows *0 based indexing*, i.e. the first element is considered at *index-0*, second at *index-1* and so on.

_Example:_

```javascript
let ar = ["Red", "Yellow", "Orange"];

console.log(ar[0]);
//output: Red

console.log(ar[2]);
//output: Orange
```

In the above example, the ar[0] outputs *Red* as it is in the 0th position, similarly, ar[2] outputs *Orange* as it is in the 2nd position.

- **Accessing elements of an array:**

  In order to access elements of an array, we need to provide the array name followed by its index inside the bracket.

  **Syntax:**

  ```javascript
  arrayName[index];
  ```

  **Example:**

  ```javascript
  let ar = [1, "Pen", false, "Text"];

  console.log(ar[1]);
  //output: Pen
  ```

- **Array methods:**

  The javascript arrays have several methods that are used to manipulate the array and produce desired results. Following are some common array methods:

  - **Push:**

    To add elements to the end of an array.

    _Syntax:_

    ```javascript
    arr.push(element);
    ```

    *Parameter:* The element to be pushed *return type:* An array with the element added to the end of the array.

  - **Pop:**

    To remove elements from the end of the array.

    _Syntax:_

    ```javascript
    arr.pop();
    ```

    *Parameter:* None *return type:* An array with the element from the end of the array.

  - **isArray():**

    Checks if the passed object is an array.

    _Syntax:_

    ```javascript
    arr.isArray(obj);
    ```

    *Parameter:* The object that has to be checked. *return type:* Returns true if the parameter is an array; otherwise, it returns false.

  - **forEach()**

    It is used to invoke the specified function for each element. It can be used to iterate through each element as well.

    _Syntax:_

    ```javascript
    arr.forEach(function(param){...});
    ```

    *Parameter:* A function that needs to be operated. *return type:* The function's response on each element.

There are several other operations that can be done on the array using **map()**, **reverse()** etc.

---

## RegExp

_We all have seen detective movies; remember how words are decoded and read using patterns? Even in real life, we encounter many instances where we need to validate the texts with particular patterns._

The **RegExp** in javascript is an object which is used to match a string with a particular pattern.

**Declaration:**

Regular Expressions (RegExp) can be created by two methods:

- **By using forward slashes:**

  In this method, we declare literals and then assign them the pattern which follows a forward slash, and it is followed by a modifier.

  **Syntax:**

  ```javascript
  let re = /pattern/modifier;
  ```

- **By Constructor:**

  Regular expressions can be declared by calling **RegExp()** constructors by passing the *pattern* as a parameter.

  **Syntax:**

  ```javascript
  let re = new RegExp("pattern");
  ```

  > Note: The parameter is passed as a string.

**Example:**

```javascript
//forward slash declaration
let p1 = /javascript/i;

//constructor declaration
let p2 = new RegExp("/javascript/i");
```

Here p1, and p2 are regular expressions for javascript.

> Here the **/javascript/** part is the RegExp and **i** is the modifier.

**RegExp modifiers:**

Modifiers are added after the declaration of RegExp. Their task is to modify the search operation according to their property.

Following are some common modifiers in Javascript:

- **g**: It is added to make sure the RegExp doesn't stop after finding the first match. It performs global matches.
- **i**: It performs a case insensitive matching.
- **m**: It performs multiline matching.

---

---

# Javascript typeof

_So far, we've seen multiple data types in javascript and their declaration and applications. But what if we're given a value, and we're supposed to tell what data type it is? Well, we've got a savior._

The javascript `typeof`, is an operator which is used to tell the *data type* of the element. It takes the element and returns a **_string_**, which has information about the data type of the elements.

**Declaration:**

It can be declared by the `typeof` keyword followed by the element whose data type we want to know.

**Syntax:**

```javascript
typeof elementName;
```

**Example:**

```javascript
var a = 100;
var b = "Hundred";
var c;

console.log(typeof a);
//output: number

console.log(typeof b);
//output: string

console.log(typeof c);
//output: undefined
```

In the above example the first output is *number* as a is a number type. Similarly, the second output is *string* as b is of string type; similarly c outputs *undefined* as c hasn't been defined yet.

> Note: typeof cannot be used if the object is an array.

**typeof common data types in javascript:**

```javascript
typeof "Javascript"; // "string"
typeof 10.3244; // "number"
typeof true; // "boolean"
typeof function () {}; // "function"
typeof myCar; // "undefined"
typeof null; // "object"
typeof NaN; // "number"
typeof ["Cat", "Dog", "Ball"]; // "object"
typeof new Date(); // "object"
typeof { model: "Swift", company: "Maruti" }; // "object"
```

**Note:**

- The type of array, date, null is object.
- The type of `NaN` is number.

---

---
