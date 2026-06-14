# 📚 BCA Semester - 1

## 💻 Problem Solving Methodologies & Programming in C

> **Subject Code:** BCA-101  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 3 : Library Functions & User Define Functions

## Topics 

### Library Functions

### Introduction of Library Functions

- Introduction of Library Functions
- Brief overview of Header Files (stdio.h, conio.h, math.h, string.h, stdlib.h, ctype.h, graphics.h, process.h, dos.h)

### Types of Library Functions

- String Functions: strcpy(), strncpy(), strcat(), strncat(), strchr(), strcmp(), strncmp(), strlen(), strstr()
- Mathematical Functions: ceil(), div(), exp(), fabs(), floor(), fmod(), log(), pow(), sqrt()
- Date & Time Functions: clock(), time(), gmtime(), localtime()
- Graphics Functions: initgraph(), closegraph(), arc(), line(), circle(), ellipse(), getx(), putx(), setcolor(), setbkcolor()
- I/O Formatting Functions: printf(), scanf(), getc(), getchar(), gets(), putc(), putchar(), puts()
- Miscellaneous Functions: delay(), clrscr(), isalnum(), isalpha(), isdigit(), islower(), isprint(), isspace(), isupper(), toupper(), tolower()
- Standard Library Functions: abs(), exit(), free(), rand()
- Memory Allocation Functions: malloc(), realloc(), calloc()

### User Defined Functions (UDF)

- Concept of User Defined Functions
- Types of User Defined Functions
- Call by Value & Call by Reference
- Nesting & Recursion
- Storage Classes


## Library Functions

### Introduction of Library Functions

#### What are Library Functions?

Library Functions are pre-defined functions provided by the C language. These functions are already written, tested, and stored in libraries. Instead of writing the same code repeatedly, programmers can directly use these functions by including the required header file.

For example, displaying output on the screen is a common task. Instead of writing code to display each character manually, we use the `printf()` library function.

```c
#include <stdio.h>

int main()
{
    printf("Hello World");
    return 0;
}
```

In the above example, `printf()` is a library function provided by C.

---

#### Why are Library Functions Used?

1. Reduce coding effort.
2. Save development time.
3. Increase program reliability.
4. Avoid rewriting common logic.
5. Make code more readable.
6. Improve program efficiency.
7. Provide standardized solutions.

---

#### Advantages of Library Functions

##### 1. Time Saving

Programmers can directly use existing functions instead of writing them from scratch.

Example:

```c
sqrt(25);
```

Finding square root manually would require multiple calculations, but `sqrt()` performs it instantly.

---

##### 2. Code Reusability

A single function can be used in multiple programs.

Example:

```c
strlen("Programming");
```

The same function can be used wherever string length is needed.

---

##### 3. Reliability

Library functions are already tested and optimized.

Example:

```c
strcmp(str1, str2);
```

This function compares strings accurately without needing custom comparison logic.

---

##### 4. Better Readability

Programs become easier to understand.

Example:

```c
pow(2,3);
```

is easier to understand than writing multiplication logic manually.

---

##### 5. Reduced Errors

Since library functions are tested, chances of bugs are minimized.

---

### Types of Library Functions

C provides many categories of library functions:

1. Input/Output Functions
2. Mathematical Functions
3. String Functions
4. Memory Management Functions
5. Character Handling Functions
6. Graphics Functions
7. Date and Time Functions
8. Utility Functions

---

## Brief Overview of Header Files

### What is a Header File?

A header file contains declarations of functions, macros, constants, and data types.

Header files allow a program to use library functions.

Header files are included using the `#include` directive.

Syntax:

```c
#include <header_file_name>
```

Example:

```c
#include <stdio.h>
```

---

### Why Header Files are Required?

Without header files, the compiler does not know about the functions being used.

Example:

```c
#include <stdio.h>

int main()
{
    printf("Hello");
}
```

Here `stdio.h` tells the compiler that `printf()` exists and how it works.

---

## stdio.h (Standard Input Output Header File)

### Purpose

Provides functions for input and output operations.

### Common Functions

- printf()
- scanf()
- getchar()
- putchar()
- gets()
- puts()

### Example

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter Age: ");
    scanf("%d",&age);

    printf("Age = %d",age);

    return 0;
}
```

### Applications

- Taking keyboard input.
- Displaying output on screen.
- Reading and writing files.

---

## conio.h (Console Input Output Header File)

### Purpose

Provides console-related functions.

### Common Functions

- clrscr()
- getch()
- getche()

### Example

```c
#include <conio.h>

int main()
{
    clrscr();

    printf("Press any key");

    getch();
}
```

### Applications

- Clearing screen.
- Accepting single character input.
- Console control operations.

---

## math.h (Mathematics Header File)

### Purpose

Provides mathematical functions.

### Common Functions

- sqrt()
- pow()
- ceil()
- floor()
- log()
- exp()

### Example

```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%f",sqrt(64));

    return 0;
}
```

Output:

```text
8.000000
```

### Applications

- Engineering calculations.
- Scientific applications.
- Statistical computations.

---

## string.h (String Handling Header File)

### Purpose

Provides functions for string manipulation.

### Common Functions

- strcpy()
- strcat()
- strcmp()
- strlen()
- strstr()

### Example

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char name[] = "Computer";

    printf("%d",strlen(name));

    return 0;
}
```

Output:

```text
8
```

### Applications

- Text processing.
- String comparison.
- String searching.
- String concatenation.

---

## stdlib.h (Standard Library Header File)

### Purpose

Provides utility functions.

### Common Functions

- malloc()
- calloc()
- realloc()
- free()
- rand()
- abs()
- exit()

### Example

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("%d",abs(-50));

    return 0;
}
```

Output:

```text
50
```

### Applications

- Dynamic memory allocation.
- Random number generation.
- Program termination.
- Data conversion.

---

## ctype.h (Character Handling Header File)

### Purpose

Provides character testing and conversion functions.

### Common Functions

- isalpha()
- isdigit()
- isalnum()
- isupper()
- islower()
- toupper()
- tolower()

### Example

```c
#include <stdio.h>
#include <ctype.h>

int main()
{
    printf("%d",isdigit('5'));

    return 0;
}
```

Output:

```text
1
```

### Applications

- Input validation.
- Character classification.
- Case conversion.

---

## graphics.h (Graphics Header File)

### Purpose

Provides graphics programming functions.

### Common Functions

- initgraph()
- line()
- circle()
- arc()
- ellipse()
- closegraph()

### Example

```c
circle(200,200,50);
```

The above function draws a circle with radius 50.

### Applications

- Drawing graphics.
- Educational projects.
- Animation programs.
- Computer graphics applications.

---

## process.h (Process Control Header File)

### Purpose

Provides process management functions.

### Common Functions

- exit()
- spawnl()
- spawnlp()

### Example

```c
#include <process.h>

exit(0);
```

### Applications

- Program termination.
- Process execution.
- Process control.

---

## dos.h (Disk Operating System Header File)

### Purpose

Provides DOS-specific functions.

### Common Functions

- delay()
- sound()
- nosound()

### Example

```c
#include <dos.h>

delay(2000);
```

The above statement pauses program execution for 2 seconds.

### Applications

- Creating delays.
- Hardware interaction.
- DOS-based applications.

---

# Types of Library Functions
## String Functions (C Library Functions)

String functions are predefined functions in C used to perform operations on character arrays (strings). These functions are declared in `string.h` header file.

```c
#include <string.h>
```

---

## 1. strcpy()

### Definition
Copies one string into another string.

### Syntax
```c
strcpy(destination, source);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char src[] = "Hello";
    char dest[20];

    strcpy(dest, src);

    printf("%s", dest);

    return 0;
}
```

### Output
```
Hello
```

---

## 2. strncpy()

### Definition
Copies specified number of characters from source string to destination string.

### Syntax
```c
strncpy(destination, source, n);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char src[] = "Programming";
    char dest[20];

    strncpy(dest, src, 5);
    dest[5] = '\0';

    printf("%s", dest);

    return 0;
}
```

### Output
```
Progr
```

---

## 3. strcat()

### Definition
Appends one string at the end of another string.

### Syntax
```c
strcat(destination, source);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str1[20] = "Hello ";
    char str2[] = "World";

    strcat(str1, str2);

    printf("%s", str1);

    return 0;
}
```

### Output
```
Hello World
```

---

## 4. strncat()

### Definition
Appends first n characters of source string to destination string.

### Syntax
```c
strncat(destination, source, n);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str1[20] = "Hello ";
    char str2[] = "World";

    strncat(str1, str2, 3);

    printf("%s", str1);

    return 0;
}
```

### Output
```
Hello Wor
```

---

## 5. strchr()

### Definition
Finds first occurrence of a character in a string.

### Syntax
```c
strchr(string, character);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Computer";

    printf("%s", strchr(str, 'p'));

    return 0;
}
```

### Output
```
puter
```

---

## 6. strcmp()

### Definition
Compares two strings.

### Syntax
```c
strcmp(string1, string2);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    printf("%d", strcmp("ABC", "ABC"));

    return 0;
}
```

### Output
```
0
```

---

## 7. strncmp()

### Definition
Compares first n characters of two strings.

### Syntax
```c
strncmp(string1, string2, n);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    printf("%d", strncmp("Programming", "Program", 7));

    return 0;
}
```

### Output
```
0
```

---

## 8. strlen()

### Definition
Returns length of string (excluding null character).

### Syntax
```c
strlen(string);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Computer";

    printf("%d", strlen(str));

    return 0;
}
```

### Output
```
8
```

---

## 9. strstr()

### Definition
Finds first occurrence of substring inside a string.

### Syntax
```c
strstr(main_string, sub_string);
```

### Example
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "C Programming";

    printf("%s", strstr(str, "Program"));

    return 0;
}
```

### Output
```
Programming
```

## Mathematical Functions (math.h)

Mathematical functions are used to perform mathematical calculations in C programming. These functions are defined in the `math.h` header file.

```c
#include <math.h>
```

---

## 1. ceil()

### Definition
Returns the smallest integer value greater than or equal to the given number.

### Syntax
```c
double ceil(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", ceil(4.3));
    return 0;
}
```

### Output
```
5.00
```

---

## 2. div()

### Definition
Performs integer division and returns quotient and remainder.

### Syntax
```c
div_t div(int numer, int denom);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    div_t result = div(10, 3);

    printf("Quotient = %d\n", result.quot);
    printf("Remainder = %d\n", result.rem);

    return 0;
}
```

### Output
```
Quotient = 3
Remainder = 1
```

---

## 3. exp()

### Definition
Returns e raised to the power of x (e^x).

### Syntax
```c
double exp(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", exp(2));
    return 0;
}
```

### Output
```
7.39
```

---

## 4. fabs()

### Definition
Returns absolute value of a floating-point number.

### Syntax
```c
double fabs(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", fabs(-5.6));
    return 0;
}
```

### Output
```
5.60
```

---

## 5. floor()

### Definition
Returns largest integer value less than or equal to given number.

### Syntax
```c
double floor(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", floor(4.9));
    return 0;
}
```

### Output
```
4.00
```

---

## 6. fmod()

### Definition
Returns remainder of division of two floating-point numbers.

### Syntax
```c
double fmod(double x, double y);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", fmod(10.5, 3.2));
    return 0;
}
```

### Output
```
0.90
```

---

## 7. log()

### Definition
Returns natural logarithm (base e) of a number.

### Syntax
```c
double log(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", log(10));
    return 0;
}
```

### Output
```
2.30
```

---

## 8. pow()

### Definition
Returns x raised to the power y.

### Syntax
```c
double pow(double x, double y);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", pow(2, 3));
    return 0;
}
```

### Output
```
8.00
```

---

## 9. sqrt()

### Definition
Returns square root of a number.

### Syntax
```c
double sqrt(double x);
```

### Example
```c
#include <stdio.h>
#include <math.h>

int main()
{
    printf("%.2f", sqrt(25));
    return 0;
}
```

### Output
```
5.00
```

---

# Date & Time Functions (time.h)

Date and time functions are used to handle system time, date, and clock-related operations in C programming.

```c
#include <time.h>
```

---

## 1. clock()

### Definition
Returns processor time consumed by the program.

### Syntax
```c
clock_t clock(void);
```

### Example
```c
#include <stdio.h>
#include <time.h>

int main()
{
    printf("%ld", clock());
    return 0;
}
```

### Output
```
(Processor time value - system dependent)
```

---

## 2. time()

### Definition
Returns current system time as number of seconds.

### Syntax
```c
time_t time(time_t *t);
```

### Example
```c
#include <stdio.h>
#include <time.h>

int main()
{
    time_t t;

    time(&t);

    printf("%ld", t);

    return 0;
}
```

### Output
```
(Current timestamp value)
```

---

## 3. gmtime()

### Definition
Converts time into UTC (Greenwich Mean Time).

### Syntax
```c
struct tm *gmtime(const time_t *timer);
```

### Example
```c
#include <stdio.h>
#include <time.h>

int main()
{
    time_t t;
    struct tm *tm_info;

    time(&t);
    tm_info = gmtime(&t);

    printf("UTC Hour: %d", tm_info->tm_hour);

    return 0;
}
```

### Output
```
UTC Hour: (depends on system time)
```

---

## 4. localtime()

### Definition
Converts time into local system time.

### Syntax
```c
struct tm *localtime(const time_t *timer);
```

### Example
```c
#include <stdio.h>
#include <time.h>

int main()
{
    time_t t;
    struct tm *tm_info;

    time(&t);
    tm_info = localtime(&t);

    printf("Local Hour: %d", tm_info->tm_hour);

    return 0;
}
```

### Output
```
Local Hour: (depends on system time)
```

## Graphics Functions (graphics.h)

Graphics functions are used to draw shapes and create graphics in C programming. These functions are mainly used in Turbo C / BGI graphics mode.

```c
#include <graphics.h>
```

---

## 1. initgraph()

### Definition
Initializes the graphics mode.

### Syntax
```c
initgraph(&gd, &gm, "path");
```

### Example
```c
#include <graphics.h>
#include <conio.h>

int main()
{
    int gd = DETECT, gm;

    initgraph(&gd, &gm, "C:\\TC\\BGI");

    getch();
    closegraph();

    return 0;
}
```

---

## 2. closegraph()

### Definition
Closes graphics mode and returns to text mode.

### Syntax
```c
closegraph();
```

---

## 3. arc()

### Definition
Draws an arc (part of a circle).

### Syntax
```c
arc(x, y, start_angle, end_angle, radius);
```

### Example
```c
arc(100, 100, 0, 180, 50);
```

---

## 4. line()

### Definition
Draws a line between two points.

### Syntax
```c
line(x1, y1, x2, y2);
```

### Example
```c
line(50, 50, 150, 150);
```

---

## 5. circle()

### Definition
Draws a circle.

### Syntax
```c
circle(x, y, radius);
```

### Example
```c
circle(200, 200, 50);
```

---

## 6. ellipse()

### Definition
Draws an ellipse shape.

### Syntax
```c
ellipse(x, y, start_angle, end_angle, x_radius, y_radius);
```

### Example
```c
ellipse(200, 200, 0, 360, 100, 50);
```

---

## 7. getx()

### Definition
Returns current x-coordinate of graphics cursor.

### Syntax
```c
int getx();
```

---

## 8. putx()

### Definition
Moves cursor to a specified x-coordinate (used with y coordinate functions).

### Syntax
```c
putpixel(x, y, color);
```

> Note: In Turbo C, pixel plotting uses `putpixel()` instead of putx()

---

## 9. setcolor()

### Definition
Sets the color for drawing graphics.

### Syntax
```c
setcolor(color);
```

### Example
```c
setcolor(RED);
```

---

## 10. setbkcolor()

### Definition
Sets background color of graphics screen.

### Syntax
```c
setbkcolor(color);
```

### Example
```c
setbkcolor(BLUE);
```

---

# I/O Formatting Functions (stdio.h)

I/O functions are used for input and output operations in C programming.

```c
#include <stdio.h>
```

---

## 1. printf()

### Definition
Displays formatted output on screen.

### Syntax
```c
printf("format", variables);
```

### Example
```c
printf("Hello World");
```

---

## 2. scanf()

### Definition
Takes input from user.

### Syntax
```c
scanf("format", &variables);
```

### Example
```c
int a;
scanf("%d", &a);
```

---

## 3. getc()

### Definition
Reads a character from file/input stream.

### Syntax
```c
getc(FILE *stream);
```

---

## 4. getchar()

### Definition
Reads a single character from keyboard.

### Syntax
```c
char getchar();
```

---

## 5. gets()

### Definition
Reads a string from input.

### Syntax
```c
gets(string);
```

---

## 6. putc()

### Definition
Writes a character to file/output stream.

### Syntax
```c
putc(char, FILE *stream);
```

---

## 7. putchar()

### Definition
Displays a single character on screen.

### Syntax
```c
putchar(char);
```

---

## 8. puts()

### Definition
Displays a string on screen.

### Syntax
```c
puts(string);
```

---

# Miscellaneous Functions (ctype.h, conio.h)

Miscellaneous functions are utility functions used for character handling, screen control, and delays.

```c
#include <ctype.h>
#include <conio.h>
```

---

## 1. delay()

### Definition
Stops program execution for given milliseconds.

### Syntax
```c
delay(milliseconds);
```

### Example
```c
delay(1000);
```

---

## 2. clrscr()

### Definition
Clears the screen.

### Syntax
```c
clrscr();
```

---

## 3. isalnum()

### Definition
Checks if character is alphanumeric.

### Syntax
```c
isalnum(ch);
```

---

## 4. isalpha()

### Definition
Checks if character is alphabet.

### Syntax
```c
isalpha(ch);
```

---

## 5. isdigit()

### Definition
Checks if character is digit.

### Syntax
```c
isdigit(ch);
```

---

## 6. islower()

### Definition
Checks if character is lowercase.

### Syntax
```c
islower(ch);
```

---

## 7. isprint()

### Definition
Checks if character is printable.

### Syntax
```c
isprint(ch);
```

---

## 8. isspace()

### Definition
Checks if character is whitespace.

### Syntax
```c
isspace(ch);
```

---

## 9. isupper()

### Definition
Checks if character is uppercase.

### Syntax
```c
isupper(ch);
```

---

## 10. toupper()

### Definition
Converts character to uppercase.

### Syntax
```c
toupper(ch);
```

---

## 11. tolower()

### Definition
Converts character to lowercase.

### Syntax
```c
tolower(ch);
```

## Standard Library Functions (stdlib.h)

Standard library functions are predefined utility functions used for general purpose operations like mathematics, memory handling, random number generation, and program control.

```c
#include <stdlib.h>
```

---

## 1. abs()

### Definition
Returns the absolute value of an integer (removes negative sign).

### Syntax
```c
int abs(int x);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a = -10;

    printf("%d", abs(a));

    return 0;
}
```

### Output
```
10
```

---

## 2. exit()

### Definition
Terminates the program immediately.

### Syntax
```c
void exit(int status);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Before Exit\n");

    exit(0);

    printf("After Exit");

    return 0;
}
```

### Output
```
Before Exit
```

---

## 3. free()

### Definition
Deallocates memory that was previously allocated using malloc, calloc, or realloc.

### Syntax
```c
free(pointer);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) malloc(sizeof(int));

    *ptr = 50;

    printf("%d\n", *ptr);

    free(ptr);

    return 0;
}
```

### Output
```
50
```

---

## 4. rand()

### Definition
Generates a random number.

### Syntax
```c
int rand(void);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("%d", rand());

    return 0;
}
```

### Output
```
(Random number output)
```

---

# Memory Allocation Functions (stdlib.h)

Memory allocation functions are used to allocate and manage dynamic memory during program execution.

---

## 1. malloc()

### Definition
Allocates single block of memory dynamically.

### Syntax
```c
ptr = (cast_type*) malloc(size);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) malloc(5 * sizeof(int));

    *ptr = 100;

    printf("%d", *ptr);

    free(ptr);

    return 0;
}
```

### Output
```
100
```

---

## 2. calloc()

### Definition
Allocates multiple blocks of memory and initializes them to zero.

### Syntax
```c
ptr = (cast_type*) calloc(n, size);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) calloc(5, sizeof(int));

    printf("%d", ptr[0]);

    free(ptr);

    return 0;
}
```

### Output
```
0
```

---

## 3. realloc()

### Definition
Reallocates previously allocated memory to a new size.

### Syntax
```c
ptr = (cast_type*) realloc(ptr, new_size);
```

### Example
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int *ptr;

    ptr = (int*) malloc(2 * sizeof(int));

    ptr = (int*) realloc(ptr, 5 * sizeof(int));

    ptr[0] = 10;

    printf("%d", ptr[0]);

    free(ptr);

    return 0;
}
```

### Output
```
10
```

## User Defined Functions (UDF) – Detailed Theory

---

## Concept of User Defined Function

User Defined Functions (UDF) are functions created by the programmer to perform a specific task. These functions are not provided by the C compiler but are written according to program requirements.

A function is a block of code that runs only when it is called. It helps in breaking a large program into smaller modules.

---

### Why UDF is Important?

- Breaks complex program into small parts (modular programming)
- Improves readability of code
- Makes debugging easier
- Promotes code reusability
- Reduces duplication of code
- Improves program structure

---

### Structure of Function

A function generally has 3 parts:

1. Function Declaration (Prototype)
2. Function Definition
3. Function Call

---

### Function Declaration

It tells compiler about function name, return type, and parameters.

```c
int add(int, int);
```

---

### Function Definition

It contains actual logic of function.

```c
int add(int a, int b)
{
    return a + b;
}
```

---

### Function Call

It is used to execute function.

```c
add(5, 10);
```

---

## Types of User Defined Functions

---

### 1. Function without arguments and without return value

- No input required
- No output returned
- Only performs task

```c
void show()
{
    printf("Hello");
}
```

---

### 2. Function with arguments and without return value

- Input is given
- No return value

```c
void add(int a, int b)
{
    printf("%d", a + b);
}
```

---

### 3. Function without arguments and with return value

- No input required
- Returns output

```c
int getValue()
{
    return 10;
}
```

---

### 4. Function with arguments and with return value

- Input given
- Output returned

```c
int add(int a, int b)
{
    return a + b;
}
```

---

## Advantages of User Defined Functions

- Code reuse
- Easy program maintenance
- Better program structure
- Reduces complexity
- Increases readability
- Easy debugging and testing

---

## Disadvantages of UDF

- Slight overhead due to function calls
- Complex for very small programs
- Requires careful design

---

## Call by Value vs Call by Reference

---

### Call by Value

- Copy of variable is passed
- Original value is not changed

#### Key Points
- Safe method
- Uses more memory (copy created)
- Changes do not affect original variable

---

### Call by Reference

- Address of variable is passed
- Original value is changed

#### Key Points
- Efficient for large data
- Less memory usage
- Direct access to memory

---

## Nesting of Functions

Nesting means calling one function inside another function.

### Example

```c
int add(int a, int b)
{
    return a + b;
}

int main()
{
    printf("%d", add(add(2,3), 5));
}
```

---

## Recursion

Recursion is a process where a function calls itself.

### Types of Recursion

- Direct recursion (function calls itself)
- Indirect recursion (function calls another function which calls it)

### Important Points

- Must have base condition
- Without base condition → infinite loop
- Used in factorial, Fibonacci, tree traversal

---

## Storage Classes in C

Storage classes define:
- Scope (where variable is accessible)
- Lifetime (how long variable exists)
- Visibility

---

### 1. auto

- Default storage class
- Local to function

```c
auto int a = 10;
```

---

### 2. register

- Stored in CPU register
- Faster access
- Cannot use address operator (&)

```c
register int a = 10;
```

---

### 3. static

- Value retains between function calls
- Memory allocated once

```c
static int count = 0;
```

---

### 4. extern

- Used to access global variables from other files
- Memory allocated elsewhere

```c
extern int x;
```

---
