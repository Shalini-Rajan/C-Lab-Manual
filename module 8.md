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
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    if (scanf("%d", &n) != 1) {
        printf("Invalid input\n");
        return 1;
    }
    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 13:
            printf("seventy three\n");
            break;
        case 14:
            printf("seventy four\n");
            break;
        case 15:
            printf("seventy five\n");
            break;
        case 16:
            printf("seventy six\n");
            break;
        case 17:
            printf("seventy seven\n");
            break;
        case 18:
            printf("seventy eight\n");
            break;
        case 19:
            printf("seventy nine\n");
            break;
        default:
            printf("greater than 13\n");
            break;
    }
    return 0;
}
```





Output:
```
Enter a number: 5
seventy one
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
```
#include <stdio.h>
#include <string.h>
int main() {
    char a[50];
    int i, h, c;
    printf("Enter a string of digits: ");
    scanf("%s", a);
    for (h = 0; h <= 3; h++) {
        c = 0;
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }
        printf("%d ", c);
    }
    for (h = 4; h <= 9; h++) {
        printf("0 ");
    }
    printf("\n");
    return 0;
}
```







Output:
```
Enter a string of digits: 012301230123
3 3 3 3 0 0 0 0 0 0
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
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char **x, char **y) {
    char *temp = *x;
    *x = *y;
    *y = temp;
}
int compare(const void *a, const void *b) {
    return strcmp(*(char **)a, *(char **)b);
}
void permute(char **s, int l, int r) {
    if (l == r) {
        for (int i = 0; i <= r; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
        return;
    }
    for (int i = l; i <= r; i++) {
        if (i != l && strcmp(s[i], s[l]) == 0) continue;
        swap(&s[l], &s[i]);
        permute(s, l + 1, r);
        swap(&s[l], &s[i]); 
    }
}

int main() {
    int n;
    char **s;
    printf("Enter number of strings: ");
    scanf("%d", &n);
    s = (char **)malloc(n * sizeof(char *));
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    for (int i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); 
        if (s[i] == NULL) {
            printf("Memory allocation failed.\n");
            return 1;
        }
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }
    qsort(s, n, sizeof(char *), compare);
    printf("\nPermutations in lexicographical order:\n");
    permute(s, 0, n - 1);
    for (int i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    return 0;
}
```





Output:
```
Input
Enter number of strings: 3
Enter string 1: cat
Enter string 2: bat
Enter string 3: ant
Output
Permutations in lexicographical order:
ant bat cat
ant cat bat
bat ant cat
bat cat ant
cat ant bat
cat bat ant


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
```
#include <stdio.h>
int min(int a, int b) {
    return (a < b) ? a : b;
}
int main() {
    int n, i, j, minDist;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    int len = n * 2 - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
           
            minDist = min(min(i, j), min(len - 1 - i, len - 1 - j));
            printf("%d ", n - minDist);
        }
        printf("\n");
    }
    return 0;
}
```






Output:
```
Input:
Enter the value of n: 4
Output:
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
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
int main() {
    int result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}
```






Output:
Enter a number: 7
Square of the number is: 49







Result:
Thus, the program is verified successfully



























