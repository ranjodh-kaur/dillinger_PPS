Questions:

##### **Q1:**  Differentiate between compiler and interpreter (at least 4 differences).    **[Marks: 2]**
##### **Q2:**  What is the output of the following?                              **[Marks: 2]**
```cpp
#include <iostream>
using namespace std;
int main() {
    int x = 0, y = 0;
    while (x++ < 5) {
        y = 0;
        while (++y <= 5) {
            if (x == 2 && y == 2) {
                cout << "Nested Loop\n";
                continue;
            }
            cout << x << "," << y << endl;
            if (x == 4 || y == 3) {
                break;
            }
        }
    }
    cout << x << " " << y << endl;
    return 0;
}
```    

##### **Q3:**  What are different ways to pass arguments in functions? Explain at least two with examples.  **[Marks: 4]**
##### **Q4:**  Sara is willing to develop a calculator program in C++ for a basic math utility. Her goal is to design a program that allows users to perform arithmetic operations interactively by reading two float values and one character value from the user. She needs your help to complete her goal.  
Can you help her by writing a menu-driven program with separate functions for addition, subtraction, multiplication, and division?  
**Input Format:**  
- The first line reads two float values from the user.  
- The second line reads a character (`+`, `-`, `*`, `/`) representing the operation to be performed.  
**Output Format:**  
The output consists of a float value representing the result of the specific operation.
##### **Q5.** With the help of a code snippet, justify how structures are different from unions. (Marks: 4)
##### **Q6.** Create a structure Student that contains the fields like: studentID, name, and age.     **[Marks: 8]**
Write a program that allows the user to perform the following tasks:
  
1. Input student details (studentID, name, age) for n students (where n is read through the keyboard).
2. Display the details of all students in the record with a serial number (which is incremented from 1 to n).
3. Find and display details of the student who is eldest.
4. In your program, make use of an array of structures and functions.
Consider: age (in terms of years) has to be a positive number of integer data type only.
studentID should have values from 1001 onwards.

________
**Solution**
_______

#### **Q1: Differentiate between compiler and interpreter (at least 4 differences).**


| Compiler                               | Interpreter                           |
|----------------------------------------|---------------------------------------|
| Translates the entire program into machine code at once. | Translates the program line-by-line. |
| Produces an executable file after translation. | Does not produce an executable file. |
| Errors are shown after the compilation is complete. | Errors are shown immediately during execution. |
| Faster for program execution since the entire code is pre-compiled. | Slower as it translates code while executing. |

---

#### **Q2: Output of the following code snippet**

#### Code:
```cpp
#include <iostream>
using namespace std;
int main() {
    int x = 0, y = 0;
    while (x++ < 5) {
        y = 0;
        while (++y <= 5) {
            if (x == 2 && y == 2) {
                cout << "Nested Loop\n";
                continue;
            }
            cout << x << "," << y << endl;
            if (x == 4 || y == 3) {
                break;
            }
        }
    }
    cout << x << " " << y << endl;
    return 0;
}
```

**Output:**
```
1,1
1,2
1,3
2,1
Nested Loop
2,3
3,1
3,2
3,3
4,1
5,1
5,2
5,3
6 3
```

---

#### **Q3: What are different ways to pass arguments in functions? Explain at least two with examples.**
**1. Pass by Value:**
- A copy of the actual parameter is passed to the function. Changes made inside the function do not affect the original variable.
- **Example:**
    ```cpp
    void add(int a) {
        a += 5;
    }
    int main() {
        int num = 10;
        add(num);
        cout << num; // Output: 10
    }
    ```

**2. Pass by Reference:**
- The actual parameter is passed to the function, allowing changes to reflect on the original variable.
- **Example:**
    ```cpp
    void add(int &a) {
        a += 5;
    }
    int main() {
        int num = 10;
        add(num);
        cout << num; // Output: 15
    }
    ```
__________
#### **Q4: Menu-driven program for arithmetic operations**

**Code:**
```cpp
#include <iostream>
using namespace std;

float add(float a, float b) {
    return a + b;
}

float subtract(float a, float b) {
    return a - b;
}

float multiply(float a, float b) {
    return a * b;
}

float divide(float a, float b) {
    if (b != 0)
        return a / b;
    else {
        cout << "Division by zero is not allowed.\n";
        return 0;
    }
}

int main() {
    float num1, num2, result;
    char operation;

    // Input from the user
    cout << "Enter two numbers: ";
    cin >> num1 >> num2;
    cout << "Enter operation (+, -, *, /): ";
    cin >> operation;

    // Perform operation
    switch (operation) {
        case '+':
            result = add(num1, num2);
            break;
        case '-':
            result = subtract(num1, num2);
            break;
        case '*':
            result = multiply(num1, num2);
            break;
        case '/':
            result = divide(num1, num2);
            break;
        default:
            cout << "Invalid operation!\n";
            return 0;
    }



    // Display result
    cout << "Result: " << result << endl;
    return 0;
}
```
__________

**Q5.** With the help of a code snippet, justify how structures are different from unions. **(Marks: 4)**  

---
**Structures and unions** are both user-defined data types in C, but they differ in how they store and manage memory for their members.  

- **Structure:**  
  Each member has its own memory location, so all members can be accessed simultaneously.  
- **Union:**  
  All members share the same memory location, meaning only one member can be accessed at a time.

---

### **Code Snippet to Demonstrate the Difference:**

```c
#include <stdio.h>
#include <string.h>

// Define a structure
struct Student {
    int studentID;
    char name[50];
    int age;
};

// Define a union
union StudentUnion {
    int studentID;
    char name[50];
    int age;
};

int main() {
    // Using structure
    struct Student student1;
    student1.studentID = 1001;
    strcpy(student1.name, "Alice");
    student1.age = 20;

    printf("Using Structure:\n");
    printf("StudentID: %d\n", student1.studentID);
    printf("Name: %s\n", student1.name);
    printf("Age: %d\n", student1.age);

    // Using union
    union StudentUnion student2;
    student2.studentID = 1002;
    printf("\nUsing Union:\n");
    printf("StudentID: %d\n", student2.studentID);

    strcpy(student2.name, "Bob");
    printf("Name: %s\n", student2.name);

    student2.age = 22;
    printf("Age: %d\n", student2.age);

    // Observing memory overwriting in union
    printf("\nAfter modifying age in union:\n");
    printf("StudentID: %d\n", student2.studentID); // Overwritten
    printf("Name: %s\n", student2.name);          // Overwritten

    return 0;
}
```

---

### **Output:**

```
Using Structure:
StudentID: 1001
Name: Alice
Age: 20

Using Union:
StudentID: 1002
Name: Bob
Age: 22

After modifying age in union:
StudentID: 22
Name: 
```

---

### **Key Differences:**

1. **Memory Allocation:**
   - **Structure:** Each member has its own memory space.
   - **Union:** All members share the same memory space.

2. **Simultaneous Access:**
   - **Structure:** All members can be accessed simultaneously without affecting others.
   - **Union:** Modifying one member affects the value of other members.

3. **Usage:**
   - **Structure:** Used when all fields need to store independent values.
   - **Union:** Used to save memory when only one field is used at a time.

_________

**Q6.** Create a structure `Student` that contains the fields like: `studentID`, `name`, and `age`. Write a program that allows the user to perform the following tasks:                                             **(Marks: 8)**
1. Input student details (`studentID`, `name`, `age`) for `n` students (where `n` is read through the keyboard).  
2. Display the details of all students in the record with a serial number (which is incremented from 1 to `n`).  
3. Find and display details of the student who is eldest.  
4. In your program, make use of an array of structures and functions.  
   - **Consider**: `age` (in terms of years) has to be a positive number of integer data type only.  
   - **studentID** should have values from `1001` onwards.  
---


```c
#include <stdio.h>
#include <string.h>

// Define the structure Student
struct Student {
    int studentID;
    char name[50];
    int age;
};

// Function to input details of students
void inputStudents(struct Student students[], int n) {
    for (int i = 0; i < n; i++) {
        students[i].studentID = 1001 + i; // Assign studentID starting from 1001
        printf("Enter name for student %d: ", i + 1);
        scanf(" %[^\n]", students[i].name);
        do {
            printf("Enter age for student %d (positive integer): ", i + 1);
            scanf("%d", &students[i].age);
            if (students[i].age <= 0) {
                printf("Invalid age! Please enter a positive integer.\n");
            }
        } while (students[i].age <= 0);
    }
}

// Function to display details of all students
void displayStudents(struct Student students[], int n) {
    printf("\nDetails of all students:\n");
    printf("Serial No. | StudentID | Name                | Age\n");
    printf("-----------------------------------------------------\n");
    for (int i = 0; i < n; i++) {
        printf("%-11d| %-10d| %-20s| %d\n", i + 1, students[i].studentID, students[i].name, students[i].age);
    }
}

// Function to find and display the eldest student
void findEldestStudent(struct Student students[], int n) {
    int maxAgeIndex = 0;
    for (int i = 1; i < n; i++) {
        if (students[i].age > students[maxAgeIndex].age) {
            maxAgeIndex = i;
        }
    }
    printf("\nDetails of the eldest student:\n");
    printf("StudentID: %d\nName: %s\nAge: %d\n", students[maxAgeIndex].studentID, students[maxAgeIndex].name, students[maxAgeIndex].age);
}

int main() {
    int n;

    // Input the number of students
    printf("Enter the number of students: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid number of students! Exiting.\n");
        return 1;
    }

    struct Student students[n];

    // Call functions to perform tasks
    inputStudents(students, n);
    displayStudents(students, n);
    findEldestStudent(students, n);

    return 0;
}
```

---

### **Explanation of the Code:**
1. **Structure Definition:** 
   - The `Student` structure is defined with fields `studentID`, `name`, and `age`.

2. **Input Validation:**
   - `age` is ensured to be a positive integer.
   - `studentID` is auto-generated starting from 1001.

3. **Functions Used:**
   - `inputStudents`: Inputs the details of students.
   - `displayStudents`: Displays the details of all students.
   - `findEldestStudent`: Finds and displays the eldest student's details.

4. **Serial Number Display:**
   - Students are listed with serial numbers incremented from 1.

---

### **Mark Distribution:**
1. **Structure Definition (2 Marks):**
   - Correct definition of the `Student` structure.

2. **Data Input and Validation (2 Marks):**
   - Proper input of `studentID`, `name`, and validated `age`.

3. **Display of Students (2 Marks):**
   - Display details of all students with formatting.

4. **Finding Eldest Student (2 Marks):**
   - Correct logic to find and display the eldest student.
