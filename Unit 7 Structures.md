# Unit-7 Structures and Unions

| TOPICS | DETAILS |
| --- | --- |
| Structures | Need and syntax of structures |
| Structure Operations | Passing and returning structures from functions, Nested Structures, Array of Structures, typedef |
| Union | Structure versus Union. |

***

#### **Structures** : Think of a **structure** like a **folder** where you store related documents together.

***

**Why Do We Need Structures?**

Imagine you want to store information about a student. You could store their name, roll number, and marks separately in different variables, but wouldn't it be more convenient to group them together under one label? That's where a **structure** comes in—it allows you to store related data in a single entity.

**Structure Syntax**:

A structure is a blueprint or template that defines a collection of variables under one name.

**Example**:

```c
struct Student {
    string name;      // Stores the student's name
    int rollNumber;   // Stores the roll number
    float marks;      // Stores the marks
};
```

Here, `Student` is like a folder that groups different types of information: `name`, `rollNumber`, and `marks`. You can create many student "folders" using this blueprint.

**Using Structures**:

You can create actual instances of the structure (folders) and use them:

```c
Student student1;
student1.name = "Alice";
student1.rollNumber = 101;
student1.marks = 89.5;
```

**Example**

```c
#include<iostream>
using namespace std;
struct Student {
    string name;      // Stores the student's name
    int rollNumber;   // Stores the roll number
    float marks;      // Stores the marks
};
int main()
{ 
Student student1;
student1.name = "Alice";
student1.rollNumber = 101;
student1.marks = 89.5;
cout<<student1.name<<endl;
cout<<student1.rollNumber<<endl;
cout<<student1.marks<<endl;
return 0;
}
```

***

### **Structure Operations:**

***

1. **Passing and Returning Structures from Functions**:<br>

Just like how you pass individual variables to functions, you can pass the whole structure too.

```c
void printStudent(Student s) {
    cout << s.name << " " << s.rollNumber << " " << s.marks;
}
```

**Example 1**

```c
#include<iostream>
using namespace std;
struct Student {
string name;      // Stores the student's name
int rollNumber;   // Stores the roll number
float marks;      // Stores the marks
};
void printStudent(Student s) {
cout << s.name << " " << s.rollNumber << " " << s.marks;
}
int main()
{ Student student1; 
student1.name = "Alice";
student1.rollNumber = 101;
student1.marks = 89.5;
printStudent(student1);
return 0;
}
```

**Example 2**

```c
#include <iostream>
using namespace std;
 struct Student {
 string name;     
 int rollNumber;  
 float marks;    
 };
 void printStudent(Student &s) {
 cout << s.name << " " << s.rollNumber << " " << s.marks;
 }
 void inStudent(Student &s) {
 s.name = "Alice";
 s.rollNumber = 101;
 s.marks = 89.5;
 }
 int main() {
 Student student1;
 inStudent(student1);
 printStudent(student1);
 return 0;
 }
```

2. **Nested Structures**:
You can have structures inside structures, like folders inside folders.

```c
struct Address {
    string city;
    int zipCode;
};

struct Student {
    string name;
    Address addr;
};
```
3. **Array of Structures**:

Think of having multiple folders (students) in one big container (an array).

```c
Student class[30]; // Array of 30 students
```

**Example 1**

```c
#include <iostream>
 using namespace std;
 #define MAX_STUDENTS 3
 // Define a structure to represent a student
 struct Student {
 string name;  // Use string instead of char array
 int id;
 };

 int main() {
 // Declare an array of Student structures
 Student students[MAX_STUDENTS];

 // Fill in the details for each student
 students[0].name = "Alice";
 students[0].id = 1001;

 students[1].name = "Bob";
 students[1].id = 1002;

 students[2].name = "Charlie";
 students[2].id = 1003;

 // Display the details of each student
 cout << "Student Details:" << endl;
 for (int i = 0; i < MAX_STUDENTS; i++) {
     cout << "Student " << i + 1 << ":" << endl;
     cout << "Name: " << students[i].name << endl;
     cout << "ID: " << students[i].id << endl;
 }
 return 0;
 }
```

**Example 2**

Define a structure called Student with members name, rollNumber, and marks. Declare an array students of type Student to hold information for multiple students. Fill in the details (name, roll number, and marks) for each student in the array. Display the details of each student in the array using a loop.

```c
#include <iostream>
using namespace std;
// Define a structure to represent a student
struct Student {
string name;   // Replaced char array with string
int rollNumber;
float marks;
};

int main() {
// Define an array of structures to hold student information
Student students[3];  // Array of 3 students

// Fill in the details for each student
students[0].name = "Alice";
students[0].rollNumber = 101;
students[0].marks = 85.5;

students[1].name = "Bob";
students[1].rollNumber = 102;
students[1].marks = 78.0;

students[2].name = "Charlie";
students[2].rollNumber = 103;
students[2].marks = 92.2;

// Display the details of each student
for (int i = 0; i < 3; i++) {
    cout << "Student " << i + 1 << " Details:" << endl;
    cout << "Name: " << students[i].name << endl;
    cout << "Roll Number: " << students[i].rollNumber << endl;
    cout << "Marks: " << students[i].marks << endl;
    cout << endl;
}
return 0;
}
```

**Example 3:**

Define a structure called Employee with members name, employeeID, and salary. Declare an array of Employee structures to store details for multiple employees. Fill in the details (name, employee ID, and salary) for each employee. Use a loop to display the details of each employee.

```c
#include <iostream>
using namespace std;

// Define a structure to represent an employee
struct Employee {
string name;     // Use string instead of char array
int employeeID;
float salary;
};

int main() {
// Declare an array of Employee structures
Employee employees[3];

// Fill in the details for each employee
employees[0].name = "John Doe";
employees[0].employeeID = 1001;
employees[0].salary = 60000.0;

employees[1].name = "Alice Smith";
employees[1].employeeID = 1002;
employees[1].salary = 55000.0;

employees[2].name = "Bob Johnson";
employees[2].employeeID = 1003;
employees[2].salary = 58000.0;

// Display the details of each employee
for (int i = 0; i < 3; i++) {
    cout << "Employee " << i + 1 << " Details:" << endl;
    cout << "Name: " << employees[i].name << endl;
    cout << "Employee ID: " << employees[i].employeeID << endl;
    cout << "Salary: $" << employees[i].salary << endl;
    cout << endl;
}
return 0;
}
```
4. **`typedef`**:

A shortcut to make your code cleaner. If typing `struct Student` feels long, you can use `typedef` to create an alias.

```c
typedef struct {
    string name;
    int rollNumber;
} Student;
```

**Example 1:** Basic Usage with Primitive Data Types

```c
typedef int Integer;
Integer x = 10;  // Now Integer is the same as int
cout << x << endl;
```

**Example 2:** Using typedef with Structures

```c
#include <iostream>
 using namespace std;
 // Define a structure
 struct Employee {
 string name;
 int employeeID;
 float salary;
 };
 // Create an alias for Employee structure
 typedef struct Employee Emp;
 int main() {
 // Now Emp can be used instead of struct Employee
 Emp e1;
 e1.name = "John Doe";
 e1.employeeID = 1234;
 e1.salary = 50000.0;
 cout << "Employee Name: " << e1.name << endl;
 cout << "Employee ID: " << e1.employeeID << endl;
 cout << "Employee Salary: " << e1.salary << endl;
 return 0;
 }
```

***

##### **Unions** : Think of a **union** like a **locker** that can hold only one item at a time, but the item can be different types.

***

**What is a Union?**<br>

A **union** is similar to a structure, but it can store only one variable at a time. All members of the union share the same memory space, so only the most recently assigned value will be stored.

**Syntax**:

```c
union Data {
    int integerValue;
    float floatValue;
    char character;
};
```

Here, `Data` is a union, and it can hold either an integer, a float, or a character, but not all of them at once. If you assign a value to `integerValue`, the other members lose their value because they all share the same memory space.

**Example**:

```c
Data d;
d.integerValue = 10;   // Stores integer
d.floatValue = 5.5;    // Overwrites integer with float
```

**Union Example**

```c
#include <iostream>
using namespace std;

union Data {
    int integerValue;
    float floatValue;
    char charValue;
};

int main() {
    Data data;  // Create a union variable

    // Assign an integer value to the union
    data.integerValue = 100;
    cout << "Integer Value: " << data.integerValue << endl;

    // Now assign a float value
    data.floatValue = 98.6;
    cout << "Float Value: " << data.floatValue << endl;

    // Now assign a character value
    data.charValue = 'A';
    cout << "Char Value: " << data.charValue << endl;

    // After assigning charValue, integerValue and floatValue may not be valid anymore
    cout << "After assigning charValue:" << endl;
    cout << "Integer Value: " << data.integerValue << endl;  // Value is overwritten
    cout << "Float Value: " << data.floatValue << endl;      // Value is overwritten
    cout << "Char Value: " << data.charValue << endl;

    return 0;
}
```

**Structures vs Unions**:

* **Structure**: All members have their own space in memory. You can access all members at the same time.
* **Union**: All members share the same space. Only one member can hold a value at any given time.

**Key Differences:**

| **Feature** | **Structure** | **Union** |
| --- | --- | --- |
| **Memory Usage** | Each member gets its own space in memory. | All members share the same memory. |
| **Access** | Can access all members at once. | Can only access one member at a time. |
| **Usage** | Used when you need to store multiple related data at once. | Used when you only need one value at a time. |

* **Structures** are useful when you want to group multiple related pieces of data and access them simultaneously.
* **Unions** are useful when you need to store different types of data but only care about one value at a time.

***
***
**Structure Excercise Program :**
___

**1. Define a structure called Person with members name, age, and height. Declare a variable person1 of type Person. Fill in the details (name, age, and height) for person1. Display the details of person1.**

```c
#include<iostream>
using namespace std;
struct Person {
string name;
int age;
float height;
};
int main() {
Person person1= {"John", 30, 5.9};
cout<<person1.name<<person1.age<<person1.height;
return 0;
}
```

**Following is by using function**

```c
#include<iostream>
using namespace std;
struct Person {
string name;
int age;
float height;
};
void displayPerson(struct Person p) {
cout<< p.name;
cout<< p.age;
cout<< p.height;
}
int main() {
Person person1 = {"John", 30, 5.9};
displayPerson(person1);
return 0;
}
```
**2. Define a structure called Point with members x and y representing coordinates. Declare a variable p1 of type Point. Fill in the coordinates for p1. Display the coordinates of p1.**

```c
#include<iostream>
using namespace std;
// Define a structure to represent a point in 2D space
struct Point {
int x;
int y;
};
int main() {
// Declare a variable of type Point
Point p1;
// Fill in the details for the point
p1.x = 10;
p1.y = 20;
// Display the details of the point
cout<< p1.x<<" "<< p1.y;
return 0;
}
```
**3. Define a structure called Book with members title, author, and price. Declare a variable book1 of type Book. Fill in the details (title, author, and price) for book1. Display the details of book1.**

```c
#include<iostream>
#include<cstring>
using namespace std;
// Define a structure to represent a book
struct Book {
string title;
string author;
float price;
};
int main() {
// Declare a variable of type Book
Book book1;
// Fill in the details for the book
strcpy(book1.title, "The C++ Programming Language");
strcpy(book1.author, "Brian W. Kernighan and Dennis M. Ritchie");
book1.price = 29.99;
// Display the details of the book
cout<<"Book Details:\n";
cout<<"Title: \n"<<book1.title;
cout<<"Author: \n"<<book1.author;
cout<<"Price: $\n"<<book1.price;
return 0;
}
```
**4. Define a structure called Car with members make, model, year, and price. Declare a variable myCar of type Car. Fill in the details (make, model, year, and price) for myCar. Display the details of myCar.**

```c
#include<iostream>
#include<cstring>
using namespace std;
// Define a structure to represent a car
struct Car {
string make;
string model;
int year;
float price;
};
int main() {
// Declare a variable of type Car
struct Car myCar;
// Fill in the details for the car
strcpy(myCar.make, "Toyota");
strcpy(myCar.model, "Corolla");
myCar.year = 2020;
myCar.price = 20000.00;
// Display the details of the car
cout<<"Car Details:\n";
cout<<"Make: "<< myCar.make;
cout<<"\nModel: "<< myCar.model;
cout<<"\nYear: "<< myCar.year;
cout<<"\nPrice: $"<< myCar.price;
return 0;
}
```
**5. Define a structure called Employee with members name, employeeID, and salary. Declare a variable emp1 of type Employee. Fill in the details (name, employee ID, and salary) for emp1. Display the details of emp1.**

```c
#include<iostream>
 using namespace std;
 // Define a structure to represent an employee
 struct Employee {
 string name;
 int employeeID;
 float salary;
 };
 int main() {
 // Declare a variable of type Employee
 struct Employee emp1;
 // Fill in the details for the employee
 cin>>emp1.name;
 emp1.employeeID = 1001;
 emp1.salary = 50000.0;
 // Display the details of the employee
 cout<<"Employee Details:\n";
 cout<<"Name: "<< emp1.name;
 cout<<"\nEmployee ID: "<< emp1.employeeID;
 cout<<"\nSalary: $"<< emp1.salary;
 return 0;
 }
```
**6. Define a structure called Computer with members brand, model, year, and price. Declare a variable myComputer of type Computer. Fill in the details (brand, model, year, and price) for myComputer. Display the details of myComputer.**

```c
#include <iostream>
using namespace std;
// Define a structure to represent a computer
struct Computer {
string brand;  // Using std::string instead of char array
string model;  // Using std::string instead of char array
int year;
float price;
};
int main() {
// Declare a variable of type Computer
Computer myComputer;
// Fill in the details for the computer
cout<<"Computer Brand: ";
cin>> myComputer.brand;
cout<<"\n Computer Model: ";
cin>>myComputer.model;
cout<<"\n Computer Year: ";
cin>>myComputer.year;
cout<<"\nComputer Price: ";
cin>>myComputer.price;
// Display the details of the computer
cout << "Computer Details:" << endl;
cout << "Brand: " << myComputer.brand << endl;
cout << "Model: " << myComputer.model << endl;
cout << "Year: " << myComputer.year << endl;
cout << "Price: $" << myComputer.price << endl;
return 0;
}
```
**7. Define a structure called BankAccount with members accountNumber, accountHolderName, and balance. Declare a variable account1 of type BankAccount. Fill in the details (account number, account holder name, and balance) for account1. Display the details of account1.**

```c
#include <iostream>
using namespace std;
// Define a structure to represent a bank account
struct BankAccount {
string accountNumber;
string accountHolderName;
float balance;
};

// Function to input bank account details
void inputBankAccountDetails(BankAccount &account) {
cin>>account.accountNumber;
cin>>account.accountHolderName;
cin>>account.balance;
}

// Function to display bank account details
void displayBankAccountDetails(const BankAccount &account) {
cout << "Bank Account Details:" << endl;
cout << "Account Number: " << account.accountNumber << endl;
cout << "Account Holder: " << account.accountHolderName << endl;
cout << "Balance: $" << account.balance << endl;
}

int main() {
// Declare a variable of type BankAccount
BankAccount account1;

// Fill in the details for the bank account
inputBankAccountDetails(account1);

// Display the details of the bank account
displayBankAccountDetails(account1);

return 0;
}
```

