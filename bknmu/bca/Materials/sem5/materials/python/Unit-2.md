# 📚 BCA Semester - 5

## 🐍 Python Programming

> **Subject Code:** BCA-501  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 5

---

# 📑 Unit 2 : Python Data Handling and File Processing

## _Topics_

- Python Files I/O

- Python Data Types
  - Python Strings
  - Python Lists
  - Python Tuples
  - Python Sets
  - Python Dictionary

- Special Symbols and Characters

- Regexes and Python

- Text Processing:
  - Comma Separated Values (CSV files)
  - JavaScript Object Notation (JSON)

---

# Python Files I/O

## Introduction

File I/O (Input/Output) in Python is used to store data permanently in files and retrieve it when needed. Normally, data stored in variables is lost when the program terminates. Files allow data to be saved and reused later.

Python provides built-in functions for creating, reading, writing, and updating files.

---

# Why Use Files?

- Store data permanently.
- Read data from existing files.
- Save program output.
- Share data between programs.
- Process large amounts of information.

Example:

- Student records
- Employee details
- Log files
- Configuration settings

---

# Opening a File

Python uses the `open()` function to open a file.

## Syntax

```python
file_object = open("filename", "mode")
```

### Parameters

- `filename` → Name of the file.
- `mode` → Specifies the operation to perform.

Example:

```python
file = open("sample.txt", "r")
```

---

# File Modes

| Mode | Description                                               |
| ---- | --------------------------------------------------------- |
| r    | Read file                                                 |
| w    | Write file (creates new file or overwrites existing file) |
| a    | Append data to file                                       |
| x    | Create new file                                           |
| rb   | Read binary file                                          |
| wb   | Write binary file                                         |
| r+   | Read and Write                                            |
| a+   | Append and Read                                           |

---

# Reading Files

## read()

Reads the entire file content.

```python
file = open("sample.txt", "r")
content = file.read()
print(content)
file.close()
```

Output:

```text
Hello Python
Welcome to File Handling
```

---

## read(n)

Reads specified number of characters.

```python
file = open("sample.txt", "r")
print(file.read(5))
file.close()
```

Output:

```text
Hello
```

---

## readline()

Reads one line at a time.

```python
file = open("sample.txt", "r")

print(file.readline())
print(file.readline())

file.close()
```

Output:

```text
Hello Python
Welcome to File Handling
```

---

## readlines()

Returns all lines as a list.

```python
file = open("sample.txt", "r")

lines = file.readlines()

print(lines)

file.close()
```

Output:

```python
['Hello Python\n', 'Welcome to File Handling']
```

---

# Writing to Files

## write()

Used to write data into a file.

```python
file = open("sample.txt", "w")

file.write("Hello Python")

file.close()
```

After execution:

```text
Hello Python
```

---

## Multiple Writes

```python
file = open("sample.txt", "w")

file.write("Python\n")
file.write("Programming\n")
file.write("Language")

file.close()
```

Output in file:

```text
Python
Programming
Language
```

---

# Appending Data

Append mode adds data at the end without deleting existing content.

```python
file = open("sample.txt", "a")

file.write("\nFile Handling")

file.close()
```

Output:

```text
Python
Programming
Language
File Handling
```

---

# Creating a New File

Mode `x` creates a new file.

```python
file = open("newfile.txt", "x")

file.close()
```

If file already exists:

```text
FileExistsError
```

---

# Closing a File

Always close files after use.

```python
file = open("sample.txt", "r")

print(file.read())

file.close()
```

Benefits:

- Saves memory.
- Prevents data corruption.
- Releases system resources.

---

# Using with Statement

Recommended method.

Syntax:

```python
with open("sample.txt", "r") as file:
    print(file.read())
```

Advantages:

- Automatically closes file.
- Cleaner code.
- Better resource management.

---

# File Pointer Methods

## tell()

Returns current cursor position.

```python
file = open("sample.txt", "r")

print(file.tell())

file.close()
```

Output:

```text
0
```

---

## seek()

Moves cursor to specified position.

```python
file = open("sample.txt", "r")

file.seek(5)

print(file.read())

file.close()
```

---

# Working with Binary Files

Used for images, videos, PDFs, etc.

## Writing Binary Data

```python
file = open("image.jpg", "wb")

# Binary data write

file.close()
```

---

## Reading Binary Data

```python
file = open("image.jpg", "rb")

data = file.read()

file.close()
```

---

# Checking File Existence

```python
import os

if os.path.exists("sample.txt"):
    print("File Exists")
else:
    print("File Not Found")
```

---

# Deleting a File

```python
import os

os.remove("sample.txt")
```

---

# Renaming a File

```python
import os

os.rename("old.txt", "new.txt")
```

---

# Common Exceptions in File Handling

## FileNotFoundError

```python
file = open("abc.txt", "r")
```

Output:

```text
FileNotFoundError
```

---

## PermissionError

Occurs when permission is denied.

```python
PermissionError
```

---

# Exception Handling with Files

```python
try:
    file = open("sample.txt", "r")
    print(file.read())

except FileNotFoundError:
    print("File not found")

finally:
    print("Program Finished")
```

---

# Advantages of File Handling

1. Permanent data storage.
2. Easy data sharing.
3. Efficient record management.
4. Supports large datasets.
5. Useful in real-world applications.

---

# Summary

- `open()` is used to open files.
- `read()`, `readline()`, and `readlines()` are used for reading.
- `write()` writes data to files.
- `append()` functionality is achieved using mode `a`.
- `close()` closes files.
- `with` statement automatically manages files.
- `tell()` and `seek()` control file pointers.
- Python supports both text and binary files.
- Exception handling improves file operation reliability.

# Python Data Types – Python Strings

## Introduction to Strings

A **String** is a sequence of characters enclosed within single quotes (`' '`), double quotes (`" "`), or triple quotes (`''' '''` or `""" """`).

Strings are one of the most commonly used data types in Python. They are used to store text data such as names, addresses, messages, emails, and more.

### Examples

```python
name = "Rahul"
city = 'Rajkot'
message = "Welcome to Python"
```

---

# Creating Strings

## Using Single Quotes

```python
str1 = 'Python'
print(str1)
```

Output:

```text
Python
```

## Using Double Quotes

```python
str2 = "Programming"
print(str2)
```

Output:

```text
Programming
```

## Using Triple Quotes

Used for multi-line strings.

```python
str3 = """Python is
Easy to Learn
Programming Language"""

print(str3)
```

Output:

```text
Python is
Easy to Learn
Programming Language
```

---

# String Characteristics

- Strings are **ordered**.
- Strings are **immutable** (cannot be changed after creation).
- Strings allow duplicate characters.
- Strings can contain letters, numbers, and special symbols.

Example:

```python
language = "Python"
```

Index Position:

```text
P  y  t  h  o  n
0  1  2  3  4  5
```

---

# Accessing Characters

## Positive Indexing

```python
text = "Python"

print(text[0])
print(text[2])
```

Output:

```text
P
t
```

## Negative Indexing

```python
text = "Python"

print(text[-1])
print(text[-2])
```

Output:

```text
n
o
```

---

# String Slicing

Slicing extracts a portion of a string.

## Syntax

```python
string[start:end]
```

Example:

```python
text = "Programming"

print(text[0:6])
```

Output:

```text
Progra
```

---

## Slicing with Negative Index

```python
text = "Programming"

print(text[-4:])
```

Output:

```text
ming
```

---

## Complete String

```python
text = "Python"

print(text[:])
```

Output:

```text
Python
```

---

# String Concatenation

Joining two or more strings using `+`.

```python
first = "Hello"
second = "Python"

result = first + " " + second

print(result)
```

Output:

```text
Hello Python
```

---

# String Repetition

Using `*` operator.

```python
print("Python " * 3)
```

Output:

```text
Python Python Python
```

---

# String Length

`len()` returns total characters.

```python
text = "Programming"

print(len(text))
```

Output:

```text
11
```

---

# String Membership Operators

## in Operator

```python
text = "Python Programming"

print("Python" in text)
```

Output:

```text
True
```

## not in Operator

```python
print("Java" not in text)
```

Output:

```text
True
```

---

# String Traversing

Using loop to access each character.

```python
text = "Python"

for ch in text:
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

---

# String Immutability

Strings cannot be modified directly.

Wrong:

```python
text = "Python"

text[0] = "J"
```

Output:

```text
TypeError
```

Correct:

```python
text = "Python"

new_text = "J" + text[1:]

print(new_text)
```

Output:

```text
Jython
```

---

# Escape Characters

Used to insert special characters.

| Escape Sequence | Meaning      |
| --------------- | ------------ |
| \n              | New Line     |
| \t              | Tab Space    |
| '               | Single Quote |
| "               | Double Quote |
| \               | Backslash    |

Example:

```python
print("Hello\nPython")
```

Output:

```text
Hello
Python
```

---

# Common String Methods

## upper()

Converts to uppercase.

```python
text = "python"

print(text.upper())
```

Output:

```text
PYTHON
```

---

## lower()

Converts to lowercase.

```python
text = "PYTHON"

print(text.lower())
```

Output:

```text
python
```

---

## capitalize()

Capitalizes first letter.

```python
text = "python programming"

print(text.capitalize())
```

Output:

```text
Python programming
```

---

## title()

Capitalizes first letter of each word.

```python
text = "python programming"

print(text.title())
```

Output:

```text
Python Programming
```

---

## strip()

Removes extra spaces.

```python
text = "   Python   "

print(text.strip())
```

Output:

```text
Python
```

---

## replace()

Replaces text.

```python
text = "I Like Java"

print(text.replace("Java", "Python"))
```

Output:

```text
I Like Python
```

---

## split()

Converts string into list.

```python
text = "Apple Mango Banana"

print(text.split())
```

Output:

```python
['Apple', 'Mango', 'Banana']
```

---

## join()

Joins list elements into string.

```python
words = ['Python', 'Java', 'C']

print("-".join(words))
```

Output:

```text
Python-Java-C
```

---

## find()

Returns first occurrence index.

```python
text = "Python Programming"

print(text.find("Program"))
```

Output:

```text
7
```

---

## count()

Counts occurrences.

```python
text = "Python Python Python"

print(text.count("Python"))
```

Output:

```text
3
```

---

# String Comparison

Strings can be compared using comparison operators.

```python
print("apple" == "apple")
print("apple" > "banana")
```

Output:

```text
True
False
```

Comparison is based on Unicode/ASCII values.

---

# String Formatting

## Using f-Strings (Recommended)

```python
name = "Rahul"
age = 20

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Rahul and I am 20 years old.
```

---

## Using format()

```python
name = "Rahul"

print("Welcome {}".format(name))
```

Output:

```text
Welcome Rahul
```

---

# Useful Built-in Functions

```python
text = "Python"
```

| Function     | Description        |
| ------------ | ------------------ |
| len(text)    | Length of string   |
| max(text)    | Largest character  |
| min(text)    | Smallest character |
| sorted(text) | Sorted characters  |
| type(text)   | Data type          |

Example:

```python
text = "Python"

print(len(text))
print(type(text))
```

Output:

```text
6
<class 'str'>
```

---

# Real-Life Example

```python
name = input("Enter Name: ")

print("Welcome", name)
print("Length:", len(name))
print("Uppercase:", name.upper())
print("Lowercase:", name.lower())
```

Sample Output:

```text
Enter Name: Rahul

Welcome Rahul
Length: 5
Uppercase: RAHUL
Lowercase: rahul
```

---

# Python Lists

## Introduction

A **List** is a collection data type used to store multiple items in a single variable.

Lists are one of the most powerful and frequently used data structures in Python because they can store different types of data and can be modified after creation.

### Example

```python
numbers = [10, 20, 30, 40, 50]
```

```python
student = ["Rahul", 20, 85.5, True]
```

Lists can contain:

- Integers
- Float values
- Strings
- Boolean values
- Other Lists

---

# Characteristics of Lists

- Ordered collection
- Mutable (can be modified)
- Allows duplicate values
- Supports indexing
- Can store mixed data types
- Dynamic size

Example:

```python
data = [10, "Python", 3.14, True]
```

---

# Creating Lists

## Empty List

```python
mylist = []
print(mylist)
```

Output:

```text
[]
```

## List with Values

```python
fruits = ["Apple", "Mango", "Banana"]
print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Banana']
```

---

# List Indexing

Each element has an index position.

```python
fruits = ["Apple", "Mango", "Banana"]
```

Index Representation:

```text
Apple   Mango   Banana
  0       1        2
```

Accessing Elements:

```python
print(fruits[0])
print(fruits[1])
```

Output:

```text
Apple
Mango
```

---

# Negative Indexing

```python
fruits = ["Apple", "Mango", "Banana"]

print(fruits[-1])
print(fruits[-2])
```

Output:

```text
Banana
Mango
```

---

# List Slicing

Syntax:

```python
list[start:end]
```

Example:

```python
numbers = [10,20,30,40,50]

print(numbers[1:4])
```

Output:

```text
[20, 30, 40]
```

---

# Modifying List Elements

Lists are mutable.

```python
fruits = ["Apple", "Mango", "Banana"]

fruits[1] = "Orange"

print(fruits)
```

Output:

```text
['Apple', 'Orange', 'Banana']
```

---

# Adding Elements

## append()

Adds element at end.

```python
fruits = ["Apple", "Mango"]

fruits.append("Banana")

print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Banana']
```

---

## insert()

Adds element at specified position.

```python
fruits = ["Apple", "Banana"]

fruits.insert(1, "Mango")

print(fruits)
```

Output:

```text
['Apple', 'Mango', 'Banana']
```

---

# Removing Elements

## remove()

Removes specific value.

```python
fruits = ["Apple", "Mango", "Banana"]

fruits.remove("Mango")

print(fruits)
```

Output:

```text
['Apple', 'Banana']
```

---

## pop()

Removes element using index.

```python
numbers = [10,20,30,40]

numbers.pop(2)

print(numbers)
```

Output:

```text
[10, 20, 40]
```

---

## del Statement

```python
numbers = [10,20,30,40]

del numbers[1]

print(numbers)
```

Output:

```text
[10, 30, 40]
```

---

# List Operations

## Concatenation

```python
list1 = [1,2,3]
list2 = [4,5,6]

print(list1 + list2)
```

Output:

```text
[1, 2, 3, 4, 5, 6]
```

---

## Repetition

```python
print([1,2] * 3)
```

Output:

```text
[1, 2, 1, 2, 1, 2]
```

---

# Membership Operators

```python
fruits = ["Apple", "Mango", "Banana"]

print("Mango" in fruits)
print("Orange" not in fruits)
```

Output:

```text
True
True
```

---

# Traversing a List

```python
fruits = ["Apple", "Mango", "Banana"]

for item in fruits:
    print(item)
```

Output:

```text
Apple
Mango
Banana
```

---

# Important List Methods

## sort()

```python
numbers = [50,10,30,20]

numbers.sort()

print(numbers)
```

Output:

```text
[10, 20, 30, 50]
```

---

## reverse()

```python
numbers = [10,20,30]

numbers.reverse()

print(numbers)
```

Output:

```text
[30, 20, 10]
```

---

## count()

```python
numbers = [1,2,2,3,2]

print(numbers.count(2))
```

Output:

```text
3
```

---

## index()

```python
fruits = ["Apple", "Mango", "Banana"]

print(fruits.index("Mango"))
```

Output:

```text
1
```

---

## copy()

```python
list1 = [1,2,3]

list2 = list1.copy()

print(list2)
```

Output:

```text
[1, 2, 3]
```

---

# Nested Lists

List inside another list.

```python
matrix = [
    [1,2,3],
    [4,5,6],
    [7,8,9]
]

print(matrix[1][2])
```

Output:

```text
6
```

---

# Useful Functions with Lists

```python
numbers = [10,20,30,40]
```

| Function     | Output |
| ------------ | ------ |
| len(numbers) | 4      |
| max(numbers) | 40     |
| min(numbers) | 10     |
| sum(numbers) | 100    |

Example:

```python
print(len(numbers))
print(sum(numbers))
```

---

# Real-Life Example

```python
marks = [75, 80, 90, 85]

total = sum(marks)
average = total / len(marks)

print("Total:", total)
print("Average:", average)
```

Output:

```text
Total: 330
Average: 82.5
```

---

# Python Tuples

## Introduction

A **Tuple** is a collection of items similar to a list, but it is **immutable**, meaning its elements cannot be changed after creation.

Tuples are written using parentheses `()`.

Example:

```python
student = ("Rahul", 20, 85.5)
```

---

# Characteristics of Tuples

- Ordered collection
- Immutable
- Allows duplicates
- Supports indexing
- Faster than lists
- Can store mixed data types

---

# Creating Tuples

## Empty Tuple

```python
t = ()
print(t)
```

Output:

```text
()
```

## Tuple with Values

```python
colors = ("Red", "Green", "Blue")
print(colors)
```

Output:

```text
('Red', 'Green', 'Blue')
```

---

# Accessing Tuple Elements

```python
colors = ("Red", "Green", "Blue")

print(colors[0])
print(colors[2])
```

Output:

```text
Red
Blue
```

---

# Negative Indexing

```python
colors = ("Red", "Green", "Blue")

print(colors[-1])
```

Output:

```text
Blue
```

---

# Tuple Slicing

```python
numbers = (10,20,30,40,50)

print(numbers[1:4])
```

Output:

```text
(20, 30, 40)
```

---

# Tuple Immutability

Wrong:

```python
colors = ("Red", "Green", "Blue")

colors[1] = "Yellow"
```

Output:

```text
TypeError
```

Because tuples cannot be modified.

---

# Tuple Operations

## Concatenation

```python
t1 = (1,2,3)
t2 = (4,5,6)

print(t1 + t2)
```

Output:

```text
(1, 2, 3, 4, 5, 6)
```

---

## Repetition

```python
print((1,2) * 3)
```

Output:

```text
(1, 2, 1, 2, 1, 2)
```

---

# Membership Operators

```python
colors = ("Red", "Green", "Blue")

print("Green" in colors)
```

Output:

```text
True
```

---

# Traversing a Tuple

```python
colors = ("Red", "Green", "Blue")

for color in colors:
    print(color)
```

Output:

```text
Red
Green
Blue
```

---

# Tuple Methods

Tuples have only two built-in methods.

## count()

```python
numbers = (1,2,2,3,2)

print(numbers.count(2))
```

Output:

```text
3
```

---

## index()

```python
colors = ("Red", "Green", "Blue")

print(colors.index("Green"))
```

Output:

```text
1
```

---

# Packing and Unpacking Tuples

## Packing

```python
student = ("Rahul", 20, "Rajkot")
```

## Unpacking

```python
name, age, city = student

print(name)
print(age)
print(city)
```

Output:

```text
Rahul
20
Rajkot
```

---

# List vs Tuple

| Feature      | List   | Tuple  |
| ------------ | ------ | ------ |
| Symbol       | []     | ()     |
| Mutable      | Yes    | No     |
| Speed        | Slower | Faster |
| Methods      | Many   | Few    |
| Memory Usage | More   | Less   |

---

# Real-Life Example

```python
student = ("Rahul", 101, 85)

print("Name:", student[0])
print("Roll No:", student[1])
print("Marks:", student[2])
```

Output:

```text
Name: Rahul
Roll No: 101
Marks: 85
```

---

# Python Sets

## Introduction

A **Set** is an unordered collection of unique elements in Python.

Sets are used when:

- Duplicate values are not allowed.
- Fast searching and membership testing are required.
- Mathematical set operations such as Union, Intersection, and Difference need to be performed.

Sets are created using curly braces `{}` or the `set()` function.

Example:

```python id="s1"
numbers = {10, 20, 30, 40}
print(numbers)
```

Output:

```text id="s2"
{10, 20, 30, 40}
```

---

# Characteristics of Sets

- Unordered collection
- Mutable (elements can be added or removed)
- Does not allow duplicate values
- Does not support indexing
- Faster lookup compared to lists
- Can store different data types

Example:

```python id="s3"
data = {10, "Python", 3.14, True}
print(data)
```

---

# Creating Sets

## Empty Set

```python id="s4"
myset = set()
print(type(myset))
```

Output:

```text id="s5"
<class 'set'>
```

**Note:** `{}` creates a dictionary, not an empty set.

---

## Set with Values

```python id="s6"
fruits = {"Apple", "Mango", "Banana"}
print(fruits)
```

Output:

```text id="s7"
{'Apple', 'Mango', 'Banana'}
```

---

# Duplicate Values in Sets

Sets automatically remove duplicates.

```python id="s8"
numbers = {10, 20, 20, 30, 30, 40}

print(numbers)
```

Output:

```text id="s9"
{10, 20, 30, 40}
```

---

# Adding Elements

## add()

Adds a single element.

```python id="s10"
fruits = {"Apple", "Mango"}

fruits.add("Banana")

print(fruits)
```

Output:

```text id="s11"
{'Apple', 'Mango', 'Banana'}
```

---

## update()

Adds multiple elements.

```python id="s12"
fruits = {"Apple", "Mango"}

fruits.update(["Banana", "Orange"])

print(fruits)
```

Output:

```text id="s13"
{'Apple', 'Mango', 'Banana', 'Orange'}
```

---

# Removing Elements

## remove()

```python id="s14"
fruits = {"Apple", "Mango", "Banana"}

fruits.remove("Mango")

print(fruits)
```

Output:

```text id="s15"
{'Apple', 'Banana'}
```

If element does not exist:

```text id="s16"
KeyError
```

---

## discard()

Safely removes an element.

```python id="s17"
fruits.discard("Orange")
```

No error occurs.

---

## pop()

Removes a random element.

```python id="s18"
fruits = {"Apple", "Mango", "Banana"}

fruits.pop()

print(fruits)
```

---

## clear()

Removes all elements.

```python id="s19"
fruits.clear()

print(fruits)
```

Output:

```text id="s20"
set()
```

---

# Traversing a Set

```python id="s21"
fruits = {"Apple", "Mango", "Banana"}

for item in fruits:
    print(item)
```

Output:

```text id="s22"
Apple
Mango
Banana
```

(Order may vary.)

---

# Membership Operators

```python id="s23"
fruits = {"Apple", "Mango", "Banana"}

print("Mango" in fruits)
print("Orange" not in fruits)
```

Output:

```text id="s24"
True
True
```

---

# Set Operations

## Union

Combines all unique elements.

```python id="s25"
A = {1, 2, 3}
B = {3, 4, 5}

print(A | B)
```

Output:

```text id="s26"
{1, 2, 3, 4, 5}
```

---

## Intersection

Returns common elements.

```python id="s27"
A = {1, 2, 3}
B = {2, 3, 4}

print(A & B)
```

Output:

```text id="s28"
{2, 3}
```

---

## Difference

Returns elements present in first set only.

```python id="s29"
A = {1, 2, 3}
B = {2, 3, 4}

print(A - B)
```

Output:

```text id="s30"
{1}
```

---

## Symmetric Difference

Returns uncommon elements.

```python id="s31"
A = {1, 2, 3}
B = {2, 3, 4}

print(A ^ B)
```

Output:

```text id="s32"
{1, 4}
```

---

# Useful Set Methods

| Method         | Description             |
| -------------- | ----------------------- |
| add()          | Add one element         |
| update()       | Add multiple elements   |
| remove()       | Remove element          |
| discard()      | Remove safely           |
| pop()          | Remove random element   |
| clear()        | Remove all elements     |
| union()        | Combine sets            |
| intersection() | Common elements         |
| difference()   | Difference between sets |

---

# Real-Life Example

```python id="s33"
students = {"Rahul", "Amit", "Rahul", "Priya"}

print(students)
```

Output:

```text id="s34"
{'Rahul', 'Amit', 'Priya'}
```

Duplicate names are automatically removed.

---

# Summary of Sets

- Created using `{}` or `set()`
- Unordered collection
- No duplicate values
- Supports mathematical set operations
- Useful for unique data storage

---

# Python Dictionary

## Introduction

A **Dictionary** is a collection of data stored in **key-value pairs**.

Each key is unique and is used to access its corresponding value.

Dictionary is created using curly braces `{}`.

Example:

```python id="d1"
student = {
    "name": "Rahul",
    "age": 20,
    "city": "Rajkot"
}

print(student)
```

Output:

```text id="d2"
{'name': 'Rahul', 'age': 20, 'city': 'Rajkot'}
```

---

# Characteristics of Dictionary

- Stores data as key-value pairs
- Mutable
- Keys must be unique
- Values can be duplicated
- Ordered (Python 3.7+)
- Fast data retrieval

---

# Creating Dictionaries

## Empty Dictionary

```python id="d3"
student = {}

print(student)
```

Output:

```text id="d4"
{}
```

---

## Dictionary with Data

```python id="d5"
employee = {
    "id": 101,
    "name": "Rahul",
    "salary": 25000
}

print(employee)
```

---

# Accessing Dictionary Values

Using key names.

```python id="d6"
student = {
    "name": "Rahul",
    "age": 20
}

print(student["name"])
```

Output:

```text id="d7"
Rahul
```

---

## Using get()

```python id="d8"
print(student.get("age"))
```

Output:

```text id="d9"
20
```

---

# Modifying Dictionary Values

```python id="d10"
student = {
    "name": "Rahul",
    "age": 20
}

student["age"] = 21

print(student)
```

Output:

```text id="d11"
{'name': 'Rahul', 'age': 21}
```

---

# Adding New Elements

```python id="d12"
student = {
    "name": "Rahul"
}

student["city"] = "Rajkot"

print(student)
```

Output:

```text id="d13"
{'name': 'Rahul', 'city': 'Rajkot'}
```

---

# Removing Elements

## pop()

```python id="d14"
student = {
    "name": "Rahul",
    "age": 20
}

student.pop("age")

print(student)
```

Output:

```text id="d15"
{'name': 'Rahul'}
```

---

## del Statement

```python id="d16"
student = {
    "name": "Rahul",
    "age": 20
}

del student["age"]

print(student)
```

Output:

```text id="d17"
{'name': 'Rahul'}
```

---

## clear()

```python id="d18"
student.clear()

print(student)
```

Output:

```text id="d19"
{}
```

---

# Dictionary Traversing

## Keys

```python id="d20"
student = {
    "name": "Rahul",
    "age": 20
}

for key in student:
    print(key)
```

Output:

```text id="d21"
name
age
```

---

## Values

```python id="d22"
for value in student.values():
    print(value)
```

Output:

```text id="d23"
Rahul
20
```

---

## Key-Value Pairs

```python id="d24"
for key, value in student.items():
    print(key, value)
```

Output:

```text id="d25"
name Rahul
age 20
```

---

# Important Dictionary Methods

## keys()

```python id="d26"
student.keys()
```

Returns all keys.

---

## values()

```python id="d27"
student.values()
```

Returns all values.

---

## items()

```python id="d28"
student.items()
```

Returns key-value pairs.

---

## update()

```python id="d29"
student = {"name": "Rahul"}

student.update({"city": "Rajkot"})

print(student)
```

Output:

```text id="d30"
{'name': 'Rahul', 'city': 'Rajkot'}
```

---

# Nested Dictionary

Dictionary inside another dictionary.

```python id="d31"
students = {
    101: {
        "name": "Rahul",
        "marks": 85
    },
    102: {
        "name": "Amit",
        "marks": 90
    }
}

print(students[101]["name"])
```

Output:

```text id="d32"
Rahul
```

---

# Dictionary Comprehension

```python id="d33"
squares = {x: x*x for x in range(1,6)}

print(squares)
```

Output:

```text id="d34"
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

# Useful Functions with Dictionary

```python id="d35"
student = {
    "name": "Rahul",
    "age": 20
}
```

| Function      | Description               |
| ------------- | ------------------------- |
| len(student)  | Number of key-value pairs |
| type(student) | Data type                 |
| max(student)  | Largest key               |
| min(student)  | Smallest key              |

Example:

```python id="d36"
print(len(student))
print(type(student))
```

Output:

```text id="d37"
2
<class 'dict'>
```

---

# Real-Life Example

```python id="d38"
student = {
    "name": "Rahul",
    "roll_no": 101,
    "marks": 85
}

print("Name:", student["name"])
print("Marks:", student["marks"])
```

Output:

```text id="d39"
Name: Rahul
Marks: 85
```

---

# Difference Between Set and Dictionary

| Feature        | Set           | Dictionary      |
| -------------- | ------------- | --------------- |
| Syntax         | `{1,2,3}`     | `{"a":1}`       |
| Data Storage   | Values only   | Key-Value Pairs |
| Duplicate Keys | Not Allowed   | Keys Unique     |
| Indexing       | Not Supported | Access by Keys  |
| Mutable        | Yes           | Yes             |

---

# Special Symbols and Characters in Python

## Introduction

Special symbols and characters are symbols that have predefined meanings in Python. They are used for mathematical operations, assignment, comparison, logical operations, string manipulation, and program control.

Understanding these symbols is essential because they form the foundation of Python programming.

---

# Arithmetic Symbols

Used to perform mathematical calculations.

| Symbol | Meaning        | Example  |
| ------ | -------------- | -------- |
| +      | Addition       | 10 + 5   |
| -      | Subtraction    | 10 - 5   |
| \*     | Multiplication | 10 \* 5  |
| /      | Division       | 10 / 5   |
| %      | Modulus        | 10 % 3   |
| //     | Floor Division | 10 // 3  |
| \*\*   | Exponent       | 2 \*\* 3 |

Example:

```python id="sp1"
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a % b)
print(a // b)
print(a ** b)
```

Output:

```text id="sp2"
13
7
30
3.333333333
1
3
1000
```

---

# Assignment Symbols

Used to assign values to variables.

| Symbol | Meaning             |
| ------ | ------------------- |
| =      | Assign              |
| +=     | Add and Assign      |
| -=     | Subtract and Assign |
| \*=    | Multiply and Assign |
| /=     | Divide and Assign   |
| %=     | Modulus and Assign  |

Example:

```python id="sp3"
x = 10

x += 5

print(x)
```

Output:

```text id="sp4"
15
```

---

# Comparison Symbols

Used to compare values.

| Symbol | Meaning               |
| ------ | --------------------- |
| ==     | Equal To              |
| !=     | Not Equal To          |
| >      | Greater Than          |
| <      | Less Than             |
| >=     | Greater Than or Equal |
| <=     | Less Than or Equal    |

Example:

```python id="sp5"
a = 10
b = 20

print(a == b)
print(a < b)
```

Output:

```text id="sp6"
False
True
```

---

# Logical Symbols

Used to combine conditions.

| Symbol | Meaning     |
| ------ | ----------- |
| and    | Logical AND |
| or     | Logical OR  |
| not    | Logical NOT |

Example:

```python id="sp7"
age = 20

print(age > 18 and age < 30)
```

Output:

```text id="sp8"
True
```

---

# Membership Symbols

Used to check membership in sequences.

| Symbol | Meaning     |
| ------ | ----------- |
| in     | Present     |
| not in | Not Present |

Example:

```python id="sp9"
name = "Python"

print("P" in name)
print("J" not in name)
```

Output:

```text id="sp10"
True
True
```

---

# Identity Symbols

Used to compare object identity.

| Symbol | Meaning          |
| ------ | ---------------- |
| is     | Same Object      |
| is not | Different Object |

Example:

```python id="sp11"
a = [1,2]
b = a

print(a is b)
```

Output:

```text id="sp12"
True
```

---

# Special Characters in Strings

## New Line (\n)

```python id="sp13"
print("Hello\nPython")
```

Output:

```text id="sp14"
Hello
Python
```

---

## Tab Space (\t)

```python id="sp15"
print("Hello\tPython")
```

Output:

```text id="sp16"
Hello    Python
```

---

## Single Quote (')

```python id="sp17"
print('It\'s Python')
```

Output:

```text id="sp18"
It's Python
```

---

## Double Quote (")

```python id="sp19"
print("He said \"Hello\"")
```

Output:

```text id="sp20"
He said "Hello"
```

---

## Backslash (\)

```python id="sp21"
print("C:\\Python")
```

Output:

```text id="sp22"
C:\Python
```

---

# Common Special Symbols

| Symbol | Purpose                 |
| ------ | ----------------------- |
| #      | Comment                 |
| :      | Block Start             |
| ,      | Separator               |
| .      | Object Access           |
| ()     | Function Call           |
| []     | List                    |
| {}     | Dictionary/Set          |
| @      | Decorator               |
| \_     | Special Variable Naming |

Example:

```python id="sp23"
# This is a comment

name = "Python"

print(name)
```

---

# Summary

- Special symbols are used to perform operations.
- Escape characters begin with backslash (`\`).
- Symbols simplify programming tasks.
- Python provides symbols for arithmetic, comparison, assignment, logical operations, and more.

---

# Regexes and Python

## Introduction

**Regex (Regular Expression)** is a sequence of characters used to search, match, validate, and manipulate text patterns.

Regex is very useful in:

- Email validation
- Mobile number validation
- Password checking
- Data extraction
- Search operations
- Text processing

Python provides regex support through the built-in `re` module.

---

# Importing Regex Module

```python id="re1"
import re
```

---

# Why Use Regex?

Without Regex:

```python id="re2"
text = "Python Programming"

if "Python" in text:
    print("Found")
```

With Regex:

```python id="re3"
import re

text = "Python Programming"

if re.search("Python", text):
    print("Found")
```

Output:

```text id="re4"
Found
```

---

# Important Regex Functions

| Function   | Purpose                    |
| ---------- | -------------------------- |
| search()   | Search pattern             |
| match()    | Match from beginning       |
| findall()  | Return all matches         |
| finditer() | Return iterator of matches |
| sub()      | Replace text               |
| split()    | Split text                 |

---

# search()

Searches entire string.

```python id="re5"
import re

text = "Welcome to Python"

result = re.search("Python", text)

print(result)
```

Output:

```text id="re6"
<re.Match object>
```

---

# match()

Matches only at beginning.

```python id="re7"
import re

text = "Python Programming"

print(re.match("Python", text))
```

Output:

```text id="re8"
<re.Match object>
```

---

# findall()

Returns all matches as a list.

```python id="re9"
import re

text = "Python Java Python C Python"

print(re.findall("Python", text))
```

Output:

```python id="re10"
['Python', 'Python', 'Python']
```

---

# split()

Splits string using regex pattern.

```python id="re11"
import re

text = "Apple,Mango,Banana"

print(re.split(",", text))
```

Output:

```python id="re12"
['Apple', 'Mango', 'Banana']
```

---

# sub()

Replaces matching text.

```python id="re13"
import re

text = "I like Java"

print(re.sub("Java", "Python", text))
```

Output:

```text id="re14"
I like Python
```

---

# Regex Special Characters

## Dot (.)

Matches any single character.

```python id="re15"
import re

print(re.findall("P.thon", "Python"))
```

Output:

```python id="re16"
['Python']
```

---

## Caret (^)

Matches beginning of string.

```python id="re17"
import re

print(re.search("^Python", "Python Language"))
```

Output:

```text id="re18"
Match Found
```

---

## Dollar ($)

Matches end of string.

```python id="re19"
import re

print(re.search("Language$", "Python Language"))
```

Output:

```text id="re20"
Match Found
```

---

## Star (\*)

Zero or more occurrences.

```python id="re21"
import re

print(re.findall("ab*", "ab abb abbb a"))
```

Output:

```python id="re22"
['ab', 'abb', 'abbb', 'a']
```

---

## Plus (+)

One or more occurrences.

```python id="re23"
import re

print(re.findall("ab+", "ab abb abbb"))
```

Output:

```python id="re24"
['ab', 'abb', 'abbb']
```

---

## Question Mark (?)

Zero or one occurrence.

```python id="re25"
import re

print(re.findall("ab?", "ab abb a"))
```

Output:

```python id="re26"
['ab', 'ab', 'a']
```

---

# Character Classes

## Digits

`\d` → Matches digits

```python id="re27"
import re

text = "Age 20"

print(re.findall(r"\d", text))
```

Output:

```python id="re28"
['2', '0']
```

---

## Non-Digits

`\D`

```python id="re29"
print(re.findall(r"\D", "A1B2"))
```

Output:

```python id="re30"
['A', 'B']
```

---

## Alphabets

`\w`

```python id="re31"
print(re.findall(r"\w", "Python123"))
```

Output:

```python id="re32"
['P','y','t','h','o','n','1','2','3']
```

---

## Spaces

`\s`

```python id="re33"
print(re.findall(r"\s", "Python Programming"))
```

Output:

```python id="re34"
[' ']
```

---

# Email Validation Example

```python id="re35"
import re

email = "abc@gmail.com"

pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'

if re.match(pattern, email):
    print("Valid Email")
else:
    print("Invalid Email")
```

Output:

```text id="re36"
Valid Email
```

---

# Mobile Number Validation

```python id="re37"
import re

mobile = "9876543210"

pattern = r'^[0-9]{10}$'

if re.match(pattern, mobile):
    print("Valid Mobile Number")
```

Output:

```text id="re38"
Valid Mobile Number
```

---

# Password Validation Example

```python id="re39"
import re

password = "Python@123"

pattern = r'^(?=.*[A-Za-z])(?=.*\d).{8,}$'

if re.match(pattern, password):
    print("Strong Password")
```

Output:

```text id="re40"
Strong Password
```

---

# Real-Life Applications of Regex

1. Form Validation
2. Search Engines
3. Data Cleaning
4. Log File Analysis
5. Web Scraping
6. Data Extraction
7. Text Processing
8. Email Verification

---

# Text Processing in Python

## Introduction

**Text Processing** refers to reading, analyzing, modifying, storing, and exchanging text data using a program.

Python provides powerful built-in modules and libraries for text processing. Two of the most commonly used formats are:

1. **CSV (Comma Separated Values)**
2. **JSON (JavaScript Object Notation)**

These formats are widely used for:

- Data Storage
- Data Exchange
- Reports
- Web Applications
- APIs
- Data Analysis

---

# Comma Separated Values (CSV Files)

## Introduction to CSV

CSV stands for **Comma Separated Values**.

A CSV file stores data in tabular form where values are separated by commas.

Example CSV File:

```text id="csv1"
ID,Name,Marks
101,Rahul,85
102,Amit,90
103,Priya,88
```

Each line represents a row, and commas separate the columns.

---

# Why Use CSV Files?

- Simple format
- Easy to read and write
- Supported by Excel
- Supported by databases
- Portable across platforms

---

# CSV Module in Python

Python provides a built-in module called **csv** for handling CSV files.

Import Statement:

```python id="csv2"
import csv
```

---

# Reading CSV Files

## csv.reader()

Used to read CSV files.

### Example

Suppose `students.csv` contains:

```text id="csv3"
ID,Name,Marks
101,Rahul,85
102,Amit,90
103,Priya,88
```

Python Program:

```python id="csv4"
import csv

with open("students.csv", "r") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

Output:

```python id="csv5"
['ID', 'Name', 'Marks']
['101', 'Rahul', '85']
['102', 'Amit', '90']
['103', 'Priya', '88']
```

---

# Writing CSV Files

## csv.writer()

Used to write data into CSV files.

Example:

```python id="csv6"
import csv

with open("students.csv", "w", newline="") as file:

    writer = csv.writer(file)

    writer.writerow(["ID", "Name", "Marks"])
    writer.writerow([101, "Rahul", 85])
    writer.writerow([102, "Amit", 90])
```

Generated CSV File:

```text id="csv7"
ID,Name,Marks
101,Rahul,85
102,Amit,90
```

---

# Writing Multiple Rows

## writerows()

Used to write multiple rows.

```python id="csv8"
import csv

data = [
    ["ID", "Name", "Marks"],
    [101, "Rahul", 85],
    [102, "Amit", 90],
    [103, "Priya", 88]
]

with open("students.csv", "w", newline="") as file:
    writer = csv.writer(file)

    writer.writerows(data)
```

---

# Reading CSV as Dictionary

## csv.DictReader()

Reads CSV rows as dictionaries.

CSV File:

```text id="csv9"
ID,Name,Marks
101,Rahul,85
102,Amit,90
```

Program:

```python id="csv10"
import csv

with open("students.csv", "r") as file:

    reader = csv.DictReader(file)

    for row in reader:
        print(row)
```

Output:

```python id="csv11"
{'ID': '101', 'Name': 'Rahul', 'Marks': '85'}
{'ID': '102', 'Name': 'Amit', 'Marks': '90'}
```

---

# Writing CSV Using Dictionary

## csv.DictWriter()

```python id="csv12"
import csv

with open("students.csv", "w", newline="") as file:

    fieldnames = ["ID", "Name", "Marks"]

    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()

    writer.writerow({
        "ID": 101,
        "Name": "Rahul",
        "Marks": 85
    })
```

---

# Advantages of CSV

1. Simple and lightweight
2. Human-readable
3. Easy to transfer
4. Supported by Excel
5. Useful for data analysis

---

# Limitations of CSV

1. No support for nested data
2. No data type information
3. Security issues with large datasets
4. Difficult to represent complex structures

---

# Real-Life Example of CSV

Student Records:

```text id="csv13"
RollNo,Name,Marks
101,Rahul,85
102,Amit,90
103,Priya,88
```

Used in:

- School Management Systems
- Employee Records
- Sales Reports
- Inventory Systems

---

# JavaScript Object Notation (JSON)

## Introduction

JSON stands for **JavaScript Object Notation**.

It is a lightweight data-interchange format used for storing and exchanging data.

JSON is widely used in:

- APIs
- Web Applications
- Mobile Applications
- Cloud Services
- Databases

---

# JSON Structure

JSON stores data in **key-value pairs**.

Example:

```json
{
  "name": "Rahul",
  "age": 20,
  "city": "Rajkot"
}
```

This structure is very similar to a Python Dictionary.

---

# JSON Data Types

| JSON Type | Example          |
| --------- | ---------------- |
| String    | "Rahul"          |
| Number    | 100              |
| Boolean   | true             |
| Array     | [1,2,3]          |
| Object    | {"name":"Rahul"} |
| Null      | null             |

---

# JSON Module in Python

Python provides a built-in **json** module.

Import:

```python id="json1"
import json
```

---

# Converting Python Object to JSON

## json.dumps()

Used to convert Python objects into JSON strings.

Example:

```python id="json2"
import json

student = {
    "name": "Rahul",
    "age": 20,
    "city": "Rajkot"
}

json_data = json.dumps(student)

print(json_data)
```

Output:

```text id="json3"
{"name": "Rahul", "age": 20, "city": "Rajkot"}
```

---

# Converting JSON to Python Object

## json.loads()

Used to convert JSON string into Python Dictionary.

Example:

```python id="json4"
import json

json_data = '''
{
    "name":"Rahul",
    "age":20
}
'''

data = json.loads(json_data)

print(data)
print(type(data))
```

Output:

```python id="json5"
{'name': 'Rahul', 'age': 20}
<class 'dict'>
```

---

# Writing JSON File

## json.dump()

Used to write JSON data into a file.

Example:

```python id="json6"
import json

student = {
    "name": "Rahul",
    "age": 20,
    "city": "Rajkot"
}

with open("student.json", "w") as file:
    json.dump(student, file)
```

Generated File:

```json
{
  "name": "Rahul",
  "age": 20,
  "city": "Rajkot"
}
```

---

# Reading JSON File

## json.load()

Used to read JSON data from a file.

Example:

```python id="json7"
import json

with open("student.json", "r") as file:

    data = json.load(file)

    print(data)
```

Output:

```python id="json8"
{'name': 'Rahul', 'age': 20, 'city': 'Rajkot'}
```

---

# Pretty Printing JSON

```python id="json9"
import json

student = {
    "name": "Rahul",
    "age": 20,
    "city": "Rajkot"
}

print(json.dumps(student, indent=4))
```

Output:

```json
{
  "name": "Rahul",
  "age": 20,
  "city": "Rajkot"
}
```

---

# Nested JSON Example

```python id="json10"
student = {
    "name": "Rahul",
    "marks": {
        "Python": 90,
        "Java": 85
    }
}

print(student["marks"]["Python"])
```

Output:

```text id="json11"
90
```

---

# CSV vs JSON

| Feature           | CSV              | JSON            |
| ----------------- | ---------------- | --------------- |
| Structure         | Tabular          | Hierarchical    |
| Data Type Support | Limited          | Multiple Types  |
| Readability       | Simple           | More Structured |
| Nested Data       | Not Supported    | Supported       |
| API Usage         | Rare             | Common          |
| Storage           | Spreadsheet Data | Web Data        |

---

# Real-Life Applications of JSON

1. REST APIs
2. Mobile Apps
3. Configuration Files
4. Web Services
5. Cloud Computing
6. Database Data Exchange

Example API Response:

```json
{
  "id": 101,
  "name": "Rahul",
  "email": "rahul@gmail.com"
}
```

---
