# EX3 Implementation of Tower of Hanoi
## DATE:
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1.Start the program
2.Read the number of disks n
3.Define a recursive function TOH(n, source, temp, destination)
4.If n == 1, move disk from source to destination
5.Otherwise:
6.Move n-1 disks from source to temp using destination
7.Move nth disk from source to destination
8.Move n-1 disks from temp to destination using source
9.Stop the program   

## Program:
```
/*
Program to implement Tower of Hanoi
Developed by: ANUSHARON.S
RegisterNumber:  212222240010
*/

#include<stdio.h>

void TOH(int n, char source, char temp, char dest)
{
    if(n == 1)
    {
        printf("Move disk 1 from %c to %c\n", source, dest);
        return;
    }

    TOH(n-1, source, dest, temp);
    printf("Move disk %d from %c to %c\n", n, source, dest);
    TOH(n-1, temp, source, dest);
}

int main()
{
    int n;

    printf("Enter number of disks: ");
    scanf("%d", &n);

    TOH(n, 'A', 'B', 'C');

    return 0;
}
```

## Output:
<img width="592" height="425" alt="image" src="https://github.com/user-attachments/assets/b0e8086f-db34-40ac-ab43-52a6a340847e" />



## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
