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
    float *ptrLength, *ptrBreadth;

    ptrLength = &length;
    ptrBreadth = &breadth;

    scanf("%f", ptrLength);

    scanf("%f", ptrBreadth);

    area = (*ptrLength) * (*ptrBreadth);

    printf("Area of rectangle = %f sq. units\n", area);

    return 0;
}
```

## OUTPUT
		       	
![image](https://github.com/user-attachments/assets/14bacf7c-1327-479e-9fc2-16ab951f6b8b)


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
#include <string.h>

int main() {
    char *str;
    str = (char *)malloc(8 * sizeof(char)); 
    if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }
    strcpy(str, "WELCOME");
    printf("The string is: %s\n", str);
    free(str);
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/04936b1f-1694-4e17-b4c4-7bc6a9ff3b83)



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



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
    char name[50];
    int rollNumber;
    float marks;
};

int main() {
    struct Student s;

    printf("Enter student name: ");
    scanf("%s", s.name);  
    printf("Enter roll number: ");
    scanf("%d", &s.rollNumber);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\n--- Student Information ---\n");
    printf("Name       : %s\n", s.name);
    printf("Roll Number: %d\n", s.rollNumber);
    printf("Marks      : %.2f\n", s.marks);

    return 0;
}
```


## OUTPUT

![image](https://github.com/user-attachments/assets/2290eadf-4bf2-4082-bd53-5bfbb12652d3)

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
    char name[50];
    int id;
    float basicSalary;
    float hra;
    float da;
    float grossSalary;
};

int main() {
    struct Employee emp[3];

    for (int i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", emp[i].name);  
        printf("ID: ");
        scanf("%d", &emp[i].id);
        printf("Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);

        emp[i].hra = 0.20 * emp[i].basicSalary;
        emp[i].da = 0.80 * emp[i].basicSalary;
        emp[i].grossSalary = emp[i].basicSalary + emp[i].hra + emp[i].da;
    }

    printf("\n--- Employee Salary Details ---\n");
    for (int i = 0; i < 3; i++) {
        printf("\nEmployee %d:\n", i + 1);
        printf("Name        : %s\n", emp[i].name);
        printf("ID          : %d\n", emp[i].id);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("HRA         : %.2f\n", emp[i].hra);
        printf("DA          : %.2f\n", emp[i].da);
        printf("Gross Salary: %.2f\n", emp[i].grossSalary);
    }

    return 0;  
}
```


 ## OUTPUT

 
![image](https://github.com/user-attachments/assets/39d6007e-7374-477e-b44d-19bd0e415d7c)

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

struct student {
    char name[20];       
    int rollno;          
    int subject[5];     
    int total;           
};

int main() {
    struct student s[2];
    int i, j;

    for (i = 0; i < 2; i++) {
        printf("Enter name of student %d: ", i + 1);
        scanf("%s", s[i].name);

        printf("Enter roll number of %s: ", s[i].name);
        scanf("%d", &s[i].rollno);

        printf("Enter marks for 5 subjects of %s:\n", s[i].name);
        for (j = 0; j < 5; j++) {
            printf("Subject %d: ", j + 1);
            scanf("%d", &s[i].subject[j]);
        }
    }

    for (i = 0; i < 2; i++) {
        s[i].total = 0;
        for (j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
    }

    for (i = 0; i < 2; i++) {
        float average = s[i].total / 5.0;
        printf("\nStudent Name: %s", s[i].name);
        printf("\nRoll Number: %d", s[i].rollno);
        printf("\nTotal Marks: %d", s[i].total);
        printf("\nAverage Marks: %.2f\n", average);
    }

    return 0;
}
```

## OUTPUT

![image](https://github.com/user-attachments/assets/b999f463-3bf6-4f20-9271-b59dec38412c)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


