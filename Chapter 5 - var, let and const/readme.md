# Introduction

Javascript provides us with multiple ways to declare a variable, but which one should we use.

Suppose we created a function and we need a constant variable inside the function, which means we want a variable that will not be updated in any case. Here if we will declare a var variable or let variable, then it can be updated, but if we declare a const variable, it will not be updated in any case and will work fine with our function.

---

---

# Variable Declaration vs Initialization

For storing any value, we need a variable, so first, we will declare a var variable and then initialize the value into the variable.

**let's see it by an example-**

```javascript
var myName;
myName = "my name";
console.log(myName); //output => "my name"
```

In the example above, we declared a variable `myName` in the first line, and then initialized the string value "my name" in the second line.

In the above example, we take a two-step approach, first declare a variable and then Initialize it but we can do declaration and initialization at the same time like this -

```javascript
var myName = "my name";
console.log(myName); //output => "my name"
```

In the above example, we take var variable as an example, but we can do Declaration and initialization same with the let and const.

---

---

## Function-scope vs Block-scope

_Before we get into the difference between let and var and const in Javascript, let us learn some of the differences between function-scope and block-scope:_

### Scope

Scope stands for where our variable will be available to use inside our code and where it will not.

**let's take an example to understand it -**

```javascript
function myFun() {
  var myName = "my name";
  console.log(myName);
}

myFun(); //output => "my name"
console.log(myName); //output => ReferenceError
```

In the example, we have a function `myFun();` inside the function, we declare a variable `myName` and print the variable `myName` on the console.

When we call our function `myFun` it successfully prints the value of variable `myName` on the console, but when we try to print the variable `myName` outside the function, it throws `referenceError` because variable `myName` has a function scope that's why it's not accessible outside the function.

---

## Function scope

Variable having Function-scope means, variable will only be available to use inside the function it declared, will not be accessible outside of function, and will give Reference Error if we try to access.

**Here is an example -**

```javascript
function name() {
  var myAge = 22;
  console.log(myAge);
}

name(); //output => 22(

console.log(myAge); //output => ReferenceError
```

In the example, we make a function name() then we declare a variable `myAge` inside the function, when we call the function, it prints the `myAge` variable on the console, But when we try to access the variable outside the function, it's throwing a Reference Error.

---

## Block-scope

Block means a pair of curly brackets, a block can be anything that contains an opening and closing curly bracket.

Variable having Block-scope will only be available to use inside the block it declared, will not be accessible outside the block, and will give Reference Error if we try to access.

**Here is an example -**

```javascript
if (true) {
  let myName = "your name";
  console.log(myName); //output=> "your name"
}
console.log(myName); //output => ReferenceError
```

In the example above, we have an if block with a true condition, and inside the if block, we declare a variable name `myName`. Now when we try to print the `myName` variable to console, it prints successfully, but when we try to print the variable outside the if block, we are getting Reference Error.

---

---

# What is the VAR Variable in JS?

Var variable is the old way to declare a variable in javascript; var variable has the function scope, But global scope when it is declared outside the function.

**Example of var variable with function scope:**

```javascript
function myFun() {
  var myName = "my name";
  console.log(myName);
}
myFun(); //output => "my name"
console.log(myName); //output=> re
```

In the example above, we have a function `myFun()`, inside the function, we declare a variable `myName` and print it on the console.

When we call the function, it successfully prints the variable `myName` on the console, but when we try to print the variable `myName` outside the function, it throws `ReferenceError` because it's not accessible outside the function.

When we declare a var variable outside the function, it will have the global scope and will be available to use everywhere inside the whole program.

**Example of var variable having global scope:**

```javascript
var myName = "your name";

function myFun() {
  console.log(myName);
}

myFun(); //output => "your name"

if (true) {
  console.log(myName); //output => "your name"
}

console.log(myName); //output => "your name"
```

In the above example, we have a variable `myName` which is declared outside the function body, and that's why having global scope.

Now, we tried to access this variable inside our function `myFun`, it print's the variable into the console, next we have an if block with the condition of true; inside this if block we again print the variable `myName` to the console and it's accessible here also.

The last thing we do is to directly access the variable, and we successfully access the variable and print it on the console.

As we can see, the variable myName is accessible everywhere inside our program because it has global scope.

---

## Hoisting of var Variable

When we declare a var variable, it gets hoisted to the top of the scope and get assigned with the value of undefined. Let's take an example to understand it -

```javascript
console.log(myName); //output => undefined
var myName = "my name";
```

In the example above, we are trying to access the variable myName before the declaration.

Here is what it will look like when the variable myName gets hoisted to the top of the scope -

```javascript
var myName;
console.log(myName); //output => undefined
myName = "my name";
```

We can see here, our variable gets hoisted to the top of the scope and initialized with undefined, but the initialization of the value happens where the variable was declared.

If we talk about only hoisting, it's a feature provided by javascript which moves variables and functions to the top of scope before code execution; It also happens when we make a function declaration.

**Example of function declaration:**

```javascript
myFun(); //output => "my name"
function myFun() {
  var myName = "my name";
  console.log(myName);
}
```

In the example above, we are calling the function before the declaration, but still, it calls the function successfully.

**Our example code will look like this after getting moved to the top:**

```javascript
function myFun() {
  var myName = "my name";
  console.log(myName);
}
myFun(); //output => "my name"
```

**Problem with the var Variable**

- var variable can be re-declared and updated. re-declaration allows declaring more than one variable with the same name, because of this reason, if we declare a new variable by mistake, it will override the original variable value.

**let's discuss how it can be re-declared with an example-**

```javascript
var name = "my name";
var myAge = 22;

if (myAge > 18) {
  var name = "another person name";
}

console.log(name); //output => "another person name"
```

Here we have a name variable, age variable, and an if conditional block, our if condition is true here so code inside the if block will run and override the previously declared name variable because of re-declaration behavior of var variable. This behavior can affect the output of code and lead to unexpected output.

- Another problem was, not able to declare a constant variable. It's okay when we want to declare a variable that can be changed/updated, but what if we want to declare a constant variable that can't be changed once it is declared.

---

# What is the Let variable in JS?

The new version of javascript (ES6) introduces two new methods of declaring variables in javascript, and one method was using the let keyword to declare variables.

**Here is an example of let variable declaration -**

```javascript
let myName = "my name";
```

In the example above, we used a let keyword to declare a let variable and initialize a string value "my name".

Let variable introduce a special feature that does not allow re-declaration of variables, if you remember, re-declaration was a problem in var variable but let variable solve this problem.

**Example of re-declaration in let variable:**

```javascript
let myName = "my name";
let myName = "not my name";

console.log(myName); //output => SyntaxError: redeclaration of let name
```

The above example shows the difference between let and var and const in javascript. In the example above, we declared a variable myName and again declared a variable with the same name when we tried to print the variable on the console it throw SyntaxError: redeclaration of let name.

**scope of let variable**

The let variable have block scope, meaning let variable will be accessible only inside the block it's declared if we try of access outside of the scope it will show Reference Error.

**let's take an example to understand it-**

```javascript
let myAge = 20;
if (myAge > 18) {
  let myName = "my name";
  console.log(myName); //output => "my name"
}
console.log(myName); //output => ReferenceError
```

The above example shows the difference between let and var and const in javascript. In the example above, we have a variable `myAge` and an if conditional block, our if condition is true here, so we came inside the if block. Inside the if block we have another variable, `myName`, which is in a block scope. We print the `myName` variable to console inside the if block now when we try to print the variable `myName` outside the if block it's not accessible, and throw `ReferenceError` because of scope.

**re-declaration of let variable**

let variable didn't allow re-declaration of variable but it allows to update the variable, re-declaration of the variable was a big problem with var variable let variable helps us to avoid the problem created by re-declaration of the variable.

**let's take an example to understand the re-declaration in the let variable -**

```javascript
let myName = "my name";
let myName = "my new name";
console.log(myName); //output => SyntaxError: redeclaration of let myName
```

The above example shows the difference between let and var and const in javascript. Here we have a variable myName then we again declare a variable with the same name and then try to print the value of the variable on console, and as a result, it throws the syntax error.

**now take an example to understand how let variable get updated -**

```javascript
let myName = "my name";
myName = "my new name";
console.log(myName); //output => "my new name"
```

The above example shows the difference between let and var and const in javascript. Here we declared a variable `myName` and assigned the value of "my name", then in the next line, we assign another value to our `myName` variable, which is "my new name". finally, when we try to print the value of `myName` variable on the console, it prints the updated value of the `myName` variable, which is "my new name" not "my name".

---

## Hoisting of let variable

let variable also get hoisted to the top of scope But did not get assigned any value, as a result, if we will try to access the let variable before declaration it will throw syntax error because it doesn't have any value to print.

**let's take an example to understand it further -**

```javascript
console.log(myName); //output => ReferenceError
let myName = "my name";
```

The above example shows the difference between let and var and const in javascript. Here we are trying to access a variable `myName` before the declaration but get `ReferenceError` because after getting hoisted to the top of scope variable remains uninitialized.

---

---

# What is the Const variable in JS?

The new version of javascript (ES6) introduces two new methods of declaring variables in javascript, one was using the const keyword to declare constant variables.

**Example of const variable:**

```javascript
const myName = "my name";
```

Let variable introduce a special feature that does allow variables to be constant if you remember declaring constant variable was a problem in var variable but const variable solve this problem.

**Let's see it by an example :**

```javascript
const myName = "my name";
myName = "not my name";

console.log(myName); //output => TypeError: invalid assignment to const 'myName'
```

The above example shows the difference between let and var and const in javascript. In the example above, we declared a variable `myName` and initialize a string value of "my name", when we try to update `myName` variable, it throws a type error because we can not update the value of the const variable.

**const declarations are block-scoped**

Const variable also has the Block scope like let variable, const variable also can't be accessed outside of the scope. Let take an example to understand:

```javascript
if (true) {
  const myName = "my name";
  console.log(myName);
}

console.log(myName); //output =>  ReferenceError: myName is not defined
```

The above example shows the difference between let and var and const in javascript. In the above example, we have an if block, and a variable `myName`, inside the if block, we successfully print the `myName` variable on the console, but when we try to print the `myName` variable outside the if block it throws an error because of the scope of const variable.

**Const Variables cannot be updated or re-declared**

Const variable can't be updated or re-declared; this behavior of const variable helps us to write the error-free code.

**let's take an example to understand updating in const -**

```javascript
const myName = "my name";
myName = "my new name";
console.log(myName); //TypeError: invalid assignment to const 'myName'
```

In the example, we have a variable `myName` in the first line, then we initialize another value to our `myName` variable.

When we try to print the `myName` variable to the console, it shows `TypeError`, which means we can't update the const variable.

**let's take an example to understand re-declaration in const -**

```javascript
const myName = "my name";
const myName = "my new name";
console.log(myName); //TypeError: invalid assignment to const 'myName'
```

The above example shows the difference between let and var and const in javascript. In the example we have a variable `myName` in the first line, then we again declared another variable with the same name.

When we try to print the `myName` variable to the console, it shows `SyntaxError`, which means we can't re-declare the const variable.

---

## Hoisting of const

Const variable also gets hoisted to the top of scope But did not get initialize any value, as a result, if we try to access the const variable before declaration it will throw syntax error because it doesn’t have any value to print and it's illegal for const variable.

**let’s take an example to understand it further:**

```javascript
console.log(myName); //output => ReferenceError
const myName = "my name";
```

The above example shows the difference between let and var and const in javascript. Here we are trying to access a variable `myName` before the declaration but get `ReferenceError` because after getting hoisted to the top of scope const variable remains uninitialized.

---

---

# Summary

_The following table briefs the difference between let and var and const in javascript:_

| var                                                                | let                                                                | const                                                               |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------- |
| var has the function or global scope.                              | let have the block scope.                                          | const variable has the block scope.                                 |
| It gets hoisted to the top of its scope and initialized undefined. | It also got hoisted to the top of its scope but didn't initialize. | It also got hoisted to the top of its scope but didn't initialize.  |
| It can be updated or re-declared.                                  | It can only be updated and can't be re-declared.                   | It can't be updated or re-declared.                                 |
| It's an old way to declare a variable.                             | It's a new way to declare variables introduced in ES6.             | It's also a new way to declare a variable, which introduces in ES6. |

---

---

---
