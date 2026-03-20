EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

int search(struct Node *head, char target) {
    struct Node *current = head;
    int position = 1;
    while (current != NULL) {
        if (current->data == target) {
            return position;
        }
        current = current->next;
        position++;
    }
    return -1;
}

struct Node* createNode(char val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node *head = createNode('A');
    head->next = createNode('B');
    head->next->next = createNode('C');

    char target = 'B';
    int result = search(head, target);

    if (result != -1) {
        printf("Character %c found at position %d\n", target, result);
    } else {
        printf("Character %c not found\n", target);
    }

    struct Node *temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:

![alt text](ac.10.1.png)



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void insert(struct Node **head, char val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node *temp = *head;
    
    newNode->data = val;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

void display(struct Node *node) {
    while (node != NULL) {
        printf("%c -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;

    insert(&head, 'S');
    insert(&head, 'M');
    insert(&head, 'L');

    display(head);

    struct Node *current = head;
    struct Node *next_node;
    while (current != NULL) {
        next_node = current->next;
        free(current);
        current = next_node;
    }

    return 0;
}
```

Output:

![alt text](ac.10.2.png)

 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *prev;
    struct Node *next;
};

void traverse(struct Node *head) {
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%c <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

struct Node* createNode(char val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

int main() {
    struct Node *head = createNode('S');
    struct Node *second = createNode('J');
    struct Node *third = createNode('N');

    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;

    traverse(head);

    struct Node *current = head;
    struct Node *nextNode;
    while (current != NULL) {
        nextNode = current->next;
        free(current);
        current = nextNode;
    }

    return 0;
}
```

Output:

![alt text](ac.10.3.png)


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, char value) {
    /* 1. Create a new node and allocate memory */
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    struct Node *last = *head;

    /* 2. Set the data of the new node */
    newNode->data = value;
    newNode->next = NULL;

    /* 3. If the list is empty, set the new node as the head */
    if (*head == NULL) {
        newNode->prev = NULL;
        *head = newNode;
        return;
    }

    /* 4. Traverse the list to find the last node */
    while (last->next != NULL) {
        last = last->next;
    }

    /* 5. Set prev pointer to last node and update last node's next */
    last->next = newNode;
    newNode->prev = last;
}

void display(struct Node *node) {
    while (node != NULL) {
        printf("%c <-> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() 
{
    struct Node *head = NULL;

    insert(&head, 'S');
    insert(&head, 'U');
    insert(&head, 'J');

    display(head);

    struct Node *current = head;
    struct Node *nextNode;
    while (current != NULL) {
        nextNode = current->next;
        free(current);
        current = nextNode;
    }
}

    return 0;

Output:

Advanced-C-Lab-Manual/ac.10.4.png


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void deleteNode(struct Node **head, char target) {
    struct Node *current = *head;
    struct Node *prev = NULL;

    if (*head == NULL) {
        printf("Linked list is empty\n");
        return;
    }

    if (current->data == target) {
        *head = current->next;
        free(current);
        printf("Node with data %c deleted from head\n", target);
        return;
    }

    while (current != NULL && current->data != target) {
        prev = current;
        current = current->next;
    }

    if (current != NULL) {
        prev->next = current->next;
        free(current);
        printf("Node with data %c deleted\n", target);
    } else {
        printf("Element %c not present in the list\n", target);
    }
}

void insert(struct Node **head, char val) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = val;
    newNode->next = *head;
    *head = newNode;
}

void display(struct Node *node) {
    while (node != NULL) {
        printf("%c -> ", node->data);
        node = node->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node *head = NULL;

    insert(&head, 'L');
    insert(&head, 'M');
    insert(&head, 'S');

    printf("Original List: ");
    display(head);

    deleteNode(&head, 'M');
    printf("After Deletion: ");
    display(head);

    struct Node *temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

Output:

Advanced-C-Lab-Manual/ac.10.5.png





Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





