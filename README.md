WAP to accept basic salary from the keyboard. Calculate the gross salary that includes basic salary, 50% DA and 40% HRA in c\\\\\\\\\
#include <stdio.h>

int main() {
    float basic_salary, da, hra, gross_salary;

    // Input basic salary from the user
    printf("Enter Basic Salary: ");
    scanf("%f", &basic_salary);

    // Calculate DA and HRA
    da = 0.5 * basic_salary; // 50% DA
    hra = 0.4 * basic_salary; // 40% HRA

    // Calculate gross salary
    gross_salary = basic_salary + da + hra;

    // Display the results
    printf("\nBasic Salary: %.2f", basic_salary);
    printf("\nDearness Allowance (DA): %.2f", da);
    printf("\nHouse Rent Allowance (HRA): %.2f", hra);
    printf("\n\nGross Salary: %.2f\n", gross_salary);

    return 0;
}

WAP to display the CLASS of students according to range given. Take 3 subject marks as input from user.
Distinction if avg_marks >=70
FIRST CLASS if avg_marks >=60 and less than 70
SECOND CLASS if avg_marks >=40 and less than 60
FAIL if avg_marks <40\\\\\\\\\\

#include <stdio.h>

int main() {
    float marks1, marks2, marks3, avg_marks;

    // Input marks for three subjects
    printf("Enter marks for three subjects:\n");
    printf("Subject 1: ");
    scanf("%f", &marks1);
    printf("Subject 2: ");
    scanf("%f", &marks2);
    printf("Subject 3: ");
    scanf("%f", &marks3);

    // Calculate average marks
    avg_marks = (marks1 + marks2 + marks3) / 3;

    // Display the average marks
    printf("Average Marks: %.2f\n", avg_marks);

    // Determine and display the class based on average marks
    if (avg_marks >= 70) {
        printf("Class: Distinction\n");
    } else if (avg_marks >= 60) {
        printf("Class: First Class\n");
    } else if (avg_marks >= 40) {
        printf("Class: Second Class\n");
    } else {
        printf("Class: Fail\n");
    }

    return 0;
}


Write a program to check whether the entered number is Armstrong or not.\\\\\\\\

#include <stdio.h>
#include <math.h>

int main() {
    int number, originalNumber, remainder, n = 0, result = 0;

    // Input a number from the user
    printf("Enter an integer: ");
    scanf("%d", &number);

    originalNumber = number;

    // Count the number of digits
    while (originalNumber != 0) {
        originalNumber /= 10;
        n++;
    }

    originalNumber = number;

    // Calculate the sum of the nth powers of its digits
    while (originalNumber != 0) {
        remainder = originalNumber % 10;
        result += pow(remainder, n);
        originalNumber /= 10;
    }

    // Check if the number is an Armstrong number
    if (result == number) {
        printf("%d is an Armstrong number.\n", number);
    } else {
        printf("%d is not an Armstrong number.\n", number);
    }

    return 0;
}

Write a program to compute i) Square root of number ii)Square of number using switch.\\\\\\\\\\\

#include <stdio.h>
#include <math.h>

int main() {
    int choice;
    double number, result;

    // Display menu
    printf("Choose an option:\n");
    printf("1. Calculate Square Root\n");
    printf("2. Calculate Square\n");
    printf("Enter your choice (1 or 2): ");
    scanf("%d", &choice);

    // Input the number
    printf("Enter a number: ");
    scanf("%lf", &number);

    // Switch statement to perform the chosen operation
    switch (choice) {
        case 1:
            if (number < 0) {
                printf("Error: Square root of a negative number is not defined.\n");
            } else {
                result = sqrt(number);
                printf("Square Root of %.2f is %.2f\n", number, result);
            }
            break;
        case 2:
            result = number * number;
            printf("Square of %.2f is %.2f\n", number, result);
            break;
        default:
            printf("Invalid choice! Please enter 1 or 2.\n");
            break;
    }

    return 0;
}


WAP to accepts a string from user and to perform Equality check of two string operation\\\\\\\\\\\\


#include <stdio.h>
#include <string.h>

int main() {
    char str1[100], str2[100];

    // Input first string
    printf("Enter the first string: ");
    fgets(str1, sizeof(str1), stdin);
    
    // Remove newline character from the string if present
    str1[strcspn(str1, "\n")] = 0;

    // Input second string
    printf("Enter the second string: ");
    fgets(str2, sizeof(str2), stdin);
    
    // Remove newline character from the string if present
    str2[strcspn(str2, "\n")] = 0;

    // Check for equality
    if (strcmp(str1, str2) == 0) {
        printf("The two strings are equal.\n");
    } else {
        printf("The two strings are not equal.\n");
    }

    return 0;
}


Write a program to perform addition of two 3X3 matrices.\\\\\\\\\\\

#include <stdio.h>

#define SIZE 3  // Define the size of the matrix

int main() {
    int matrix1[SIZE][SIZE], matrix2[SIZE][SIZE], sum[SIZE][SIZE];
    int i, j;

    // Input elements of the first matrix
    printf("Enter elements of the first 3x3 matrix:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix1[i][j]);
        }
    }

    // Input elements of the second matrix
    printf("Enter elements of the second 3x3 matrix:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix2[i][j]);
        }
    }

    // Calculate the sum of the two matrices
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            sum[i][j] = matrix1[i][j] + matrix2[i][j];
        }
    }

    // Display the resulting matrix
    printf("Sum of the two matrices:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("%d ", sum[i][j]);
        }
        printf("\n");
    }

    return 0;
}


WAP to accepts a string from user and to calculate length of string without using string functions\\\\\\\\\\\\

#include <stdio.h>

int main() {
    char str[100];  // Array to store the input string
    int length = 0; // Variable to store the length of the string
    char ch;

    // Input the string from the user
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Calculate the length of the string manually
    // Loop until we encounter the null character '\0'
    while (str[length] != '\0') {
        // Check for the newline character added by fgets
        if (str[length] == '\n') {
            break; // Stop counting if we hit a newline
        }
        length++; // Increment the length for each character
    }

    // Output the length of the string
    printf("The length of the string is: %d\n", length);

    return 0;
}


