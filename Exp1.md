EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

```c
#include <stdio.h>

struct eligible {
    int age;
    char n[50];
};

int main() {
    struct eligible e;

    printf("Enter age: ");
    scanf("%d", &e.age);
    printf("Enter name: ");
    scanf("%s", e.n);

    if (e.age <= 6)
        printf("Vaccine Eligibility: No\n");
    else
        printf("Vaccine Eligibility: Yes\n");

    printf("Age: %d\n", e.age);
    printf("Name: %s\n", e.n);

    return 0;
}
```


Output:

```
Enter age: 25
Enter name: Ramesh
Vaccine Eligibility: Yes
Age: 25
Name: Ramesh
```


Result:
Thus, the program is verified successfully.
