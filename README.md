# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *pLength, *pBreadth;

    // Point the pointers to the addresses of length and breadth
    pLength = &length;
    pBreadth = &breadth;

    // Take input
    printf("Enter length of rectangle: ");
    scanf("%f", pLength);

    printf("Enter breadth of rectangle: ");
    scanf("%f", pBreadth);

    // Calculate area using pointers
    area = (*pLength) * (*pBreadth);

    printf("Area of rectangle = %.2f\n", area);

    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/b7473406-35fc-4527-9470-360468095407)


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    char *str;

    // Allocate memory for 8 characters (7 letters + 1 for null terminator)
    str = (char *)malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Copy "WELCOME" into allocated memory
    str[0] = 'W';
    str[1] = 'E';
    str[2] = 'L';
    str[3] = 'C';
    str[4] = 'O';
    str[5] = 'M';
    str[6] = 'E';
    str[7] = '\0'; // Null terminator

    // Print the string
    printf("%s\n", str);

    // Free the allocated memory
    free(str);

    return 0;
}
```
## OUTPUT

![image](https://github.com/user-attachments/assets/26df2f66-c472-4668-9956-875e20d0b8f7)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    int rollNumber;
    char name[50];
    float marks;
};

int main() {
    struct Student s;

    // Input student information
    printf("Enter roll number: ");
    scanf("%d", &s.rollNumber);

    printf("Enter name: ");
    scanf(" %[^\n]", s.name); // To read string with spaces

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    // Display student information
    printf("\nStudent Information:\n");
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/4d71e57d-3b1f-495d-8a71-eaf23f22bb12)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct Employee {
    int id;
    char name[50];
    float basicSalary;
    float grossSalary;
};

int main() {
    struct Employee emp[3];
    int i;

    // Read data for 3 employees
    for(i = 0; i < 3; i++) {
        printf("Enter details for Employee %d\n", i+1);

        printf("ID: ");
        scanf("%d", &emp[i].id);

        printf("Name: ");
        scanf(" %[^\n]", emp[i].name); // To read string with spaces

        printf("Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        // Calculate Gross Salary
        // Let's assume: Gross Salary = Basic Salary + 20% of Basic Salary (HRA) + 10% of Basic Salary (DA)
        emp[i].grossSalary = emp[i].basicSalary + (0.2 * emp[i].basicSalary) + (0.1 * emp[i].basicSalary);

        printf("\n");
    }

    // Display employee details
    printf("\nEmployee Details:\n");
    for(i = 0; i < 3; i++) {
        printf("Employee %d\n", i+1);
        printf("ID: %d\n", emp[i].id);
        printf("Name: %s\n", emp[i].name);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("Gross Salary: %.2f\n", emp[i].grossSalary);
        printf("\n");
    }

    return 0;
}
```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/e7e53a46-c030-4ec8-8738-2adcdca95909)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct Student {
    char name[50];
    int marks1, marks2, marks3;
    int total;
    float average;
};

int main() {
    struct Student s;

    // Input student details
    printf("Enter student's name: ");
    scanf(" %[^\n]", s.name);

    printf("Enter marks in 3 subjects:\n");
    printf("Subject 1: ");
    scanf("%d", &s.marks1);
    printf("Subject 2: ");
    scanf("%d", &s.marks2);
    printf("Subject 3: ");
    scanf("%d", &s.marks3);

    // Calculate total and average
    s.total = s.marks1 + s.marks2 + s.marks3;
    s.average = s.total / 3.0;

    // Display result
    printf("\nStudent Details:\n");
    printf("Name: %s\n", s.name);
    printf("Total Marks: %d\n", s.total);
    printf("Average Marks: %.2f\n", s.average);

    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/754f5f01-e999-4d36-93a3-921701602622)

 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


