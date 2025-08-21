# MST-2 Questions

>Q1 Is it possible to declare more than one array in the same declaration statement? Justify you answer.
>
>Q2 List advantages of functions.
>
>Q3 Differentiate between call by value and call by reference (include example(s)).
>
>Q4 Write a C++ program that uses recursion to compute the multiplication of elements in a one-dimensional integer array.
>
>QS With the help of code snippet, justify how structures are different from unions.
>
>Q6 You are the HR manager of a company, and you are using employee management system to manage the employee data. The system allows you to add new employees, display all employees, search for an employee by ID, update employee salary, and delete an employee. Your task is to

```
Create a struct employee with
Attributes:
Name: String
ID: Integer
Department:
String
Salary: Double
Also, in the program add the Functions:
addEmployee (): Adds the employee to the directory
displayEmployees (): Displays all the employees present in directory
searchEmployee (): Search for the employee with Emp ID
update Employee Salary (): Updates the salary of employee with Emp ID
delete Employee:): Deletes the employee from the directory with Emp ID
For every addition of new employee, print a message as "Employee added successfully!"
If there are no employees left in the directory, print "No employees to display"
If Employee not found print "Employee not found"
```

____
**Solution**
### Q1: Is it possible to declare more than one array in the same declaration statement? Justify your answer.  
**Answer**: Yes, it is possible to declare more than one array in the same declaration statement in C++ or C. Arrays can be declared in the same way as multiple variables of the same data type, separated by commas.  
**Example**:  
```cpp
int arr1[10], arr2[20], arr3[15];
```  
This declaration creates three arrays: `arr1` with 10 elements, `arr2` with 20 elements, and `arr3` with 15 elements.  

---

### Q2: List advantages of functions.  
**Answer**:  
1. **Code Reusability**: Functions allow code to be reused multiple times, reducing redundancy.  
2. **Improved Readability**: They make programs easier to read and maintain by breaking them into smaller modules.  
3. **Reduced Complexity**: Complex problems can be divided into smaller tasks, simplifying debugging and testing.  
4. **Ease of Maintenance**: Changes can be made in one function without affecting others.  
5. **Facilitates Teamwork**: Different team members can work on separate functions independently.  

---

### Q3: Differentiate between call by value and call by reference (include example(s)).  

| **Aspect**          | **Call by Value**                                     | **Call by Reference**                                  |
|----------------------|------------------------------------------------------|-------------------------------------------------------|
| **Definition**       | Passes a copy of the value to the function.           | Passes the actual address of the variable to the function. |
| **Effect on Original Data** | Changes made inside the function do not affect the original data. | Changes made inside the function affect the original data. |
| **Implementation**   | Use of value variables as function arguments.         | Use of reference or pointer variables as function arguments. |
| **Example**          | See below                                            | See below                                             |

**Example**:  
**Call by Value**:  
```cpp
void modifyValue(int a) {
    a = 10; // Changes the copy
}
int main() {
    int x = 5;
    modifyValue(x);
    cout << x; // Output: 5
}
```  
**Call by Reference**:  
```cpp
void modifyValue(int &a) {
    a = 10; // Changes the original
}
int main() {
    int x = 5;
    modifyValue(x);
    cout << x; // Output: 10
}
```  

---

### Q4: Write a C++ program that uses recursion to compute the multiplication of elements in a one-dimensional integer array.  
**Answer**:  
```cpp
#include <iostream>
using namespace std;

int multiplyArray(int arr[], int size) {
    if (size == 0) 
        return 1; // Multiplicative identity
    return arr[size - 1] * multiplyArray(arr, size - 1);
}

int main() {
    int arr[] = {2, 3, 4, 5};
    int size = sizeof(arr) / sizeof(arr[0]);
    cout << "Multiplication of array elements: " << multiplyArray(arr, size) << endl;
    return 0;
}
```  

---

### Q5: With the help of a code snippet, justify how structures are different from unions.  
**Answer**:  

| **Aspect**          | **Structure**                                | **Union**                                   |
|----------------------|----------------------------------------------|--------------------------------------------|
| **Memory Allocation** | Each member has its own memory location.     | All members share the same memory location. |
| **Size**             | Size equals the sum of all member sizes.     | Size equals the size of the largest member. |
| **Use Case**         | Used for storing different types of data.    | Used for memory-efficient programs.         |

**Code Example**:  
```cpp
#include <iostream>
using namespace std;

struct StructExample {
    int a;
    char b;
    double c;
};

union UnionExample {
    int a;
    char b;
    double c;
};

int main() {
    StructExample s = {10, 'A', 3.14};
    UnionExample u;
    u.a = 10; // Sets 'a'

    cout << "Structure size: " << sizeof(s) << endl;
    cout << "Union size: " << sizeof(u) << endl;

    // Accessing union members
    u.b = 'A'; // Overwrites 'a'
    cout << "Union member 'a' after setting 'b': " << u.a << endl; // Undefined behavior

    return 0;
}
```  

---

### Q6: Employee Management System (Struct and Functions Implementation)  

**Code**:  
Here is the simplified employee management system without using vectors. Instead, we use a static array to store employee records:

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Employee {
    string name;
    int id;
    string department;
    double salary;
};

const int MAX_EMPLOYEES = 100;
Employee employees[MAX_EMPLOYEES];
int employeeCount = 0;

void addEmployee() {
    if (employeeCount >= MAX_EMPLOYEES) {
        cout << "Employee directory is full!" << endl;
        return;
    }

    Employee e;
    cout << "Enter Name: ";
    cin >> e.name;
    cout << "Enter ID: ";
    cin >> e.id;
    cout << "Enter Department: ";
    cin >> e.department;
    cout << "Enter Salary: ";
    cin >> e.salary;
    employees[employeeCount++] = e;

    cout << "Employee added successfully!" << endl;
}

void displayEmployees() {
    if (employeeCount == 0) {
        cout << "No employees to display." << endl;
        return;
    }
    for (int i = 0; i < employeeCount; i++) {
        cout << "ID: " << employees[i].id 
             << ", Name: " << employees[i].name 
             << ", Department: " << employees[i].department 
             << ", Salary: " << employees[i].salary << endl;
    }
}

void searchEmployee() {
    int id;
    cout << "Enter Employee ID to search: ";
    cin >> id;
    for (int i = 0; i < employeeCount; i++) {
        if (employees[i].id == id) {
            cout << "Found: ID: " << employees[i].id 
                 << ", Name: " << employees[i].name 
                 << ", Department: " << employees[i].department 
                 << ", Salary: " << employees[i].salary << endl;
            return;
        }
    }
    cout << "Employee not found." << endl;
}

void updateEmployeeSalary() {
    int id;
    cout << "Enter Employee ID to update salary: ";
    cin >> id;
    for (int i = 0; i < employeeCount; i++) {
        if (employees[i].id == id) {
            cout << "Enter new salary: ";
            cin >> employees[i].salary;
            cout << "Salary updated successfully!" << endl;
            return;
        }
    }
    cout << "Employee not found." << endl;
}

void deleteEmployee() {
    int id;
    cout << "Enter Employee ID to delete: ";
    cin >> id;
    for (int i = 0; i < employeeCount; i++) {
        if (employees[i].id == id) {
            for (int j = i; j < employeeCount - 1; j++) {
                employees[j] = employees[j + 1]; // Shift elements left
            }
            employeeCount--;
            cout << "Employee deleted successfully!" << endl;
            return;
        }
    }
    cout << "Employee not found." << endl;
}

int main() {
    int choice;
    while (true) {
        cout << "\n1. Add Employee\n2. Display Employees\n3. Search Employee\n4. Update Employee Salary\n5. Delete Employee\n6. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        switch (choice) {
            case 1: addEmployee(); break;
            case 2: displayEmployees(); break;
            case 3: searchEmployee(); break;
            case 4: updateEmployeeSalary(); break;
            case 5: deleteEmployee(); break;
            case 6: return 0;
            default: cout << "Invalid choice! Try again." << endl;
        }
    }
}
```

