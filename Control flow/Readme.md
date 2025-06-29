# Control flow in Shell Scripting

Control flow statements are the backbone of making decisions in programming. In scripting these statements let your script decide what to do of how to proceed based on conditions, loops, or user inputs.
Bash and other shell interpreters provide control flow statements like
- if-else
- for loops
- while loops and
- case statements to control the flow of execution in your scripts.

 ## What is Control Flow?
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

## The Script Breakdown:
`#!/bin/bash:` This line is the shebang. It tells the system the script should be run with the Bash interpreter.

`read -p "Enter a number: " num:` This command asks you, the user, to enter a number. The -p option allows us to display a prompt message on the screen when you execute the script.


Execute the script.

Notice that when you execute the script, it just asks you to enter a number. Even when you type a number and hit enter, it takes the number, but you don’t really see what it does with the number. That is because the `read` command in the script has its own way of taking inputs from the user, and storing the value into a variable passed to the `read` command.

The `read` command is used to capture user input and store it in a variable. When you use `read` followed by a variable name (in the case of our script, num), Bash waits for the user to enter something into the command line `(stdin)`. Once the user presses enter, `read` assigns the input to the variable. Now, let’s make more sense of the script. Update the code to the below and execute:

```
#!/bin/bash
read -p "Enter a number: " num
echo "You have entered the number $num"
```
Notice how we have now used `echo` to return back to the screen `(stdout)` the value stored in the `$num ` variable.

Since we now have something stored in the `$num` variable, we can use control flow to determine what the script executes next.

## if statement
The if statement in Bash scripts allows you to execute commands based on conditions. The basic syntax is:

```
if [ condition ]; then
    commands
fi
```


- **if**: This keyword starts the conditional statement.

- **[ condition ]**: The condition to evaluate. Brackets [ ] are used to enclose the condition being tested.

- **then**: If the condition is true, execute the commands that follow this keyword.

- **fi**: Ends the if statement. It’s basically if spelled backward, indicating the conclusion of the conditional block.

Now let’s bring it into our code.

```
if [ $num -gt 0 ]; then
  echo "The number is positive."
fi
```
The part above tests if the value in $num is greater than 0, then most likely you have entered a positive number. Now update your code to the below.

```
#!/bin/bash
read -p "Enter a number: " num
echo "You have entered the number $num"
if [ $num -gt 0 ]; then
  echo "The number is positive."
fi
```

Notice the keyword -gt in the condition. These are called operators that are used within the condition block to perform numeric comparisons between values.

Run the code and experience the output.

elif statement
After understanding the if statement, we move on to the elif part of control flow in Bash scripts. elif stands for "else if", allowing you to test additional conditions if the previous if conditions were not met. It helps you add more layers of decision-making.

Example:
```
if [ condition1 ]; then
  command1
elif [ condition2 ]; then
  command2
fi
```
 
- **elif:**  This keyword is used right after an if or another elif block. It allows you to specify an alternative condition to test if the previous conditions were false.

- **[ condition2 ]:** The new condition you want to evaluate. Like the if statement, this condition is enclosed in square brackets [ ].

- **then:** If the elif condition is true, execute the commands that follow this keyword.

Now, let’s apply elif to our script to handle a scenario where the entered number might be negative:

```
#!/bin/bash
read -p "Enter a number: " num
echo "You have entered the number $num"
if [ $num -gt 0 ]; then
  echo "The number is positive."
elif [ $num -lt 0 ]; then
  echo "The number is negative."
fi
```

In this updated version of the script:

The `if [ $num -gt 0 ];` then part checks if num is greater than 0 and prints "The number is positive." if true.

If the first condition isn’t met (i.e., the number is not greater than 0), the `elif [ $num -lt 0 ];` then checks if num is less than 0. If this condition is true, it prints "The number is negative."

This way, the script can differentiate between positive and negative numbers, providing specific feedback based on the value of num.

Notice the `-lt` "less than" operator in t

## Task
- Create a file and name it `Control_flow.sh`
- Put the code below and execute the script and experience what happen.

   ![image](https://github.com/user-attachments/assets/ddd9f8f4-1bfd-4a4b-8231-490c6c288471)


![image](https://github.com/user-attachments/assets/db107228-742f-4fc0-a107-9b1d1cd88424)

## FOR LOOP
The for loop is used to iterate over a list of values or a range of numbers. It is particularly useful when you know in advance how many times you need to execute the loop body.

The for loop has two main forms:

List form: Iterates over a list of items

Here is a basic syntax:

```
for item in list1 list2 list3; do
  echo $item
done
```
  
-  **for**: This keyword initiates the loop, signaling the start of a block of code that will repeat.

- **item**: This is a variable that temporarily holds the value of each item in the list as the loop iterates. For each iteration of the loop, **item** takes on the value of the next item in the list, allowing the commands inside the loop to act on this value.

- **in**: This keyword is followed by a list of items that the loop will iterate over. This list can be a series of values, an array, or the output of a command. The loop executes once for each item in this list.

- A semicolon is used to separate the list of items from the **do** keyword that follows. If you place the **do** keyword on the next line, the semicolon is optional.

- **do**: This keyword precedes the block of commands that will be executed for each item in the list. The block can contain one or multiple commands, and it can perform a wide range of actions, from simple echoes to complex conditional logic.

- **done**: This keyword marks the end of the loop. It signifies that all commands in the loop have been executed for each item in the list, and the loop is complete.

Let’s examine a real example:

```
  #!/bin/bash

for i in 1 2 3 4 5
do
  echo "Hello, World! This is message $i"
done
```

In this example:

The loop starts with **for i in 1 2 3 4 5**, meaning the variable **i** will take each value in the list (1, 2, 3, 4, 5) in turn.

For each value of **i**, the loop executes the commands between **do** and **done**.

The command echo **"Hello, World! This is message $i"** prints a greeting along with the current value of **i**. Once **i** has taken each value in the list, the loop ends.

The same code can also be re-written using a range syntax:

```
for i in {1..5}
do
  echo "Counting... $i"
done
```
