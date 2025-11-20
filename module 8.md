## EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

## Aim:
To write a C program print the lowercase English word corresponding to the number

## Algorithm:
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
 
## Program:

```
#include <stdio.h>

int main() {
    int n;

  
    printf("Enter a number: ");
    scanf("%d", &n);


    switch(n) {
        case 5:
            printf("seventy one\n");
            break;

        case 6:
            printf("seventy two\n");
            break;

        case 7:
            printf("seventy three\n");
            break;

        case 8:
            printf("seventy four\n");
            break;

        case 9:
            printf("seventy five\n");
            break;

        case 10:
            printf("seventy six\n");
            break;

        case 11:
            printf("seventy seven\n");
            break;

        case 12:
            printf("seventy eight\n");
            break;

        case 13:
            printf("seventy nine\n");
            break;

        default:
            printf("Greater than 13\n");
    }

    return 0;
}
```




## Output:


<img width="441" height="225" alt="image" src="https://github.com/user-attachments/assets/f9f93406-9f74-4d1b-9ab7-b608dc6b059d" />



## Result:
Thus, the program is verified successfully
 
## EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .

## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.

## Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char str[1000];
    int freq[4] = {0};  

    
    scanf("%s", str);

    for (int i = 0; i < strlen(str); i++) {
        if (str[i] >= '0' && str[i] <= '3') {
            freq[str[i] - '0']++;
        }
    }

    
    for (int i = 0; i < 4; i++) {
        printf("%d ", freq[i]);
       
    }
 

    return 0;
}

```




## Output:


<img width="287" height="254" alt="image" src="https://github.com/user-attachments/assets/6adbc059-e575-40a5-9497-e7cdf1a1f9ae" />







## Result:
Thus, the program is verified successfully

## EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.

## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
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
 
## Program:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>


int cmp(const void *a, const void *b) {
    return strcmp(*(char * const *)a, *(char * const *)b);
}


void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}


int next_permutation(char **s, int n) {
    int i = n - 2;


    while (i >= 0 && strcmp(s[i], s[i+1]) >= 0)
        i--;

    if (i < 0)
        return 0; 
    int j = n - 1;
    while (strcmp(s[j], s[i]) <= 0)
        j--;

  
    swap(&s[i], &s[j]);

   
    int left = i + 1, right = n - 1;
    while (left < right) {
        swap(&s[left], &s[right]);
        left++;
        right--;
    }

    return 1;
}

int main() {
    int n;
    scanf("%d", &n);

    char **s = malloc(n * sizeof(char*));

    for (int i = 0; i < n; i++) {
        s[i] = malloc(100 * sizeof(char));
        scanf("%s", s[i]);
    }

    
    qsort(s, n, sizeof(char*), cmp);

   
    for (int i = 0; i < n; i++)
        printf("%s ", s[i]);
    printf("\n");

    while (next_permutation(s, n)) {
        for (int i = 0; i < n; i++)
            printf("%s ", s[i]);
        printf("\n");
    }

    for (int i = 0; i < n; i++)
        free(s[i]);
    free(s);

    return 0;
}



```




## Output:


<img width="461" height="381" alt="image" src="https://github.com/user-attachments/assets/37bc8eb9-1a3e-4636-924d-5a6ad7c2b680" />






## Result:
Thus, the program is verified successfully
 
## EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.

## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.

## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:

```
#include <stdio.h>
int main()
{
    int n,i,j;
    scanf("%d",&n);
    int size=2*n-1;
    for(i=0;i<size;i++)
    {
        
        for(j=0;j<size;j++)
        {
            int top=i;
            int left=j;
            int bottom=size-1-i;
            int right=size-1-j;
            
            int min=top;
            if(left<min) min=left;
            if(right<min) min=right;
            if(bottom<min) min=bottom;
            
            printf("%d",n-min);
            
            if(j!=size-1) printf(" ");
        }
        printf("\n");
    }
}

```




## Output:


<img width="963" height="631" alt="image" src="https://github.com/user-attachments/assets/b4338158-a004-4cc7-b569-10e1a79f5147" />







## Result:
Thus, the program is verified successfully

## EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

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

## Program:

```
#include <stdio.h>

int square();  

int main() {
    int result;

    result = square();    

    printf("Square = %d\n", result);

    return 0;
}

int square() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    return n * n;  
}


```

## Output:


<img width="342" height="256" alt="image" src="https://github.com/user-attachments/assets/6d242a89-ac14-46fa-ad3b-6242d0426250" />







## Result:
Thus, the program is verified successfully
