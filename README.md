# To-Do List Python Code

# Function to display the to-do list
def show_tasks(tasks):
    if not tasks:
        print("Your to-do list is empty.")
    else:
        print("\nTo-Do List:")
        for idx, task in enumerate(tasks, start=1):
            print(f"{idx}. {task}")
    print()

# Function to add a new task
def add_task(tasks):
    task = input("Enter a new task: ")
    tasks.append(task)
    print(f"'{task}' has been added to your to-do list.\n")

# Function to remove a task
def remove_task(tasks):
    try:
        task_no = int(input("Enter the task number to remove: "))
        if 0 < task_no <= len(tasks):
            removed_task = tasks.pop(task_no - 1)
            print(f"'{removed_task}' has been removed from your to-do list.\n")
        else:
            print("Invalid task number.\n")
    except ValueError:
        print("Please enter a valid number.\n")

# Main function to manage the to-do list
def main():
    tasks = []
    
    while True:
        print("To-Do List Options:")
        print("1. View to-do list")
        print("2. Add a task")
        print("3. Remove a task")
        print("4. Exit")
        
        choice = input("Choose an option (1-4): ")

        if choice == '1':
            show_tasks(tasks)
        elif choice == '2':
            add_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            print("Exiting the to-do list. Goodbye!")
            break
        else:
            print("Invalid choice. Please select a valid option (1-4).\n")

# Run the to-do list application
if __name__ == "__main__":
    main()
