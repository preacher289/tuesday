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


Write a program to compute i)cube of a number ii)factorial of number using switch.\\\\\\\\\\

#include <stdio.h>

int main() {
    int choice, number, i;
    long long factorial = 1; // Use long long to handle larger factorials

    // Display menu
    printf("Choose an operation:\n");
    printf("1. Compute the cube of a number\n");
    printf("2. Compute the factorial of a number\n");
    printf("Enter your choice (1 or 2): ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            // Compute the cube of a number
            printf("Enter a number: ");
            scanf("%d", &number);
            printf("The cube of %d is %d\n", number, number * number * number);
            break;

        case 2:
            // Compute the factorial of a number
            printf("Enter a non-negative integer: ");
            scanf("%d", &number);
            if (number < 0) {
                printf("Factorial is not defined for negative numbers.\n");
            } else {
                for (i = 1; i <= number; i++) {
                    factorial *= i; // Calculate factorial
                }
                printf("The factorial of %d is %lld\n", number, factorial);
            }
            break;

        default:
            printf("Invalid choice! Please select 1 or 2.\n");
            break;
    }

    return 0;
}


WAP to accept basic salary from the keyboard. Calculate the gross salary that includes basic salary, 40% DA and 25% HRA.\\\\\\\\\\


#include <stdio.h>

int main() {
    float basic_salary, da, hra, gross_salary;

    // Accept basic salary from the user
    printf("Enter the basic salary: ");
    scanf("%f", &basic_salary);

    // Calculate DA (40% of basic salary)
    da = 0.40 * basic_salary;

    // Calculate HRA (25% of basic salary)
    hra = 0.25 * basic_salary;

    // Calculate gross salary
    gross_salary = basic_salary + da + hra;

    // Display the results
    printf("Basic Salary: %.2f\n", basic_salary);
    printf("Dearness Allowance (DA): %.2f\n", da);
    printf("House Rent Allowance (HRA): %.2f\n", hra);
    printf("Gross Salary: %.2f\n", gross_salary);

    return 0;
}


Write a program to perform Subtraction of two 3X3 matrices.\\\\\\\\\\

#include <stdio.h>

#define SIZE 3 // Define the size of the matrix

int main() {
    int matrix1[SIZE][SIZE], matrix2[SIZE][SIZE], result[SIZE][SIZE];
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

    // Perform subtraction of the two matrices
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            result[i][j] = matrix1[i][j] - matrix2[i][j];
        }
    }

    // Display the result
    printf("Result of subtraction (Matrix1 - Matrix2):\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}


WAP to accepts a string from user and to perform reverse of string operation without using string functions\\\\\\\\\\

#include <stdio.h>

#define MAX_LENGTH 100 // Define maximum length for the string

int main() {
    char str[MAX_LENGTH]; // Array to hold the input string
    char reversed[MAX_LENGTH]; // Array to hold the reversed string
    int length = 0; // Variable to store the length of the string
    int i;

    // Accept a string from the user
    printf("Enter a string: ");
    fgets(str, MAX_LENGTH, stdin); // Read the string from standard input

    // Calculate the length of the string manually
    while (str[length] != '\0') {
        // Check for newline character and stop counting
        if (str[length] == '\n') {
            break;
        }
        length++;
    }

    // Reverse the string
    for (i = 0; i < length; i++) {
        reversed[i] = str[length - 1 - i]; // Assign characters in reverse order
    }
    reversed[length] = '\0'; // Null-terminate the reversed string

    // Display the reversed string
    printf("Reversed string: %s\n", reversed);

    return 0;
}

WAP to accept from user the number of Fibonacci numbers to be generated and print the Fibonacci series using recursion\\\\\\\\\\\


#include <stdio.h>

// Function to calculate the nth Fibonacci number using recursion
int fibonacci(int n) {
    if (n == 0) {
        return 0; // Base case: F(0) = 0
    } else if (n == 1) {
        return 1; // Base case: F(1) = 1
    } else {
        return fibonacci(n - 1) + fibonacci(n - 2); // Recursive case
    }
}

int main() {
    int count, i;

    // Accept the number of Fibonacci numbers to generate
    printf("Enter the number of Fibonacci numbers to generate: ");
    scanf("%d", &count);

    // Print the Fibonacci series
    printf("Fibonacci Series:\n");
    for (i = 0; i < count; i++) {
        printf("%d ", fibonacci(i)); // Call the recursive function
    }
    printf("\n");

    return 0;
}


Write a program to perform transpose of 3X3 matrices.\\\\\\\\


#include <stdio.h>

#define SIZE 3 // Define the size of the matrix

int main() {
    int matrix[SIZE][SIZE], transpose[SIZE][SIZE];
    int i, j;

    // Input elements of the matrix
    printf("Enter elements of the 3x3 matrix:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix[i][j]);
        }
    }

    // Calculate the transpose of the matrix
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            transpose[j][i] = matrix[i][j]; // Swap rows and columns
        }
    }

    // Display the original matrix
    printf("\nOriginal Matrix:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    // Display the transposed matrix
    printf("\nTransposed Matrix:\n");
    for (i = 0; i < SIZE; i++) {
        for (j = 0; j < SIZE; j++) {
            printf("%d ", transpose[i][j]);
        }
        printf("\n");
    }

    return 0;
}


C Program to Store Information of a Student Using Structure.\\\\\\\\

#include <stdio.h>
#include <string.h>

// Define a structure to hold student information
struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main() {
    struct Student student; // Declare a variable of type Student

    // Input student information
    printf("Enter student name: ");
    fgets(student.name, sizeof(student.name), stdin);
    student.name[strcspn(student.name, "\n")] = 0; // Remove newline character

    printf("Enter roll number: ");
    scanf("%d", &student.rollNumber);

    printf("Enter marks: ");
    scanf("%f", &student.marks);

    // Display student information
    printf("\nStudent Information:\n");
    printf("Name: %s\n", student.name);
    printf("Roll Number: %d\n", student.rollNumber);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}


Write a function for addition of two numbers.\\\\\\\\


#include <stdio.h>

// Function to add two numbers
int add(int a, int b) {
    return a + b; // Return the sum of a and b
}

int main() {
    int num1, num2, sum;

    // Input two numbers from the user
    printf("Enter first number: ");
    scanf("%d", &num1);
    
    printf("Enter second number: ");
    scanf("%d", &num2);

    // Call the add function
    sum = add(num1, num2);

    // Display the result
    printf("The sum of %d and %d is: %d\n", num1, num2, sum);

    return 0;
}





