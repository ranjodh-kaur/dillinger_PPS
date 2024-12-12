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
##### **Q4:**  **Scenario:**                                                                    **[Marks: 4]**
Sara is willing to develop a calculator program in C++ for a basic math utility. Her goal is to design a program that allows users to perform arithmetic operations interactively by reading two float values and one character value from the user. She needs your help to complete her goal.  
Can you help her by writing a menu-driven program with separate functions for addition, subtraction, multiplication, and division?  
**Input Format:**  
- The first line reads two float values from the user.  
- The second line reads a character (`+`, `-`, `*`, `/`) representing the operation to be performed.  
**Output Format:**  
The output consists of a float value representing the result of the specific operation.  

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
5 1
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
