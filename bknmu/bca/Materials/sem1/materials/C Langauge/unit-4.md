# 📚 BCA Semester - 1

## 💻 Problem Solving Methodologies & Programming in C

> **Subject Code:** BCA-101  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 4 : Array & Structures

## Topics

### Array

- Concept of Array
- Types of arrays
  - Single dimensional array
  - Two dimensional array
  - Multi-dimensional array
- String arrays
- Array with functions using UDF
- Use of Arrays in Programming


### Structures

- Concept of Structure
- Initializations and declarations
- Array with structures
  - Array of Structure
  - Array within structure
- Udf with structures
- Nested structures
- Introduction to union
- Difference between Structure & Union


## Array

---

## Concept of Array

An array is a data structure that stores multiple values of the same data type in a continuous memory location under a single variable name. Each element in an array is accessed using an index number starting from 0.

Arrays are used when we want to store large amounts of similar data efficiently without declaring multiple variables.

---

### Memory Representation (Diagram)

```
Index:   0     1     2     3     4
        ---------------------------
Array:  |10| |20| |30| |40| |50|
        ---------------------------
Address increasing →
```

---

## Types of Arrays

Arrays are mainly classified into three types:

---

## 1. Single Dimensional Array

### Definition
A single dimensional array is a linear array that stores elements in a single row. Each element is accessed using one index.

---

### Syntax

```c
data_type array_name[size];
```

---

### Example

```c
#include <stdio.h>

int main()
{
    int a[5] = {10, 20, 30, 40, 50};
    int i;

    for(i = 0; i < 5; i++)
    {
        printf("%d ", a[i]);
    }

    return 0;
}
```

---

### Output

```
10 20 30 40 50
```

---

### Diagram

```
a[0]  a[1]  a[2]  a[3]  a[4]
10    20    30    40    50
```

---

## 2. Two Dimensional Array

### Definition
A two dimensional array stores data in row and column format (matrix form). It is used to represent tables.

---

### Syntax

```c
data_type array_name[rows][columns];
```

---

### Example

```c
#include <stdio.h>

int main()
{
    int a[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    int i, j;

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 3; j++)
        {
            printf("%d ", a[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```

---

### Output

```
1 2 3
4 5 6
```

---

### Diagram

```
Row \ Col   0   1   2
----------------------
0           1   2   3
1           4   5   6
```

---

## 3. Multi-Dimensional Array

### Definition
A multi-dimensional array is an array that contains more than two dimensions. It is used for complex data structures.

---

### Syntax

```c
data_type array_name[size1][size2][size3]...;
```

---

### Example (3D Array)

```c
#include <stdio.h>

int main()
{
    int a[2][2][2] = {
        {
            {1, 2},
            {3, 4}
        },
        {
            {5, 6},
            {7, 8}
        }
    };

    int i, j, k;

    for(i = 0; i < 2; i++)
    {
        for(j = 0; j < 2; j++)
        {
            for(k = 0; k < 2; k++)
            {
                printf("%d ", a[i][j][k]);
            }
        }
    }

    return 0;
}
```

---

### Output

```
1 2 3 4 5 6 7 8
```

---

### Diagram (3D Representation)

```
Layer 0:
1 2
3 4

Layer 1:
5 6
7 8
```


## String Arrays

### Definition
A string array is an array of multiple strings where each element is a character array. It is used to store multiple names or text values.

---

### Syntax

```c
char array_name[size][length];
```

---

### Example

```c
#include <stdio.h>

int main()
{
    char name[3][10] = {"Ram", "Shyam", "Amit"};
    int i;

    for(i = 0; i < 3; i++)
    {
        printf("%s\n", name[i]);
    }

    return 0;
}
```

---

### Output

```
Ram
Shyam
Amit
```

---

### Diagram

```
name[0] -> R a m \0
name[1] -> S h y a m \0
name[2] -> A m i t \0
```

---

## Array with Functions using UDF

### Definition
Arrays can be passed to User Defined Functions (UDF) to perform operations like printing, searching, sorting, and processing data.

---

### Syntax

```c
return_type function_name(data_type array[], int size);
```

---

### Example (Print Array using Function)

```c
#include <stdio.h>

void printArray(int arr[], int n)
{
    int i;
    for(i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }
}

int main()
{
    int a[5] = {10, 20, 30, 40, 50};

    printArray(a, 5);

    return 0;
}
```

---

### Output

```
10 20 30 40 50
```

---

### Diagram

```
Main Array → Function → Output
[10 20 30 40 50] → printArray() → 10 20 30 40 50
```

---

## Use of Arrays in Programming

### Definition
Arrays are used to store multiple values of the same type in a single variable for efficient data handling.

---

### Uses / Applications

- Storing multiple values in a single variable
- Searching data using loops
- Sorting data (Bubble, Selection sort)
- Matrix operations in mathematics
- Storing student records or marks
- Data processing in large programs

---

### Example Use Case

```c
#include <stdio.h>

int main()
{
    int marks[5] = {50, 60, 70, 80, 90};
    int i, sum = 0;

    for(i = 0; i < 5; i++)
    {
        sum = sum + marks[i];
    }

    printf("Total = %d", sum);

    return 0;
}
```

---

### Output

```
Total = 350
```

---

### Diagram

```
marks → [50 | 60 | 70 | 80 | 90]
Sum   → 350
```

## Structures

---

## Concept of Structure

A structure is a user-defined data type in C that allows grouping of different types of variables under a single name. Unlike arrays, structures can store different data types such as int, float, char, etc. together.

Structures are mainly used to represent real-world objects like Student, Employee, Book, etc.

---

### Why Structure is Used?

- To store different data types in one unit
- To represent real-world records
- To manage complex data easily
- To improve program organization

---

### Syntax of Structure

```c
struct structure_name
{
    data_type member1;
    data_type member2;
    data_type member3;
};
```

---

### Example of Structure

```c
struct student
{
    int id;
    char name[20];
    float marks;
};
```

---

### Diagram Representation

```
student
----------------
id     → int
name   → char[20]
marks  → float
----------------
```

---

## Initializations and Declarations

---

## Declaration of Structure Variable

Structure variables are created using struct keyword.

### Syntax

```c
struct structure_name variable_name;
```

---

### Example

```c
struct student s1;
```

---

## Initialization of Structure Variable

Structure variables can be initialized at the time of declaration.

---

### Syntax

```c
struct structure_name variable_name = {value1, value2, value3};
```

---

### Example

```c
struct student s1 = {1, "Rahul", 85.5};
```

---

### Program Example

```c
#include <stdio.h>

struct student
{
    int id;
    char name[20];
    float marks;
};

int main()
{
    struct student s1 = {1, "Rahul", 85.5};

    printf("ID: %d\n", s1.id);
    printf("Name: %s\n", s1.name);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

---

### Output

```
ID: 1
Name: Rahul
Marks: 85.50
```

---

### Diagram

```
s1
----------------
id     → 1
name   → Rahul
marks  → 85.5
----------------
```
## Array with Structures

---

## Array of Structure

### Definition
An array of structure is a collection of structure variables where each element of the array represents a structure. It is used to store multiple records like students, employees, etc.

---

### Syntax

```c
struct structure_name array_name[size];
```

---

### Example

```c
#include <stdio.h>

struct student
{
    int id;
    char name[20];
};

int main()
{
    struct student s[2] = {
        {1, "Ram"},
        {2, "Shyam"}
    };

    int i;

    for(i = 0; i < 2; i++)
    {
        printf("%d %s\n", s[i].id, s[i].name);
    }

    return 0;
}
```

---

### Output

```
1 Ram
2 Shyam
```

---

### Diagram

```
s[0] → id=1, name=Ram
s[1] → id=2, name=Shyam
```

---

## Array within Structure

### Definition
Array within structure means a structure member itself is an array. It is used to store multiple values inside a single structure.

---

### Syntax

```c
struct structure_name
{
    data_type array_name[size];
};
```

---

### Example

```c
#include <stdio.h>

struct student
{
    int id;
    int marks[3];
};

int main()
{
    struct student s1 = {1, {70, 80, 90}};
    int i;

    printf("ID: %d\n", s1.id);

    for(i = 0; i < 3; i++)
    {
        printf("%d ", s1.marks[i]);
    }

    return 0;
}
```

---

### Output

```
ID: 1
70 80 90
```

---

### Diagram

```
student
----------------
id     → 1
marks  → [70 80 90]
----------------
```

---

## UDF with Structures

### Definition
User Defined Functions (UDF) can be used with structures to pass structure variables to functions for processing.

---

### Syntax

```c
return_type function_name(struct structure_name variable);
```

---

### Example

```c
#include <stdio.h>

struct student
{
    int id;
    char name[20];
};

void display(struct student s)
{
    printf("%d %s", s.id, s.name);
}

int main()
{
    struct student s1 = {1, "Rahul"};

    display(s1);

    return 0;
}
```

---

### Output

```
1 Rahul
```

---

### Diagram

```
Main → Structure Data → Function → Output
s1 → display(s1) → print data
```

## Nested Structures

### Definition
A nested structure is a structure inside another structure. It is used to represent complex data in an organized way.

---

### Syntax

```c
struct outer
{
    data_type member1;

    struct inner
    {
        data_type member;
    } inner_var;
};
```

---

### Example

```c
#include <stdio.h>

struct date
{
    int d;
    int m;
    int y;
};

struct student
{
    int id;
    char name[20];
    struct date dob;
};

int main()
{
    struct student s1 = {1, "Rahul", {10, 5, 2005}};

    printf("ID: %d\n", s1.id);
    printf("Name: %s\n", s1.name);
    printf("DOB: %d-%d-%d\n", s1.dob.d, s1.dob.m, s1.dob.y);

    return 0;
}
```

---

### Output

```
ID: 1
Name: Rahul
DOB: 10-5-2005
```

---

### Diagram

```
student
---------------------
id   → 1
name → Rahul
dob
   ├── d → 10
   ├── m → 5
   └── y → 2005
---------------------
```

---

## Introduction to Union

### Definition
A union is a user-defined data type in C where all members share the same memory location. Only one member can store a value at a time.

---

### Syntax

```c
union union_name
{
    data_type member1;
    data_type member2;
};
```

---

### Example

```c
#include <stdio.h>

union data
{
    int i;
    float f;
};

int main()
{
    union data d;

    d.i = 10;
    printf("i = %d\n", d.i);

    d.f = 5.5;
    printf("f = %.2f\n", d.f);

    return 0;
}
```

---

### Output

```
i = 10
f = 5.50
```

---

### Diagram

```
Memory (Shared)
----------------
i  or  f
(one at a time)
----------------
```

---

## Difference Between Structure & Union

| Structure | Union |
|----------|------|
| Each member has separate memory | All members share same memory |
| All members can store values at same time | Only one member can store value at a time |
| Memory usage is high | Memory usage is low |
| Changing one member does not affect others | Changing one member affects others |
| Used for storing multiple data | Used for memory saving |
| Example: student record | Example: multiple data types in same space | 
