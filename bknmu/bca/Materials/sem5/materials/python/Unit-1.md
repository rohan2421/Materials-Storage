# 📚 BCA Semester - 5

## 🐍 Python Programming

> **Subject Code:** BCA-501  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 5

---

# 📑 Unit 1 : Introduction to Python

## _Topics_

- Python History, Features & Installation
- Introduction to Python IDLE
- Basic Syntax
- Indentation
- Reserved Words
- Naming Conventions
- Python Variables
- Literals
- Operators
- Comments
- Input and Output
- `print()` Function
- Python Conditional Statements
  - if Statement
  - if...else Statement
  - Nested if Statement
  - elif Ladder
- Python Looping Statements
  - for Loop
  - while Loop
  - Nested Loops
- Python Functions
  - Defining Functions
  - Function Arguments
  - Return Statement
  - Recursive Functions
- Python Modules
  - Creating Modules
  - Importing Modules
  - Built-in Modules
  - User Defined Modules

---

## 1. Python History, Features & Installation

### Introduction to Python

Python is a popular high-level, general-purpose, interpreted programming language known for its simple English-like syntax, readability, and power.
Python is widely used in:

- Web Development (Django, Flask, FastAPI)
- Desktop GUI Applications (Tkinter, PyQt)
- Data Science & Analytics (Pandas, NumPy)
- Machine Learning & AI (TensorFlow, PyTorch)
- Automation & Scripting
- Game Development
- Cyber Security (Penetration testing scripts)
- Cloud Computing & DevOps

### What is Python?

**Definition:** Python is a high-level, interpreted, object-oriented, and general-purpose programming language designed to be easy to learn and use.

- **High-level:** Hides complex hardware details and memory management.
- **Interpreted:** Executed line-by-line by the Python Interpreter.
- **Object-oriented:** Supports classes, objects, inheritance, polymorphism, encapsulation, etc.
- **General-purpose:** Can be used to build almost any type of application.

**Simple Example:**

```python
print("Hello World")
```

**Output:**

```text
Hello World
```

### History of Python

#### Who Developed Python?

Python was created by **Guido van Rossum** in the late 1980s.

#### Why Python Was Created?

During the late 1980s, popular programming languages like C, C++, and Pascal were powerful but complex and hard to learn. Guido van Rossum wanted a language that was simple, readable, easy to learn, yet powerful enough for general scripting.

#### Development Timeline

- **1989:** Work on Python started at Centrum Wiskunde & Informatica (CWI) in the Netherlands.
- **1991:** The first public version, Python 0.9.0, was released, featuring classes, functions, modules, exception handling, etc.
- **2000:** Python 2.0 was released, introducing garbage collection, Unicode support, and list comprehensions.
- **2008:** Python 3.0 was released, bringing major improvements, modern syntax, and better Unicode support (but it was not backward compatible with Python 2.x).
- **Present Day:** Python is maintained by the Python Software Foundation (PSF) and remains one of the world's top languages.

#### Why Is It Called Python?

The name "Python" was not named after the snake. Guido van Rossum was a fan of the British comedy show **"Monty Python's Flying Circus"** and decided to use the name "Python" because it was short, unique, and slightly mysterious.

#### Evolution of Python

```text
1989  → Development Started
1991  → Python 0.9.0 Released
2000  → Python 2.0 Released
2008  → Python 3.0 Released
Today → Python 3.x Series (Maintained by PSF)
```

### Features of Python

1. **Simple and Easy to Learn:** Python syntax is simple, clean, and resembles English.
   _Example:_
   ```python
   if age >= 18:
       print("Eligible")
   ```
2. **High-Level Language:** Developers do not need to worry about memory management, garbage collection, or pointer arithmetic.
3. **Interpreted Language:** Python code is compiled to bytecode and executed line-by-line by the Python Interpreter. No separate compilation step is needed.
4. **Object-Oriented Language:** Supports modular OOP design using Classes, Objects, Inheritance, etc.
5. **Platform Independent / Portable:** Write once, run anywhere. The same Python script runs on Windows, macOS, and Linux.
6. **Open Source:** Python is free to use, modify, and distribute.
7. **Dynamically Typed:** Variable types are declared automatically at runtime.
8. **Large Standard Library:** Provides pre-built modules for math, file I/O, database connections, and networking.
9. **Extensible:** You can easily integrate C/C++ or Java code into Python.
10. **Database Support:** Has built-in interfaces to connect with MySQL, Oracle, PostgreSQL, SQLite, and MongoDB.
11. **Huge Community Support:** Millions of developers globally share code, packages (via PyPI), and solutions.

### Applications of Python

- **Web Development:** Built using frameworks like Django, Flask, and FastAPI.
- **Data Science & Analytics:** Processing data using NumPy, Pandas, and Matplotlib.
- **Artificial Intelligence & ML:** Training models using TensorFlow, Keras, and PyTorch.
- **Automation & Scripting:** Automating file operations, web scraping, and cron tasks.
- **Desktop Apps:** Built using Tkinter or PyQt libraries.
- **Cybersecurity:** Used for network scanning, exploit scripts, and malware analysis.

### Advantages and Limitations of Python

**Advantages:**

- Easy to read, write, and maintain.
- Highly productive (fewer lines of code than C/C++ or Java).
- Dynamic, extensible, and portable.
- Vast collection of third-party libraries.

**Limitations:**

- **Execution Speed:** Slower than compiled languages like C or C++ because it is interpreted.
- **Memory Usage:** Consumes more memory due to dynamic typing and garbage collection.
- **Mobile Development:** Not ideal or widely used for mobile applications.

### Installation of Python

#### Step-by-Step Guide

1. **Download:** Visit the official website: `https://www.python.org` and download the installer for your OS.
2. **Add to PATH:** Run the installer and **MUST** check the option **"Add Python to PATH"** before clicking install.
   - _Why?_ Adding Python to PATH allows you to run Python commands from the Command Prompt/Terminal.
3. **Install Now:** Click "Install Now" to finish installation.
4. **Verify:** Open Command Prompt and type:
   ```cmd
   python --version
   ```
   If verified, it outputs `Python 3.x.x`. You can also verify `pip` (package manager) using `pip --version`.

---

## 2. Introduction to Python IDLE

### What is IDLE?

IDLE stands for **Integrated Development and Learning Environment**. It is Python's default IDE and is automatically installed with Python on Windows.

### Purpose of IDLE

IDLE provides a simple environment for beginners to write, run, test, and debug Python scripts.

### Features of Python IDLE

- **Syntax Highlighting:** Displays keywords, strings, comments, and variables in different colors for readability.
- **Interactive Shell:** A prompt (`>>>`) that runs Python code immediately upon pressing Enter.
- **Script Editor:** A text editor to write, save (as `.py`), and run complete scripts.
- **Auto-Indentation:** Automatically indents blocks of code.
- **Debugger:** Built-in support to run code step-by-step to find bugs.

### How to Open IDLE

- **Method 1:** Open Windows Start Menu, search for **IDLE (Python 3.x)**, and click it.
- **Method 2:** Open Command Prompt and type `idle` (if Python is added to PATH).

### Python IDLE Interface

IDLE starts with the **Python Shell** by default. To write a script, go to `File -> New File` to open the **Script Editor Window**.

### Python Shell (Interactive Mode)

The Python Shell shows the command prompt:

```python
>>>
```

This is the **Python Prompt**. Any command typed here executes immediately.
_Example:_

```python
>>> 5 + 10
15
```

### Script Mode

For writing larger, multi-line programs, use the Script Mode.

1. Open IDLE, go to `File -> New File`.
2. Write your code:
   ```python
   name = "Rohan"
   print(name)
   ```
3. Save the file with a `.py` extension (e.g. `student.py`) using `File -> Save` or `Ctrl + S`.
4. Run the program by pressing **F5** or going to `Run -> Run Module`.
5. The output is displayed in the Python Shell window:
   ```text
   Rohan
   ```

### Interactive Mode vs Script Mode

| Feature         | Interactive Mode (`>>>`)               | Script Mode (`.py`)            |
| :-------------- | :------------------------------------- | :----------------------------- |
| **Execution**   | Code runs line-by-line immediately     | Runs the entire file at once   |
| **Saving Code** | Cannot save code for future use        | Code is saved in a `.py` file  |
| **Best For**    | Quick testing, learning, and debugging | Building complete applications |
| **Editing**     | Hard to edit previous lines            | Easy to edit and re-run        |

### Creating Your First Python Program

**Using Shell:**

```python
>>> print("Welcome to Python")
Welcome to Python
```

**Using Script Editor:**
Create `hello.py` and write:

```python
print("Welcome to Python")
```

Run using **F5**. Output:

```text
Welcome to Python
```

---

## 3. Basic Syntax of Python

### What is Syntax?

Syntax refers to the set of rules that define how Python programs must be written. Just like grammar in human languages, if syntax rules are violated, a **SyntaxError** is thrown.

**Correct Syntax:**

```python
print("Hello World")
```

**Incorrect Syntax (Missing Parentheses):**

```python
print "Hello World"
# Output: SyntaxError: Missing parentheses in call to 'print'
```

### Characteristics of Python Syntax

- **Simplicity:** Very clean, readable, and uses simple English keywords.
- **No Semicolons Required:** Unlike C/C++/Java, lines in Python do not end with semicolons (though they are optional).
- **Case Sensitivity:** Python is case-sensitive. `age`, `Age`, and `AGE` are treated as three completely different identifiers.
  ```python
  name = "Rohan"
  print(name)  # Works
  print(Name)  # Throws NameError: name 'Name' is not defined
  ```

### Python Program Structure

A Python program consists of statements, indentation, variables, comments, and blocks.

### Python Statements

A statement is an instruction given to Python.

- **Single-Line Statement:**
  ```python
  x = 10
  ```
- **Semicolon Usage:** You can put multiple statements on a single line using semicolons, though it is not recommended by PEP 8.
  ```python
  x = 10; y = 20; print(x + y)  # Valid but discouraged
  ```

### String Values in Python

Strings can be enclosed in single quotes (`'`), double quotes (`"`), or triple quotes (`'''` or `"""`).

- **Single/Double Quotes:** Used for single-line strings.
  ```python
  s1 = 'Hello'
  s2 = "World"
  ```
- **Triple Quotes:** Used for multi-line strings or docstrings.
  ```python
  s3 = """This is a
  multi-line string."""
  ```

### Python Blocks (Code Blocks)

In other languages like C, Java, or C++, code blocks are defined using curly braces `{}`. In Python, blocks are defined entirely using **Indentation**.

```python
if True:
    print("Inside Block")
```

---

## 4. Indentation in Python

### What is Indentation?

Indentation refers to the leading spaces (whitespace) at the beginning of a line of code. In Python, indentation is not just for readability; it is a syntax requirement used to define the scope and structure of code blocks (like functions, loops, conditions, and classes).

### Why Indentation is Important?

In languages like C or Java, braces are used:

```c
if (x > 0) {
    printf("Positive");
}
```

In Python, braces are replaced by a colon (`:`) and indentation:

```python
if x > 0:
    print("Positive")
```

### Indentation Example

```python
if True:
    print("Line 1 of block")
    print("Line 2 of block")
print("Outside the block")
```

**Output:**

```text
Line 1 of block
Line 2 of block
Outside the block
```

### Incorrect Indentation

If indentation is missing or inconsistent, Python will throw an **IndentationError**.

```python
if True:
print("Hello")  # IndentationError: expected an indented block
```

### Nested Indentation

Each nested block must be indented further.

```python
if True:
    print("Outer block")
    if True:
        print("Inner block")
```

### Recommended Indentation (PEP 8)

PEP 8 recommends using **4 spaces** per indentation level. Do not mix tabs and spaces as it can lead to hard-to-detect errors.

### Indentation in Loops, Functions, and Classes

**Loops:**

```python
for i in range(3):
    print(i)  # Indented
```

**Functions:**

```python
def greet():
    print("Hello")  # Indented
```

**Classes:**

```python
class Student:
    pass  # Indented
```

### Advantages of Indentation

- **Better Readability:** Code has a uniform visual structure.
- **Cleaner Structure:** No cluttered braces.
- **Less Syntax:** Fewer characters to type.
- **Consistency:** Forces all programmers to write neatly formatted code.

---

## 5. Reserved Words (Keywords)

### What are Reserved Words?

Reserved words (or **Keywords**) are special words that have predefined, fixed meanings in Python. They form the vocabulary of the language and cannot be used as variable names, function names, class names, or any other user-defined identifiers.

**Incorrect Usage:**

```python
if = 10
# Output: SyntaxError: invalid syntax
```

### Characteristics of Reserved Words

- **Predefined Meaning:** Already built into Python.
- **Case Sensitive:** Must be written exactly as defined (e.g. `True` starts with capital T, `and` is lowercase).
- **Cannot be modified.**

### List of Python Reserved Words

Python has around 35 keywords. Some common ones:
`False`, `None`, `True`, `and`, `as`, `assert`, `break`, `class`, `continue`, `def`, `del`, `elif`, `else`, `except`, `finally`, `for`, `from`, `global`, `if`, `import`, `in`, `is`, `lambda`, `nonlocal`, `not`, `or`, `pass`, `raise`, `return`, `try`, `while`, `with`, `yield`.

### Commonly Used Reserved Words

- **Conditional:** `if`, `else`, `elif` (used for making decisions).
- **Loops:** `for`, `while` (used for repeating code).
- **Loop Controls:** `break`, `continue` (controls loop execution).
- **Structure:** `def` (define function), `return` (exit function), `class` (define class).
- **Imports:** `import`, `from` (importing modules).
- **Exception Handling:** `try`, `except`, `finally` (handling errors).
- **Null/No-op:** `pass` (used as a placeholder statement).

### Checking Python Keywords Programmatically

You can list all keywords in Python using the `keyword` module:

```python
import keyword
print(keyword.kwlist)
```

### Difference Between Keywords and Identifiers

| Feature          | Keywords             | Identifiers                             |
| :--------------- | :------------------- | :-------------------------------------- |
| **Meaning**      | Predefined by Python | Defined by the programmer               |
| **Purpose**      | Syntax structure     | Name of variables, functions, etc.      |
| **Modification** | Cannot be changed    | Can be named anything (following rules) |
| **Examples**     | `if`, `for`, `class` | `name`, `age`, `student_record`         |

---

## 6. Naming Conventions in Python

### Introduction

Naming conventions are recommended guidelines for naming variables, functions, classes, modules, and constants. Following these rules makes your code clean, readable, and professional. Python's official styling guide is **PEP 8**.

### Why Naming Conventions Are Important?

- Improves readability for team members.
- Helps in identifying what an identifier represents (e.g., classes vs variables).
- Makes code maintenance easier.

### Rules for Naming Identifiers

1. **Valid Characters:** Can contain letters (A-Z, a-z), digits (0-9), and underscore (`_`).
2. **No Digits at the Start:** Cannot start with a digit.
   - `student1` is valid.
   - `1student` is invalid.
3. **No Keywords:** Cannot use Python keywords.
4. **Case Sensitive:** `temp` and `TEMP` are different variables.
5. **No Special Symbols:** Cannot use symbols like `@`, `$`, `%`, etc.

### PEP 8 Naming Conventions

- **Variables:** Use lowercase with words separated by underscores (`snake_case`).
  _Example:_ `student_name`, `total_marks`
- **Functions:** Same as variables (`snake_case`).
  _Example:_ `calculate_average()`, `display_data()`
- **Classes:** Use capital letters for the start of each word without spaces (`PascalCase` or `CamelCase`).
  _Example:_ `StudentRecord`, `DatabaseConnection`
- **Constants:** Use all capital letters with underscores (`UPPER_CASE`).
  _Example:_ `PI = 3.14159`, `MAX_LIMIT = 100`
- **Modules & Packages:** Short, lowercase names. Underscores can be used if it improves readability.
  _Example:_ `math.py`, `utilities.py`

### Good vs Bad Examples

- **Good:** `student_age`, `calculate_sum()`, `MAX_SPEED`
- **Bad:** `a`, `data1`, `temp_var_xyz`, `1_number`

### Advantages of Naming Conventions

- **Readability:** Easy to read.
- **Maintenance:** Easier to update.
- **Consistency:** Fits standard Python codes globally.

---

## 7. Python Variables

Variables represent reserved memory locations used to store values. In Python, variables do not require explicit declaration to reserve memory space; the declaration happens automatically when a value is assigned to a variable.

### What is a Variable?

A variable is a named container that references a memory location where data is stored.

- Unlike other statically-typed programming languages (like C, C++, or Java), in Python, variables do not have a fixed data type.
- A variable is created the moment you first assign a value to it using the assignment operator (`=`).

### Dynamic Typing in Python

Python is a dynamically-typed language. This means:

1. You do not need to specify the data type (like `int`, `float`, `str`) when declaring a variable.
2. The data type of a variable is determined automatically at runtime based on the value it holds.
3. The same variable can hold values of different data types at different times.

**Example:**

```python
# Dynamically typed assignment
x = 10       # x is automatically an integer
print(x)

x = "Hello"  # x is now a string
print(x)
```

### Object Reference & Memory Allocation

In Python, variables are references pointing to objects in memory, not the actual values themselves.

- When you write `y = 10`, Python creates an integer object `10` in memory and makes the variable `y` point to it.
- If you write `z = y`, both `y` and `z` point to the same memory location of the object `10`.

### Multiple Assignments

Python allows you to assign a single value to multiple variables simultaneously, or assign multiple values to multiple variables in a single line.

**Assigning a single value to multiple variables:**

```python
a = b = c = 100
print(a)  # Output: 100
print(b)  # Output: 100
print(c)  # Output: 100
```

**Assigning multiple values to multiple variables:**

```python
roll_no, name, percentage = 24, "Rohan", 85.5
print(roll_no)    # Output: 24
print(name)       # Output: "Rohan"
print(percentage) # Output: 85.5
```

---

## 8. Literals in Python

Literals are raw data or values represented directly in the source code. They are constants assigned to variables.

### Types of Literals in Python

#### 1. Numeric Literals

Numeric literals are immutable (unchangeable) and belong to three distinct types:

- **Integers (int):** Whole numbers without fractional parts (e.g., `10`, `-50`, `1000`).
- **Floating Point Numbers (float):** Numbers containing decimal points or exponent symbols (e.g., `3.14`, `-0.005`, `1.5e2`).
- **Complex Numbers (complex):** Written in the form `a + bj`, where `a` is the real part and `b` is the imaginary part (e.g., `3 + 4j`).

**Example:**

```python
integer_literal = 200
float_literal = 98.6
complex_literal = 1 + 2j
```

#### 2. String Literals

String literals are created by enclosing text in quotes.

- **Single Line Strings:** Enclosed in single quotes (`'`) or double quotes (`"`).
- **Multi-line Strings:** Enclosed in triple quotes (`'''` or `"""`). These can span multiple lines and preserve all newlines and formatting.

**Example:**

```python
single_line = "Welcome to Python"
multi_line = """This is a
multi-line string literal
that spans across lines."""
```

#### 3. Boolean Literals

There are exactly two boolean literals in Python:

- `True` (represents logical true / active)
- `False` (represents logical false / inactive)

**Example:**

```python
is_active = True
has_finished = False
```

#### 4. Special Literals (None)

Python has one special literal: `None`.

- It is used to define a null variable or void value.
- It indicates the absence of a value or that a variable has not been initialized with anything meaningful yet.

**Example:**

```python
value = None
```

#### 5. Literal Collections

Python supports literal representations for various built-in collections:

- **List Literals:** Ordered, mutable values enclosed in square brackets `[]`.
- **Tuple Literals:** Ordered, immutable values enclosed in parentheses `()`.
- **Dictionary Literals:** Key-value pairs enclosed in curly braces `{}`.
- **Set Literals:** Unordered unique values enclosed in curly braces `{}`.

**Example:**

```python
fruits_list = ["Apple", "Banana", "Cherry"]
coordinates_tuple = (12.5, 45.8)
student_dict = {"name": "Rohan", "age": 20}
unique_numbers_set = {1, 2, 3, 3, 2, 1} # Becomes {1, 2, 3}
```

---

## 9. Operators in Python

Operators are special symbols used to perform operations on variables and values (operands).

### Types of Operators in Python

Python provides the following types of operators:

1. **Arithmetic Operators**
2. **Assignment Operators**
3. **Comparison (Relational) Operators**
4. **Logical Operators**
5. **Bitwise Operators**
6. **Membership Operators**
7. **Identity Operators**

### 1. Arithmetic Operators

Used to perform standard mathematical calculations.
| Operator | Name | Example (a=10, b=3) | Result |
| :---: | :--- | :--- | :--- |
| `+` | Addition | `a + b` | `13` |
| `-` | Subtraction | `a - b` | `7` |
| `*` | Multiplication | `a * b` | `30` |
| `/` | Division | `a / b` | `3.3333...` |
| `%` | Modulus (Remainder) | `a % b` | `1` |
| `//` | Floor Division (Integer Div) | `a // b` | `3` |
| `**` | Exponent (Power) | `a ** b` | `1000` |

### 2. Assignment Operators

Used to assign values to variables, often combining an operation with assignment (compound assignments).
| Operator | Example | Equivalent To |
| :---: | :--- | :--- |
| `=` | `x = 5` | `x = 5` |
| `+=` | `x += 3` | `x = x + 3` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 3` | `x = x * 3` |
| `/=` | `x /= 3` | `x = x / 3` |
| `%=` | `x %= 3` | `x = x % 3` |
| `//=` | `x //= 3` | `x = x // 3` |
| `**=` | `x **= 3` | `x = x ** 3` |

### 3. Comparison Operators

Used to compare two values. The result is always a Boolean value (`True` or `False`).
| Operator | Name | Example (x=10, y=20) | Result |
| :---: | :--- | :--- | :--- |
| `==` | Equal | `x == y` | `False` |
| `!=` | Not Equal | `x != y` | `True` |
| `>` | Greater Than | `x > y` | `False` |
| `<` | Less Than | `x < y` | `True` |
| `>=` | Greater Than or Equal To | `x >= y` | `False` |
| `<=` | Less Than or Equal To | `x <= y` | `True` |

### 4. Logical Operators

Used to combine conditional statements.

- **`and` Operator:** Returns `True` if both statements are true.
  ```python
  x = 5
  print(x > 3 and x < 10)  # Output: True
  ```
- **`or` Operator:** Returns `True` if at least one statement is true.
  ```python
  x = 5
  print(x > 3 or x < 2)    # Output: True
  ```
- **`not` Operator:** Reverse the result; returns `False` if the result is true.
  ```python
  x = 5
  print(not(x > 3))        # Output: False
  ```

### 5. Bitwise Operators

Used to perform operations on binary numbers (bit level).
| Operator | Name | Description | Example (a=5 (0101), b=3 (0011)) |
| :---: | :--- | :--- | :--- |
| `&` | Bitwise AND | Sets each bit to 1 if both bits are 1 | `a & b` -> `1` (0001) |
| `|` | Bitwise OR | Sets each bit to 1 if one of the bits is 1 | `a | b` -> `7` (0111) |
| `^` | Bitwise XOR | Sets each bit to 1 if only one of the bits is 1 | `a ^ b` -> `6` (0110) |
| `~` | Bitwise NOT | Inverts all the bits | `~a` -> `-6` |
| `<<` | Zero fill left shift | Shift left by pushing zeros in from the right | `a << 1` -> `10` (1010) |
| `>>` | Signed right shift | Shift right by pushing copies of the leftmost bit | `a >> 1` -> `2` (0010) |

### 6. Membership Operators

Used to test if a sequence (like a string, list, or tuple) is present in an object.

- **`in` Operator:** Returns `True` if the specified value is present.
  ```python
  fruits = ["apple", "banana"]
  print("apple" in fruits)      # Output: True
  ```
- **`not in` Operator:** Returns `True` if the specified value is not present.
  ```python
  fruits = ["apple", "banana"]
  print("cherry" not in fruits)  # Output: True
  ```

### 7. Identity Operators

Used to compare the objects, not if they are equal, but if they are actually the same object pointing to the same memory location.

- **`is` Operator:** Returns `True` if both variables point to the same object.
  ```python
  x = ["apple", "banana"]
  y = ["apple", "banana"]
  z = x
  print(x is z)  # Output: True
  print(x is y)  # Output: False (even though they have the same content)
  ```
- **`is not` Operator:** Returns `True` if both variables do not point to the same object.
  ```python
  print(x is not y)  # Output: True
  ```

### Operator Precedence & Associativity

Operator precedence determines the grouping of terms in an expression and decides how an expression is evaluated.

```text
Highest Precedence
  1. Parentheses: ()
  2. Exponentiation: **
  3. Unary positive/negative/NOT: +x, -x, ~x
  4. Multiplication, Division, Modulus, Floor Division: *, /, %, //
  5. Addition and Subtraction: +, -
  6. Bitwise Shift: <<, >>
  7. Bitwise AND: &
  8. Bitwise XOR/OR: ^, |
  9. Comparison, Identity, Membership: ==, !=, >, <, >=, <=, is, is not, in, not in
  10. Logical NOT: not
  11. Logical AND: and
  12. Logical OR: or
Lowest Precedence
```

---

## 10. Comments in Python

Comments are lines of code that Python ignores during execution. They are written to explain the logic of the code, make it readable, and document details for other developers.

### Why Use Comments?

- **Code Readability:** Explains why a block of code was written.
- **Debugging:** Temporarily disables lines of code during testing.
- **Documentation:** Helps team members understand complex logic easily.

### Types of Comments

#### 1. Single-Line Comments

Single-line comments start with the hash symbol (`#`). Everything after the `#` symbol on that line is treated as a comment.

**Example:**

```python
# This is a single-line comment
print("Hello World")  # This prints a greeting message
```

#### 2. Multi-Line Comments

Python does not have a dedicated syntax for multi-line comments. However, they can be implemented in two ways:

- **Multiple Hash Symbols:** Writing `#` at the start of each line. (Highly recommended by PEP 8).
- **Triple-Quoted String Literals (Docstrings):** Unassigned multi-line strings using `"""` or `'''`. Since they are not assigned to variables, Python reads them and ignores them.

**Example using multiple hash symbols:**

```python
# This is line 1 of the comment
# This is line 2 of the comment
# Explaining the math formula below
area = 3.14 * r * r
```

**Example using docstrings:**

```python
"""
This is a multi-line comment.
It is treated as a string literal by Python,
but since it is not assigned to a variable,
it is ignored during program execution.
"""
print("Multi-line comment example")
```

### Docstrings (Documentation Strings)

Docstrings are a special type of multi-line comment used inside modules, classes, functions, or methods to document their purpose.

- Unlike normal comments, docstrings are stored by Python in the `__doc__` attribute and can be accessed dynamically.
- They must be placed as the very first line of a function, class, or module.

**Example:**

```python
def square(num):
    """This function returns the square of the input number."""
    return num * num

# Accessing docstring using __doc__
print(square.__doc__)
# Output: This function returns the square of the input number.
```

---

## 11. Input and Output in Python

Any software program needs to interact with users. This is done by taking data from users (Input) and presenting results to users (Output).

### Python Output: print() Function

The `print()` function is used to output text, variables, or expressions to the screen.

- E.g., `print("Welcome")` displays `Welcome`.
- _(See the next major section for a highly detailed explanation of all parameters like `sep`, `end`, f-strings, and string formatting.)_

### Python Input: input() Function

To accept user input at runtime, Python provides the built-in `input()` function.

**Syntax:**

```python
variable_name = input("Prompt Message: ")
```

#### Crucial Note: input() Always Returns a String

Regardless of what the user inputs (numbers, characters, symbols), the `input()` function always converts the input into a string (`str`).

**Example:**

```python
age = input("Enter your age: ")
print(type(age)) # Output: <class 'str'>
# Trying mathematical operations directly on age will raise a TypeError!
# E.g., print(age + 5) will raise a TypeError
```

### Typecasting Input Values

To perform mathematical or logic calculations on user inputs, you must explicitly convert the input string to the desired data type. This process is called typecasting.

- **Convert to Integer:** Use `int()`
- **Convert to Float:** Use `float()`
- **Evaluate Expression Directly:** Use `eval()`

**Example - Integer Input:**

```python
# Convert input string to integer
age = int(input("Enter age: "))
print("Age next year:", age + 1)
```

**Example - Float Input:**

```python
# Convert input string to decimal float
price = float(input("Enter product price: "))
discount = price * 0.10
print("Discount amount:", discount)
```

**Example - Dynamic Evaluation with eval():**
The `eval()` function parses the input string and evaluates it as a Python expression or data type automatically.

```python
# eval automatically converts input '10.5' to float, '[1,2,3]' to list, etc.
data = eval(input("Enter expression or value: "))
print(type(data))
```

### Taking Multiple Inputs in One Line

You can accept multiple inputs in a single line using the `split()` string method. By default, it splits inputs based on spaces.

**Example:**

```python
# Accept first and last name in one go
first_name, last_name = input("Enter first and last name (space-separated): ").split()
print("First Name:", first_name)
print("Last Name:", last_name)

# Accept multiple integers in one line using list comprehension
x, y, z = [int(i) for i in input("Enter three space-separated numbers: ").split()]
print("Sum:", x + y + z)
```

---

## 12. print() Function in Python

### Introduction

# What is print() Function?

#### Definition

The `print()` function is a built-in Python function used to display output on the screen.

#### Simple Definition

Whatever value is passed inside `print()`, Python displays it on the output screen.

### Syntax

```python
print(value)
```

or

```python
print(object1, object2, object3, ...)
```

### Flow of print()

```text
Data
  ↓
print()
  ↓
Screen Output
```

### Basic Example

```python
print("Hello World")
```

Output:

```text
Hello World
```

### Printing Numbers

```python
print(100)
```

Output:

```text
100
```

### Printing Decimal Numbers

```python
print(25.75)
```

Output:

```text
25.75
```

### Printing Boolean Values

```python
print(True)
```

Output:

```text
True
```

### Printing Variables

Variables can be displayed using `print()`.

Example:

```python
name = "Rohan"

print(name)
```

Output:

```text
Rohan
```

### Printing Multiple Variables

```python
name = "Rohan"
age = 20

print(name, age)
```

Output:

```text
Rohan 20
```

### Multiple Values in print()

You can display multiple values at the same time.

Example:

```python
print("Name:", "Rohan", "Age:", 20)
```

Output:

```text
Name: Rohan Age: 20
```

### Default Separator

When multiple values are printed, Python automatically inserts a space.

Example:

```python
print("A", "B", "C")
```

Output:

```text
A B C
```

### sep Parameter

The `sep` parameter changes the separator between values.

Syntax:

```python
print(value1, value2, sep="separator")
```

#### Example

```python
print("A", "B", "C", sep="-")
```

Output:

```text
A-B-C
```

#### Example

```python
print("2026", "06", "10", sep="/")
```

Output:

```text
2026/06/10
```

### end Parameter

Normally, `print()` moves the cursor to the next line after printing.

Example:

```python
print("Hello")
print("Python")
```

Output:

```text
Hello
Python
```

#### Using end Parameter

Syntax:

```python
print(value, end="text")
```

#### Example

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

#### Example

```python
print("A", end="-")
print("B")
```

Output:

```text
A-B
```

### Printing Strings

Strings can be displayed using single or double quotes.

Example:

```python
print("Python")
```

Output:

```text
Python
```

#### Example

```python
print('Programming')
```

Output:

```text
Programming
```

### Printing Special Characters

#### New Line (\n)

```python
print("Hello\nPython")
```

Output:

```text
Hello
Python
```

#### Tab Space (\t)

```python
print("Name\tAge")
```

Output:

```text
Name    Age
```

#### Backslash (\\)

```python
print("C:\\Python")
```

Output:

```text
C:\Python
```

### Printing Expressions

Python can calculate expressions inside `print()`.

Example:

```python
print(10 + 20)
```

Output:

```text
30
```

#### Example

```python
print(5 * 6)
```

Output:

```text
30
```

### Printing Variable and Text Together

Example:

```python
name = "Rohan"

print("My Name is", name)
```

Output:

```text
My Name is Rohan
```

### String Concatenation with print()

Example:

```python
name = "Rohan"

print("Hello " + name)
```

Output:

```text
Hello Rohan
```

### Formatted Output Using f-Strings

Python provides f-strings for professional output formatting.

Syntax:

```python
f"text {variable}"
```

#### Example

```python
name = "Rohan"
age = 20

print(f"My Name is {name}")
print(f"My Age is {age}")
```

Output:

```text
My Name is Rohan
My Age is 20
```

#### Example

```python
a = 10
b = 20

print(f"Sum = {a+b}")
```

Output:

```text
Sum = 30
```

### Printing Different Data Types

```python
name = "Rohan"
age = 20
salary = 25000.50
student = True

print(name)
print(age)
print(salary)
print(student)
```

Output:

```text
Rohan
20
25000.5
True
```

### Nested print()

Example:

```python
print(print("Hello"))
```

Output:

```text
Hello
None
```

Explanation:

```text
Inner print() executes first.
Outer print() prints returned value.
```

Since `print()` returns:

```python
None
```

the output contains `None`.

### Real-Life Example

Student Information Program

```python
name = "Rohan"
course = "BCA"
semester = 1

print("Student Information")
print("------------------")
print("Name :", name)
print("Course :", course)
print("Semester :", semester)
```

Output:

```text
Student Information
------------------
Name : Rohan
Course : BCA
Semester : 1
```

### Common Mistakes

#### Missing Quotes

Wrong:

```python
print(Hello)
```

Output:

```text
NameError
```

Correct:

```python
print("Hello")
```

#### Missing Parentheses

Wrong:

```python
print "Hello"
```

Output:

```text
SyntaxError
```

Correct:

```python
print("Hello")
```

### Advantages of print()

#### Easy Output Display

#### Useful for Learning

#### Helps in Debugging

#### Supports Multiple Data Types

#### Supports Formatting

### Interview Questions

#### What is print() Function?

The `print()` function is used to display output on the screen.

#### Is print() Built-in?

```text
Yes
```

It is a built-in Python function.

#### What is the Default Separator in print()?

```text
Space
```

#### Which Parameter Changes Separator?

```python
sep
```

#### Which Parameter Prevents New Line?

```python
end
```

#### What Does print() Return?

```python
None
```

#### How to Print Multiple Values?

```python
print(a, b, c)
```

### Summary

The `print()` function is used to display information on the screen.

Basic Syntax:

```python
print(value)
```

Important Features:

```text
Display Text
Display Numbers
Display Variables
Display Expressions
Multiple Values
Formatted Output
```

Useful Parameters:

```python
sep
end
```

Examples:

```python
print("Hello")

print(10)

print(name)

print("A", "B", sep="-")

print("Hello", end=" ")
```

The `print()` function is one of the most important functions in Python because it allows programmers to display results, debug programs, and interact with users effectively.

## 13. Python Conditional Statements

Conditional Statements program ne decision levama madad kare chhe.

Program condition check kare chhe ane condition na result pramane alag-alag code execute kare chhe.

### Why Conditional Statements?

Example:

```text
Marks ≥ 35 → Pass
Marks < 35 → Fail
```

Program ne decision levu pade ke student pass chhe ke fail.

Aava decision mate Conditional Statements vapray chhe.

### Types of Conditional Statements

```text
1. if Statement
2. if...else Statement
3. Nested if Statement
4. elif Ladder
```

### 1. if Statement

#### Introduction

`if` statement condition check kare chhe.

Condition True hoy to block execute thay.

Condition False hoy to block skip thay.

#### Syntax

```python
if condition:
    statement
```

#### Flow Diagram

```text
Condition
    │
 ┌──┴──┐
 │True │
 └──┬──┘
    │
 Execute
 Statement
```

#### Example 1

```python
age = 20

if age >= 18:
    print("Eligible For Voting")
```

Output:

```text
Eligible For Voting
```

#### Example 2

```python
number = 10

if number > 0:
    print("Positive Number")
```

Output:

```text
Positive Number
```

#### Example 3

```python
marks = 80

if marks >= 35:
    print("Pass")
```

Output:

```text
Pass
```

#### False Condition Example

```python
marks = 20

if marks >= 35:
    print("Pass")
```

Output:

```text
No Output
```

Reason:

```text
Condition False
```

### Multiple Statements in if

```python
age = 20

if age >= 18:
    print("Eligible")
    print("Can Vote")
    print("Adult")
```

Output:

```text
Eligible
Can Vote
Adult
```

### Important Notes

✔ Condition True hoy to j block execute thay.

✔ Colon (`:`) compulsory chhe.

✔ Indentation compulsory chhe.

### 2. if...else Statement

#### Introduction

Ketlik vakhat be possibilities hoy.

Example:

```text
Pass / Fail

Adult / Minor

Even / Odd
```

Aava case ma `if...else` vapray.

#### Syntax

```python
if condition:
    statement
else:
    statement
```

#### Flow Diagram

```text
Condition
    │
 ┌──┴──┐
 │     │
True False
 │     │
 ▼     ▼
if   else
Block Block
```

#### Example 1

```python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

#### Example 2

```python
number = 5

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Odd
```

#### Example 3

```python
marks = 25

if marks >= 35:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Fail
```

#### Example 4

```python
salary = 30000

if salary >= 25000:
    print("Good Salary")
else:
    print("Low Salary")
```

Output:

```text
Good Salary
```

### Advantages of if...else

```text
Two-way decision making

Easy to understand

Most commonly used
```

### 3. Nested if Statement

#### Introduction

Ek `if` ni andar biju `if` lakhvama aave tene Nested if kahe.

#### Syntax

```python
if condition1:

    if condition2:
        statement
```

#### Structure

```text
if
 │
 └── if
      │
      └── Statement
```

#### Example 1

```python
age = 20

if age >= 18:

    if age <= 60:
        print("Working Age")
```

Output:

```text
Working Age
```

#### Example 2

```python
username = "admin"
password = "123"

if username == "admin":

    if password == "123":
        print("Login Success")
```

Output:

```text
Login Success
```

#### Example 3

```python
marks = 75

if marks >= 35:

    if marks >= 70:
        print("Distinction")
```

Output:

```text
Distinction
```

#### Example 4

```python
number = 10

if number > 0:

    if number % 2 == 0:
        print("Positive Even")
```

Output:

```text
Positive Even
```

### Nested if with else

```python
age = 15

if age >= 18:

    if age >= 21:
        print("Adult")
else:
    print("Minor")
```

Output:

```text
Minor
```

### Advantages of Nested if

```text
Complex conditions handle kari shake

Multiple levels na decision mate useful

Authentication systems ma use thay
```

### Disadvantages

```text
Code lambo thai shake

Readability ochhi thai shake
```

### 4. elif Ladder

#### Introduction

Jo ghani conditions check karvi hoy to `elif` vapray.

`elif` no arth:

```text
Else If
```

### Syntax

```python
if condition1:
    statement

elif condition2:
    statement

elif condition3:
    statement

else:
    statement
```

#### Flow

```text
Condition1
    │
 True?
    │
    ▼

Else Check Condition2
    │
 True?
    │
    ▼

Else Check Condition3
    │
 True?
    │
    ▼

Else Block
```

#### Example 1

```python
marks = 85

if marks >= 90:
    print("Grade A")

elif marks >= 75:
    print("Grade B")

elif marks >= 50:
    print("Grade C")

else:
    print("Fail")
```

Output:

```text
Grade B
```

#### Example 2

```python
day = 3

if day == 1:
    print("Monday")

elif day == 2:
    print("Tuesday")

elif day == 3:
    print("Wednesday")

else:
    print("Invalid Day")
```

Output:

```text
Wednesday
```

#### Example 3

```python
number = 0

if number > 0:
    print("Positive")

elif number < 0:
    print("Negative")

else:
    print("Zero")
```

Output:

```text
Zero
```

#### Example 4

```python
age = 65

if age < 13:
    print("Child")

elif age < 20:
    print("Teenager")

elif age < 60:
    print("Adult")

else:
    print("Senior Citizen")
```

Output:

```text
Senior Citizen")
```

### Important Rules

✔ First True condition execute thay.

✔ Biji conditions check thati nathi.

✔ Optional else lakhai shake.

✔ Unlimited elif vapri shakay.

### if vs if...else vs elif

| Statement | Conditions       |
| --------- | ---------------- |
| if        | Single Condition |
| if...else | Two Choices      |
| elif      | Multiple Choices |

### Real Life Example

Student Result System

```python
marks = 78

if marks >= 90:
    print("A Grade")

elif marks >= 75:
    print("B Grade")

elif marks >= 50:
    print("C Grade")

else:
    print("Fail")
```

Output:

```text
B Grade
```

### Interview Questions

#### What is if Statement?

Condition True hoy to block execute kare.

#### What is if...else Statement?

Be choices vachche decision leva mate vapray.

#### What is Nested if?

Ek if ni andar biju if lakhvu.

#### What is elif?

Multiple conditions check karva mate vapray.

#### elif nu Full Form Shu Chhe?

```text
Else If
```

#### Colon (`:`) Kem Mukvu Pade?

Python block start darshava mate.

## 14. Python Looping Statements

Looping Statements no upyog ekaj code ne vaar-vaar execute karva mate thay chhe.

Jo koi statement ne ghani vakhat chalavvi hoy to loop vaprvama aave chhe.

### What is Loop?

Loop etle code nu repeated execution.

Example:

```text
Welcome
Welcome
Welcome
Welcome
Welcome
```

Aa message 5 vakhat print karvo hoy to 5 print lakhva ni jagyae loop vapri shakay.

### Without Loop

```python
print("Welcome")
print("Welcome")
print("Welcome")
print("Welcome")
print("Welcome")
```

### With Loop

```python
for i in range(5):
    print("Welcome")
```

Output:

```text
Welcome
Welcome
Welcome
Welcome
Welcome
```

### Why Loops?

Loops thi:

```text
Code Reusability

Less Coding

Time Saving

Easy Data Processing
```

male chhe.

### Types of Loops in Python

```text
1. for Loop
2. while Loop
3. Nested Loops
```

### 1. for Loop

#### Introduction

`for` loop no upyog sequence na darek element par iterate karva mate thay chhe.

Sequence:

```text
String

List

Tuple

Set

Dictionary

Range
```

### Syntax

```python
for variable in sequence:
    statement
```

#### Flow

```text
Start
  │
Get Item
  │
Execute Block
  │
Next Item
  │
Repeat
  │
End
```

#### Example 1

```python
for i in range(5):
    print(i)
```

Output:

```text
0
1
2
3
4
```

#### How range(5) Works?

```python
range(5)
```

Generate kare:

```text
0 1 2 3 4
```

#### Example 2

```python
for i in range(1, 6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

#### Example 3

```python
for i in range(1, 11):
    print(i)
```

Output:

```text
1
2
3
4
5
6
7
8
9
10
```

#### Example 4

```python
for i in range(2, 11, 2):
    print(i)
```

Output:

```text
2
4
6
8
10
```

### Understanding range()

Syntax:

```python
range(start, stop, step)
```

#### start

Starting value.

#### stop

Ending value (exclude).

#### step

Increment value.

#### Example

```python
for i in range(10, 0, -1):
    print(i)
```

Output:

```text
10
9
8
7
6
5
4
3
2
1
```

### for Loop with String

```python
name = "Python"

for ch in name:
    print(ch)
```

Output:

```text
P
y
t
h
o
n
```

### for Loop with List

```python
numbers = [10, 20, 30]

for num in numbers:
    print(num)
```

Output:

```text
10
20
30
```

### for Loop with Tuple

```python
data = (1, 2, 3)

for x in data:
    print(x)
```

Output:

```text
1
2
3
```

### for Loop with Dictionary

```python
student = {
    "name":"Rohan",
    "age":20
}

for key in student:
    print(key)
```

Output:

```text
name
age
```

### Advantages of for Loop

```text
Easy Iteration

Useful with Collections

Simple Syntax
```

### 2. while Loop

#### Introduction

`while` loop condition True hoy tya sudhi execute thay chhe.

### Syntax

```python
while condition:
    statement
```

#### Flow

```text
Condition
    │
 True?
    │
Execute
    │
Check Again
    │
Repeat
```

#### Example 1

```python
i = 1

while i <= 5:
    print(i)

    i += 1
```

Output:

```text
1
2
3
4
5
```

#### Working

```text
i = 1

1 <= 5 → True

Print 1

i = 2

2 <= 5 → True

Print 2

Continue...
```

#### Example 2

```python
count = 1

while count <= 3:
    print("Hello")

    count += 1
```

Output:

```text
Hello
Hello
Hello
```

#### Example 3

```python
number = 10

while number > 0:
    print(number)

    number -= 1
```

Output:

```text
10
9
8
7
6
5
4
3
2
1
```

### Infinite Loop

Condition hamesha True hoy.

Example:

```python
while True:
    print("Python")
```

Output:

```text
Python
Python
Python
...
```

#### Avoid Infinite Loop

```python
i += 1
```

jeva update statement lakhvu jaruri chhe.

### while with User Input

```python
password = ""

while password != "admin":
    password = input("Enter Password: ")
```

### Advantages of while Loop

```text
Condition Based

Flexible

Useful for Unknown Iterations
```

### Difference Between for and while

| for Loop         | while Loop          |
| ---------------- | ------------------- |
| Sequence Based   | Condition Based     |
| Fixed Iterations | Variable Iterations |
| Easy Syntax      | More Flexible       |
| Uses range()     | Uses Condition      |

### 3. Nested Loops

#### Introduction

Ek loop ni andar biju loop lakhvama aave tene Nested Loop kahe chhe.

#### Structure

```python
for ...:

    for ...:

        statement
```

#### Flow

```text
Outer Loop
     │
     ▼
Inner Loop
     │
     ▼
Execute
```

#### Example 1

```python
for i in range(3):

    for j in range(3):

        print(i, j)
```

Output:

```text
0 0
0 1
0 2

1 0
1 1
1 2

2 0
2 1
2 2
```

# Understanding

Outer Loop:

```text
0
1
2
```

Inner Loop darek outer iteration mate complete chale chhe.

#### Example 2

```python
for i in range(1,4):

    for j in range(1,4):

        print("*", end=" ")

    print()
```

Output:

```text
* * *

* * *

* * *
```

#### Example 3

```python
for i in range(1,6):

    for j in range(i):

        print("*", end=" ")

    print()
```

Output:

```text
*

* *

* * *

* * * *

* * * * *
```

#### Multiplication Table

```python
for i in range(1,4):

    for j in range(1,11):

        print(i * j, end=" ")

    print()
```

Output:

```text
1 2 3 4 5 6 7 8 9 10

2 4 6 8 10 12 14 16 18 20

3 6 9 12 15 18 21 24 27 30
```

#### Nested while Loop

```python
i = 1

while i <= 3:

    j = 1

    while j <= 3:

        print(j, end=" ")

        j += 1

    print()

    i += 1
```

Output:

```text
1 2 3

1 2 3

1 2 3
```

### Uses of Nested Loops

```text
Pattern Programs

Matrix Operations

Tables

Game Development

Data Processing
```

### Common Mistakes

#### Missing Colon

Wrong:

```python
for i in range(5)
    print(i)
```

#### Missing Indentation

Wrong:

```python
for i in range(5):
print(i)
```

#### Infinite while Loop

Wrong:

```python
i = 1

while i <= 5:
    print(i)
```

Reason:

```text
i never changes
```

### Interview Questions

## What is Loop?

Code ne vaar-vaar execute karva mate vaprati structure.

## Types of Loops in Python?

```text
for Loop

while Loop

Nested Loop
```

#### range(5) Shu Generate Kare?

```text
0 1 2 3 4
```

#### while Loop Kya Sudhi Chale?

Condition True hoy tya sudhi.

#### Nested Loop Shu Chhe?

Ek loop ni andar biju loop.

#### Infinite Loop Shu Chhe?

Condition hamesha True hoy ane loop kyare pan stop na thay.

## 15. Python Functions

Function etle code no reusable block.

Ekaj code ne vaar-vaar lakhvani jagyae function banavi ne ghani vakhat call kari shakay.

### Why Functions?

Without Function:

```python
print("Welcome")
print("Welcome")
print("Welcome")
```

Program moto thata same code repeat thay.

With Function:

```python
def welcome():
    print("Welcome")

welcome()
welcome()
welcome()
```

Output:

```text
Welcome
Welcome
Welcome
```

### Advantages of Functions

```text
Code Reusability

Easy Maintenance

Less Code

Better Readability

Modular Programming
```

### Types of Functions

```text
Built-in Functions

User Defined Functions
```

Examples:

```python
print()

input()

len()

type()
```

Built-in Functions chhe.

### Defining Functions

#### Introduction

Function banava mate `def` keyword vapray chhe.

### Syntax

```python
def function_name():
    statements
```

#### Example 1

```python
def greet():
    print("Hello Python")
```

Function create thayu.

#### Calling Function

```python
greet()
```

Output:

```text
Hello Python
```

#### Example 2

```python
def student():
    print("Name : Rohan")
    print("Course : BCA")

student()
```

Output:

```text
Name : Rohan
Course : BCA
```

#### Flow

```text
Function Definition
        │
        ▼
Function Call
        │
        ▼
Execute Statements
```

### Function Arguments

#### Introduction

Arguments thi function ne data mokli shakay.

### Syntax

```python
def function_name(parameter):
    statements
```

#### Example 1

```python
def greet(name):
    print("Hello", name)

greet("Rohan")
```

Output:

```text
Hello Rohan
```

#### Working

```text
name parameter

"Rohan" argument
```

Argument parameter ma store thay.

#### Multiple Arguments

```python
def student(name, age):
    print(name)
    print(age)

student("Rohan", 20)
```

Output:

```text
Rohan
20
```

#### Example

```python
def add(a, b):
    print(a + b)

add(10, 20)
```

Output:

```text
30
```

#### Default Arguments

```python
def greet(name="Guest"):
    print("Hello", name)

greet()
```

Output:

```text
Hello Guest
```

#### Example

```python
greet("Rohan")
```

Output:

```text
Hello Rohan
```

#### Keyword Arguments

```python
def student(name, age):
    print(name)
    print(age)

student(age=20, name="Rohan")
```

Output:

```text
Rohan
20
```

#### Arbitrary Arguments

Multiple values accept kari shake.

```python
def numbers(*data):
    print(data)

numbers(10,20,30)
```

Output:

```text
(10, 20, 30)
```

### Return Statement

#### Introduction

Function value return karva mate `return` vapre chhe.

### Syntax

```python
def function():
    return value
```

#### Example 1

```python
def add():
    return 10 + 20

result = add()

print(result)
```

Output:

```text
30
```

#### Example 2

```python
def square(num):
    return num * num

print(square(5))
```

Output:

```text
25
```

#### Example 3

```python
def student():
    return "Rohan"

print(student())
```

Output:

```text
Rohan
```

#### Returning Multiple Values

```python
def data():
    return 10,20,30

a,b,c = data()

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

### Difference

| print()                 | return                 |
| ----------------------- | ---------------------- |
| Display Output          | Return Value           |
| Value Store Nathi Thati | Value Store Thai Shake |
| Screen Mate             | Processing Mate        |

### Recursive Functions

#### Introduction

Je function potane j call kare tene Recursive Function kahe.

### Syntax

```python
def function():
    function()
```

#### Flow

```text
Function Call
      │
      ▼
Same Function Call
      │
      ▼
Repeat
```

#### Example 1

```python
def show():
    print("Python")
    show()

show()
```

Infinite recursion thase.

#### Base Condition

Recursive function ma stop condition jaruri chhe.

#### Example 2

```python
def count(n):

    if n == 0:
        return

    print(n)

    count(n-1)

count(5)
```

Output:

```text
5
4
3
2
1
```

#### Factorial Using Recursion

```python
def factorial(n):

    if n == 1:
        return 1

    return n * factorial(n-1)

print(factorial(5))
```

Output:

```text
120
```

#### Working

```text
5 × factorial(4)

4 × factorial(3)

3 × factorial(2)

2 × factorial(1)

1
```

### Advantages of Recursion

```text
Short Code

Tree Traversal

Mathematical Problems
```

### Disadvantages

```text
More Memory

Slow for Large Data
```

### Summary

Functions:

```python
def function():
```

Arguments:

```python
def add(a,b):
```

Return:

```python
return value
```

Recursion:

```python
function()
```

potane j call kare.

## 16. Python Modules

Module etle Python file jema functions, variables ane classes hoy.

### What is Module?

Example:

```python
math.py
```

Ek module chhe.

### Why Modules?

```text
Code Reusability

Organization

Easy Maintenance

Modular Programming
```

### Types of Modules

```text
Built-in Modules

User Defined Modules
```

### Creating Modules

#### Introduction

Normal Python file create kari module banavi shakay.

#### Example

File:

```text
mymodule.py
```

Inside File

```python
def greet():
    print("Hello Python")
```

Module ready.

#### Using Module

```python
import mymodule

mymodule.greet()
```

Output:

```text
Hello Python
```

### Importing Modules

#### Introduction

Module no use karva mate import karvu pade.

### Syntax

```python
import module_name
```

#### Example

```python
import math
```

#### Using Imported Module

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

#### Import Specific Function

```python
from math import sqrt

print(sqrt(36))
```

Output:

```text
6.0
```

#### Import Multiple Functions

```python
from math import sqrt, factorial
```

#### Import All

```python
from math import *
```

#### Alias Name

```python
import math as m

print(m.sqrt(49))
```

Output:

```text
7.0
```

### Built-in Modules

#### Introduction

Python sathe predefined modules aave chhe.

#### Common Built-in Modules

```text
math

random

datetime

os

sys

calendar
```

#### math Module

```python
import math

print(math.pi)
```

Output:

```text
3.141592653589793
```

#### sqrt()

```python
import math

print(math.sqrt(64))
```

Output:

```text
8.0
```

#### factorial()

```python
import math

print(math.factorial(5))
```

Output:

```text
120
```

#### random Module

```python
import random

print(random.randint(1,10))
```

Output:

```text
Random Number
```

#### datetime Module

```python
import datetime

print(datetime.datetime.now())
```

Output:

```text
Current Date & Time
```

### User Defined Modules

#### Introduction

Programmer pote create karela modules.

#### Step 1

Create File:

```text
calculator.py
```

#### Step 2

Write Code

```python
def add(a,b):
    return a+b
```

#### Step 3

Use Module

```python
import calculator

print(calculator.add(10,20))
```

Output:

```text
30
```

#### Example

calculator.py

```python
def square(n):
    return n*n
```

main.py

```python
import calculator

print(calculator.square(5))
```

Output:

```text
25
```

### Advantages of Modules

```text
Code Reusability

Better Organization

Easy Testing

Easy Maintenance

Reduced Duplication
```
