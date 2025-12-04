Welcome or welcome back to my blog. This is my second blog.

My name is Jayson and this blog is about debugging.

This bolg is going to be about debugging and going over the debugging worksheet.


What is debugging you might ask? Well, debugging is one of the most important skills a programmer can build. It’s the process of finding, understanding, and fixing errors in code so that a program runs the way it’s supposed to. When I debug, I usually follow a simple pattern: read the error, identify where the problem happens, test small changes, and confirm the solution. In my recent debugging worksheet, I went through several code snippets that each had their own challenges. Here’s what I learned from each one.


Snippet 1: 
<br>
<img src="/blog/images/Screenshot 2025-12-02 at 8.47.50 AM.png" alt="code 1"> <br>

What it was supposed to do: <br>
Check a numeric temperature and print whether it is hot, temperate, or cold.

Problems found: <br>

The order and coverage of the conditions leave gaps. For example, temperatures between 0 and 50 are not handled at all.

The cold check elif temperature < 0 is unreachable for many values because earlier elif temperature > 50 will accept most positive numbers.


solved it: <br>

"""<br>
temperature = 75

if temperature > 80: <br>
    print("It's hot")<br>
elif temperature > 50:<br>
    print("It's temperate")<br>
elif temperature >= 0: <br>
    print("It's chilly") <br>
else:<br>
    print("It's cold")

"""
<br>

Snippet 2: <br>
<img src="/blog/images/Screenshot 2025-12-02 at 8.48.33 AM.png" alt="code 2"> <br>

What it was supposed to do: It was supposed to count how many spaces are in the string "Hello, world, my name is".<br>

What went wrong: A character in a string is never an empty string, so the condition is never true. This makes the loop run, but it never increments count, so the final answer becomes
<br>

solved it: <br>
'''<br>
text = "Hello, world, my name is"<br>
count = 0<br>

for char in text:<br>
    if char == " ": <br>
        count += 1<br>

print(count) <br>

''' <br>


Snippet 3: <br>
<img src="/blog/images/Screenshot 2025-12-02 at 8.48.56 AM.png" alt="code 3"> <br>
 What it was supposed to do:
Ask the user for a number n and then, for each number from 1 up to n (exclusive or inclusive depending on intent), print whether that number is even or odd.

Problems found: input() returns a string; range(1, n) will crash unless n is converted to an integer.

The loop was written in broken pieces.

The condition was wrong because % 2 is never negative.

The code said even when it meant odd because the condition was backwards. <br>

solved it: <br>
'''<br>
print("give me a number") <br>
n = int(input()) <br>

for num in range(1, n + 1): <br>
    if num % 2 == 0: <br>
        print(num, "is even.") <br>
    else: <br> 
        print(num, "is odd.") <br>
'''
<br>

Snippet 4: 
<img src="/blog/images/Screenshot 2025-12-02 at 9.08.41 AM.png" alt="code 4"> <br>

What it was supposed to do: <br>
Read an integer, refuse negatives, compute the factorial of a nonnegative integer, and print the result. <br>

Problems found: <br>

The negative number check was wrong.

The indentation was messed up.

The loop didn’t go all the way to the number.

It tried to add strings and numbers together, which doesn’t work.
Edge case: factorial of 0 should be 1; code should handle 0 correctly.
<br> 

solved it: <br>
'''<br>
num = int(input("Enter an integer: "))<br>

if num < 0:br>
    print("No negative numbers.")<br>
else:<br>
    result = 1<br>
    for i in range(1, num + 1):<br>
        result *= i<br>
    print("Factorial of", num, "is", result)<br>
'''
<br>


Conclusion:

Working through all four of these snippets helped me get better at spotting small mistakes. A lot of the problems were simple things like wrong conditions, wrong characters, or forgetting to convert input to numbers. Debugging made me slow down and check the logic step by step instead of guessing. Now I pay more attention to the order of conditions, indentation, and what types my variables actually are. This will make writing and fixing code easier for me in the future.