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
    float length, width;
    float *ptr_length, *ptr_width, area;

    ptr_length = &length;
    ptr_width = &width;

    printf("Enter length of the rectangle: ");
    scanf("%f", ptr_length);

    printf("Enter width of the rectangle: ");
    scanf("%f", ptr_width);

    area = (*ptr_length) * (*ptr_width);

    printf("The area of the rectangle is: %.2f\n", area);

    return 0;
}
```



## OUTPUT 
![image](https://github.com/user-attachments/assets/a939a44e-9c8d-4d6c-8b2a-787b66751f45)
		       	


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
        printf("Memory allocation failed!\n");
        return 1;
    }

    strcpy(str, "WELCOME");  

    printf("%s\n", str);

    free(str);  

    return 0;
}

```

## OUTPUT
![image](https://github.com/user-attachments/assets/537a9f16-40c7-45bd-845c-db2a394a2d52)


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
    int rollNo;
    char name[50];
    float marks;
};

int main() {
    struct Student student;

    printf("Enter Roll Number: ");
    scanf("%d", &student.rollNo);

    printf("Enter Name: ");
    getchar();  // to consume the newline character left by previous input
    fgets(student.name, sizeof(student.name), stdin);

    printf("Enter Marks: ");
    scanf("%f", &student.marks);

    printf("\nStudent Information:\n");
    printf("Roll Number: %d\n", student.rollNo);
    printf("Name: %s", student.name);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}
```


## OUTPUT
![image](https://github.com/user-attachments/assets/76f92ccc-d3d3-4bb3-94ac-e1476bb133f9)


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
    float allowances;
    float grossSalary;
};

int main() {
    struct Employee emp[3];
    
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);
        
        printf("Enter Name: ");
        getchar();  // to consume newline character left by previous input
        fgets(emp[i].name, sizeof(emp[i].name), stdin);
        
        printf("Enter Basic Salary: ");
        scanf("%f", &emp[i].basicSalary);
        
        printf("Enter Allowances: ");
        scanf("%f", &emp[i].allowances);
        
        emp[i].grossSalary = emp[i].basicSalary + emp[i].allowances;
        printf("\n");
    }
    
    printf("Employee Details and Gross Salaries:\n");
    for (int i = 0; i < 3; i++) {
        printf("Employee %d:\n", i + 1);
        printf("Name: %s", emp[i].name);
        printf("Basic Salary: %.2f\n", emp[i].basicSalary);
        printf("Allowances: %.2f\n", emp[i].allowances);
        printf("Gross Salary: %.2f\n\n", emp[i].grossSalary);
    }
retun 0;
}
    

```

 ## OUTPUT
![image](https://github.com/user-attachments/assets/2ce20622-03fe-4561-8556-dbada13ea549)


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
    float marks[5];
    float total;
    float average;
};

int main() {
    struct Student student;
    
    printf("Enter student name: ");
    getchar();  
    fgets(student.name, sizeof(student.name), stdin);
    
    student.total = 0;
    
    printf("Enter marks for 5 subjects:\n");
    for (int i = 0; i < 5; i++) {
        printf("Subject %d: ", i + 1);
        scanf("%f", &student.marks[i]);
        student.total += student.marks[i];
    }
    
    student.average = student.total / 5;
    
    printf("\nStudent Information:\n");
    printf("Name: %s", student.name);
    printf("Total Marks: %.2f\n", student.total);
    printf("Average Marks: %.2f\n", student.average);
    
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/5575e41f-3ce0-4479-9845-c9c3765438df)
    
 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


