## NAME :- Keerthika S
## REGISTER NUMBER :- 212223040093

## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d)
        return a;
    else if (b >= a && b >= c && b >= d)
        return b;
    else if (c >= a && c >= b && c >= d)
        return c;
    else
        return d;
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

## Output:

<img width="303" height="320" alt="437716486-a5485f04-be0f-4e04-9542-60937db8c0b2" src="https://github.com/user-attachments/assets/9c7d7d3a-7576-4169-9954-6caa6b0de4c4" />



## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.

--------------------------------------------------------------------------------------------------------------
 
## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS

## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int maxAND = 0, maxOR = 0, maxXOR = 0;
    for(int i=1;i<=n;i++){
        for(int j=i+1;j<=n;j++){
            if((i & j) < k && (i & j) > maxAND) maxAND = i & j;
            if((i | j) < k && (i | j) > maxOR) maxOR = i | j;
            if((i ^ j) < k && (i ^ j) > maxXOR) maxXOR = i ^ j;
        }
    }
    printf("Maximum AND = %d\n", maxAND);
    printf("Maximum OR = %d\n", maxOR);
    printf("Maximum XOR = %d\n", maxXOR);
}

int main() {
    int n,k;
    printf("Enter n and k: ");
    scanf("%d %d",&n,&k);
    calculate_the_max(n,k);
    return 0;
}

```

## Output:

<img width="308" height="352" alt="437716697-1b7aba2f-60c4-4d0b-8395-3f35c87a78e8" src="https://github.com/user-attachments/assets/e91e7130-465f-400b-b538-3292474ba420" />


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.

--------------------------------------------------------------------------------------------
 
## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
```
#include <stdio.h>

int main() {
    int noshel, noque;
    printf("Enter number of shelves and queries: ");
    scanf("%d %d",&noshel,&noque);

    int shelarr[noshel][100]; // assuming max 100 books per shelf
    int nobookarr[noshel];
    for(int i=0;i<noshel;i++) nobookarr[i]=0;

    int k,c;
    for(int q=0;q<noque;q++){
        int type;
        printf("Enter query type: ");
        scanf("%d",&type);
        if(type == 1){ // add book
            int shel, book;
            printf("Enter shelf number and book: ");
            scanf("%d %d",&shel,&book);
            shelarr[shel][nobookarr[shel]] = book;
            nobookarr[shel]++;
        } else if(type == 2){ // print number of books on a shelf
            int shel;
            printf("Enter shelf number: ");
            scanf("%d",&shel);
            printf("Number of books: %d\n", nobookarr[shel]);
        } else if(type == 3){ // print specific book
            int shel, idx;
            printf("Enter shelf number and book index: ");
            scanf("%d %d",&shel,&idx);
            if(idx<nobookarr[shel])
                printf("Book: %d\n", shelarr[shel][idx]);
            else
                printf("Invalid index\n");
        }
    }
    return 0;
}

```

## Output:

<img width="300" height="227" alt="437716986-24d22216-610e-4198-a72c-2e597dae9afc" src="https://github.com/user-attachments/assets/4fd165a4-a51c-416c-9ba9-541b9e548870" />



## Result:
Thus, the program to write the logic for the requests is verified successfully.

-----------------------------------------------------------------------------------------
 
## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.

## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, sum = 0;
    scanf("%d", &n);
    
    int *arr = (int*)malloc(n * sizeof(int));
    if (arr == NULL) {
        return 1;
    }
    
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    
    printf("%d\n", sum);
    
    free(arr);
    return 0;
}
```

## Output:

<img width="435" height="230" alt="437717069-76837834-4026-4653-b125-5f9225943011" src="https://github.com/user-attachments/assets/b8fd3404-cbab-44b8-a978-aaf5c55969c6" />


 


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.

---------------------------------------------------------------------------------------------------
 
## EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A  SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```
#include <stdio.h>

int main() {
    char sentence[100];
    int i = 0, words = 0;
    int inWord = 0;

    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (sentence[i] != ' ' && sentence[i] != '\n') {
            if (inWord == 0) {
                words++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
        i++;
    }

    printf("The number of words in the sentence is: %d\n", words);

    return 0;
}
```

## Output:

<img width="806" height="609" alt="image" src="https://github.com/user-attachments/assets/9b70b1a4-cbfb-4d87-974c-aa68d727f888" />




## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.

------------------------------------------------------------------------------------
