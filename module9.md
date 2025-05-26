EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define SIZE 100  
int stack[SIZE];
int top = -1;
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Stack elements (top to bottom):\n");
    for (int i = top; i >= 0; i--) {
        printf("%d\n", stack[i]);
    }
}
void push(int value) {
    if (top == SIZE - 1) {
        printf("Stack overflow! Cannot push %d\n", value);
    } else {
        stack[++top] = value;
        printf("%d pushed to stack.\n", value);
    }
}
void pop() {
    if (top == -1) {
        printf("Stack underflow! Nothing to pop.\n");
    } else {
        printf("%d popped from stack.\n", stack[top--]);
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\nStack Operations Menu:\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Display Stack\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();  
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }
    return 0;
}
```


Output:
```
Stack Operations Menu:
1. Push
2. Pop
3. Display Stack
4. Exit
Enter your choice: 1
Enter value to push: 10
10 pushed to stack.
Enter your choice: 1
Enter value to push: 20
20 pushed to stack.
Enter your choice: 3
Stack elements (top to bottom):
20
10
Enter your choice: 2
20 popped from stack.
Enter your choice: 3
Stack elements (top to bottom):
10
Enter your choice: 4
Exiting program.
```






Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
float stack[SIZE]; 
int top = -1;      
void push(float value) {
    if (top >= SIZE - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed to stack at position %d\n", value, top);
    }
}
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Current Stack (top to bottom):\n");
    for (int i = top; i >= 0; i--) {
        printf("%.2f\n", stack[i]);
    }
}
int main() {
    int choice;
    float value;
    while (1) {
        printf("\nStack Push Menu:\n");
        printf("1. Push Element\n");
        printf("2. Display Stack\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter a floating-point value to push: ");
                scanf("%f", &value);
                push(value);
                break;
            case 2:
                display();
                break;
            case 3:
                printf("Exiting...\n");
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
    return 0;
}
```



Output:
```
Stack Push Menu:
1. Push Element
2. Display Stack
3. Exit
Enter your choice: 1
Enter a floating-point value to push: 12.5
12.50 pushed to stack at position 0

Enter your choice: 1
Enter a floating-point value to push: 7.25
7.25 pushed to stack at position 1

Enter your choice: 2
Current Stack (top to bottom):
7.25
12.50
```





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>
#define SIZE 100 
int queue[SIZE];
int front = -1, rear = -1;
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = value;
    printf("%d enqueued to queue.\n", value);
}
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow! Nothing to dequeue.\n");
        return;
    }
    printf("%d dequeued from queue.\n", queue[front++]);
    if (front > rear) {
        front = rear = -1;
    }
}
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements (front to rear):\n");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}
int main() {
    int choice, value;
    while (1) {
        printf("\nQueue Operations Menu:\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display Queue\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
    return 0;
}
```

Output:
```
Queue Operations Menu:
1. Enqueue
2. Dequeue
3. Display Queue
4. Exit
Enter your choice: 1
Enter value to enqueue: 10
10 enqueued to queue.

Enter your choice: 1
Enter value to enqueue: 20
20 enqueued to queue.

Enter your choice: 3
Queue elements (front to rear):
10 20

Enter your choice: 2
10 dequeued from queue.

Enter your choice: 3
Queue elements (front to rear):
20
```


Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>
#define SIZE 100 
float queue[SIZE];
int front = -1, rear = -1;
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot enqueue %.2f\n", value);
        return;
    }
    if (front == -1) {
        front = 0;
    }
    queue[++rear] = value;
    printf("%.2f enqueued to queue.\n", value);
}
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements (front to rear):\n");
    for (int i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");
}
int main() {
    int choice;
    float value;
    while (1) {
        printf("\nQueue Operations Menu:\n");
        printf("1. Enqueue (Insert)\n");
        printf("2. Display Queue\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter a float value to enqueue: ");
                scanf("%f", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }
    return 0;
}
```



Output:
```
Queue Operations Menu:
1. Enqueue (Insert)
2. Display Queue
3. Exit
Enter your choice: 1
Enter a float value to enqueue: 3.14
3.14 enqueued to queue.

Enter your choice: 1
Enter a float value to enqueue: 2.71
2.71 enqueued to queue.

Enter your choice: 2
Queue elements (front to rear):
3.14 2.71

Enter your choice: 3
Exiting program.
```


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
#include <stdio.h>
#define SIZE 100
int queue[SIZE];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue is empty. No elements to delete.\n");
        return;
    }
    printf("Deleted element: %d\n", queue[front]);
    front++;
    if (front > rear) {
        front = rear = -1;  
    }
}
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
        return;
    }
    if (front == -1) front = 0;
    queue[++rear] = value;
}
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
        return;
    }
    printf("Queue elements: ");
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
}
int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display(); 
    dequeue();  
    display();  
    dequeue();  
    dequeue();  
    dequeue();  
    return 0;
}
```

Output:
Queue elements: 10 20 30 
Deleted element: 10
Queue elements: 20 30 
Deleted element: 20
Deleted element: 30
Queue is empty. No elements to delete.




Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
