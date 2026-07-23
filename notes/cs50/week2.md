<center><h1>CS50 week 2 - Arrays</h1></center>

## Debugging

* Pause program execution.
* Step through code line-by-line.
* Examine variable states at specific moments to identify logical errors.

## Compilation Process Steps

| Step | Output / Description |
| :--- | :--- |
| Preprocessing | Processes ``#include`` and ``#define`` macros (converts them to actual source code) |
| Compiling | Translates the preprocessed C code into Assembly code |
| Assembling | Converts assembly code into Binary Machine Code (zeros and ones) |
| Linking | Combines your compiled code with external libraries (like ``cs50.h`` or ``stdio.h``) into one executable.

## Arrays

It is a data structure that allows storing multiple elements of the same type under a single variable name

* Array declarations:
```c
type name[size];
```
* The `type` is what kind of variable each element od the array will be
* the `name` is what you want to call your array
* the `size` is how many elements you would like your array to contain

Example: Using a function with an array

```c
#include <cs50.h>
#include <stdio.h>

// Here prototipe de average function
float average(int length, int numbers[]);

int main(void)
{
    // Constant, number of scores
    const int N = 3;
    // Here the Array is created
    int scores[N];
    // Loop to get 3 scores
    for (int i = 0; i < N; i++)
    {
        scores[i] = get_int("Scores: ");
    }
    // here call the average function, length = N, numbers = scores
    printf("Average: %f\n", average(N, scores));
}
// The function calculate de average of 3 scores
float average(int length, int numbers[])
{
    int sum = 0;
    for (int i = 0; i < length; i++)
    {
        sum += numbers[i];
    }
    return sum / (float) length;
}

```

* **Strings** are actually Arrays of characters (char).
* Every string ends with a special invisible byte called the NUL Terminator (\0) (all bits set to 0).
* The NUL character tells the computer where the string ends in memory.

## Header files

```c
#include <string.h>
```
Function: ``strlen(string)``,  Output Type: int, Returns the length of a string, 
* Example: 
```c
int len = strlen("Hi");
```
---

```c
#include <ctype.h>
```
Function: ``toupper(char)``, Output Type: char, Converts a lowercase character to uppercase.
* Example:
```c
char c = toupper('a');
```
## Cryptography

* **Plaintext**: The original, human-readable message.
* **Ciphertext**: The encrypted, unreadable message.
* **Cipher**: The algorithm used to scramble the plaintext.
* **Key**: A secret parameter used by the cipher to control the scrambling process.

## Functions

A function acts like a **black box** that takes zero or more inputs and returns a single output.

### Why do we use functions?

* **Code Organization**: Keeps main clean and breaks complex problems into smaller, manageable subparts.
* **Simpler Debugging**: Debugging a 10-line function is much easier than sifting through thousands of lines inside main.
* **Reusability / Recycling**: Write a function once and reuse it across multiple programs

### Function Declaration
```c
return-type name(argument-list);
```

* The `return-type` is what kind of variable the function will output.
* The `name` is what you want to call your function.
* The `argument-list` is the comma-separated set of inputs to your function, each of which has a type and a name.

## What are the characteristics of good design?

* Simple
* Easy to read
* efficient

## Examples of efficiency 
```c
// Efficient, is better declare n in the loop so don't have to recomputer strlen again and again
for (int i = 0, n = strlen(string); i < n; i++)

// Not efficient
for (int i = 0; i < strlen(string); i++)
```
Another
```c
// Efficient, months are not going to change, better define them has a constant
const int MONTHS_IN_YEAR = 12;
for (int i = 0; i < MONTHS_IN_YEAR; i++)

// Not efficient
for (int i = 0; i < 12; i++)
```
Another
```c
// Efficient, el "Else" is redundant
int main(void)
{
    if (EXPRESSION)
    {
        return 0;
    }
    return 1;
}

// Not efficient
int main(void)
{
    if (EXPRESSION)
    {
        return 0;
    }
    else
    {
        return 1;
    }
}
```
Another
```c
// Efficient, if the condition is false, its exit inmediately
int main(void)
{
    bool success = true;
    if (!success)
    {
        return 1;
    }
    // Lots of code
    return 0;
}

// Not efficient
int main(void)
{
    bool success = true;
    if (!success)
    {
        // Lots of code
        return 0;
    }
    else
    {
        return 1;
    }
}
```