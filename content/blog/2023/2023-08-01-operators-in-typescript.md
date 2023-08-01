---
authors: [irtaza]
title: "Operators in TypeScript"
categories: ["Node"]
date: 2023-08-01 00:00:00 +1100
excerpt: "TypeScript is a superset of JavaScript that adds static typing and other features to the language. Its operators are crucial to understanding the language and writing effective code. Operators are symbols or keywords in a programming language that perform operations on values, such as arithmetic operations, string concatenation, and comparisons. Understanding operators in TypeScript is essential because they are fundamental building blocks of the language and are used in almost every programming aspect. By choosing the right operator for the job, you can often simplify your code and make it easier to understand and maintain. In this article, we will explore the most important operators in TypeScript and provide examples of how they can be used in real-world applications to help you write more efficient and readable code."
image: images/stock/0065-java-1200x628-branded.jpg
url: typescript-operators
---

TypeScript is a superset of JavaScript that adds static typing and other features to the language. Its operators are crucial to understanding the language and writing effective code. 

Operators are symbols or keywords in a programming language that perform operations on values, such as arithmetic operations, string concatenation, and comparisons.

**Understanding operators in TypeScript is essential because they are fundamental building blocks of the language and are used in almost every programming aspect.** By choosing the right operator for the job, you can often simplify your code and make it easier to understand and maintain. In this article, we will explore the most important operators in TypeScript and provide examples of how they can be used in real-world applications to help you write more efficient and readable code.

{{% github "https://github.com/thombergs/code-examples/tree/master/nodejs/operators-in-typescript" %}}

# What operators are in Typescript?
In Typescript, **operators are symbols used to perform operations on variables or values.** They can be classified into several categories based on their functions.

## Concatenation Operators
Concatenation operators in TypeScript are used to combine strings and values together. The most common concatenation operator is the plus sign (+). When used with strings, the plus sign combines them into a single string. When used with a string and another data type (other than a string), the plus sign concatenates it to the end of the string.

For example, let's say we have two strings, "Hello" and "World". We can use the concatenation operator to combine them into a single string:

```ts
let greeting = "Hello" + "World";
console.log(greeting);
```
Output:
~~~ts
HelloWorld
~~~

We can also use the concatenation operator to combine a string and a value:

~~~ts
let age = 30;
let message = "I am " + age + " years old.";
console.log(message); 
~~~
Output:
~~~ts
I am 30 years old.
~~~

In this example, the concatenation operator combines the string "I am " with the value of the age variable (30) and the string " years old." to create the final message.

Concatenation operators are useful in situations where we need to build dynamic strings based on values or user input. Using concatenation operators, we can create custom messages or outputs tailored to our specific needs.

## Arithmetic Operators
Arithmetic operators allow us to perform mathematical operations such as addition, subtraction, multiplication, division etc. on numerical values (constants and variables). Let’s take a look at them:

~~~ts
let x = 5;
let y = 10;

console.log(x + y); // Output: 15
console.log(x - y); // Output: -5
console.log(x * y); // Output: 50
console.log(x / y); // Output: 0.5
console.log(y % x); // Output: 0

let z = 3;
z++; 
console.log(z);   // Output: 4

let a = 10;
a--;
console.log(a);   // Output: 9
~~~

- **Addition (`+`):** adds two or more values. The addition operator (+) can also perform string concatenation when used with strings. More information is in the [Concatenation Operators](#concatenation-operators) section.

- **Subtraction (`-`):** subtracts two or more values

- **Multiplication (`*`):** multiplies two or more values, and the precision of the result depends on the data types involved. When multiplying two integers, the result will also be an integer, preserving the whole number portion of the calculation. Similarly, when multiplying two floats, the result will also be a float, retaining the decimal precision. When we multiply an integer by a float or a float by an integer, the result will be a float. In TypeScript, the multiplication operation between an integer and a float promotes the integer to a float and performs the multiplication as a floating-point operation. The resulting value will retain the decimal precision of the float and include any fractional component.

- **Division (`/`):** divides two or more values, and the precision and data type of the result depend on the types of the operands. If we divide two integers, the result will be an integer, and any decimal portion will be truncated. For example, `5 / 2` would result in `2`, as the remainder is discarded. However, if either the numerator or denominator is a float, the result will be a float. Dividing an integer by a float or a float by an integer will yield a float result, preserving decimal precision.

- **Modulus (`%`):** returns the remainder of a division operation.

- **Increment (`++`):** increases the value of the variable by one.

- **Decrement (`--`):** decreases the value of the variable by one.
  
- **If used with non-number variables, with the exception of the `+` operator, TypeScript's compiler will not allow these operations and raise a compilation error.**

## Relational Operators
Relational Operators are used to compare two values and determine their relationship. Let’s take a look at some relational operators commonly used in Typescript:

~~~ts
let x = 10;
let y = 5;

console.log(x == y); // false
console.log(x === "10"); // false (different data types)
console.log(x != y); // true
console.log(x !== "10"); // true (different data types)
console.log(x > y); // true
console.log(x < y); // false
console.log(x >= y); // true
console.log(x <= y); // false
~~~

- **Equality Operator (`==`):** This operator compares two values but doesn't consider their data types. If the values are equal, it returns true. Otherwise, it returns false. When comparing non-number variables with the Equality operator (`==`), it will check their data type. If the non-number variables have different data types, it will attempt to convert them to a common type. For example, if one variable is a string and the other is a number, it will try to convert the string to a number before performing the comparison. The result of the comparison will be true if the converted values are equal, and false otherwise. It's worth noting that using the Equality operator (`==`) for non-numerical variables can lead to unexpected behaviour due to type coercion, and it's generally recommended to use the Strict Equality operator (`===`) for more predictable comparisons.

- **Strict Equality Operator (`===`):** This operator compares two values for equality, and it considers their data types. If the values are equal in value and type, it returns true. Otherwise, it returns false. When comparing non-numerical variables, it performs a strict comparison without type conversion. If the variables have different data types, the comparison returns false. It returns true only when the variables have the same data type and value.

- **Inequality Operator (`!=`):** This operator compares two values for inequality. If the values are not equal, it returns true. Otherwise, it returns false.

- **Strict Inequality Operator (`!==`):** This operator compares two values for inequality, and considers their data types. It returns true if the values are not equal in value or type. Otherwise, it returns false.

- **Greater Than Operator (`>`):** This operator checks if the left operand is greater than the right operand. If it is, it returns true. Otherwise, it returns false. When used with strings, it performs a lexicographical comparison. It checks if the left operand appears after the right operand in lexicographical order. For example, `"apple" > "banana"` would return `false` since "apple" comes before "banana" in lexicographical order.

- **Less Than Operator (`<`):** This operator checks if the left operand is less than the right operand. If it is, it returns true. Otherwise, it returns false. When used with strings, it checks if the left operand appears before the right operand in lexicographical order. For example, `"apple" < "banana"` would return `true` since "apple" comes before "banana" in lexicographical order.

- **Greater Than or Equal To Operator (`>=`):** This operator checks if the left operand is greater than or equal to the right operand. If it is true, it returns true. Otherwise, it returns false. When used with strings, it checks if the left operand is greater than or equal to the right operand. For example, `"apple" >= "banana"` would return `false` since "apple" is not greater than or equal to "banana".

- **Less Than or Equal To Operator (`<=`):** This operator checks if the left operand is less than or equal to the right operand. If it is true, it returns true. Otherwise, it returns false. When used with strings, it checks if the left operand is smaller than or equal to the right operand. For example, `"apple" <= "banana"` would return `true` since "apple" is less than "banana".

### Difference Between Equality and Strict Equality Operator
When it comes to comparing values, it is essential to understand the difference between the equality (`==`) and strict equality (`===`) operators. The equality operator only compares the values of the operands, while the strict equality operator compares both the values and types of the operands. Let’s take a look at this code:

~~~ts
let x = 10;
let y = 5;
let a = "apple";
let b = "banana";

console.log(x == y); // false
console.log(x == 10); // true
console.log(x === y); // false (same type but different value)
console.log(x === "10"); // false (different data types)
console.log(x === 10); // true (same data types and value)
console.log(a == b); // false
console.log(a == "apple"); // true
console.log(a === b); // false (same type but different value)
console.log(a === "apple"); // true (same data types and value)
console.log(a === 10); // false (different data types and value)

~~~

- In the given example, the expression `x == y` returns false because the values of `x` and `y` are not equal.
- The expression `x == 10` returns true because `x` is equal to `10`.
- The expression `x === y` returns false because `x` and `y` are of the same type but of different values.
- The expression `x === '10'` returns false because `x` is a number and `'10'` is a string (i.e. they are of different types).
- Finally, the expression `x === 10` returns true because both `x` and `10` are of the same data type (number) and have the same value.

## Logical Operators

Logical operators in TypeScript allow you to perform logical operations on boolean values. ​​Let's take a look at some Logical Operators:

~~~ts
let x = 5;
let y = 10;
let z = 15;

console.log(x < y && y < z); // true
console.log(x > y || y < z); // true
console.log(!(x > y)); // true
~~~

**AND (`&&`) Operator:** The AND `&&` operator returns true if both operands are true.

**OR (`||`) Operator:** The OR `||` operator returns true if at least one of the operands is true.

**NOT (`!`) Operator:** The NOT `!` operator negates a boolean value, converting true to false and vice versa. 

## Bitwise Operators
Bitwise operators in TypeScript operate on binary representations of numbers. They are useful for performing operations at the binary level, manipulating individual bits, working with flags, or optimizing certain algorithms that require low-level bit manipulations. Understanding their behaviour and how to use them correctly can be valuable when working with binary data or implementing certain advanced programming techniques.

Some of the common bitwise operators include AND (`&`), OR (`|`), XOR (`^`), left shift (`<<`), right shift (`>>`), and complement (`~`). These operators are particularly useful when working with flags, binary data, or performance optimizations. Let’s take a look at them:

~~~ts
let a = 5; // 0101 in binary
let b = 3; // 0011 in binary

console.log(a & b); // 0001 (AND)
console.log(a | b); // 0111 (OR)
console.log(a ^ b); // 0110 (XOR)
console.log(a << 1); // 1010 (Left Shift)
console.log(a >> 1); // 0010 (Right Shift)
console.log(~a); // 1010 (Complement)
~~~

**AND (`&`):** The AND operator, represented by the symbol `&`, performs a logical AND operation between corresponding bits of two numbers. The result is a new number where each bit is set to 1 only if both bits in the same position of the operands are 1.

**OR (`|`):** The OR operator, represented by the symbol `|`, performs a logical OR operation between corresponding bits of two numbers. The result is a new number where each bit is set to 1 if at least one of the bits in the same position of the operands is 1.

**XOR (`^`):** The XOR operator, represented by the symbol `^`, performs a logical exclusive OR operation between corresponding bits of two numbers. The result is a new number where each bit is set to 1 only if one of the bits in the same position of the operands is 1, but not both.

**Left Shift (`<<`):** The left shift operator, represented by the symbol `<<`, shifts the binary bits of a number to the left by a specified number of positions. The leftmost bits are discarded, and new zeros are added on the right side. Each shift to the left doubles the value of the number.

**Right Shift (`>>`):** The right shift operator, represented by the symbol `>>`, shifts the binary bits of a number to the right by a specified number of positions. The rightmost bits are discarded, and new zeroes are added on the left side. For positive numbers, each shift to the right halves the value of the number.

**Complement (`~`):** The complement operator, represented by the symbol `~`, performs a bitwise NOT operation on a number, flipping all its bits. This operator effectively changes each 0 to 1 and each 1 to 0.

# Conclusion
By mastering the usage of these operators and applying best practices, you can enhance your TypeScript programming skills and develop more effective solutions. Whether you're working on small-scale projects or large-scale applications, a solid understanding of operators will contribute to your success in writing maintainable and performant code.

You can find all the code used in this article on [GitHub](https://github.com/thombergs/code-examples/tree/master/nodejs/operators-in-typescript).


