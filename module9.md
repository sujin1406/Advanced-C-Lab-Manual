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

#define MAX 5

int stack[MAX], top = -1;

void push(int x) {
    if(top == MAX - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = x;
}

void display() {
    if(top == -1)
        printf("Stack is Empty\n");
    else {
        for(int i = top; i >= 0; i--)
            printf("%d ", stack[i]);
    }
}

int main() {
    push(10);
    push(20);
    push(30);

    printf("Stack elements:\n");
    display();

    return 0;
}
```

Output:
![alt text](ac.9.1.png)



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
#include <stdlib.h>

int max_size = 10;
int top = -1;
float *stack;

void push(float value) {
    if (top >= max_size - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("Pushed: %.2f\n", value);
    }
}

int main() {
    stack = (float *)malloc(max_size * sizeof(float));

    if (stack == NULL) {
        return 1;
    }

    push(10.5);
    push(20.75);
    push(30.12);

    free(stack);

    return 0;
}
```

Output:

![alt text](ac.9.2.png)




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
#include <stdlib.h>


int queue[5];
int front = 0;
int rear = -1;
int i;

void display() {
    if (front > rear) {
        printf("Queue is Empty\n");
    } else {
        printf("Queue elements: ");
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    rear++;
    queue[rear] = 10;
    
    rear++;
    queue[rear] = 20;
    
    rear++;
    queue[rear] = 30;

    display();

    return 0;
}
```

Output:

![alt text](ac.9.3.png)


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
#include <stdlib.h>

int size = 5;
int front = -1;
int rear = -1;
float *queue;

void enqueue(float value) {
    if (rear == size - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
        printf("Inserted %.2f into the queue\n", value);
    }
}

int main() {
    queue = (float *)malloc(size * sizeof(float));

    if (queue == NULL) {
        return 1;
    }

    enqueue(10.55);
    enqueue(20.40);
    enqueue(30.12);

    free(queue);

    return 0;
}
```
Output:

![alt text](ac.9.4.png)

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
#include <stdlib.h>

int size = 5;
int front = -1;
int rear = -1;
float *queue;

void dequeue() {
    if (front == -1) {
        printf("Queue is Empty, no elements to delete\n");
    } else {
        float deleted_element = queue[front];
        printf("Deleted: %.2f\n", deleted_element);
        front++;
        
        if (front > rear) {
            front = -1;
            rear = -1;
        }
    }
}

void enqueue(float value) {
    if (rear == size - 1) {
        printf("Queue Overflow\n");
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
    }
}

int main() {
    queue = (float *)malloc(size * sizeof(float));

    if (queue == NULL) {
        return 1;
    }

    enqueue(15.55);
    enqueue(25.40);

    dequeue();
    dequeue();
    dequeue();

    free(queue);

    return 0;
}
```


Output:

![alt text](ac.9.5.png)


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
