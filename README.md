# ToDoList Python Project

This is an extremely simple Python to do list. Inspired by Shaun Halverson https://www.youtube.com/watch?v=aEIHZDv_23U this project allows users to manage their tasks. 
Very beginner-friendly project that demonstrates basic concepts like functions, loops, and error handling in Python.

## Features
- **Add a task**: Users can input tasks, which will be added to the list.
- **View all tasks**: Displays a numbered list of all tasks.
- **Delete a task**: Users can delete a specific task by selecting its number.
- **Exit the program**: Users can exit the application when they are finished.

## How to Run the Project
1. Clone this repository:
   ```bash
   git clone https://github.com/YourUsername/ToDoList.git
2. Navigate to the project directory:
   ```bash
   cd ToDoList
4. Run the program
   ```bash
   python ToDoList_Project.py



## Example Output: 
Welcome to the to do list app :)

    Please select one of the following options
    -----------------------------------------
    1. Add a new task
    2. Delete a task
    3. List tasks
    4. Quit
    Enter your choice: 1
    Please enter the task: Learn Python
    Task 'Learn Python' added to the list.


### **Documented Code**
Here’s a version with comments to make it easier to read!   

```python
# Initialize an empty list to store tasks
tasks = []

# Function to add a task to the to-do list
def addTask():
    task = input("Please enter the task: ")
    tasks.append(task)  # Add the task to the list
    print(f"Task '{task}' added to the list.")

# Function to list all tasks in the to-do list
def listTasks():
    if not tasks:  # Check if the task list is empty
        print("There are no tasks currently.")
    else:
        print("Current Tasks:")
        for index, task in enumerate(tasks):  # Enumerate for numbered output
            print(f"Task #{index}: {task}")

# Function to delete a task from the to-do list
def deleteTask():
    listTasks()  # Display current tasks
    try:
        # Prompt user for the task number to delete
        taskToDelete = int(input("Enter the # of the task to delete: "))
        if taskToDelete >= 0 and taskToDelete < len(tasks):  # Ensure valid input
            removed_task = tasks.pop(taskToDelete)  # Remove the task from the list
            print(f"Task '{removed_task}' was deleted.")
        else:
            print(f"Task #{taskToDelete} was not found.")
    except ValueError:
        print("Invalid input. Please enter a valid task number.")  # Handle invalid input

# Main function to run the to-do list application
if __name__ == "__main__":
    print("Welcome to the to do list app :)")
    
    # Infinite loop for the application menu
    while True:
        print("\nPlease select one of the following options")
        print("-----------------------------------------")
        print("1. Add a new task")
        print("2. Delete a task")
        print("3. List tasks")
        print("4. Quit")
        
        choice = input("Enter your choice: ")  # Get user input
        
        if choice == "1":  # Add a task
            addTask()
        elif choice == "2":  # Delete a task
            deleteTask()
        elif choice == "3":  # List all tasks
            listTasks()
        elif choice == "4":  # Exit the application
            break
        else:
            print("Invalid input. Please try again.")  # Handle invalid menu choices

    print("Goodbye!")
