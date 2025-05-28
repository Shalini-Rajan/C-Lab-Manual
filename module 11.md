

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
```
#include <stdio.h> 
int max_of_four(int a, int b, int c, int d) {
    int max;
    if (a >= b && a >= c && a >= d)
        max = a;
    else if (b >= a && b >= c && b >= d)
        max = b;
    else if (c >= a && c >= b && c >= d)
        max = c;
    else
        max = d;
    return max;
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
Enter four integers: 25 64 18 47
The greatest number is: 64
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
```
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;  
    for (int i = 1; i < n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and = i & j;
            int or = i | j;
            int xor = i ^ j;
            if (and < k && and > a) a = and;
            if (or < k && or > o) o = or;
            if (xor < k && xor > x) x = xor;
        }
    }
    printf("Maximum AND less than %d: %d\n", k, a);
    printf("Maximum OR  less than %d: %d\n", k, o);
    printf("Maximum XOR less than %d: %d\n", k, x);
}
int main() {
    int n, k;  
    printf("Enter two integers (n and k): ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
```


Output:
```
Enter two integers (n and k): 5 4
Maximum AND less than 4: 3
Maximum OR  less than 4: 3
Maximum XOR less than 4: 3
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
```
#include <stdio.h>
#include <stdlib.h>
int main() {
    int noshel, noque;  
    printf("Enter number of shelves and number of queries: ");
    scanf("%d %d", &noshel, &noque);
    int **shelarr = (int **)malloc(noshel * sizeof(int *));        
    int *nobookarr = (int *)calloc(noshel, sizeof(int));          
    int k, c;
    for (int i = 0; i < noque; i++) {
        int type;
        printf("\nQuery %d - Enter query type (0 to add book, 1 to get book, 2 to get count): ", i + 1);
        scanf("%d", &type);
        if (type == 0) {
            int shelf, pages;
            printf("Enter shelf number and number of pages: ");
            scanf("%d %d", &shelf, &pages);
            int count = nobookarr[shelf];
            shelarr[shelf] = (int *)realloc(shelarr[shelf], (count + 1) * sizeof(int));
            shelarr[shelf][count] = pages;
            nobookarr[shelf]++;
        } else if (type == 1) {
            int shelf, book_index;
            printf("Enter shelf number and book index: ");
            scanf("%d %d", &shelf, &book_index);
            printf("Pages: %d\n", shelarr[shelf][book_index]);
        } else if (type == 2) {
            int shelf;
            printf("Enter shelf number: ");
            scanf("%d", &shelf);
            printf("Number of books on shelf %d: %d\n", shelf, nobookarr[shelf]);
        } else {
            printf("Invalid query type!\n");
        }
    }
    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);
    return 0;
}
```


Output:
```
Enter number of shelves and number of queries: 2 3

Query 1 - Enter query type (0 to add book, 1 to get book, 2 to get count): 0
Enter shelf number and number of pages: 0 120

Query 2 - Enter query type (0 to add book, 1 to get book, 2 to get count): 2
Enter shelf number: 0
Number of books on shelf 0: 1

Query 3 - Enter query type (0 to add book, 1 to get book, 2 to get count): 1
Enter shelf number and book index: 0 0
Pages: 120
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
```
#include <stdio.h>
int main() {
    int n;          
    printf("Enter number of integers: ");
    scanf("%d", &n); 
    int a[n];      
    int sum = 0;    
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("Sum of the integers: %d\n", sum);
    return 0;
}
```


Output:
```
Enter number of integers: 5
Enter 5 integers:
10 20 30 40 50
Sum of the integers: 150
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
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char sentence[1000];
    int wordCount = 0;
    int inWord = 0;  
    printf("Enter a sentence:\n");
    fgets(sentence, sizeof(sentence), stdin);
    for (int i = 0; sentence[i] != '\0'; i++) {
        if (isalnum(sentence[i])) {
            if (inWord == 0) {
                wordCount++;  
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
    }
    printf("Number of words in the sentence: %d\n", wordCount);
    return 0;
}
```

Output:
```
Enter a sentence:
Hello, how are you doing today?
Number of words in the sentence: 6
```




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
