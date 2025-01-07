#include <stdio.h>
#include <string.h>

#define MAX_TASKS 100 //macro 
#define MAX_LENGTH 100 //macro

typedef struct {  //structure
    char task[MAX_LENGTH]; //tasks with maximum length
    int isCompleted; 
} ToDo;  //typedef - wherever struct to be used, ToDo can be used

ToDo tasks[MAX_TASKS]; //tasks must be within the limit
int taskCount = 0;  //initially the task count is 0

void addTask() {  //1) adding task
    if (taskCount >= MAX_TASKS) //if task exceeds maximum limit
    {
        printf("Task list is full!\n");
        return;
    }
    printf("Enter the task: ");
    getchar(); // To consume the leftover newline character
    fgets(tasks[taskCount].task, MAX_LENGTH, stdin);
    tasks[taskCount].task[strcspn(tasks[taskCount].task, "\n")] = '\0'; // Remove newline character
    //strcspn - Here, strcspn() is being used to find the index of the newline character '\n' in the task string
    tasks[taskCount].isCompleted = 0; //incrementing the completed task count
    taskCount++; //increement the task count
    printf("Task added successfully!\n");
}

void viewTasks() {  //view the tasks assigned
    if (taskCount == 0) {  //if there is no task
        printf("No tasks to display!\n");
        return;
    }
    printf("\nTo-Do List:\n");
    for (int i = 0; i < taskCount; i++) { //using loop to display all the tasks
        printf("%d. [%c] %s\n", i + 1, tasks[i].isCompleted ? 'X' : ' ', tasks[i].task); // marks 'X' if the task is completed
    }
}

void markTaskCompleted() {  //if task is completed
    int taskNumber;
    printf("Enter the task number to mark as completed: ");
    scanf("%d", &taskNumber);
    if (taskNumber < 1 || taskNumber > taskCount)//if the entered choice is invalid  
    {
        printf("Invalid task number!\n");
        return;
    }
    tasks[taskNumber - 1].isCompleted = 1; //compiler recognizes as n-1 (index)
    printf("Task marked as completed!\n");
}

void deleteTask() {  //delete the task if done
    int taskNumber;
    printf("Enter the task number to delete: ");
    scanf("%d", &taskNumber);
    if (taskNumber < 1 || taskNumber > taskCount) //if the entered choice is invalid 
    {
        printf("Invalid task number!\n");
        return;
    }
    for (int i = taskNumber - 1; i < taskCount - 1; i++) {
        tasks[i] = tasks[i + 1]; //deleting the task
    }
    taskCount--; //decrement the index
    printf("Task deleted successfully!\n");
}

int main() { //execution starts
    int choice;

    do {  //do while loop
        printf("\nTo-Do List Menu:\n");
        printf("1. Add Task\n");
        printf("2. View Tasks\n");
        printf("3. Mark Task as Completed\n");
        printf("4. Delete Task\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) { //switching choices
            case 1:
                addTask(); //function call
                break; //terminate
            case 2:
                viewTasks(); //function call
                break;//terminate
            case 3:
                markTaskCompleted();  //function call
                break;//terminate
            case 4:
                deleteTask(); //function call
                break; //terminate
            case 5:
                printf("Exiting the program. Goodbye!\n");
                break;//terminate
            default:
                printf("Invalid choice! Please try again.\n");
        }
    } while (choice != 5); //if it is out of choices

    return 0;
}
