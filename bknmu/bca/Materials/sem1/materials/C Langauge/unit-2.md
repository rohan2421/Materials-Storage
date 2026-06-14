# 📚 BCA Semester - 1

## 💻 Problem Solving Methodologies & Programming in C

> **Subject Code:** BCA-101  
> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 2 : Branching & Looping

## *Branching & Looping*

### *Decision Structure*

- If Statements
  - Simple if Statement
  - if...else Statement
  - Nested if Statement
  - else if Ladder
  - Multiple if Statements

- Switch Statement

- Conditional (Ternary) Operator

### *Looping Structures*

- For Loop

- While Loop

- Do...While Loop

- Nesting of Loops
  - Nested For Loop
  - Nested While Loop
  - Nested Do...While Loop
  - Mixed Nested Loops

### *Jumping Statements*

- Break Statement

- Continue Statement

- Go To Statement

---++-

# Branching & Looping

# Decision Structure

## Introduction

In programming, a **Decision Structure** is used to make decisions based on one or more conditions.

A program normally executes statements sequentially. However, many real-world problems require the program to choose between different actions depending on specific conditions.

Decision structures allow a program to:

- Compare values.
- Test conditions.
- Select alternative actions.
- Control the flow of execution.

---

## Why Decision Structures are Required?

Decision structures help programs:

- Make logical decisions.
- Execute different statements under different conditions.
- Improve flexibility.
- Solve real-world problems.

### Examples

- Checking whether a student passed or failed.
- Determining eligibility for voting.
- Finding the largest number.
- Calculating discounts.

---

# If Statements

## Introduction

The **if statement** is the simplest decision-making statement in C.

It executes a block of code only when a specified condition is true.

---

# 1. Simple If Statement

## Definition

A simple if statement executes a statement or block of statements only if the condition is true.

If the condition is false, the statements inside the if block are skipped.

---

## Syntax

```c
if(condition)
{
    statement1;
    statement2;
}
```

---

## Flow Diagram

```text
        ┌────────────┐
        │ Condition  │
        └──────┬─────┘
               │
         True  │
               ▼
      ┌────────────────┐
      │ Execute Block  │
      └────────────────┘
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int age = 20;

    if(age >= 18)
    {
        printf("Eligible for Voting");
    }

    return 0;
}
```

---

## Output

```text
Eligible for Voting
```

---

## Working

Condition:

```c
age >= 18
```

Result:

```text
20 >= 18 → True
```

Therefore, the if block executes.

---

# 2. if...else Statement

## Definition

The if...else statement is used when there are two possible outcomes.

- If condition is true → if block executes.
- If condition is false → else block executes.

---

## Syntax

```c
if(condition)
{
    statements;
}
else
{
    statements;
}
```

---

## Flow Diagram

```text
            ┌───────────┐
            │ Condition │
            └─────┬─────┘
              True│False
                  │
           ┌──────┴──────┐
           ▼             ▼
      ┌────────┐    ┌────────┐
      │ If     │    │ Else   │
      └────────┘    └────────┘
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int marks = 40;

    if(marks >= 35)
    {
        printf("Pass");
    }
    else
    {
        printf("Fail");
    }

    return 0;
}
```

---

## Output

```text
Pass
```

---

## Working

Condition:

```c
40 >= 35
```

Result:

```text
True
```

Hence the if block executes.

---

# 3. Nested If Statement

## Definition

When an if statement is placed inside another if statement, it is called a Nested If Statement.

Nested if is useful when multiple conditions need to be checked sequentially.

---

## Syntax

```c
if(condition1)
{
    if(condition2)
    {
        statements;
    }
}
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int age = 20;
    int citizen = 1;

    if(age >= 18)
    {
        if(citizen == 1)
        {
            printf("Eligible for Voting");
        }
    }

    return 0;
}
```

---

## Output

```text
Eligible for Voting
```

---

## Working

Condition 1:

```c
age >= 18
```

True

Condition 2:

```c
citizen == 1
```

True

Both conditions are true, so the statement executes.

---

# 4. Else If Ladder

## Definition

The else if ladder is used when multiple conditions must be checked one after another.

The program executes the first condition that becomes true and skips the remaining conditions.

---

## Syntax

```c
if(condition1)
{
    statements;
}
else if(condition2)
{
    statements;
}
else if(condition3)
{
    statements;
}
else
{
    statements;
}
```

---

## Flow Diagram

```text
      Condition1
           │
      True ▼
      Block1

      False
           │
      Condition2
           │
      True ▼
      Block2

      False
           │
      Condition3
           │
      True ▼
      Block3

      False
           │
           ▼
      Else Block
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int marks = 75;

    if(marks >= 90)
    {
        printf("Grade A+");
    }
    else if(marks >= 75)
    {
        printf("Grade A");
    }
    else if(marks >= 50)
    {
        printf("Grade B");
    }
    else
    {
        printf("Fail");
    }

    return 0;
}
```

---

## Output

```text
Grade A
```

---

## Working

Marks = 75

```text
75 >= 90 → False
75 >= 75 → True
```

The second condition becomes true.

Output:

```text
Grade A
```

Remaining conditions are skipped.

---

# 5. Multiple If Statements

## Definition

In Multiple If Statements, each if condition is checked independently.

Unlike else if ladder, every condition is evaluated.

---

## Syntax

```c
if(condition1)
{
    statements;
}

if(condition2)
{
    statements;
}

if(condition3)
{
    statements;
}
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int num = 12;

    if(num > 0)
    {
        printf("Positive\n");
    }

    if(num % 2 == 0)
    {
        printf("Even\n");
    }

    return 0;
}
```

---

## Output

```text
Positive
Even
```

---

## Working

Both conditions are checked separately.

```text
12 > 0      → True
12 % 2 == 0 → True
```

Therefore both statements execute.

---

# Switch Statement

## Definition

The switch statement is used when one variable must be compared against multiple constant values.

It provides an alternative to long else-if ladders.

---

## Syntax

```c
switch(expression)
{
    case value1:
        statements;
        break;

    case value2:
        statements;
        break;

    case value3:
        statements;
        break;

    default:
        statements;
}
```

---

## Components of Switch

### switch

Evaluates an expression.

### case

Represents a possible value.

### break

Terminates the switch block.

### default

Executes if no case matches.

---

## Example

```c
#include<stdio.h>

int main()
{
    int day = 3;

    switch(day)
    {
        case 1:
            printf("Monday");
            break;

        case 2:
            printf("Tuesday");
            break;

        case 3:
            printf("Wednesday");
            break;

        default:
            printf("Invalid Day");
    }

    return 0;
}
```

---

## Output

```text
Wednesday
```

---

## Flow Diagram

```text
          Expression
                │
      ┌─────────┼─────────┐
      ▼         ▼         ▼
   Case1     Case2     Case3
      │         │         │
      └────┬────┴────┬────┘
           ▼
         End
```

---

## Advantages of Switch

- Easy to read.
- Faster than long else-if ladders.
- Improves code clarity.

---

## Limitations of Switch

- Only equality comparisons.
- Case values must be constants.
- Cannot directly use relational operators.

---

# Conditional (Ternary) Operator

## Definition

The Conditional Operator is a shorthand form of if...else.

It is the only operator in C that requires three operands.

---

## Syntax

```c
condition ? expression1 : expression2;
```

---

## Working

```text
Condition True  → expression1
Condition False → expression2
```

---

## Example

```c
#include<stdio.h>

int main()
{
    int a = 10;
    int b = 20;

    int max;

    max = (a > b) ? a : b;

    printf("Maximum = %d", max);

    return 0;
}
```

---

## Output

```text
Maximum = 20
```

---

## Explanation

Condition:

```c
a > b
```

Result:

```text
10 > 20 → False
```

Therefore:

```c
max = b;
```

Output:

```text
20
```

---

# Difference Between if...else and Ternary Operator

| if...else | Ternary Operator |
|------------|------------------|
| Multiple lines | Single line |
| Easy for complex logic | Suitable for simple logic |
| More readable for large programs | More compact |
| Statement based | Expression based |

---

## Example Comparison

### Using if...else

```c
if(a > b)
{
    max = a;
}
else
{
    max = b;
}
```

---

### Using Ternary Operator

```c
max = (a > b) ? a : b;
```

---

# Looping Structures

## Introduction

In programming, a **Loop** is used to execute a block of statements repeatedly until a specified condition becomes false.

Loops help programmers avoid writing the same code multiple times.

Instead of repeating statements manually, a loop can execute them automatically.

---

## Why Loops are Required?

Loops are useful when:

- Printing numbers repeatedly.
- Processing large amounts of data.
- Traversing arrays.
- Creating patterns.
- Performing repetitive calculations.

---

## Advantages of Loops

- Reduces code length.
- Improves readability.
- Saves development time.
- Simplifies maintenance.
- Reduces errors caused by repeated code.

---

# Types of Loops in C

C provides three looping structures:

1. For Loop
2. While Loop
3. Do...While Loop

---

# For Loop

## Definition

The **for loop** is an entry-controlled loop.

The condition is checked before execution of the loop body.

It is generally used when the number of iterations is known in advance.

---

## Syntax

```c
for(initialization; condition; increment/decrement)
{
    statements;
}
```

---

## Components of For Loop

### Initialization

Executed only once at the beginning.

```c
i = 1;
```

---

### Condition

Checked before every iteration.

```c
i <= 5;
```

---

### Increment/Decrement

Updates the loop variable.

```c
i++;
```

---

## Flow Diagram

```text
          Initialization
                 │
                 ▼
           Condition
           True │ False
                │
                ▼
          Execute Body
                │
                ▼
         Increment/
         Decrement
                │
                └─────────► Back to Condition
```

---

## Example 1: Print Numbers 1 to 5

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

---

## Output

```text
1
2
3
4
5
```

---

## Dry Run

| Iteration | i | Condition |
|------------|----|------------|
| 1 | 1 | True |
| 2 | 2 | True |
| 3 | 3 | True |
| 4 | 4 | True |
| 5 | 5 | True |
| 6 | 6 | False |

---

# Example 2: Reverse Counting

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 5; i >= 1; i--)
    {
        printf("%d ", i);
    }

    return 0;
}
```

---

## Output

```text
5 4 3 2 1
```

---

# While Loop

## Definition

A **while loop** is an entry-controlled loop.

The condition is checked before executing the loop body.

If the condition is false initially, the loop body will not execute even once.

---

## Syntax

```c
while(condition)
{
    statements;
}
```

---

## Flow Diagram

```text
            Condition
           True │ False
                │
                ▼
          Execute Body
                │
                ▼
            Update
                │
                └────────► Back to Condition
```

---

## Example 1: Print Numbers 1 to 5

```c
#include<stdio.h>

int main()
{
    int i = 1;

    while(i <= 5)
    {
        printf("%d\n", i);

        i++;
    }

    return 0;
}
```

---

## Output

```text
1
2
3
4
5
```

---

## Dry Run

| Iteration | i | Condition |
|------------|----|------------|
| 1 | 1 | True |
| 2 | 2 | True |
| 3 | 3 | True |
| 4 | 4 | True |
| 5 | 5 | True |
| 6 | 6 | False |

---

# Example 2: Sum of First 5 Numbers

```c
#include<stdio.h>

int main()
{
    int i = 1;
    int sum = 0;

    while(i <= 5)
    {
        sum = sum + i;
        i++;
    }

    printf("%d", sum);

    return 0;
}
```

---

## Output

```text
15
```

---

# Do...While Loop

## Definition

A **do...while loop** is an exit-controlled loop.

The condition is checked after execution of the loop body.

Therefore, the loop executes at least one time regardless of the condition.

---

## Syntax

```c
do
{
    statements;
}
while(condition);
```

---

## Flow Diagram

```text
        Execute Body
              │
              ▼
          Condition
      True │     │ False
           │     ▼
           └──► End
           │
           ▼
     Back to Body
```

---

## Example 1: Print Numbers 1 to 5

```c
#include<stdio.h>

int main()
{
    int i = 1;

    do
    {
        printf("%d\n", i);

        i++;
    }
    while(i <= 5);

    return 0;
}
```

---

## Output

```text
1
2
3
4
5
```

---

# Example 2: Condition False Initially

```c
#include<stdio.h>

int main()
{
    int i = 10;

    do
    {
        printf("%d", i);
    }
    while(i < 5);

    return 0;
}
```

---

## Output

```text
10
```

---

## Explanation

Although:

```c
i < 5
```

is false,

the loop executes once because the condition is checked after execution.

---

# Difference Between While and Do...While

| While Loop | Do...While Loop |
|-------------|----------------|
| Entry Controlled | Exit Controlled |
| Condition Checked First | Condition Checked Last |
| May Execute Zero Times | Executes At Least Once |
| Faster for Conditional Execution | Useful for Menu Programs |

---

# Nesting of Loops

## Definition

When one loop is placed inside another loop, it is called **Nested Looping**.

The outer loop controls how many times the inner loop executes.

---

## Syntax

```c
for(...)
{
    for(...)
    {
        statements;
    }
}
```

---

## Working of Nested Loops

```text
Outer Loop
    └── Inner Loop Executes Completely

Outer Loop Next Iteration
    └── Inner Loop Executes Again
```

---

# Nested For Loop

## Example

```c
#include<stdio.h>

int main()
{
    int i, j;

    for(i = 1; i <= 3; i++)
    {
        for(j = 1; j <= 3; j++)
        {
            printf("%d ", j);
        }

        printf("\n");
    }

    return 0;
}
```

---

## Output

```text
1 2 3
1 2 3
1 2 3
```

---

# Pattern Program Using Nested For Loop

## Example

```c
#include<stdio.h>

int main()
{
    int i, j;

    for(i = 1; i <= 5; i++)
    {
        for(j = 1; j <= i; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

---

## Output

```text
*
* *
* * *
* * * *
* * * * *
```

---

# Nested While Loop

## Example

```c
#include<stdio.h>

int main()
{
    int i = 1;

    while(i <= 3)
    {
        int j = 1;

        while(j <= 3)
        {
            printf("%d ", j);
            j++;
        }

        printf("\n");

        i++;
    }

    return 0;
}
```

---

## Output

```text
1 2 3
1 2 3
1 2 3
```

---

# Nested Do...While Loop

## Example

```c
#include<stdio.h>

int main()
{
    int i = 1;

    do
    {
        int j = 1;

        do
        {
            printf("%d ", j);
            j++;
        }
        while(j <= 3);

        printf("\n");

        i++;
    }
    while(i <= 3);

    return 0;
}
```

---

## Output

```text
1 2 3
1 2 3
1 2 3
```

---

# Mixed Nested Loops

Different types of loops can also be nested.

---

## Example

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 3; i++)
    {
        int j = 1;

        while(j <= 3)
        {
            printf("%d ", j);
            j++;
        }

        printf("\n");
    }

    return 0;
}
```

---

## Output

```text
1 2 3
1 2 3
1 2 3
```

---

# Applications of Nested Loops

Nested loops are commonly used for:

- Pattern Printing
- Matrix Operations
- Table Generation
- Array Traversal
- Searching and Sorting Algorithms

---

# Comparison of Loops

| Feature | For Loop | While Loop | Do...While Loop |
|-----------|-----------|-----------|----------------|
| Control Type | Entry Controlled | Entry Controlled | Exit Controlled |
| Initialization | Inside Loop | Outside Loop | Outside Loop |
| Condition Check | Before Execution | Before Execution | After Execution |
| Executes At Least Once | No | No | Yes |
| Best Used For | Known Iterations | Unknown Iterations | Menu Driven Programs |

---
# Jumping Statements

## Introduction

Normally, a program executes statements sequentially from top to bottom. However, in some situations, we may need to alter the normal flow of execution.

C provides **Jumping Statements** that transfer control from one part of a program to another.

These statements are used to:

- Exit loops prematurely.
- Skip specific iterations.
- Transfer control to another location in the program.

---

## Types of Jumping Statements in C

1. Break Statement
2. Continue Statement
3. Goto Statement

---

# Break Statement

## Definition

The **break statement** is used to immediately terminate a loop or switch statement.

When a break statement is encountered, control exits from the loop or switch and moves to the statement following it.

---

## Syntax

```c
break;
```

---

## Flow Diagram

```text
       Loop Starts
            │
            ▼
      Condition Check
            │
            ▼
      Break Encountered
            │
            ▼
      Exit Loop Immediately
            │
            ▼
      Next Statement
```

---

## Example 1: Break in For Loop

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        if(i == 5)
        {
            break;
        }

        printf("%d ", i);
    }

    return 0;
}
```

---

## Output

```text
1 2 3 4
```

---

## Explanation

Loop Execution:

```text
i = 1 → Print
i = 2 → Print
i = 3 → Print
i = 4 → Print
i = 5 → break
```

When `i` becomes 5, the loop terminates immediately.

---

## Example 2: Break in Switch Statement

```c
#include<stdio.h>

int main()
{
    int choice = 2;

    switch(choice)
    {
        case 1:
            printf("One");
            break;

        case 2:
            printf("Two");
            break;

        case 3:
            printf("Three");
            break;
    }

    return 0;
}
```

---

## Output

```text
Two
```

---

## Why Break is Important in Switch?

Without break:

```c
case 2:
    printf("Two");
```

The execution would continue to the next cases (fall-through behavior).

Break prevents this.

---

## Advantages of Break Statement

- Terminates loops immediately.
- Saves unnecessary iterations.
- Improves efficiency.
- Useful in search operations.

---

# Continue Statement

## Definition

The **continue statement** skips the remaining statements of the current iteration and transfers control to the next iteration of the loop.

Unlike break, continue does not terminate the loop.

---

## Syntax

```c
continue;
```

---

## Flow Diagram

```text
        Loop Iteration
              │
              ▼
      Continue Encountered
              │
              ▼
      Skip Remaining Code
              │
              ▼
      Next Iteration
```

---

## Example 1: Continue in For Loop

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        if(i == 3)
        {
            continue;
        }

        printf("%d ", i);
    }

    return 0;
}
```

---

## Output

```text
1 2 4 5
```

---

## Explanation

Execution:

```text
i = 1 → Print
i = 2 → Print
i = 3 → Continue
i = 4 → Print
i = 5 → Print
```

The value 3 is skipped.

---

## Example 2: Print Odd Numbers Only

```c
#include<stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        if(i % 2 == 0)
        {
            continue;
        }

        printf("%d ", i);
    }

    return 0;
}
```

---

## Output

```text
1 3 5 7 9
```

---

## Explanation

All even numbers are skipped using continue.

---

## Advantages of Continue Statement

- Skips unwanted iterations.
- Simplifies loop logic.
- Reduces nested conditions.
- Improves readability.

---

# Difference Between Break and Continue

| Break Statement | Continue Statement |
|-----------------|-------------------|
| Terminates the loop completely | Skips only current iteration |
| Control exits loop | Control moves to next iteration |
| Used to stop execution | Used to skip execution |
| Applicable in loops and switch | Applicable only in loops |

---

## Example Comparison

### Using Break

```c
for(i = 1; i <= 5; i++)
{
    if(i == 3)
    {
        break;
    }

    printf("%d ", i);
}
```

### Output

```text
1 2
```

---

### Using Continue

```c
for(i = 1; i <= 5; i++)
{
    if(i == 3)
    {
        continue;
    }

    printf("%d ", i);
}
```

### Output

```text
1 2 4 5
```

---

# Goto Statement

## Definition

The **goto statement** transfers program control directly to a labeled statement within the same function.

It provides an unconditional jump from one part of the program to another.

---

## Syntax

```c
goto label;

...

label:
    statements;
```

---

## Components

### goto

Transfers control.

### Label

Destination point for the jump.

---

## Flow Diagram

```text
      Statement
          │
          ▼
       goto Label
          │
          ▼
       Label:
          │
          ▼
      Statements
```

---

## Example 1: Simple Goto

```c
#include<stdio.h>

int main()
{
    goto message;

    printf("This will not execute");

message:

    printf("Hello World");

    return 0;
}
```

---

## Output

```text
Hello World
```

---

## Explanation

Program jumps directly to:

```c
message:
```

Therefore:

```c
printf("This will not execute");
```

is skipped.

---

## Example 2: Using Goto in Looping

```c
#include<stdio.h>

int main()
{
    int i = 1;

start:

    printf("%d ", i);

    i++;

    if(i <= 5)
    {
        goto start;
    }

    return 0;
}
```

---

## Output

```text
1 2 3 4 5
```

---

## Working

```text
Print 1
Jump to start
Print 2
Jump to start
Print 3
Jump to start
Print 4
Jump to start
Print 5
Stop
```

---

# Advantages of Goto Statement

- Simple unconditional jump.
- Useful for exiting deeply nested loops.
- Can simplify certain low-level operations.

---

# Disadvantages of Goto Statement

- Makes code difficult to understand.
- Reduces readability.
- Difficult to debug.
- Creates "Spaghetti Code".
- Modern programming discourages excessive use.

---

## Example of Spaghetti Code

```c
goto A;

A:
goto B;

B:
goto C;

C:
printf("Confusing Code");
```

This type of coding becomes difficult to maintain.

---

# Best Practices

### Use Break

When exiting loops or switch statements.

### Use Continue

When skipping specific iterations.

### Avoid Excessive Goto

Use loops and functions instead whenever possible.

---

# Comparison of Jumping Statements

| Feature | Break | Continue | Goto |
|----------|----------|----------|----------|
| Terminates Loop | Yes | No | No |
| Skips Current Iteration | No | Yes | No |
| Jumps to Label | No | No | Yes |
| Used in Loop | Yes | Yes | Yes |
| Used in Switch | Yes | No | No |
| Readability | High | High | Low |

---

