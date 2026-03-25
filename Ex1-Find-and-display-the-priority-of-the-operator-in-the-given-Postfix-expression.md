# EX 1 Display operator precedence in the infix expression.
## DATE:
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start the program
2.Declare a character array to store the infix expression
3.Read the infix expression from the user
4.Traverse each character of the expression
5.Check if the character is an operator (+, -, *, /, %)
6.Display the precedence of the operator
7.Stop the program 

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: ANUSHARON.S
RegisterNumber:  212222240010


#include<stdio.h>
#include<string.h>

int precedence(char op)
{
    if(op == '+' || op == '-')
        return 1;
    else if(op == '*' || op == '/' || op == '%')
        return 2;
    else
        return 0;
}

int main()
{
    char exp[100];
    int i;

    printf("Enter infix expression: ");
    scanf("%s", exp);

    printf("\nOperator Precedence:\n");

    for(i = 0; exp[i] != '\0'; i++)
    {
        if(exp[i] == '+' || exp[i] == '-' ||
           exp[i] == '*' || exp[i] == '/' ||
           exp[i] == '%')
        {
            printf("%c -> %d\n", exp[i], precedence(exp[i]));
        }
    }

    return 0;
}
*/
```

## Output:
<img width="463" height="315" alt="image" src="https://github.com/user-attachments/assets/674a1cf1-71f9-42d5-afa5-032e482e4b69" />




## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
