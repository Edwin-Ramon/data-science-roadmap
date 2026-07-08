<center><h1>CS50 week 0 - Scratch</h1></center>

## AI in programing

```py
from openai import OpenAI #Imports a library from OpenAI, to use abilities from that library

client = OpenAI() #Creates a chat client

prompt = input("Prompt: ") #Allows us to ask

response = client.responses.create( #creates the client's answer in the "response" variable

    input=prompt, #Here comes de question, comes from de "Prompt variable which is a string

    model="gpt-5" #Define model of AI
)

print(response.output_text) #Print the asnwer
```

---

## Introduction to Computer Science

### Computational Thinking

Computer sciences is not just about learning to program, but learning how to think, **solve problems**, and master tools

* How do you represent it?
* How do you process it? 

#### Problem solving

input-> **Black Box** -> output

* Blackbox: the input, generates a output, that resolve a problem

inputs and outputs are represented by zero and one

* Unary: composed by a single digit
* Binary: system all computers understand, the unit is a bit: 0 or  1, those are the only digits available

* Transistor: In real computers, we don't use light bulbs as in the video, but millions of tiny components called transistors.

  * If the transistor is **on**, it allows electricity to flow (representing a 1).

  * If the transistor is **off**, the electricity dissipates (representing a 0).

  * Conclusion: The key to representing complex information isn't making a "smarter" light bulb, but combining thousands or millions of these simple switches to create systems capable of storing and processing much larger numbers.

* Decimal system: contains 10 digits available, **0 through 9**

If you have two bits, you can have four possible combinations (00, 01, 10, 11), allowing you to count up to the number 3. If you add a third bit, the possibilities double again, allowing you to count up to 7.

**Main point**: each time you add a new "bit", you double the number of unique values ​​you can represent.

1 byte = 8 bits (one byte can represent exactly 2^8 = 256), it is the standard size that was historically chosen to represent an individual character.

## ASCII

(American Standard Code for Information Interchange) standard that assigns a specific number to each character (letter, symbol, etc.).

<img src="https://rafaramoneblog.wordpress.com/wp-content/uploads/2017/05/codigo-ascii1-yw.jpg" alt="Code ASCII" width="500">

RGB: digital displays create colors by combining three lights: **red**, **green**, and **blue** (RGB). Each pixel uses a numerical value **(0-255)** to define the intensity of each color, requiring 1 byte per color. With 24 bits per pixel, it's possible to generate more than 16 million distinct colors. Thus, any image is actually a grid of numbers that the computer translates visually.

## Algorithm

 Step by step instructions for solving some problem, is not just representing information, is how you process it (they are basically a sequence of steps or precise instructions given to the computer to solve a problem)

 very algorithm transforms an Input into a desired Output through a defined set of logical steps.
 
 Efficiency: The quality of an algorithm is measured by its efficiency (how it scales).
 
 * Linear (n): Checking items one by one (slow for large data).
 * Logarithmic (log n): Dividing the problem in half repeatedly (highly efficient, e.g., Binary Search).
  
Coding is not just writing lines of text, it is the art of designing efficient algorithms that minimize the number of steps required to reach a solution.

 ### Pseudocode

```
// Algorithm: Binary Search

1. Pick up phone book                  // Initial step: Acquire the data source
2. Open to middle of phone book        // Initial split: Divide the problem in half
3. Look at page                        // Inspect the current data point
4. If person is on page                // Base case: Check if target is found
5.    Call person                      // Success: Execute the desired action
6. Else if person is earlier in book   // Decision step: Is the target in the left half?
7.    Open to middle of left half      // Discard the right half (efficiency optimization)
8.    Go back to line 3                // Loop: Repeat the process with the new section
9. Else if person is later in book     // Decision step: Is the target in the right half?
10.   Open to middle of right half     // Discard the left half (efficiency optimization)
11.   Go back to line 3                // Loop: Repeat the process with the new section
12. Else                               // Case: The target was not found in the book
13.    Quit                            // Terminate: Prevent an infinite loop
```

All the functions are verbs or acctions (Pick up, open to)
Conditionals: Decides the road (if, else if, esle)
Booleans expression: yes or no questions
Loop: cyclical behavior

* Function: reusable code blocks
* Arguments: these are the input data you pass to the function so it can work with data


By using the `define` block, you are defining what that word or action means for the program.
Once defined, that block becomes a function that can be used as many times as you want in the program.

## Key ideas of the week:

* A computer only understands bits (0 and 1).
* Programming consists of transforming inputs into outputs using algorithms.
* Some algorithms are much more efficient than others; choosing the right one is a fundamental skill.