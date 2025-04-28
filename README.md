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
    float length, width, area;
    float *ptrLength = &length, *ptrWidth = &width, *ptrArea = &area;

    printf("Enter length of rectangle: ");
    scanf("%f", ptrLength);

    printf("Enter width of rectangle: ");
    scanf("%f", ptrWidth);

    *ptrArea = (*ptrLength) * (*ptrWidth);

    printf("Area of rectangle: %.2f\n", *ptrArea);

    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/f508a90c-8288-420d-a8fb-2a81b5ddea36)
		       	


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
#include <strings.h>

int main() {
    char *str;
    str = (char*) malloc(8 * sizeof(char));

    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }
    strcpy(str,"WELCOME");
    printf("%s\n", str);
    return 0;
}
```


## OUTPUT
![image](https://github.com/user-attachments/assets/2834339b-b218-4694-ab18-6fe281fa9078)

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

struct Employee 
{
    int id;
    char name[50];
    float age;
};

int main() 
{
    struct Employee employees;
    scanf("%d", &employees.id);
    scanf(" %s", employees.name);
    scanf("%f", &employees.age);
    printf("Rollno is: %d\nName is: %s\nPercentage is: %.2f\n", employees.id, employees.name, employees.age);
   return 0;
}
```


## OUTPUT
![image](https://github.com/user-attachments/assets/90e0f663-de44-4bee-a294-3e83c084e13e)



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
    float basicSalary;
    float hra;
    float da;
    float grossSalary;
};

int main() {
    struct Employee emp[3];

    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);
        
        printf("Enter Name: ");
        scanf("%s", emp[i].name);
         printf("Enter Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);
        
        printf("Enter HRA: ");
        scanf("%f", &emp[i].hra);
        
        printf("Enter DA: ");
        scanf("%f", &emp[i].da);

        emp[i].grossSalary = emp[i].basicSalary + emp[i].hra + emp[i].da;
        printf("\n");
    }

    printf("Employee Details and Gross Salary:\n");
    for (int i = 0; i < 3; i++) {
        printf("Employee %d\n", i + 1);
        printf("Name: %s\n", emp[i].name);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("HRA: %.2f\n", emp[i].hra);
        printf("DA: %.2f\n", emp[i].da);
        printf("Gross Salary: %.2f\n", emp[i].grossSalary);
        printf("\n");
    }

    return 0;
}
```



 ## OUTPUT
![image](https://github.com/user-attachments/assets/61e42c4a-3eaa-44f8-84bb-7cf209f8f011)
 

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
    int marks[5];
    float total;
    float average;
};

int main() {
    struct Student student;
    int sum = 0;

    printf("Enter student's name: ");
    scanf("%s", student.name);
   printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%d", &student.marks[i]);
        sum += student.marks[i];
    }

    student.total = sum;
    student.average = sum / 5.0;

    printf("\nStudent Name: %s\n", student.name);
    printf("Total Marks: %.2f\n", student.total);
    printf("Average Marks: %.2f\n", student.average);

    return 0;
}
```

## OUTPUT
 ![image](https://github.com/user-attachments/assets/2f93b2a1-541b-4b92-b48a-56558b63e8dc)
 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


