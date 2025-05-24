# Ex2 Conversion of the infix expression into postfix expression
## DATE:
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Initialize a stack and a character array exp with the infix expression (e.g., "3%2+4*(A&B)").
2. Scan each character of the expression:
   If it's an operand, print it.
   If it's an opening parenthesis (, push it onto the stack.
   If it's a closing parenthesis ), pop and print all operators until ( is encountered.
   If it's an operator, pop and print higher or equal priority operators from the stack before pushing it.
3. After scanning, pop and print all remaining operators from the stack.
4. Output the final postfix expression.
5. Terminate the program.

## Program:
```
Program to convert the infix expression into postfix expression
Developed by: SHAHIN J
RegisterNumber:  212223040190

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
    if(top == -1)
        return -1;
    else
        return stack[top--];
}
int priority(char x)
{
    if(x == '(')
        return 0;
    if(x == '&' || x == '|')
        return 1;
    if(x == '+' || x == '-')
        return 2;
    if(x == '*' || x == '/' || x == '%')
        return 3;
    if(x == '^')
        return 4;
    return 0;
}
char IntoPost(char *exp)
{
    char *e, x;
   
   
    e = exp;
    
    while(*e != '\0')
    {
        if(isalnum(*e))
            printf("%c ",*e);
        else if(*e == '(')
            push(*e);
        else if(*e == ')')
        {
            while((x = pop()) != '(')
                printf("%c ", x);
        }
        else
        {
            while(priority(stack[top]) >= priority(*e))
                printf("%c ",pop());
            push(*e);
        }
        e++;
    }
    
    while(top != -1)
    {
        printf("%c ",pop());
    }return 0;
}


int main()
{
    char exp[100]="3%2+4*(A&B)";
    IntoPost(exp);
    return 1;
    
}
```

## Output:
![image](https://github.com/user-attachments/assets/fb475367-39a5-4f3f-9f09-3c63f813c4c6)



## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
