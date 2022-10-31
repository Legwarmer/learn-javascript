# Introduction

We've already seen the traditional way of writing strings in javascript. Now imagine we are writing a program that takes a user's name and their math and science score and returns a statement that states their name and score. *For e.g., if the user inputs Jon as his and and 10, 11 are his math and science score, respectively, then the program will return: 'Hi Jon, your total score is 21'.*

To achieve the above result by the traditional string method, we have to break the resulting string into parts. We would take a string Hi and then concatenate it with the name input using the + operator. Then we will concatenate the , your total score is string to the result string, and in the end, we will do the sum `mathScore` + `scienceScore` and concatenate the sum to the resulting string. It would look something like this:

```javascript
"Hi " + userName + ", your total score is " + (mathScore + scienceScore);
```

Template literals javascript can be used to write the above expression in an easier way. Template literals in javascript are literals declared using backticks(\`\`) within which we can write stings and add placeholders within the backticks(\`\`). This placeholder can contain variables or expressions; by default, the template literal returns a string expression. These are also known as untagged template literals. We can also call a function and pass the string as an argument, these are known as tagged template literals.

The **backtick(\`\`)** key is present on the **top-left** of the keyboard.

> **Note:** All of these complex mechanisms and symbols are discussed in detail in the below sections. So don't worry, even if you can't understand them yet.

## Syntax

```javascript
//untagged template literals
`This is an untagged template literal``This is an untagged template literal with a ${variable}`;

//Tagged template literals
func`This is tagged template literal with a ${variable}`;
```

The *untagged template* literals are simply declared by using ***backticks* (\`\`)**. The untagged template literals would simply return a string.

The **${ variable }** is used to place *placeholders* in template literals. The *variable* inside the braces is the placeholder, and it can be the value of any data type.

The *func* before the template literal in a tagged template literal is **tagged template**. It is generally a *function* that gets called when we declare the *tagged template literals*, with the template literal as an argument.

---

---

# Template Literals and its types

Template literals are ES6 addition to Javascript that allows users to embed expressions. These expressions can be a number or a string or a variable or constant of any data type in Javascript.

The template literals are declared by using *backticks* (**``**). By default, the template literals concatenate its parts into a string. These strings are also known as *dynamic strings*, as they could include *variables* placeholders whose values can be changed.

The *placeholder* in template literals are declared by **${}**. The placeholder can be placed inside the braces, and it can be a constant or a variable or an arithmetic expression, etc.

The template literals in Javascript support multiple features like *multiline strings*, *nesting*, expression *interpolation* etc.

The template literals in Javascript are mainly of two types:

### Untagged template literals

The *untagged template literals* javascript concatenates the whole expression and returns a string. It simplifies string interpolation (for e.g. before the introduction of template literals, in order to place a numeric value in between a string, we have to divide the string into two parts and then concatenate the strings and the numeric values using the + operator, whereas in untagged template literals we can simply insert variables and expression using **${}**).

### Tagged template literals

The tagged template literals allow us to call the tagged template as a function.

We have discussed the **tagged template literals** javascript in much detail with examples in the below section.

---

---

# Multiline Strings

It's a common practice to write text pieces in multiple lines. In the traditional strings (which is declared by using '' or "" in javascript), this could be achieved by using **\n**.

**For Example**

```javascript
var str =
  "This is the first line of a string\n" +
  "This is the second line of the string";

console.log(str);
//Output:
//This is the first line of a string
//This is the second line of the string
```

In the above example, the compiler, while logging through the string before the + operator encounters the **\n**, thus it changes the line before printing the string after the + operator.

The above result can be achieved by the untagged template literals without adding any `\n`. We can change the line of the string output by simply changing the line of the string inside the (**\`\`**) during string declaration.

**Example:**

```javascript
var str1 = `This is the first line
This is the second line
`;

var str2 = `This is an example of
multiline strings in 
javascript.`;

console.log(str1);
//This is the first line
//This is the second line

console.log(str2);
//This is an example of
//multiline strings in
//javascript.
```

In the above example, we can see that the line of the string output has changed when we have changed the line of string inside the backticks (``) in the declaration. This is the multiline string property of template literals javascript.

---

---

# Expression Interpolation

The template literals Javascript support expression interpolation, i.e. we can embed *placeholders* or *expressions* in between the string.

In traditional strings, in order to add and expression to the concatenate the expression using + operator. For e.g.,

```javascript
var name = "Jon";
var mathScore = 10;
var scienceScore = 8;

console.log(
  name +
    " has scored " +
    mathScore +
    " in maths and " +
    scienceScore +
    " in Science.\nThus his total score is = " +
    (mathScore + scienceScore) +
    "."
);
// Jon has scored 10 in maths and 8 in Science.
//Thus his total score is = 18.
```

In the above example, the variables *name*, *mathScore*, *scienceScore* are concatenated with the strings to produce the output. This is the express interpolation property of template literals javascript.

The above result can be used by using **${}** inside the template literals. We can place the variable or expressions inside the braces and it will *substitute* the variables and expressions with their values.

**Example:**

```javascript
var name = "Jon";
var mathScore = 10;
var scienceScore = 8;

console.log(`${name} has scored ${mathScore} in maths and ${scienceScore} in Science.
Thus his total score is = ${mathScore + scienceScore} .`);
// Jon has scored 10 in maths and 8 in Science.
//Thus his total score is = 18.
```

In the example the variables *name*, *mathScore* and *scienceScore* and the expression *mathScore + scienceScore* are substituted by their respective values. Also, the line is changed in the output as we have changed the line within the backticks.

---

---

# Nesting Templates

Nesting templates mean including a new template literal within a template literal. Template literals in javascript allow the nesting of templates, i.e., we can declare a new template literal inside a template literal.

_Nesting templates come in handy in situations where there is multiple condition checking. It can be used to nest conditional operators._

Templates are nested by declaring backticks strings inside a template by using **${}**.

**Example:**

```javascript
function minVal(a, b, c) {
  let ans = `min value is  ${b < a && b < c ? `b` : `${a < c ? `a` : `c`}`}`;

  console.log(ans);
}

minVal(1, 2, 3);
//min value is a

minVal(2, 1, 3);
//min value is b

minVal(2, 3, 1);
//min value is c
```

In the above example, the **first** inputs are **_a = 1, b = 2, c = 3_**, now the **_(b<a && b<c)_** expression will be return *false* as **b > a**, thus the conditional operator will return *${(a<c) ? a:c}*. since **_a < c_** so the second operator will return a. The the final result will be **min value is a**. Here we can see that the program first iterates through the outer template, since the **_(b<a && b<c)_** condition returns a new template so it goes inside that template and appends it's output to the final result.

In the **second** case, the input are **a = 2, b = 1, c = 3**. Now the **_(b<a && b<c)_** expression will be return *true* as **b < a** and **b < c**. Thus the conditional operator will return the inner template literal b, which will get appended to the resulting string.

In the **third** case, the inputs are **a = 2, b = 3, c = 1**, now the **_(b<a && b<c)_** expression will be return *false* as **b > a** and **b > c**, thus the conditional operator will return *${(a<c) ? a:c}*. since **_a > c_** so the second operator will return c. The the final result will be **min value is c**. Here we can see that the program first iterates through the outer template, since the **_(b<a && b<c)_** condition returns a new template so it goes inside that template and appends it's output to the final result.

---

---

# Tagged Templates

The tagged templates can be used it parse template literals with a function. The tagged template before the string *calls the function*, and the string values are passed to the function as an array of arguments. If there are *substitutions* in the string, then these substitutions are passed as the next arguments.

**Example:**

```javascript
var name = "Jon";
var mathScore = 10;
var scienceScore = 8;

function func(str, userName, mathS, scienceS) {
  let s1 = str[0];
  let s2 = str[1];
  let s3 = str[2];

  let totalScore = mathS + scienceS;

  return `${userName}${s1}${mathS}${s2}${scienceS}${s3}${totalScore}`;
}

var JonScore = func`${name} has scored ${mathScore} in maths and ${scienceScore} in Science. Thus his total score is = `;

console.log(JonScore);
// Jon has scored 10 in maths and 8 in Science. Thus his total score is = 18`
```

In the above example, the *func* is a tagged function, which is called with the template literal {name} has scorednamehasscored{_**mathScore**_} in maths and ${_**scienceScore**_} in Science. Thus his total score is =.

The *func* function gets called with four arguements: **str**, **userName** ,**mathS**, **scienceS**

The **str** is an array of string elements that is in the literal. // ['has scored ', 'in maths and ', 'in Science. Thus his total score is = ']

The **userName** does takes the value of ${**name**} Similarly **mathS** and **scienceS** will take the values of **mathScore** and **scienceScore** respectively.

The str elements are accessed through their indexed and stored in **s1, s2, s3**.

The function adds these score and stores into a variable totalScore and then returns the expression.

{userName}userName{s1}{mathS}mathS{s2}{scienceS}scienceS{s3}{totalScore}totalScore

Where the values if placeholders are substituted.

---

---

# Raw Strings

_We've already seen how `\n` can be used to change the line of a string. Similarly, we can use other escape sequences to skip lines, spaces, etc._

The **raw** is a property of the first argument of the tagged template that allows us to access the string in the exact same way they were entered (_i.e. the escape sequences like `\n`, `\t` are also simply considered as a string_).

**Example:**

```javascript
function func(str) {
  console.log(str[0]); //This is an example of:
  //  Raw strings

  console.log(str.raw[0]); // This is an example of:\n Raw strings
}

func`This is an example of:\n Raw strings`;
```

In the above example, as we all know in template literals javascript, the first argument of the tagged template in template literals javascript is the array of string values that are passed, the *str* is an array with *This is an example of:\n Raw strings* as its value.

Now, the **str[0]**, will output the string value. While printing the string, it encounters **`\n`** thus, it changes the line and prints the rest of the string.

Similarly, the **str.raw[0]**, will output the string value. While printing the string it encounters the **`\n`** as well, but due to the raw property, it considers the *`\n`* as a string only, thus it doesn’t change the line, prints *`\n`* and keeps printing the string.

---

---

---
