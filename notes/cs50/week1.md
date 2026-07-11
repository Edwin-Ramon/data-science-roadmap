<center><h1>CS50 week 1 - C</h1></center>

```c
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
} 
```

* Source code: The human-readable text written in a high-level language.

* Machine code: The binary instructions (0s and 1s) that the computer actually executes.

* Compiler: A program that translates source code into machine code.

**Every time we change de code, we need to recompile it again**

## Escape Sequences

```
\n      # Moves to a new line
\r      # Moves the cursor to the beginning of the current line
\"      # It is used within a text string to print or represent a double quote
\'      #
```

## Technical reference library of the course

https://manual.cs50.io/

---
## Core terminal Commands 

| Command | Description |
| :--- | :--- |
| `ls` | **List:** Shows the files and folders in your current directory. |
| `cd` | **Change Directory:** Moves you into a different folder (e.g., `cd foldername`). |
| `mkdir` | **Make Directory:** Creates a new folder. |
| `rmdir` | **Remove Directory:** Deletes an empty folder. |
| `rm` | **Remove:** Deletes a file. **Warning:** This is permanent! |
| `cp` | **Copy:** Copies a file or directory (e.g., `cp old.c new.c`). |
| `mv` | **Move/Rename:** Renames a file or moves it to a new location. |
| `pwd` | **Print Working Directory:** Tells you exactly which folder you are in. |
| `clear` | **Clear:** Cleans the terminal screen of previous text. |

---

## Conditionals

* Just If example
```c
if (x < y)
{
    printf("x is less than y\n");
}
```

* If else example
```c
if (x < y)
{
    printf("x is less than y\n");
}
else
{ 
    printf("x is not less than y\n");
}
```
* Bigger example
```c
if (x < y)
{
    printf("x is less than y\n");
}
else
{
    if (x > y)
    {
        printf("x is greater than y\n");
    }
    else
    {
        printf("x is equal to y\n");
    }
}
```

or

```c
if (x < y)
{
    printf("x is less than y\n");
}
else if (x > y)
{
    printf("x is greater than y\n");
}
else
{
    printf("x is equal to y\n");
}
```
---

## Operators

| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `=` | Assignment (sets a value) | `x = 10;` |
| `==` | Equality comparison | `if (x == 10)` |
| `!=` | Not equal to | `if (x != 0)` |
| `>` | Greater than | `if (x > 5)` |
| `<` | Less than | `if (x < 5)` |
| `>=` | Greater than or equal to | `if (x >= 10)` |
| `<=` | Less than or equal to | `if (x <= 10)` |

## Types

| Type | Description | Format Specifier |
| :--- | :--- | :--- |
| `bool` | Boolean (true/false) | `%i` |
| `char` | Single character | `%c` |
| `int` | Integer (whole number) | `%i` |
| `long` | Larger integer | `%li` |
| `float` | Floating-point number | `%f` |
| `double` | Larger floating-point | `%f` |
| `string` | Sequence of characters | `%s` |
---

## Loops

### Way 1

```c
int i = 0;
while (i < 3)
{
    printf("Hello\n");
    i++;
}
```
### way 2

```c
for (int i = 0; i < 3; i++)
{
    printf("Hello\n");
}
```
---

### Input validation
```c
#include <stdio.h>
#include <cs50.h>

int main(void)
{
    int n;
    // 1. Input Validation Loop
    while (true)
    {
        n = get_int("What is n?: ");
        if (n >= 0)
        {
            break;    // Exit the loop if n is valid (n >= 0)
        }
    }

    // 2. Execution Loop
    for (int i = 0; i < n; i++)
    {
        printf("Hello\n");
    }
}
```
---


### Define function

```c
#include <cs50.h>
#include <stdio.h>

//The compiler needs to know a function exists before it is called.
void meow(int n); 

int main(void)
{
    // Calling the function
    meow(3);
}

// Definition: The actual code for the function
void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```
---

### Cicle into a cicle

```c
#include <stdio.h>

int main(void)
{
    // For each row
    for (int i = 0; i < 3; i++)
    {
        // For each column
        for (int j = 0; j < 3; j++)
        {
            // Print one brick
            printf("#");
        }
        printf("\n");
    }
}

// It returns this:
###
###
###
```
## Arithmetic Operators

| Operator | Operation | Description |
| :--- | :--- | :--- |
| `+` | Addition | Sums two values |
| `-` | Subtraction | Subtracts one value from another |
| `*` | Multiplication | Multiplies two values |
| `/` | Division | Divides two values |
| `%` | Modulo | Returns the remainder of a division |
---

## Data Types

* int = integer, size= 4 bytes, memory= 32 bits
Rage between: -2^31 - 0 - 2^31-1 (-2 billion to 2 billion)

unsigned (qualifier): It removes the ability to store negative numbers, doubling the positive range (0 to ~4 billion).

* char = single character, size = 1 byte, memory = 8 bits
Rage between: -128 - 0 - 127

* float = real numbers (decimal), size = 4 byte, memory = 32 bits

* double = real numbers (high precision), size = 8 bytes, memory = 64 bits

* void = Placeholder / No return

## Boolean Expressions

### Logical operators

Logical AND `&&` is true if both operators are true, otherwise flase

| X | Y | ``X && Y`` | 
| :--- | :--- | :--- |
| true | true | true | 
| true | false | false |
| false | true | false |
| false | false | false |
 

Logical OR `||` is true if at least one operand is true, otherwise is false

| X | Y | `X OR Y` | 
| :--- | :--- | :--- |
| true | true | true | 
| true | false | true |
| false | true | true |
| false | false | false |

Logical NOT ``!`` inverts the value if its operand

| X | ``!X`` |
| :--- | :--- | 
| true | false |
| false | true |

## Conditional statement

``if``: Executes the code block between ``{}`` only if the expression is true.

``if-else``: Provides two paths. If true, the first block executes; if false, the ``else`` block executes.

### switch Statements

```c
switch (variable) {
    case 1:
        // code
        break;
    case 2:
        // code
        break;
    default:
        // code
}
```
* break: I must use break at the end of each case to prevent "fall-through" (where code execution continues into the next case).

### Ternary operator

``int mayor = (edad >= 18) ? 1 : 0;``

* A condition is evaluated (which can be true or false).

* If the condition is true, "mayor" receives the value 1

* If the condition is false, "mayor" receives the value 0

## Preprocessor Directives (Macros)

Syntax: ``#define NAME value`` (No semicolon at the end)

Macros are replaced before compilation

If you need to change the value (e.g., moving from a 52-card deck to a 32-card deck), you only need to update the ``#define`` at the top of your file. Recompile, and the change propagates everywhere

```c
#define DECKSIZE 52
```