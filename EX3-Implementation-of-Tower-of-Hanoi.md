# EX 1 Display operator precedence in the infix expression.
## DATE:
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Initialize a character array ch with the string "+7*45%20".
2. Loop through each character of the string.
3. Check if the current character is an operator (+, -, *, /, %, ^, &, |).
4. Determine the priority of the operator using the priority() function (assumed to be defined elsewhere).
5. Print the operator along with its priority level (Lowest, Second Lowest, Second Highest, or Highest).  

## Program:
```
Program to find and display the priority of the operator in the given Postfix expression
Developed by: SHAHIN J
RegisterNumber:  212223040190

#include <stdio.h>
#include<string.h>

   
int main()
{
   int i,j;
   char ch[100]="+7*45%20";
   
   for(i=0;i<strlen(ch);i++)
   {
   if(ch[i]=='+'||
   ch[i]=='-'||
   ch[i]=='*'||
   ch[i]=='/'||
   ch[i]=='%'||
   ch[i]=='^'||
   ch[i]=='&'||
   ch[i]=='|')
       {
       j=priority(ch[i]);
       switch(j)
       {
           case 1:
             printf("%c  ----> ",ch[i]);
           printf("Lowest Priority\n");
             break;
            case 2:
             printf("%c  ----> ",ch[i]);
           printf("Second Lowest Priority\n");
             break;
            case 3:
             printf("%c  ----> ",ch[i]);
           printf("Second Highest Priority\n"); 
             break;
            case 4:
             printf("%c  ----> ",ch[i]);
           printf("Highest Priority\n");
             break;
       }
       }
   }
   
    return 0;
```

## Output:
![image](https://github.com/user-attachments/assets/bb7a7414-bc53-44a1-9de8-79b579dd53e3)


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
