---
layout: post
title: Lesson Summaries for P2
description: Key Takeaways from lessons
courses: {'csp': {'week': 1}}
comments: True
sticky_rank: 1
---

## 3.1 Variables in JavaScript and Python

### JavaScript Variables
- **What**: Containers for data values.
- **Types**:
  - `var`: Function-scoped variable (older way).
  - `let`: Block-scoped variable (preferred for modern use).
  - `const`: Block-scoped constant (cannot be reassigned).
- **Scope**: 
  - Global
  - Local
  - Block-scoped (only within `{ }`).

---

### Python Variables
- **What**: Names that point to values; dynamically typed.
- **Types**: 
  - `int`, `float`, `str`, `bool`
  - Complex types: lists, dictionaries.
- **Scope**:
  - Local
  - Global
  - Nonlocal (within nested functions).
- **Constants**: Typically in uppercase (e.g., `MAX_VALUE`).

---

## 3.2 Data Abstraction in JavaScript and Python

### JavaScript Data Abstraction
- **What**: Hides implementation details; shows only essentials.
- **How**:
  - **Objects**: Group data and methods.
  - **Modules**: Expose public APIs; hide internal workings.
- **Why**: Makes code modular and maintainable.

---

### Python Data Abstraction
- **What**: Similar to JavaScript; hides complex details.
- **How**:
  - **Abstract Base Classes (ABCs)**: Use `abc` module to define abstract methods.
- **Why**: Promotes clean code; focus on high-level logic.

---

### Key Differences
- **Variables**: 
  - JavaScript: Uses `var`, `let`, `const`.
  - Python: Dynamic typing without explicit declaration.
  
- **Data Abstraction**:
  - JavaScript: Objects and modules.
  - Python: Abstract base classes.

## 3.3 Mathematical Expressions in JavaScript and Python

### JavaScript Mathematical Expressions
- **Basic Operators**:
  - `+`: Addition
  - `-`: Subtraction
  - `*`: Multiplication
  - `/`: Division
  - `%`: Modulus (remainder)
  
- **Order of Operations**: 
  - Parentheses first `()`
  - Exponents `**` (use `Math.pow(base, exp)` for power)
  - Multiplication and Division `*`, `/`
  - Addition and Subtraction `+`, `-`
  
- **Increment/Decrement**:
  - `++`: Increment by 1
  - `--`: Decrement by 1

- **Math Object**: 
  - `Math.random()`: Random number
  - `Math.max()`, `Math.min()`: Max/Min values
  - `Math.sqrt()`: Square root

---

### Python Mathematical Expressions
- **Basic Operators**:
  - `+`: Addition
  - `-`: Subtraction
  - `*`: Multiplication
  - `/`: Division (returns float)
  - `//`: Floor division (returns integer)
  - `%`: Modulus (remainder)
  - `**`: Exponentiation (power)

- **Order of Operations**: 
  - Parentheses first `()`
  - Exponents `**`
  - Multiplication and Division `*`, `/`, `//`
  - Addition and Subtraction `+`, `-`
  
- **Built-in Functions**:
  - `abs()`: Absolute value
  - `pow(base, exp)`: Power
  - `min()`, `max()`: Min/Max values
  - `round()`: Rounding

---

### Key Differences
- **Exponentiation**:
  - JavaScript: `Math.pow(base, exp)` or `base ** exp` (ES6+)
  - Python: Use `**` directly.
  
- **Floor Division**:
  - JavaScript: No direct equivalent; use `Math.floor(a / b)` for integer division.
  - Python: Use `//` for floor division.

- **Random Numbers**:
  - JavaScript: `Math.random()`
  - Python: `random.random()` (import `random` module).

## 3.4 Strings in JavaScript and Python

### JavaScript Strings
- **Definition**: A sequence of characters; can be created using:
  - Single quotes: `'Hello'`
  - Double quotes: `"Hello"`
  - Backticks (template literals): `` `Hello` `` (allows multi-line and interpolation).

- **Common Methods**:
  - `.length`: Get string length.
  - `.toLowerCase()`: Convert to lowercase.
  - `.toUpperCase()`: Convert to uppercase.
  - `.substring(start, end)`: Extract a part of the string.
  - `.indexOf(substring)`: Find the position of a substring.
  - `.replace(old, new)`: Replace a substring.

- **Template Literals**: Use backticks for:
  - Multi-line strings.
  - String interpolation: `` `Hello, ${name}` ``.

---

### Python Strings
- **Definition**: A sequence of characters; can be created using:
  - Single quotes: `'Hello'`
  - Double quotes: `"Hello"`
  - Triple quotes: `'''Hello'''` or `"""Hello"""` (allows multi-line).

- **Common Methods**:
  - `len()`: Get string length.
  - `.lower()`: Convert to lowercase.
  - `.upper()`: Convert to uppercase.
  - `.strip()`: Remove whitespace from both ends.
  - `.find(substring)`: Find the position of a substring.
  - `.replace(old, new)`: Replace a substring.

- **F-Strings**: Use for string interpolation (Python 3.6+):
  - Example: `f"Hello, {name}"`.

---

### Key Differences
- **Template Literals**: 
  - JavaScript: Uses backticks for multi-line and interpolation.
  - Python: Uses f-strings or `.format()` method for interpolation.

- **Triple Quotes**:
  - JavaScript: No direct equivalent for multi-line strings; use backticks.
  - Python: Tripl

## 3.5 Booleans in JavaScript and Python

### JavaScript Booleans
- **Definition**: A data type that can be either `true` or `false`.
- **Usage**:
  - Often used in conditional statements (e.g., `if`, `while`).
  - Can be the result of comparison operators:
    - `==`: Equality
    - `!=`: Inequality
    - `===`: Strict equality (checks type and value)
    - `!==`: Strict inequality

- **Truthy and Falsy Values**:
  - **Falsy Values**: `false`, `0`, `""` (empty string), `null`, `undefined`, `NaN`.
  - **Truthy Values**: Everything else (e.g., non-zero numbers, non-empty strings).

- **Logical Operators**:
  - `&&`: Logical AND
  - `||`: Logical OR
  - `!`: Logical NOT

---

### Python Booleans
- **Definition**: A data type that can be either `True` or `False` (note the capitalization).
- **Usage**:
  - Used in conditional statements (e.g., `if`, `while`).
  - Result of comparison operators:
    - `==`: Equality
    - `!=`: Inequality
    - `is`: Identity check

- **Truthy and Falsy Values**:
  - **Falsy Values**: `False`, `0`, `""` (empty string), `None`, empty collections (e.g., `[]`, `{}`).
  - **Truthy Values**: Everything else (e.g., non-zero numbers, non-empty strings).

- **Logical Operators**:
  - `and`: Logical AND
  - `or`: Logical OR
  - `not`: Logical NOT

---

### Key Differences
- **Boolean Literals**:
  - JavaScript: `true`, `false` (lowercase).
  - Python: `True`, `False` (capitalized).

- **Comparison Operators**:
  - JavaScript has str

## 3.6 Conditionals in JavaScript and Python

### JavaScript Conditionals
- **If Statement**:
  ```javascript
  if (condition) {
      // The code which you want to execute goes here :)  
  }

## 3.7 Nested Conditionals in JavaScript and Python

### JavaScript Nested Conditionals
- **Definition**: Conditionals inside another conditional.
  
- **Example**:
  ```javascript
  if (condition1) {
      // when condition one is true. 
      if (condition2) {
          // if condition 2 is true
      } else {
          // code when the second condition is false
      }
  } else {
      // code for when the condiotion is false
  }

## 3.8 Iteration in JavaScript and Python

### JavaScript Iteration
- **For Loop**:
  ```javascript
  for (let i = 0; i < length; i++) {
      // code to execute lol
  }










