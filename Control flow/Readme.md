# Control flow in Shell Scripting

Control flow statements are the backbone of making decisions in programming. In scripting these statements let your script decide what to do of how to proceed based on conditions, loops, or user inputs.
Bash and other shell interpreters provide control flow statements like
- if-else
- for loops
- while loops and
- case statements to control the flow of execution in your scripts.

 # What is Control Flow?
Control flow directs the order in which commands or instructions are executed in a script. It’s like a roadmap that decides which path to take based on certain conditions or how many times to visit a place.

Let’s examine an if-else statement in Bash to understand how it makes decisions based on user input.

The script below ask for a number and then tells us if the number is positive, negative or zero.

```
#!/bin/bash

read -p "Enter a number: " num

if [ $num -gt 0 ]; then
    echo "The number is positive."
elif [ $num -lt 0 ]; then
    echo "The number is negative."
else
    echo "The number is zero."
fi
```
