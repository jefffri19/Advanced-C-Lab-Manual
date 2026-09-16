EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```c
#include <stdio.h>

int main() {
    int n;

    printf("Enter a number (71-79): ");
    scanf("%d", &n);

    switch (n) {
        case 71: printf("seventy one\n"); break;
        case 72: printf("seventy two\n"); break;
        case 73: printf("seventy three\n"); break;
        case 74: printf("seventy four\n"); break;
        case 75: printf("seventy five\n"); break;
        case 76: printf("seventy six\n"); break;
        case 77: printf("seventy seven\n"); break;
        case 78: printf("seventy eight\n"); break;
        case 79: printf("seventy nine\n"); break;
        default: printf("Number is out of range (71-79)\n");
    }

    return 0;
}
```




Output:


```
Enter a number (71-79): 74
seventy four
```






Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int count[10] = {0};

    printf("Enter a string of digits: ");
    scanf("%s", a);

    for (int h = 0; a[h] != '\0'; h++) {
        if (a[h] >= '0' && a[h] <= '9')
            count[a[h] - '0']++;
    }

    for (int d = 0; d <= 9; d++) {
        printf("%d ", count[d]);
    }
    printf("\n");

    return 0;
}
```




Output:


```
Enter a string of digits: 112233440
1 2 2 2 2 0 0 0 0 0 
```






Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

char **perms;
int count;

void swap(char *x, char *y) {
    char t = *x;
    *x = *y;
    *y = t;
}

void collect(char *str, int l, int r) {
    if (l == r) {
        perms[count] = (char *)malloc(50);
        strcpy(perms[count], str);
        count++;
        return;
    }
    for (int k = l; k <= r; k++) {
        swap(&str[l], &str[k]);
        collect(str, l + 1, r);
        swap(&str[l], &str[k]);
    }
}

int cmpfunc(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

int main() {
    int n;
    printf("Enter number of strings: ");
    scanf("%d", &n);

    char **s = (char **)malloc(n * sizeof(char *));
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(50 * sizeof(char));
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }

    for (int i = 0; i < n; i++) {
        int len = strlen(s[i]);
        char buf[50];
        strcpy(buf, s[i]);

        int factorial = 1;
        for (int f = 2; f <= len; f++) factorial *= f;

        perms = (char **)malloc(factorial * sizeof(char *));
        count = 0;

        collect(buf, 0, len - 1);
        qsort(perms, count, sizeof(char *), cmpfunc);

        printf("Permutations of %s in lexicographical order:\n", s[i]);
        for (int p = 0; p < count; p++) {
            printf("%s\n", perms[p]);
            free(perms[p]);
        }
        free(perms);
    }

    for (int i = 0; i < n; i++) free(s[i]);
    free(s);

    return 0;
}
```




Output:


```
Enter number of strings: 1
Enter string 1: AB
Permutations of AB in lexicographical order:
AB
BA
```






Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```c
#include <stdio.h>

int main() {
    int n, i, j, min;

    printf("Enter n: ");
    scanf("%d", &n);

    int len = n * 2 - 1;

    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int distTop = i;
            int distBottom = len - i - 1;
            int distLeft = j;
            int distRight = len - j - 1;

            min = distTop;
            if (distBottom < min) min = distBottom;
            if (distLeft < min) min = distLeft;
            if (distRight < min) min = distRight;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:


```
Enter n: 4
4 4 4 4 4 4 4 
4 3 3 3 3 3 4 
4 3 2 2 2 3 4 
4 3 2 1 2 3 4 
4 3 2 2 2 3 4 
4 3 3 3 3 3 4 
4 4 4 4 4 4 4 
```






Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```c
#include <stdio.h>

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result = square();
    printf("Square = %d\n", result);
    return 0;
}
```




Output:


```
Enter a number: 9
Square = 81
```






Result:
Thus, the program is verified successfully



























