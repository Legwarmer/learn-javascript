# Introduction

Before starting this article, I assume that you know a few important concepts, such as how to store an object in the fields and how to name storage, by calling them variables. You also know how you can use an array, the container object that stores many elements or data types. Now, the question is, what do we do with them? In many cases, you have assigned a value or initialized the value by using an assignment operator(=). After assigning a value to two operands, you can add them by using a + symbol. You can perform many types of operations on one or more than one operand by using such symbols. These symbols are called operators.

---

---

# Addition Operator

This JavaScript arithmetic operator adds two numeric operands together. The add(+) operator is a bit different:

If one of the operands is a string, the result of the operation is a string, according to these rules:

- If both operands are strings, the second string is concatenated to the first.
- If only one operand is a string, the other operand is converted to a string, and the result is the concatenation of the two strings.
- If single or both operands are decimal values, then it returns the decimal values.
- *Infinity* added to *–Infinity* results `NaN`.

This behavior of add operator is a source of common mistakes, as this code snippet shows:

**Syntax:** You just need to write two integers. These two integers are stored in variables num1 and num2, respectively. Then, these two numbers are added using the + operator, and the result is printed in the console.

```javascript
num1 + num2;
```

**Example:**

```javascript
var num1 = 22;
var num2 = 28;
var num3 = 10.2;
var num3 = 20.6;
console.log("22 + 28 = " + num1 + num2); // 22 + 28 = 2228
console.log("22 + 28 = " + (num1 + num2)); // 22 + 28 = 50
console.log("10.2 + 20.6 = " + (num1 + num2)); // 10.2 + 20.6 = 30.8
```

**Explanation:**

- Addition Operator(+) is ambiguous. It means **"concatenate"** or **"add"**. The expression in the first console.log() method converts num1 to a string, because the left operand of add is another string. The result is a string, so num2 is converted to a string, too.
- In the second expression, the parentheses change the operator precedence, and so first, the num1 + num2 expression is evaluated to 50, then this value is converted to a string.

JavaScript Arithmetic operators can handle special values, such as `NaN`, Infinity, and –Infinity.

- If any of the operands is `NaN`, the operation result will be `NaN`, too.
- If an operation provides a result that is higher than the maximum value that can be represented by Number, the result is 'Infinity'.
- Similarly, if the result is lower than the lowest negative value that can be represented by Number, the result is '–Infinity'.

---

---

# Subtraction Operator

This JavaScript arithmetic operator subtracts the right operand from the left. Subtraction Operator(-), however has only one meaning subtract. So it subtracts only. There is no opposite of concatenation (I think) and the subtraction operator(-) only performs subtraction regardless of the type of operands.

- '_Infinity_' subtracted from '_Infinity_' results `NaN`.

**Syntax:** You just need to write two integers. These two integers are stored in variables num1 and num2 respectively. Then, these two numbers are subtracted using the - operator, and the result is printed in the console.

```javascript
num1 - num2;
```

**Examples:**

```javascript
var num1 = 28;
var num2 = 22;
var num3 = 28.5;
var num4 = 22.75;
console.log("28 - 22 = " + num1 - num2); // 28 - 22 = NaN
console.log("28 - 22 = " + (num1 - num2)); // 28 - 22 = 6
console.log("28.50 - 22.75 = " + (num3 - num4)); // 28.50 - 22.75 = 5.75
```

**Explanation:**

- The expression in the first console.log() method converts num1 to a string, because the left operand of subtraction is another string. The result is a NaN, If the string value cannot be converted into a Number.
- In the second expression, the parentheses change the operator precedence, and so first, the num1 - num2 expression is evaluated to 6, then this value is converted to a string.
- In the third expression, the decimal value is subtracted.

---

---

# Multiplication Operator

This JavaScript arithmetic operator multiplies the two operands together. Multiplication Operator is defined as (\*) and multiply two value and return a product.

- **Infinity** multiplied by **0** results `NaN`.
- **Infinity** multiplied by **Infinity** results Infinity.
- If **Infinity** is multiplied by any **finite number** other than 0, the result is either Infinity or –Infinity, depending on the sign of the second operand.

**Syntax:** You just need to write two integers. These two integers are stored in variables num1 and num2, respectively. Then, these two numbers are multiply using the \* operator, and the result is printed in the console.

```javascript
num1 * num2;
```

**Examples:**

```javascript
var num1 = 28;
var num2 = 22;
console.log("28 * 22 = " + num1 * num2); // 28 * 22 = 616

var num1 = 28;
var num2 = -22;
console.log("28 * -22 = " + num1 * num2); // 28 * -22 = -616

var num1 = "scaler";
var num2 = 22;
console.log("scaler * 22 = " + num1 * num2); // scaler * 22 = NaN
```

**Explanation:**

- In the expression, the parentheses change the operator precedence, and so first, the num1 \* num2 expression is evaluated to 616, then this value is converted to a string.

---

---

# Division Operator

This JavaScript arithmetic operator divides the left operand by the value of the right operand. Division Operator is defined as (/) and divides two value and return a quotient.

- 'Infinity divided by **Infinity** results `NaN`.
- 'Zero' divided by **zero** results `NaN`.
- If a **nonzero finite number** is divided by **zero**, the result is either Infinity or –Infinity, depending on the sign of the first operand.
- If Infinity is divided by any number, the result is either Infinity or –Infinity, depending on the sign of the second operand.

**Syntax:** You just need to write two integers. These two integers are stored in variables num1 and num2, respectively. Then, these two numbers are divided using the / operator, and the result is printed in the console.

```javascript
num1 / num2;
```

**Examples:**

```javascript
var num1 = 28;
var num2 = 22;
console.log("28 / 22 = " + num1 / num2); // 28 / 22 = 1.2727272727272727

var num1 = 28;
var num2 = 0;
console.log("28 / 0 = " + num1 / num2); // 28 / 0 = Infinity
```

**Explanation:**

- In the expression, the parentheses change the operator precedence, and so first, the num1 / num2 expression is evaluated to 1.2727272727272727, then this value is converted to a string.

---

---

# Modulus Operator

This JavaScript arithmetic operator gives the remainder of the left operand when divided by the right operand. It is also known as the Remainder operator. Modulus Operator is defined as (%) and divides two value and return a remainder. Using the Modulus operator, we can find the number is odd or even if we do a number modulo 2 answer is **zero** then it means the number is **even**. If we do a number modulo 2 answer is **one**, then it means the number is **odd**.

- If the dividend is an **infinite** number and the divisor is a **finite number**, **modulus** results NaN.
- If the dividend is **zero** and the divisor is **nonzero**, modulus results **zero**.

> Generally, the remainder operator is useful only when its operands are positive integers.

Another application of the Modulus Operator is to strip the digits from a number.

**Syntax:** You just need to write two integers. These two integers are stored in variables num1 and num2, respectively. Then, these two numbers use the % operator to calculate the modulus of the number, and the result is printed in the console.

```javascript
num1 % num2;
```

**Examples:**

```javascript
var num1 = 28;
var num2 = 22;
console.log("28 % 22 = " + (num1 % num2)); // 28 % 22 = 6

var num1 = 1;
var num2 = 2;
console.log("1 % 2 = " + (num1 % num2)); // 1 % 2 = 1

123 % 10; // returns 3
```

**Explanation:**

- In the expression, the parentheses change the operator precedence, and so first the num1 % num2 expression is evaluated to 6, then this value is converted to a string.
- The last example is interesting since 2 cannot divide 1 at all, the remainder is just the number being divided.

---

---

# Exponentiation Operator

This JavaScript arithmetic operator gives the exponent of the left operand raised to the power of the right operand. Exponentiation Operator is defined as (\*\*) and raises the first operand to the power second operand and returns an exponent.

**Syntax:** You just need to write two integers. These two integers are stored in variable num1 and num2, respectively. Then, these two numbers are Exponentiation using the \*\* operator, and the result is printed in the console.

```javascript
num1 ** num2;
```

**Examples:**

```javascript
var num1 = 2;
var num2 = 2;
console.log("2 ** 2 = " + num1 ** num2); // 2 ** 2 = 4
```

**Explanation:**

- In the expression, the parentheses change the operator precedence, and so first the num1 \*\* num2 expression is evaluated to 4, then this value is converted to a string.

---

---

# Increment Operator

This JavaScript arithmetic operator increases the value of the operand by one. Increment Operator is defined by a double plus sign (++). This is a unary operator, x++ produces a value of x before adding 1 to x. This is called the **post-increment operator**, since the value is produced, and then the variable is incremented. On the other hand,++x produces a value of x after adding 1 to x. This is called the **pre-increment operator**,

**Syntax:** You just need to write integers. This integer is stored in variable x respectively. Then, this numbers is incremented using the ++ operator, and the result is printed in the console.

```javascript
x++; // Post-increment Operator
++x; // Pre-increment Operator
```

**Examples:**

```javascript
var x = 20;
x++; // x returns 21
console.log(x);

var x = 20;
var y = x++; // y is 20, x is 21
console.log(x);
console.log(y);

var x = 20;
var y = ++x; // y is 21, x is 21
console.log(x);
console.log(y);
```

**Explanation:**

- In the first expression, variable x value is 20 and then it's increment by 1 because we perform Increment operator on it, so the result will be 21.
- In the second expression, variable x value is 20 then we perform increment operator on x, and save into y but the value of y is 20 because increment happens post assignment.
- In the third expression, variable x value is 20 then we perform increment operator on x and save into y but the value of y is 21 because increment happens before assignment.

---

---

# Decrement Operator

This JavaScript arithmetic operator decreases the value of the operand by one. Decrement Operator is defined by a double minus sign (--). This is a unary operator, x-- produces a value of x before subtracting 1 to x. This is called the **post-decrement operator**, since the value is produced, and then the variable is decremented. On the other hand, --x decrements the variable first, and then produces the value the **pre-decrement operator**.

**Syntax:** You just need to write integers. This integer is stored in variable x respectively. Then, this numbers is decremented using the -- operator, and the result is printed in the console.

```javascript
x--; //Post-decrement Operator
--x; //Pre-decrement Operator
```

**Examples:**

```javascript
var x = 20;
x--; // x returns 19
console.log(x);

var x = 20;
var y = x--; // y is 20, x is 19
console.log(x);
console.log(y);

var x = 20;
var y = --x; // y is 19, x is 19
console.log(x);
console.log(y);
```

**Explanation:**

- In the first expression, variable x value is 20 and then it's decrement by 1 because we perform decrement operator on it, so the result will be 19.
- In the second expression, variable x value is 20 then we perform decrement operator on x and save into y but the value of y is 20 because decrement happens post assignment.
- In the third expression, variable x value is 20 then we perform decrement operator on x and save into y but the value of y is 19 because decrement happens before assignment.

---

---

# Unary Negation (-) Operator

The unary negation operator converts a non-number or something to a number because it doesn't perform any operations on numbers. It can convert a string into integer and float values, and it can also convert Boolean values true, false, NULL into a number. It also supports decimal, hexadecimal and negative values.

**Syntax:** You just need to write integers. This integer is stored in variable x respectively. Then, this number negates the value using the - operator, and the result is printed in the console.

```javascript
-x; // convert an operand into a number and negate the value after that.
```

**Examples:**

```javascript
const x = +3;
const y = -x;
console.log(x); // x = 3
console.log(y); // y = -3

const x = -"0xFF";
console.log(x); // x = -255

const x = -"123e-5";
console.log(x); // x = -0.00123

const x = -"3.14";
console.log(x); // x = -3.14

console.log(-true); // -1
console.log(-false); // -0
console.log(-null); // -0
console.log(
  -function (val) {
    return val;
  }
); // NaN
console.log(-1n); // -1n
```

**Explanation:**

- In the first example value of x is 3 and we perform the unary negation operator on to it.
- In the second example value of x as a hexadecimal number 0xFF so it's converted into a decimal number and applies unary negation(-) operator, so it prints -255.

---

---

# Unary Plus (+) Operator

Unary plus operator(+) tries to convert If the operand is not a number. if the operand is already a number, it does nothing. It is the fastest and preferred way of converting something into a number because it does not perform any other operations on the number. It can convert a string, Boolean values, and NULL to a number. If the operand cannot be converted into a number, the unary plus operator(+) will return `NaN`.

**Syntax:** You just need to write integers. This integer is stored in variable x respectively. Then, this converts its operand to Number type using the + operator, and the result is printed in the console.

```javascript
+x; //converts its operand to Number type
```

**Examples:**

```javascript
const x = 1;
const y = "2";
console.log(+x); // 1
console.log(+y); // 2

+true + // 1
  false + // 0
  null; // 0
```

**Explanation:**

- In the first example value of x is 1, and we perform the unary plus operator on it, but it does nothing.
- In the second example, we apply the unary plus operator on boolean values and NULL, so it converts all into number.

---

---

# Working of Math Operators With Different Data Types

Now we are going to see how math operators work on different data types like strings, numbers, and Booleans.

### + operator

- **Number with Number** While both the operands are numbers, + operator simply adds them.

  ```javascript
  let value = 10 + 20;
  console.log(value);
  ```

  **Output:**

  ```javascript
  30;
  ```

- **Number with String** While one of the operands is string and the other is the number, + operator concatenates them.

  ```javascript
  let value = 10 + "hello";
  console.log(value);
  ```

  **Output:**

  ```javascript
  "10hello";
  ```

- **Number with Boolean** During arithmetic operations Boolean true is converted to 1 and false to 0. Hence while adding numbers with Booleans like true and false, they are treated as 1 and 0.

  ```javascript
  let value = 10 + true; // 10 + 1
  let value_1 = 10 + false; // 10 + 0
  console.log(value);
  console.log(value_1);
  ```

  **Output:**

  ```javascript
  11;
  10;
  ```

### - operator

- **Number with Number** While both the operands are numbers, - operator subtracts them.

  ```javascript
  let value = 10 - 20;
  console.log(value);
  ```

  **Output:**

  ```javascript
  -10;
  ```

- **Number with String** While one of the operands is a string and the other is the number, no arithmetic operation is done as it shows `NaN` (Not a Number) in the output.

  ```javascript
  let value = 10 - "hello";
  console.log(value);
  ```

  **Output:**

  ```javascript
  NaN;
  ```

- **Number with Boolean** During arithmetic operations Boolean true is converted to 1 and false to 0. Hence while subtracting numbers with Booleans like true and false, they are treated as 1 and 0.

  ```javascript
  let value = 10 - true; // 10 - 1
  let value_1 = 10 - false; // 10 - 0
  console.log(value);
  console.log(value_1);
  ```

  **Output:**

  ```javascript
  9;
  10;
  ```

---

---

---
