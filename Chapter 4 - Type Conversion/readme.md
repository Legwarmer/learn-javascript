# Introduction to JavaScript type conversion

Firstly, to get started with type conversions, we need to know that any calculation can be done among the same data types only. So what if we force JavaScript to do any such operations, like adding a number to a string?, well in such cases, the Javascript compiler, by default, converts the number to the string format and then concatenates them both, this is what type conversions are.

### Type Conversion in JavaScript

Type conversion in JavaScript is the conversion of one data type to another data type (such as string to a number, object to a Boolean, and so on) which is required by the function or operator to work in the right way to give the expected results.

Type conversions take place when any operation is done with different data types, these conversions can be either done by the Javascript compiler or manually by us.

**Let’s now Understand these Conversions with a Few Examples:**

```javascript
// Number is converted into String
console.log("5" + 3); // '53'

// String is converted into Number for calculation
console.log("5" - 3); // 2
console.log("5" * 3); // 15

// expression is converted into boolean
console.log(null == 1); // false

// When the result is not a number
console.log("Ale" - 2021); // NaN
```

In the above example, we are operating between different data types, so as discussed earlier Javascript compiler by default, converts a string to a number when we use -, \*, / operators while, number to a string by + operator.

The loose equality `==` operator also does conversion if needed, as in 3rd example where null is converted into `0` first and then the comparison expression is `0 == 1`, which is false.

Also, in case when there is no valid operation, as in the last example, the Javascript compiler automatically converts the expression result into a number which is *Not a Number* and the developer console shows `NaN`.

---

---

# Types of type conversion in Javascript

Basically, there are two ways in which type conversion in Javascript takes place : Implicit and Explicit type conversions.

- **Implicit type conversions -** Automatic type conversion done by Javascript compiler.
- **Explicit type conversions -** Manual type conversion done by us.

Any data type, whether it’s primitive or an objects, is valid subject to type conversions, and the logic behind objects and primitives work differently, but both primitives and objects can only be converted into these three types :

- _to string_
- _to number_
- _to boolean_

**Let’s now first talk about Implicit and Explicit type conversion in Javascript.**

---

---

# Implicit type conversion

**Implicit conversions** are the conversions of one data type into another data type (ensuring that operations are done among same data types) for the operators or functions to work correctly. *These conversions are also known as type coercion in Javascript.*

These conversions usually happens when you apply operators to values of different types, like `'2' * 5`, `1 == null`, `null == new Date()` or can be triggered due to external context like `if(value) { ... }`, where `value` is coerced to a Boolean.

**In the instance above, let’s now talk about where these conversions occur in Javascript with the help of a few examples:**

```javascript
// Implicit conversion to string
"25" + 15; // '2515'

// Implicit conversions to a number
23 * "2"; // 46
23 - true; // 22  // true is converted into 1
true - null; // 1
false + undefined; // NaN  // undefined into NaN

// Implicit conversions in statements
const arr = [];
if (arr) {
  console.log("Hello World");
} // Hello World
// Here the empty arr is converted into a Boolean true
```

One operator that does not trigger implicit type coercion is `===`, which is a strict equality operator, whereas the loose equality operator `==` does both comparison and conversion if needed.

Implicit type conversions are like a double-edged sword, as it may sometimes lead to errors or defects in our code, but also a useful mechanism that allows us to write a lot less code. We will see in the next section how implicit conversions lead to issues.

**Note -** Remember these observations from the following code block :

```jsx
// Here, the addition operator triggers the conversion of 1 into string
1 + 'Team';   // '1Team'

// but in this case, operation is done as follows:
1 == 1 + 'Team';
==> 1 == '1Team';  // false
```

Here, in the first case 1 + 'Team' the + operator triggers the conversion of 1 into a string as always. But in the second case, it returns false to the console, because of the precedence of the + operator over == operator.

---

---

# Explicit type conversions

**Explicit conversions** are the conversions that are manually performed by the developer in the source code in order to get the required changes and to undo the errors done by the implicit type conversions. Such conversions are **also** referred as **_typecasting in JavaScript._**

Now, you might think that where Implicit type conversions fail to give required changes, well to understand this let’s take an example: you might remember that when we use the prompt() function, it always returns a string to the developer console, this may lead errors in our function as :

```javascript
const pensInBag = prompt("How many pens you have in your bag?");
const pensInHand = 10;
const totalPens = pensInHand + pensInBag;
console.log(totalPens);
// if i enter 5 in prompt window then:
// expected result: 15
// Actually appeared: 105
```

In this example, we have seen how implicit type conversions can leads to a huge error/bug in a codebase, and to avoid such bugs we need to change the data type of value of `pensInBag` from *string* to a *number* manually, for which we can use Number() function. Similarly, for other manual conversions we can use `Boolean()`, `String()`, `Number()`, `parseInt()`, etc. functions.

**Explicit conversions can rescue us from such errors caused by implicit conversions, let’s see how:**

Here, we will use the Number() function to change the data type of value of `pensInBag` from a string to a number so as to get the correct output.

```javascript
// Explicit conversions solved previous problem
const pensInBag = Number(prompt("How many pens you have in your bag?"));
const pensInHand = 10;
const totalPens = pensInHand + pensInBag;
console.log(totalPens);
// here now if i enter 5 then
// result appeared as expected: 15
```

**Here are some other examples of explicit type conversions in primitive values:**

```jsx
// conversion to string using String()
String(2 - true); // '1'
"56" === String(56); // true

// conversion to number using Number()
Number(prompt()); // converts prompt value into a Number
Number("2350e-2"); // '23.5'
Number("23") + 7; // 30

// conversion to Boolean Explicitly
Boolean(""); // false
Boolean(2) == true; //true
```

In the above example, we know the === operator does not trigger any type conversions, so we need to put the String() function to get correct results. Similarly, in the last example, we prevent the conversion of the true into a *number* by using the Boolean() function.

---

---

# The Most Common Data Conversions

Type conversions are a significant part of JavaScript, there is a lot of flexibility in the language and the ability to convert one data type into another data type. The different types of type conversion in JavaScript are :

- String conversions
- Numeric conversions
- Boolean conversions
- Symbol conversions

**Let’s now first begin with type conversions for Primitives**

---

## String Conversion

The conversion of a data type into a string is something known as **_String Conversion._** To explicitly convert a data type into a string, we just need to apply the String() function, and implicit string conversion can be triggered by the use of + binary operator when one operand is a string.

**All primitive values are converted to strings naturally, as you might expect:**

```jsx
// String Conversion Implicitly
"25" + 56; // '2556'
"25" + null; // '25null'
"Ale " + undefined; // 'Ale undefined'
"25" + false; // '25fasle'

// String Conversion Explicitly
String(23); // '23'
String(true); // 'true'
String(32 - false); // '32'
String(32 - true); // '31'
```

**Explanation**

From the above example, we have conquered that the + operator tends to convert the value of different data types into a string when there is an addition between a string and an operand of a different data type.

---

## Numeric Conversion

Now, it’s time for Numeric conversions, likewise string conversion, we use the Number() method to convert strings, Booleans, and other numeric expressions into a number Explicitly.

**Implicit numeric conversion is tricky because it is triggered in many cases :**

- Comparison operators (`>`, `<`, `=>`, `<=`)
- arithmetic operators ( `+`  `/` `%` ).
- Bitwise operators ( `|` `&` `^` `~`)
- unary `+` operator
- loose equality operator `==` (incl. `!=`).

**Note:** that binary + operator does not trigger numeric conversion when any operand is a string. Also, == does not trigger numeric conversions when both operands are strings.

**Let’s now look at some of the examples of numeric conversions:**

```javascript
// Explicit conversion into number
Number(" 12 "); // 12
Number("-12.34"); // -12.34
Number("\n"); // 0

//null and indefined into a number
Number(null); // 0
Number(undefined); // NaN

// Booleans into Number
Number(true); // 1
Number(false); // 0

// Difference between results of the same prompt..
prompt("what is you age?"); // '26'
Number(prompt("what is you age?")); // 26
```

While converting a string to a number, JavaScript compiler first removes the empty whitespaces like \n, \t characters and returns `NaN`, if the result after trimming white spaces is not a valid number.

Also, we need to handle null and undefined differently as, null becomes 0 whereas undefined becomes `NaN` when converted into a number.

---

**Points to Remember:**

1.  In an expression, when we apply == operator to null or undefined, numeric conversions does not happen. Also, null is equal to null or undefined, and cannot be equal to anything else.

```jsx
null == null; // true
null == 0; // false
// null cannot be converted into 0 with equality operator
null == undefined; // true
```

2.  Always keep in mind while using the **prompt function** that it always returns you a String, it automatically converts any input by the user into a string. To operate with the numeric data obtained from the user via prompt, we always need to convert that into a number using Number() method.
3.  To get an integer value from a given value, we use the `parseInt()` method :

```jsx
console.log(parseInt(65.456)); // 65
```

4.  According to operator precedence, the + operator has left-to-right associativity, so if we have an expression 2 + 3 + '4' + 'number' the the operation is done in the following way :

```jsx
2 + 3 + '4' + 'number'
==> 5 + '4' + 'number'
// number 5 is converted implicitly into string and then concatenated
==> '54' + 'number'
==> '54number'
```

---

## Boolean Conversion

Conversion of an expression into a boolean is known as **_boolean conversion_**. This conversion can be either done explicitly by the Boolean() Function, or implicitly in logical contexts (like in if/else ) or triggered by the use of the logical operators (||, &&, !).

**For instance:**

```jsx
Boolean(2); // true

// conversion to boolean implicitly in an statement
if (" ") {
  console.log(`Empty string`);
} // Empty string

// implicit conversions due to logical operators
!!2; // true
"" || 23; // 23
```

Logical operators such as || and && do Boolean conversions internally but return the value of original operands even if they are not Boolean. **As in the above example :**

```javascript
"" || 23; // returns 23, instead of giving true
```

**Points to Remember -**

- We know that there are namely two Boolean results : true or false, so it's just easier to remember the list of false values.

```jsx
Boolean(""); // false
Boolean(0); // false
Boolean(-0); // false
Boolean(NaN); // false
Boolean(null); // false
Boolean(undefined); // false
Boolean(false); // false
```

All other values except these, are truthy values, including object, array, date, and so on. Even all Symbols, Empty objects, and arrays are truthy values.

**Note:** Sometimes, we counter an error or confusion, when we use `5 == true`, it results False, while when we use if(5) {}, then 5 is evaluated as true and enters if/else statement.

```jsx
// In Developer console
5 == true; // false

if (5) {
  console.log("5 is a truthy value");
} // 5 is a truthy value
```

What happens here is that, when you compare 'something' with a number, then JavaScript will convert that 'something' into a number.

So when you compare `5 == true`, JavaScript tends to convert true into 1 and, we clearly know that 1 is not equal to 5; hence the comparison is false.

While in the case of `if(5) {}`, 5 is converted into a Boolean, and as we know, 5 is a truthy value, so it enters the if block.

**Recommended:** You can always opt for Explicit conversions in such situations to avoid errors, since 5 is a truthy value, you could do Boolean(5) == true, and now it returns true.

---

## Symbol Conversion

Symbol conversion is a bit tricky and can only be converted explicitly, but not implicitly. Specifically, symbols cannot be coerced into strings or numbers so that they cannot be used accidentally used as properties that would be otherwise expected to behave as a symbol.

When we use console.log() to show the outputs of the symbols, and it works because console.log() calls String() on the symbols to create useful results.

**For instance:**

```jsx
let mySymbol = Symbol.for("mySymbol"),
  str = String(mySymbol);

console.log(str); // 'Symbol(mySymbol)'
```

If you tries to add a symbol directly with a string, it will throws a TypeError as :

```jsx
let mySymbol = Symbol.for("mySymbol"),
  sum = mySymbol + "";
console.log(sum); // Uncaught TypeError: Cannot convert a Symbol value to a string
```

Concatenating mySymbol to a string requires mySymbol to be first converted into a string, and an error is thrown when coercion is detected, preventing its use in this manner.

Similarly, you cannot coerce a symbol to a number, all mathematical operators throws an error when used with a symbol.

```jsx
let mySymbol = Symbol.for("mySymbol"),
  factor = mySymbol / 2;
console.log(factor); // Uncaught TypeError: Cannot convert a Symbol value to a number
```

The above example attempts to divide a symbol by 2, but throws an error regardless of the operator used.

**Note:** You can use a logical operator with symbols because all symbols are considered as true, just like any other non-empty value in JavaScript.

---

---

# Type conversion in Objects

So far, we have learned about type conversion for primitives. Now when it comes to objects and the compiler encounters expressions like `[2] + [5, 3]`, first it needs to convert an object to a primitive, which is then converted into a Boolean, string, or a number.

_The easiest case for any non-primitive value is the Boolean conversion, its always coerced to true, no matter if the object or array is empty or not._

Both numeric and string conversion make use of two methods of the input object: `valueOf` and `toString`. Both methods are declared on `Object.prototype` and thus available for any derived types, such as Date, Array, etc.

---

---

# JavaScript type conversion Table

In the table below are some of the most common JavaScript values conversion to Number, String, and Boolean :point_down:

| Value           | String conversion | Number conversion | Boolean conversion |
| --------------- | ----------------- | ----------------- | ------------------ |
| 20              | '20'              | 20                | true               |
| '20'            | '20'              | 20                | true               |
| false           | 'false'           | 0                 | false              |
| true            | 'true'            | 1                 | true               |
| 0               | '0'               | 0                 | false              |
| '0'             | '0'               | 0                 | true               |
| NaN             | 'NaN'             | NaN               | false              |
| null            | 'null'            | 0                 | false              |
| undefined       | 'undefined'       | NaN               | false              |
| []              | ''                | 0                 | true               |
| \"\"            | \"\"              | 0                 | false              |
| [23]            | '23'              | 23                | true               |
| [10,23]         | '10,23'           | NaN               | true               |
| \"\"            | ' '               | 0                 | true               |
| ['fun']         | 'fun'             | NaN               | true               |
| ['fun','enjoy'] | 'fun,enjoy'       | NaN               | true               |
| function(){}    | 'function(){}'    | NaN               | true               |
| {}              | '[object Object]' | NaN               | true               |
| Infinity        | 'Infinity'        | Infinity          | true               |
| -Infinity       | '-Infinity'       | -Infinity         | true               |

---

---

# JavaScript typeof operator

Let's introduce you to another Operator in JavaScript called as `typeof` operator. In JavaScript, for us to make conversions explicitly, first, we need to know the type of data that is to be converted.

This `typeof` operator helps us to determine the data type of JavaScript variables and values used.

```javascript
console.log(typeof 10); // 'number'
console.log(typeof "Hello"); // 'string'
console.log(typeof []); // 'object'

console.log(typeof null); // 'object'
console.log(typeof undefined); // 'undefined'
console.log(typeof function () {}); // 'function'
```

**Remember -** The **typeof** operator can't be used to determine if an object is an Array or not.

To determine if an object is an Array, we can use **`Array.isArray()`** method.

- **Array.isArray()** is a syntax that returns a Boolean **-** true if the object is an array, otherwise false.

```javascript
// To determine whether the object is an Array

const arr = [23, 56, 25];
console.log(Array.isArray(arr)); // true

const notArr = { name: "Ale", job: "Developer" };
console.log(Array.isArray(notArr)); // false
```

---

---

---
