# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number :212224040034
# Date : 18/09/25
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include<stdio.h>
#include<ctype.h>
#include<string.h>
#include<stdlib.h>
#define MAX_EXPRESSION_SIZE 100
int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[5]; // Array to store addresses
    char b[MAX_EXPRESSION_SIZE], d[5], c, srch;
    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i; 
    printf("Given Expression: %s\n", b);
    printf("\nSymbol Table\n");
    printf("Symbol\taddr\ttype\n");
    for (j = 0; j < n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) { 
            if (j == n - 1 || !isalpha(b[j + 1])) { 
                void *p = malloc(sizeof(char));
                add[x] = p; 
                d[x] = c; 
                printf("%c\t%p\tidentifier\n", c, p);
                x++;
            }
        }
    }
    getchar();
    printf("\nThe symbol to be searched: ");
    srch = getchar();
    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address %p\n", srch, add[i]);
            flag = 1;
            break;
        }
    }
    if (flag == 0) {
        printf("Symbol Not Found\n");
    }
    for (i = 0; i < x; i++) {
        free(add[i]);
    }
    return 0;
}

```
# OUTPUT
SEARCH INPUT:
<img width="1385" height="637" alt="Screenshot 2025-09-18 153549" src="https://github.com/user-attachments/assets/48555107-fc0e-46bb-898f-8c9a55e8bf79" />

INPUT CANNOT FIND:

<img width="1280" height="516" alt="Screenshot 2025-09-18 153651" src="https://github.com/user-attachments/assets/ec9d1804-8e74-4e94-967e-ec646eadf70d" />


# RESULT
### The program to implement a symbol table is executed and the output is verified.
