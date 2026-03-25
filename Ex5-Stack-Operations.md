# Ex5 Stack Operations
## DATE:
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1.Start the program
2.Initialize stack and set top = -1
3.Define push() function to insert element into stack
4.Define pop() function to remove element from stack
5.Read elements and perform push/pop operations
6.Display stack elements
7.Stop the program 

## Program:
```
/*
Program to perform push and pop operations using stack
Developed by: ANUSHARON.S
RegisterNumber:  212222240010
*/

#include<stdio.h>

#define MAX 5

int stack[MAX];
int top = -1;

void push(int x)
{
    if(top == MAX - 1)
    {
        printf("Stack Overflow\n");
    }
    else
    {
        stack[++top] = x;
        printf("%d pushed into stack\n", x);
    }
}

void pop()
{
    if(top == -1)
    {
        printf("Stack Underflow\n");
    }
    else
    {
        printf("%d popped from stack\n", stack[top--]);
    }
}

void display()
{
    int i;
    if(top == -1)
    {
        printf("Stack is empty\n");
    }
    else
    {
        printf("Stack elements:\n");
        for(i = top; i >= 0; i--)
        {
            printf("%d\n", stack[i]);
        }
    }
}

int main()
{
    int choice, value;

    do
    {
        printf("\n1.Push\n2.Pop\n3.Display\n4.Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
                printf("Enter value: ");
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
                printf("Exiting...");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while(choice != 4);

    return 0;
}
```

## Output:

<img width="605" height="758" alt="image" src="https://github.com/user-attachments/assets/19f25aeb-d88f-4202-ad9a-c686a6886bd7" />


## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
