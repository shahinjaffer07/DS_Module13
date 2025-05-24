# EX3 Implementation of Tower of Hanoi
## DATE:
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1. Start with n disks on peg A, using pegs B (auxiliary) and C (destination).
2. If n > 0, recursively move the top n-1 disks from A to C using B as auxiliary.
3. Move the remaining largest disk from A to B and print the move.
4. Recursively move the n-1 disks from C to B using A as auxiliary.
5. Repeat until all disks are moved from A to B following the rules.  

## Program:
```
Program to implement Tower of Hanoi
Developed by: SHAHIN J
RegisterNumber: 212223040190

#include<stdio.h>
void TOH(int n,char x,char y,char z)
{
    if(n>0)
  {
      TOH(n-1,x,z,y);
      printf("%c to %c\n",x,y);
      TOH(n-1,z,y,x);
  }
}
int main()
{
   int n=3;
    TOH(n,'A','B','C');
}
```

## Output:
![image](https://github.com/user-attachments/assets/bbee71f8-3422-4f18-bd9a-18f28f3636d2)


## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
