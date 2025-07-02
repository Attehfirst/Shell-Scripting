# Bash Script For Generating a Multiplication Table

Objective: Create a Bash script that generates a multiplication table for a number entered by the user. This project will help you practice using loops, handling user input, and applying conditional logic in Bash scripting.

## Project Description

Your script should prompt the user to enter a number and then ask if they prefer to see a full multiplication table from 1 to 10 or a partial table within a specified range. Based on the user's choice, the script will display the corresponding multiplication table.

## Project Requirements

- **User Input for Number**: The script must first ask the user to input a number for which the multiplication table will be generated.
  
**Choice of Table Range**: Next, ask the user if they want a full multiplication table (1 to 10) or a partial table. If they choose partial, prompt them for the start and end of the range.

**Use of Loops**: Implement the logic to generate the multiplication table using loops. You may use either the list form or C-style for loop based on what’s appropriate.

**Conditional Logic**: Use if-else statements to handle the logic based on the user’s choices (full vs. partial table and valid range input).

**Input Validation**: Ensure that the user enters valid numbers for the multiplication table and the specified range. Provide feedback for invalid inputs and default to a full table if the range is incorrect.

**Readable Output**: Display the multiplication table in a clear and readable format, adhering to the user’s choice of range.

**Comments and Code Quality**: Your script should be well-commented, explaining the purpose of different sections and any important variables or logic used. Ensure the code is neatly formatted for easy readability.

**Example Script Flow**:

1. Prompt the user to enter a number for the multiplication table.
2. Ask if they want a full table or a partial table.
 - If partial, prompt for the start and end numbers of the range.
3. Validate the range inputs and handle invalid or out-of-bound entries.
4. Generate and display the multiplication table according to the specified range.
5.
 Bonus
6. Enhanced User Interaction: Incorporate additional checks or features, like repeating the program for      another number without restarting the script.
7. Creative Display Options: Offer different formatting styles for the table display and let the user        choose.
Below is an example output for a full multiplication:

```
 #!/bin/bash

# Prompt the user to enter a number
read -p "Enter a number to generate its multiplication table: " number

# Using list-form for loop
for i in 1 2 3 4 5 6 7 8 9 10
do
  result=$((number * i))
  echo "$number x $i = $result"
done


# Ask the user for a number
read -p "Enter a number to generate its multiplication table: " number

# Ask if full or partial table is desired
echo -e "\nDo you want a:"
echo "1. Full Table (1 to 10)"
echo "2. Partial Table (custom range)"
read -p "Choose 1 or 2: " choice

if [[ "$choice" == "1" ]]; then
  # Full table using list-form for loop
  for i in 1 2 3 4 5 6 7 8 9 10
  do
    echo "$number x $i = $((number * i))"
  done

elif [[ "$choice" == "2" ]]; then
  # Ask for custom start and end
  read -p "Enter the starting number: " start
  read -p "Enter the ending number: " end

  # Validate input
  if ! [[ "$start" =~ ^[0-9]+$ && "$end" =~ ^[0-9]+$ ]]; then
    echo "❌ Please enter valid numeric values for the range."
    exit 1
  fi

  if (( start > end )); then
    echo "❌ Start must not be greater than end."
    exit 1
  fi

  # Create a list using seq, still within list-form context
  for i in $(seq $start $end)
  do
    echo "$number x $i = $((number * i))"
  done

else
  echo "❌ Invalid choice. Exiting."
  exit 1
fi


# Prompt for the base number
read -p "Enter a number to generate its multiplication table: " number

# Validate the number
if ! [[ "$number" =~ ^[0-9]+$ ]]; then
  echo "❌ Invalid input. Please enter a positive integer."
  exit 1
fi

# Ask for full or partial table
echo -e "\nDo you want a:"
echo "1. Full Table (1 to 10)"
echo "2. Partial Table (custom range)"
read -p "Choose 1 or 2: " choice

# Handle full table
if [[ "$choice" == "1" ]]; then
  echo -e "\nMultiplication Table for $number (1 to 10):"
  echo "-------------------------------------------"
  for i in 1 2 3 4 5 6 7 8 9 10
  do
    echo "$number x $i = $((number * i))"
  done

# Handle partial table
elif [[ "$choice" == "2" ]]; then
  read -p "Enter starting number: " start
  read -p "Enter ending number: " end

  # Validate range input
  if ! [[ "$start" =~ ^[0-9]+$ && "$end" =~ ^[0-9]+$ ]]; then
    echo "❌ Start and end must be positive integers."
    exit 1
  fi

  if (( start > end )); then
    echo "❌ Start number must not be greater than end number."
    exit 1
  fi

  if (( start < 1 || end > 1000 )); then
    echo "⚠️ Please enter a practical range between 1 and 1000."
    exit 1
  fi

  echo -e "\nMultiplication Table for $number ($start to $end):"
  echo "---------------------------------------------------"
  for i in $(seq $start $end)
  do
    echo "$number x $i = $((number * i))"
  done

else
  echo "❌ Invalid choice. Please enter 1 or 2."
  exit 1
fi


```

Objective: Write a Bash script that generates a multiplication table for a given number. The script should prompt the user to enter a number and then display the multiplication table for that number up to 10. Your task is to use both styles of for loops to achieve this: the list form and the C-style form.

Part 1: Using List Form For Loop Prompt the User: First, your script should ask the user to input a number. Use the read command to capture this input into a variable.

Generate Multiplication Table: Use a list form for loop to iterate through the numbers 1 to 10. In each iteration, calculate the product of the user’s number and the iterator variable, then print the result in a clear format.



![image](https://github.com/user-attachments/assets/73304244-4c2b-4894-b919-6dda3899f3fc)

![image](https://github.com/user-attachments/assets/0d898124-78b5-48ea-9ac1-8dd7f8e2bbda)


Part 2: Using C-style For Loop Repeat the Prompt: You don’t need to ask the user again if you’re making this a single script. Just proceed with the C-style loop using the same variable.

Generate Multiplication Table with C-style Loop: Now, write a C-style for loop to achieve the same task as in Part 1. Compare how this approach differs from the list form loop in terms of syntax and clarity.

![image](https://github.com/user-attachments/assets/b9bdb1d1-fee5-4b10-ac82-479de2fcf3cc)



![image](https://github.com/user-attachments/assets/36e700b9-4b1e-4196-aa09-8e1bb5d3b2da)

| Feature                  | List-Form Loop                       | C-Style Loop                                 |
| ------------------------ | ------------------------------------ | -------------------------------------------- |
| Syntax                   | `for i in 1 2 3 4 ...`               | `for (( i=start; i<=end; i++ ))`             |
| Flexibility              | Less flexible (fixed list)           | More flexible (supports expressions)         |
| Readability (simple use) | Clear for fixed ranges               | Clear for dynamic, computed ranges           |
| Performance              | Slightly faster for small fixed sets | Better for large, dynamic or calculated sets |




