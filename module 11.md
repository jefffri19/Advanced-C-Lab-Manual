

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```c
#include <stdio.h>

int max_of_four(int n1, int n2, int n3, int n4) {
    int greater;

    if (n1 >= n2 && n1 >= n3 && n1 >= n4)
        greater = n1;
    else if (n2 >= n1 && n2 >= n3 && n2 >= n4)
        greater = n2;
    else if (n3 >= n1 && n3 >= n2 && n3 >= n4)
        greater = n3;
    else
        greater = n4;

    return greater;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}
```

Output:
```
Enter four integers: 12 45 7 33
The greatest number is: 45
```

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```c
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    int i, j;

    for (i = 1; i <= n; i++) {
        for (j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val  = i | j;
            int xor_val = i ^ j;

            if (and_val < k && and_val > a) a = and_val;
            if (or_val < k && or_val > o) o = or_val;
            if (xor_val < k && xor_val > x) x = xor_val;
        }
    }

    printf("%d\n", a);
    printf("%d\n", o);
    printf("%d\n", x);
}

int main() {
    int n, k;

    printf("Enter n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```

Output:
```
Enter n and k: 8 5
4
3
4
```

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```c
#include <stdio.h>

int main() {
    int noshel, noque;

    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    int shelarr[100][100];
    int nobookarr[100];

    for (int i = 0; i < noshel; i++) {
        printf("Enter number of books on shelf %d: ", i + 1);
        scanf("%d", &nobookarr[i]);

        for (int j = 0; j < nobookarr[i]; j++) {
            printf("Enter book %d on shelf %d: ", j + 1, i + 1);
            scanf("%d", &shelarr[i][j]);
        }
    }

    int k, c;

    for (int q = 0; q < noque; q++) {
        printf("Enter query (book index to find): ");
        scanf("%d", &k);

        c = 0;
        int found = 0;

        for (int i = 0; i < noshel && !found; i++) {
            if (k <= c + nobookarr[i]) {
                int position = k - c;
                printf("Book %d is on shelf %d, position %d, value = %d\n",
                       k, i + 1, position, shelarr[i][position - 1]);
                found = 1;
            }
            c += nobookarr[i];
        }

        if (!found)
            printf("Book %d does not exist (only %d books total)\n", k, c);
    }

    return 0;
}
```

Output:
```
Enter number of shelves and queries: 2 1
Enter number of books on shelf 1: 3
Enter book 1 on shelf 1: 10
Enter book 2 on shelf 1: 20
Enter book 3 on shelf 1: 30
Enter number of books on shelf 2: 2
Enter book 1 on shelf 2: 40
Enter book 2 on shelf 2: 50
Enter query (book index to find): 4
Book 4 is on shelf 2, position 1, value = 40
```


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```c
#include <stdio.h>

int main() {
    int n;

    printf("Enter number of integers: ");
    scanf("%d", &n);

    int a[n];
    int sum = 0;

    for (int i = 0; i < n; i++) {
        printf("Enter integer %d: ", i + 1);
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum of the integers = %d\n", sum);

    return 0;
}
```

Output:
```
Enter number of integers: 4
Enter integer 1: 5
Enter integer 2: 10
Enter integer 3: 15
Enter integer 4: 20
Sum of the integers = 50
```

 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```c
#include <stdio.h>

int main() {
    char sentence[200];
    int count = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    int inWord = 0;
    for (int i = 0; sentence[i] != '\0'; i++) {
        if (sentence[i] != ' ' && sentence[i] != '\n' && sentence[i] != '\t') {
            if (inWord == 0) {
                count++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
    }

    printf("Number of words = %d\n", count);

    return 0;
}
```

Output:
```
Enter a sentence: This is a sample sentence
Number of words = 5
```



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
