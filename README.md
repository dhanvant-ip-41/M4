# EX-16-LEFT-SHIFT-OPERATION
## AIM
To write a C Program to perform the basic left shift operation for 44 integer number with 3 shifts.

## ALGORITHM
1.	Start the program.
2.	Assign values of a and b as 44 and 3.
3.	Use left shift operator (<<) and shift the value of a three times.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    int num = 44;
    int shift = 3;
    int result;
    result = num << shift;
    printf("Original number: %d\n", num);
    printf("After left shifting by %d positions: %d\n", shift, result);
    return 0;
}
```
## OUTPUT

![445622160-f07d2204-593e-4e45-89ee-fc37a8dbfc08](https://github.com/user-attachments/assets/7653f67f-f0cf-4000-b895-8492b2caa377)








## RESULT
Thus the program to perform the basic left shift operation for 44 integer number with 3 shifts has been executed successfully.




 
 


# EX-17-TWO-NUMBERS-ARE-EQUAL-OR-NOT


## AIM

Write a C Program to check whether the two numbers are equal or not using simple if statement.

## ALGORITHM

1.	Start the program.
2.	Read two numbers.
3.	If first number is equal to second number, display both are equal.
4.	Otherwise display both are not equal.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    int num1, num2;

    printf("Enter first number: ");
    scanf("%d", &num1);

    printf("Enter second number: ");
    scanf("%d", &num2);

    if (num1 == num2) {
        printf("The two numbers are equal.\n");
    }

    if (num1 != num2) {
        printf("The two numbers are not equal.\n");
    }

    return 0;
}

```

## OUTPUT
![445625755-ad284eef-0d31-4d5d-9e08-8b11bea0233a](https://github.com/user-attachments/assets/f2f9168d-47b6-4ef0-be99-2b06f7320d2e)
 
## RESULT

Thus the program to check whether the two numbers are equal or not using simple if statement has been executed successfully
 
 


# EX-18-STRING-LOWERCASE-CONVERSION
## AIM
Write a C Program to convert the given string into lowercase.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using tolower( ) function convert the given string into its lowercase.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <ctype.h>  // for tolower()

int main() {
    char str[100];

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  // safer than gets()

    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = tolower(str[i]);
    }

    printf("Lowercase string: %s\n", str);

    return 0;
}

```
## OUTPUT

![445626369-975ea7c8-d71b-4e43-974d-1eae1af07ce1](https://github.com/user-attachments/assets/428aaa81-026c-453c-8a05-c3fbccafb52f)



## RESULT
Thus the program to convert the given string into lowercase has been executed successfully
 
 


# EX-19-COUNT-OF-WORDS-IN-A-STRING
## AIM
Write a C Program to count the total number of words in a given string using do While loop.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using for loop, inspect the string character by character.
4.	Whenever a space is encountered increment count by 1.
5.	Display the result.
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[200];
    int i = 0, wordCount = 0;
    int inWord = 0;

    printf("Enter a string:\n");
    fgets(str, sizeof(str), stdin);

    do {
        if (str[i] == '\0' || str[i] == '\n') {
            // End of string
            break;
        }

        if (isspace(str[i]) || ispunct(str[i])) {
            if (inWord) {
                wordCount++;
                inWord = 0;
            }
        } else {
            inWord = 1;  // inside a word
        }
        i++;
    } while (1);

    if (inWord) {
        wordCount++;
    }

    printf("Total number of words: %d\n", wordCount);

    return 0;
}

```
## OUTPUT

![445626978-aa9ca958-4141-4dbb-b0e3-ad632fc46869](https://github.com/user-attachments/assets/e403d07d-01dd-4cf3-b0e8-0998b88ff4be)




## RESULT
Thus the program to count the total number of words in a given string using do While loop has been executed successfully
 
 


# EX  -20 -COMPARING TWO STRINGS
## AIM
write a Program to compare two strings without using strcmp().
## ALGORITHM
Step 1: Start the program.
Step 2: Declare two character arrays c1 and c2 of size 100 to store the strings. Also, declare an integer variable
             flag and initialize it to 0, and i for indexing.      
Step 3: Read the first string c1 using scanf("%[^\n]", c1); — this reads input until a newline is encountered 
            (i.e., can include spaces).
Step 4: Read the second string c2 using scanf("%s", c2); — this reads input until a space or newline (i.e., no 
            spaces in the second string).
Step 5: Start comparing characters of both strings from index i = 0.
Step 6: Repeat the following while neither c1[i] nor c2[i] is '\0' (i.e., end of string):
•	If c1[i] is not equal to c2[i], set flag = 1.
•	Increment i by 1.
Step 7: After the loop, check the value of flag:
•	If flag == 0, print "strings are same".
•	Otherwise, print "strings are not same".
Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    char str1[100], str2[100];
    int i = 0;
    int equal = 1;  // Assume strings are equal initially

    printf("Enter first string: ");
    fgets(str1, sizeof(str1), stdin);

    printf("Enter second string: ");
    fgets(str2, sizeof(str2), stdin);

    while (str1[i] != '\0' && str2[i] != '\0') {
        // Ignore newline characters that fgets might store
        if (str1[i] == '\n') str1[i] = '\0';
        if (str2[i] == '\n') str2[i] = '\0';

        if (str1[i] != str2[i]) {
            equal = 0;  // Not equal
            break;
        }
        i++;
    }

    if (str1[i] != '\0' || str2[i] != '\0') {
        equal = 0;
    }

    if (equal) {
        printf("Strings are equal.\n");
    } else {
        printf("Strings are not equal.\n");
    }

    return 0;
}
```

## OUTPUT
 ![445627687-64aecc51-ac0f-41f8-ac66-905e290bb579](https://github.com/user-attachments/assets/e06f6c93-4a9d-435a-b839-d32f54623fa5)


## RESULT
Thus the C Program to compare two strings without using strcmp() has been executed successfully.

