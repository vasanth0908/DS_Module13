# Ex4 Evaluation of prefix expression
## DATE:
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1.Start the program
2.Initialize an empty stack
3.Read the prefix expression
4.Scan the expression from right to left
5.If operand → push to stack
6.If operator →
   Pop two operands from stack
   Perform the operation
   Push result back to stack
7.Repeat until expression ends
8.Final result will be at top of stack
9.Display the result   

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: ANUSHARON.S
RegisterNumber:  212222240010
*/

#include<stdio.h>
#include<ctype.h>
#include<string.h>

int stack[100];
int top = -1;

void push(int x)
{
    stack[++top] = x;
}

int pop()
{
    return stack[top--];
}

int main()
{
    char prefix[100];
    int i, op1, op2, result;

    printf("Enter prefix expression: ");
    scanf("%s", prefix);

    int len = strlen(prefix);

    for(i = len - 1; i >= 0; i--)
    {
        if(isdigit(prefix[i]))
        {
            push(prefix[i] - '0'); // convert char to int
        }
        else
        {
            op1 = pop();
            op2 = pop();

            switch(prefix[i])
            {
                case '+': push(op1 + op2); break;
                case '-': push(op1 - op2); break;
                case '*': push(op1 * op2); break;
                case '/': push(op1 / op2); break;
            }
        }
    }

    result = pop();

    printf("Result = %d", result);

    return 0;
}
```

## Output:

<img width="463" height="215" alt="image" src="https://github.com/user-attachments/assets/96b48e2f-93f8-4742-980f-a60477f18274" />


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
