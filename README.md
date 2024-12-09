WAP TO CHECK ARMSTRONG OR NOT]]]]]]]

#include <stdio.h>
#include <math.h>

// Function to calculate the number of digits
int order(int x) {
    int n = 0;
    while (x) {
        n++;
        x = x / 10;
    }
    return n;
}

// Function to check whether the given number is an Armstrong number or not
int isArmstrong(int x) {
    int n = order(x);
    int temp = x, sum = 0;
    while (temp) {
        int r = temp % 10;
        sum += pow(r, n);
        temp = temp / 10;
    }
    return (sum == x);
}

// Driver Code
int main() {
    int x;
    printf("Enter a number: ");
    scanf("%d", &x);
    
    if (isArmstrong(x)) {
        printf("%d is an Armstrong number.\n", x);
    } else {
        printf("%d is not an Armstrong number.\n", x);
    }
    
    return 0;
}

WAP to accept basic salary from the keyboard. Calculate the gross salary that includes basic salary, 50% DA and 40% HRA in c]]]]]]]]]]]]]


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

C Program to Store Information of a Student Using Structure.]]]]]]]]]]]]

#include <stdio.h>
#include <string.h>

// Define a structure to hold student information
struct Student {
    char name[50];
    int roll_number;
    float marks;
};

int main() {
    struct Student student; // Declare a variable of type Student

    // Input student information
    printf("Enter Student Name: ");
    fgets(student.name, sizeof(student.name), stdin); // Read string input
    student.name[strcspn(student.name, "\n")] = 0; // Remove newline character

    printf("Enter Roll Number: ");
    scanf("%d", &student.roll_number);

    printf("Enter Marks: ");
    scanf("%f", &student.marks);

    // Display student information
    printf("\nStudent Information:\n");
    printf("Name: %s\n", student.name);
    printf("Roll Number: %d\n", student.roll_number);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}

Write a function for addition of two numbers.]]]]]]]]

#include <stdio.h>

// Function to add two numbers
float add(float a, float b) {
    return a + b; // Return the sum of a and b
}

int main() {
    float num1, num2, sum;

    // Input two numbers from the user
    printf("Enter first number: ");
    scanf("%f", &num1);
    
    printf("Enter second number: ");
    scanf("%f", &num2);

    // Call the add function
    sum = add(num1, num2);

    // Display the result
    printf("The sum of %.2f and %.2f is: %.2f\n", num1, num2, sum);

    return 0;
}


Write a program to perform transpose of 3X3 matrices]]]]]]]]

#include <stdio.h>

#define SIZE 3 // Define the size of the matrix

// Function to print the matrix
void printMatrix(int matrix[SIZE][SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
}

// Function to calculate the transpose of the matrix
void transposeMatrix(int matrix[SIZE][SIZE], int transposed[SIZE][SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            transposed[j][i] = matrix[i][j]; // Swap rows and columns
        }
    }
}

int main() {
    int matrix[SIZE][SIZE], transposed[SIZE][SIZE];

    // Input elements of the matrix
    printf("Enter elements of the 3x3 matrix:\n");
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            printf("Element [%d][%d]: ", i + 1, j + 1);
            scanf("%d", &matrix[i][j]);
        }
    }

    // Calculate the transpose
    transposeMatrix(matrix, transposed);

    // Display the original matrix
    printf("\nOriginal Matrix:\n");
    printMatrix(matrix);

    // Display the transposed matrix
    printf("\nTransposed Matrix:\n");
    printMatrix(transposed);

    return 0;

    WAP to accept from user the number of Fibonacci numbers to be generated and print the Fibonacci series using recursion]]]]]]]]]

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
    int count;

    // Input the number of Fibonacci numbers to generate
    printf("Enter the number of Fibonacci numbers to generate: ");
    scanf("%d", &count);

    // Print the Fibonacci series
    printf("Fibonacci Series:\n");
    for (int i = 0; i < count; i++) {
        printf("%d ", fibonacci(i));
    }
    printf("\n");

    return 0;
}

