# 📚 BCA Semester - 1

## 💻 Problem Solving Methodologies & Programming in C

> **Subject Code:** BCA-101  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 5 : Pointers & File Handling

## Topics

### Pointers

- Concept of Pointers
- Pointer to Variables
- Pointer to Array
- Pointer within Array
- Pointer to Structure
- Pointers within Structure
- Pointer to Pointer
- Use of pointers in Dynamic Programming

---

### File Handling

- Concept of data files
- Importance of file handling
- I/O Operation
- Command line arguments


## Pointers

---

## Concept of Pointers

### Definition
A pointer is a variable that stores the memory address of another variable. Instead of storing actual value, a pointer stores the address where the value is stored in memory.

Pointers are very powerful in C programming because they provide direct memory access.

---

### Why Pointers are Used?

- To access memory directly
- For dynamic memory allocation
- To pass arguments efficiently to functions
- To handle arrays and strings efficiently
- To improve program performance

---

### Memory Concept (Diagram)

```
Variable     Value     Address
--------------------------------
a            10        1000
pointer p    1000      2000
```

Here:
- `a` stores value 10
- `p` stores address of `a`

---

### Syntax of Pointer

```c
data_type *pointer_name;
```

---

### Example

```c
int *p;
```

---

### Pointer Operators

| Operator | Meaning |
|----------|--------|
| &        | Address of operator |
| *        | Value at address (dereference) |

---

### Example Program

```c
#include <stdio.h>

int main()
{
    int a = 10;
    int *p;

    p = &a;

    printf("Value of a = %d\n", a);
    printf("Address of a = %p\n", &a);
    printf("Pointer p stores address = %p\n", p);
    printf("Value using pointer = %d\n", *p);

    return 0;
}
```

---

### Output

```
Value of a = 10
Address of a = (some address)
Pointer p stores address = (same address)
Value using pointer = 10
```

---

## Pointer to Variables

---

### Definition
Pointer to variable means a pointer that stores the address of a normal variable.

It is the simplest and most common use of pointers.

---

### Working Diagram

```
a = 10
|
|---- stored in memory location 1000

p = &a
|
|---- stores 1000 (address of a)
```

---

### Syntax

```c
data_type *pointer;
pointer = &variable;
```

---

### Example Program

```c
#include <stdio.h>

int main()
{
    int a = 20;
    int *p;

    p = &a;

    printf("Value of a = %d\n", a);
    printf("Value using pointer = %d\n", *p);

    return 0;
}
```

---

### Output

```
Value of a = 20
Value using pointer = 20
```

---

### Key Points

- Pointer stores address of variable
- `&` gives address
- `*` gives value at address
- Pointer must be of same data type as variable



## Pointer within Array

### Definition
Pointer within array means using a pointer to access and traverse array elements using pointer arithmetic instead of array indexing.

---

### Concept Diagram

```
Array:   a[0]   a[1]   a[2]   a[3]
         10     20     30     40
          ↑
          p
p+1 → a[1]
p+2 → a[2]
p+3 → a[3]
```

---

### Syntax

```c
data_type *pointer;
pointer = array_name;
```

---

### Example Program

```c
#include <stdio.h>

int main()
{
    int a[5] = {10, 20, 30, 40, 50};
    int *p = a;
    int i;

    for(i = 0; i < 5; i++)
    {
        printf("%d ", *(p + i));
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

### Key Points

- Pointer stores base address of array
- `*(p + i)` is used to access elements
- Faster traversal than normal indexing in some cases

---

## Pointer to Structure

### Definition
A pointer to structure is a pointer that stores the address of a structure variable. It is used to access structure members using pointer.

---

### Concept Diagram

```
Structure s1
-------------
id   = 1
name = Rahul

Pointer p
p → address of s1
```

---

### Syntax

```c
struct structure_name *pointer;
```

---

### Example Program

```c
#include <stdio.h>

struct student
{
    int id;
    char name[20];
};

int main()
{
    struct student s1 = {1, "Rahul"};
    struct student *p;

    p = &s1;

    printf("ID = %d\n", p->id);
    printf("Name = %s\n", p->name);

    return 0;
}
```

---

### Output

```
ID = 1
Name = Rahul
```

---

### Key Points

- `->` operator is used with structure pointer
- Efficient for handling large structures
- Widely used in dynamic memory and linked list

---

## Pointers within Structure

### Definition
Pointers within structure means a structure that contains pointer variables as its members. These pointers can store addresses of variables, arrays, or dynamically allocated memory.

---

### Concept Diagram

```
Structure student
-------------------------
id   → int
name → pointer (char *)
-------------------------

name → stores address of string
```

---

### Syntax

```c
struct structure_name
{
    data_type *pointer_member;
};
```

---

### Example Program

```c
#include <stdio.h>

struct student
{
    int id;
    char *name;
};

int main()
{
    struct student s1;

    s1.id = 1;
    s1.name = "Rahul";

    printf("ID = %d\n", s1.id);
    printf("Name = %s\n", s1.name);

    return 0;
}
```

---

### Output

```
ID = 1
Name = Rahul
```

---

### Key Points

- Structure can store pointer variables
- Useful for dynamic memory allocation
- Helps in efficient memory usage
- Common in advanced data structures like linked list

## Pointer to Pointer

### Definition
A pointer to pointer (double pointer) is a pointer that stores the address of another pointer. It is used to indirectly access data through multiple levels of indirection.

---

### Concept Diagram

```
Value      Pointer        Pointer to Pointer
-----      -------        -------------------
a = 10  →   p = &a   →     pp = &p

pp → p → a
```

---

### Syntax

```c
data_type **pointer_name;
```

---

### Example Program

```c
#include <stdio.h>

int main()
{
    int a = 10;
    int *p;
    int **pp;

    p = &a;
    pp = &p;

    printf("Value of a = %d\n", a);
    printf("Value using p = %d\n", *p);
    printf("Value using pp = %d\n", **pp);

    return 0;
}
```

---

### Output

```
Value of a = 10
Value using p = 10
Value using pp = 10
```

---

### Key Points

- Pointer stores address of variable
- Pointer to pointer stores address of pointer
- Used in dynamic memory and complex data structures
- Access requires multiple dereferencing (`**`)

---

## Use of Pointers in Dynamic Programming

### Definition
Pointers are widely used in dynamic memory allocation, where memory is allocated during runtime instead of compile time.

---

### Why Dynamic Memory is Needed?

- Memory requirement is not fixed
- Efficient memory utilization
- Avoid memory wastage
- Useful for large data structures

---

### Functions Used

| Function  | Purpose |
|----------|--------|
| malloc() | Allocates memory |
| calloc() | Allocates and initializes memory |
| realloc()| Resizes allocated memory |
| free()   | Releases memory |

---

## Dynamic Memory Allocation using Pointer

---

### 1. malloc()

Allocates single block of memory.

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *p;

    p = (int*) malloc(sizeof(int));

    *p = 50;

    printf("%d", *p);

    free(p);

    return 0;
}
```

---

### Output

```
50
```

---

### 2. calloc()

Allocates multiple blocks and initializes them to zero.

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *p;

    p = (int*) calloc(5, sizeof(int));

    printf("%d", p[0]);

    free(p);

    return 0;
}
```

---

### Output

```
0
```

---

### 3. realloc()

Resizes previously allocated memory.

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *p;

    p = (int*) malloc(2 * sizeof(int));

    p = (int*) realloc(p, 5 * sizeof(int));

    p[0] = 100;

    printf("%d", p[0]);

    free(p);

    return 0;
}
```

---

### Output

```
100
```

---

### Key Points

- Pointers are essential for dynamic memory
- Memory is allocated at runtime
- Helps in efficient memory management
- Used in linked list, stack, queue, trees


## File Handling in C

---

## Concept of Data Files

A data file is a collection of data stored on a storage device (like HDD/SSD) permanently. Unlike variables in memory, files retain data even after program execution ends.

In C, files are used to store input/output data permanently.

---

### Types of Files

- **Text File**: Stores data in human-readable form (ASCII)
- **Binary File**: Stores data in machine-readable form (0s and 1s)

---

### File Pointer

C uses a file pointer of type `FILE *` to handle files.

```c
FILE *fp;
```

---

### Diagram

```
Program → FILE Pointer → File (Disk Storage)
```

---

## Importance of File Handling

File handling is important because:

- Data is stored permanently
- Data can be reused later
- Useful for large data storage
- Helps in database-like operations
- Reduces dependency on program memory

---

## I/O Operations in File Handling

File operations are used to create, read, write, append, and close files.

---

## Common File Functions

| Function | Purpose |
|----------|--------|
| fopen()  | Open file |
| fclose() | Close file |
| fprintf()| Write formatted data |
| fscanf() | Read formatted data |
| fgetc()  | Read single character |
| fputc()  | Write single character |
| fgets()  | Read string |
| fputs()  | Write string |

---

## 1. Opening a File (fopen)

### Syntax

```c
FILE *fp;
fp = fopen("filename", "mode");
```

### Modes

| Mode | Meaning |
|------|--------|
| r    | Read |
| w    | Write |
| a    | Append |
| r+   | Read + Write |
| w+   | Write + Read |
| a+   | Append + Read |

---

## Example (Write in File)

```c
#include <stdio.h>

int main()
{
    FILE *fp;

    fp = fopen("test.txt", "w");

    fprintf(fp, "Hello File Handling");

    fclose(fp);

    return 0;
}
```

---

## 2. Reading from File

```c
#include <stdio.h>

int main()
{
    FILE *fp;
    char data[100];

    fp = fopen("test.txt", "r");

    fscanf(fp, "%s", data);

    printf("%s", data);

    fclose(fp);

    return 0;
}
```

---

## 3. Character I/O in File

### Write Character

```c
fputc('A', fp);
```

### Read Character

```c
char ch = fgetc(fp);
```

---

## 4. String I/O in File

### Write String

```c
fputs("Hello World", fp);
```

### Read String

```c
fgets(str, 100, fp);
```

---

## File Handling Diagram

```
Program
   |
   | fopen()
   ↓
FILE Pointer
   |
   ↓
File on Disk
   |
   | read/write
   ↓
Data Stored Permanently
```

---

## Command Line Arguments

---

## Concept

Command line arguments are parameters passed to a program during execution from the command prompt.

They allow users to provide input without using scanf.

---

## Syntax

```c
int main(int argc, char *argv[])
```

### Parameters

- argc → argument count (number of arguments)
- argv → argument vector (array of strings)

---

## Diagram

```
Command Line:
./program 10 20

argc = 3
argv[0] = program
argv[1] = 10
argv[2] = 20
```

---

## Example Program

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[])
{
    int a, b, sum;

    a = atoi(argv[1]);
    b = atoi(argv[2]);

    sum = a + b;

    printf("Sum = %d", sum);

    return 0;
}
```

---

## Output (Run in terminal)

```
./program 10 20
Sum = 30
```

---

## Key Points

- Used for passing input during execution
- No need of scanf()
- argv stores input as string
- atoi() converts string to integer
- Useful in scripting and automation
