# Ex2 Conversion of the infix expression into postfix expression
## DATE:
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start the program
2.Initialize an empty stack for operators
3.Read the infix expression from the user
4.Scan the expression from left to right
5.If operand → add to postfix expression
6.If ‘(’ → push to stack
7.If ‘)’ → pop from stack until ‘(’ is found
8.If operator →
9.Pop operators from stack with higher or equal precedence
10.Push current operator to stack
11.After scanning, pop all remaining operators from stack
12.Display the postfix expression
13.Stop  

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: ANUSHARON.S
RegisterNumber: 212222240010
*/

#include<stdio.h>
#include<ctype.h>

char stack[100];
int top = -1;

void push(char x)
{
    stack[++top] = x;
}

char pop()
{
    return stack[top--];
}

int precedence(char x)
{
    if(x == '+' || x == '-')
        return 1;
    if(x == '*' || x == '/')
        return 2;
    return 0;
}

int main()
{
    char infix[100], postfix[100];
    int i, j = 0;

    printf("Enter infix expression: ");
    scanf("%s", infix);

    for(i = 0; infix[i] != '\0'; i++)
    {
        if(isalnum(infix[i]))  // operand
        {
            postfix[j++] = infix[i];
        }
        else if(infix[i] == '(')
        {
            push(infix[i]);
        }
        else if(infix[i] == ')')
        {
            while(stack[top] != '(')
            {
                postfix[j++] = pop();
            }
            pop(); // remove '('
        }
        else // operator
        {
            while(top != -1 && precedence(stack[top]) >= precedence(infix[i]))
            {
                postfix[j++] = pop();
            }
            push(infix[i]);
        }
    }

    while(top != -1)
    {
        postfix[j++] = pop();
    }

    postfix[j] = '\0';

    printf("Postfix expression: %s", postfix);

    return 0;
}
```

## Output:
<img width="475" height="239" alt="image" src="https://github.com/user-attachments/assets/3c744568-6545-4586-9f64-e6a23e9f0703" />



## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
