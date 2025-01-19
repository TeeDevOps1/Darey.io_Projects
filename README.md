## Linux Shell Scripting Capstone Project
# Objective: Create a bash script that generates a multiplication table for a number entered by the user. 
The script should prompt the user to enter a number and then ask if they prefer to see a full multiplication table from 1 to 10 or a partial table within a specified range. Based on the user's choice, the script will display the corresponding multiplication table.

# Here is how i carried out this project.

  1. I created a folder called multiplication_table.sh
  2. The code is written in two types, One is c stle for loops while the other uses list style for loops
  3. Below is the line of code for the project and its explanation.

## Part 1 using C-style for loop

   #!/bin/bash

# Main loop to allow repeated execution
while true; do
    # Prompt the user to enter a number
    echo "Please enter a number for the multiplication table: "
    read number

    # Ask if they want a full or partial table
    echo "Do you want a full multiplication table (1-10) or a partial table? (Enter 'full' or 'partial'): "
    read choice

    if [[ "$choice" == "full" ]]; then
        # Generate and display the full multiplication table (1-10)
        echo "Full multiplication table for $number:"
        for i in {1..10}; do
            result=$((number * i))
            echo "$number x $i = $result"
        done
    elif [[ "$choice" == "partial" ]]; then
        # Prompt for start and end range for the partial table
        echo "Enter the start range: "
        read start
        echo "Enter the end range: "
        read end

        # Generate and display the partial multiplication table
        echo "Partial multiplication table for $number from $start to $end:"
        for ((i = start; i <= end; i++)); do
            result=$((number * i))
            echo "$number x $i = $result"
        done
    else
        # Invalid choice handling which helps to validate input
        echo "Invalid choice. Please run the script again and enter 'full' or 'partial'."
    fi

    # Ask if the user wants to enter another number
    echo "Do you want to generate a table for another number? (yes/no): "
    read repeat

    if [[ "$repeat" != "yes" ]]; then
        echo "Goodbye!"
        break
    fi
done

# To run this script, Save the file as multiplication_table.sh
Run the script with ./multiplication_table.sh.

![mult1](https://github.com/user-attachments/assets/57874118-0552-4366-b8e9-ef40f786fa02)


## Part 2, using List style for loop

#!/bin/bash

# Main loop to allow repeated execution
while true; do
    # Prompt the user to enter a number
    echo "Please enter a number for the multiplication table: "
    read number

    # Ask if they want a full or partial table
    echo "Do you want a full multiplication table (1-10) or a partial table? (Enter 'full' or 'partial'): "
    read choice

    if [[ "$choice" == "full" ]]; then
        # Generate and display the full multiplication table (1-10) using list form
        echo "Full multiplication table for $number:"
        for i in 1 2 3 4 5 6 7 8 9 10; do
            result=$((number * i))
            echo "$number x $i = $result"
        done
    elif [[ "$choice" == "partial" ]]; then
        # Prompt for start and end range for the partial table
        echo "Enter the start range: "
        read start
        echo "Enter the end range: "
        read end

        # Generate and display the partial multiplication table
        echo "Partial multiplication table for $number from $start to $end:"
        for ((i = start; i <= end; i++)); do
            result=$((number * i))
            echo "$number x $i = $result"
        done
    else
        # Invalid choice handling
        echo "Invalid choice. Please run the script again and enter 'full' or 'partial'."
    fi

    # Ask if the user wants to enter another number. Thsi helps the user to run another test for the script without restarting the script.
    echo "Do you want to generate a table for another number? (yes/no): "
    read repeat

    if [[ "$repeat" != "yes" ]]; then
        echo "Goodbye!"
        break
    fi
done

# Explanation of the Changes:
List Form for for Loop: For the full multiplication table, instead of using {1..10}, the loop now explicitly lists the numbers 1 2 3 4 5 6 7 8 9 10 for the multiplication table. This is the "list form" of the for loop.
Partial Table Generation: The partial table still uses the for ((i = start; i <= end; i++)) form, since we are calculating the range dynamically based on the user's input.






 
