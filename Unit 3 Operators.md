
# Unit-3 Operators
_______


| Topics | Detail |
| --- | --- |
| Different types of Operators: | Assignment Operators, Numeric operators, Prefix and postfix operators, Binary number system, Bitwise operators, Logical operators, Relational operators, Short-circuit operators, sizeof operator |
| Operator precedence and associativity. |  |
| Type conversion. |  |

***

### 1. Assignment Operators

* Think of assignment operators as the act of "giving" a value to something.
* In a classroom, it's like assigning each student a seat number. You assign a value to a variable using =.
* Description: Used to assign values to variables.

**Examples:** =, +=, -=, *=, /=, %=

   ```c
    #include <iostream>
    using namespace std;
    int main() {
    int x = 5;
    cout<<x; //output 5
    x += 3;
    cout<<x; //output 8
    x -= 3;
    cout<<x; //output 5
    x *= 3;
    cout<<x;// output 15
    x /= 3;
    cout<<x; // output 5
    x %= 3;
    cout<<x; // output 2
    return 0;
    }
```

### 2. Numeric Operators / Arithmetic Operators

Description: Used for mathematical calculations.<br>
**Arithmetic operators** are like basic calculators that add, subtract, multiply, or divide.
* x + y adds two numbers, x - y subtracts, x * y multiplies, and x / y divides.

**Examples:** + (addition), - (subtraction), * (multiplication), / (division), % (modulus)

   ```c
    #include <iostream>
    using namespace std;
    int main() {
    int x = 5;
    int y = 3;
    cout<< x + y; // Output 8
    return 0;
    }
```

### 3. Prefix and Postfix Operators:

Think of prefix and postfix operators like a person checking items off a list, sometimes before or after counting them.

**Prefix:** The operator appears before the variable, e.g., + + x , - - x.<br>
**Postfix:** The operator appears after the variable, e.g., x + + , x - -.

**Prefix Operator:**

- Prefix Increment (++var): Increments the value of var by 1, and then returns the incremented value.
 - Prefix Decrement (–var): Decrements the value of var by 1, and then returns the decremented value.

 ```c
    #include <iostream>
    using namespace std;
    int main() {
    int a = 5;
    int b;

    // Prefix increment
    b = ++a; // a is incremented first, then b is assigned the value of a
    cout<<"Prefix increment:" <<endl;
    cout<<"a = "<<a<< endl; // 6
    cout<<"b = "<<b<< endl; // 6

    // Reset a
    a = 5;
    // Postfix increment
    b = a++; // b is assigned the value of a, then a is incremented
    cout<<"Postfix increment:"<<endl;
    cout<<"a = "<<a<<endl; // 6
    cout<< "b = " << b <<endl; // 5

    // Prefix decrement
    b = --a; // a is decremented first, then b is assigned the value of a
    cout<< "Prefix decrement:"<<endl;
    cout << "a = " << a <<endl; // 5
    cout << "b = " << b <<endl; // 5

    // Postfix decrement
    b = a--; // b is assigned the value of a, then a is decremented
   cout<< "Postfix decrement:"<<endl;
   cout << "a = " << a <<endl; // 4
   cout << "b = " << b <<endl; // 5

    return 0;
    }
   ```

**Postfix Operator**
- Postfix Increment (var++): Returns the current value of var, and then increments the value by 1.
- Postfix Decrement (var–): Returns the current value of var, and then decrements the value by 1.

### 4. Binary Number System

* Imagine you have a switchboard with only two options: ON (1) and OFF (0).
**Description:** A base-2 numeral system using digits 0 and 1. Common in computing for representing binary data.

#### - Binary to Decimal Conversion

![Screenshot 2024-08-28143235.png](https://www.dropbox.com/scl/fi/a17kic69omno2npm9rxs5/Screenshot-2024-08-28-143235.png?rlkey=ss3vb86wfeew1er029g7kuv6j&dl=0&raw=1)

#### - Decimal to Binary Conversion

![Screenshot 2024-08-29 114917.png](https://www.dropbox.com/scl/fi/4lycqipoae1yy1gjif4ec/Screenshot-2024-08-29-114917.png?rlkey=kvnaycxyuazlbn5g0zsq6yqsn&dl=0&raw=1)

### 5. Bitwise Operators

* Bitwise operators are like working on each switch in a circuit board, turning bits on or off in each position individually.
* Description: Operate on binary representations of numbers.
* Example: The bitwise AND & operator keeps a bit on only if both corresponding bits are 1. For 5 & 3, the result is 1 (because in binary, 101 & 011 = 001).

**Examples:** & (AND), | (OR), ^ (XOR), ~ (NOT), << (left shift), >> (right shift)

```c
#include <iostream>
using namespace std;
int main() {
    int a = 5; // binary: 0101
    int b = 3; // binary: 0011
   cout << "a & b: " << (a & b) << endl; // 1
   cout << "a | b: " << (a | b) << endl; // 7
   cout << "a ^ b: " << (a ^ b) << endl; // 6
   cout << "~a: " << (~a) << endl;       // -6
   cout << "a << 1: " << (a << 1) << endl; // 10
   cout << "a >> 1: " << (a >> 1) << endl; // 2
    return 0;
}

```

### 6. Logical Operators

* Logical operators are like filters that decide if conditions are met.
* Example: if (x > 0 && y > 0) checks if both x and y are greater than 0.
* Description: Used to perform logical operations.

**Examples:** && (AND), || (OR), ! (NOT)

```c
#include <iostream>
using namespace std;
int main() {
int x = 5;
int y = 3;
// Returns 1 (true) because 5 is greater than 3 AND 5 is less than 10
cout<<( x > 3 && x < 10); // Output 1
cout<<(x > 3 || x < 4); // Output 1
cout<<(!(x > 3 && x < 10)); // Output 0
return 0;
}
```

### 7. Relational Operators

* These are like comparison tools, like when you check if one item is bigger or equal to another.
* Example: x > y checks if x is greater than y
* Description: Compare two values and return a boolean result.

**Examples:** == (equal to), != (not equal to), > (greater than), < (less than), >= (greater than or equal to), <= (less than or equal to)

```c
#include <iostream>
using namespace std;
int main() {
int x = 5;
int y = 5;
cout<<( x == y); // returns 1 (true) because 5 is equal to 5
cout<<( x != y); // returns 1 (true) because 5 is not equal to 3
cout<<( x > y); // returns 1 (true) because 5 is greater than 3
cout<<( x < y); // returns 0 (false) because 5 is not less than 3
cout<<( x >= y); // Returns 1(true) because five is greater than, or equal, to 3
cout<<( x <= y); // Returns 0 (false) because 5 is neither less than or equal to 3
return 0;
}
```

### 8. Short-Circuit Operators

* Imagine you stop reading a checklist as soon as you confirm everything is okay, without going through all items.
* Description: Logical operators that stop evaluating as soon as the result is determined.
* Example: In if (x > 0 && y > 0), if x is not greater than 0, it won't even check y.
* Short-circuit operators (&&, ||) skip the second condition if the result can be determined from the first condition alone. This can improve efficiency in conditions.

**Examples:** && (AND), || (OR)

```c
// C program to illustrate the concept
// of short circuiting
#include <iostream>
using namespace std;
// Driver Code
int main()
{
    int x = 1;

    if (x || ++x) {
        cout<<x;
    }

    return 0;
}
```

### 9. sizeof Operator

* sizeof is like a ruler that measures how much space an item takes up.
* Example: sizeof(int) tells you how many bytes an integer occupies in memory.
* Explanation: The sizeof operator returns the amount of memory, in bytes, required to store a data type or variable.
* Description: Returns the size of a data type or object in bytes.
**Like:** sizeof(int) might return 4.

```c
#include <iostream>
using namespace std;
int main() {
    int a = 10;
    double b = 12.34;
    
    cout<< sizeof(int);
    cout<<sizeof(a);
    cout<<sizeof(double);
    cout<<sizeof(b);
    
    return 0;
}
```

**Output:**
Size of int: 4 bytes
Size of a: 4 bytes
Size of double: 8 bytes
Size of b: 8 bytes

### 10. Operator Precedence and Associativity

* Precedence and associativity are like traffic rules that decide which vehicles (operators) go first at an intersection.
* Example: In 3 + 4 * 5, multiplication (*) has higher precedence than addition (+), so 4 *5 happens first.
* Operators with higher precedence execute before those with lower precedence. Associativity defines the direction of execution when operators have the same precedence, such as left-to-right or right-to-left.
* **Operator Precedence:** Determines the order in which operators are evaluated.<br>
**Associativity:** Defines how operators of the same precedence are grouped in the absence of parentheses  ( ).

**Examples:** In 3 + 4 * 2, multiplication has higher precedence, so it is evaluated before addition.

![precedence](https://media.geeksforgeeks.org/wp-content/uploads/20230516162457/Operator-Precedence-in-C-01.webp)

![p2](https://media.geeksforgeeks.org/wp-content/uploads/20230721155606/Operator-Associativity.png)

![p3](https://media.geeksforgeeks.org/wp-content/uploads/20230721155606/Operator-Associativity.png)

### 11. Type Conversion

* Type conversion is like changing the format of a recipe to make it compatible with different measurement units.
* Example: float f = 3; automatically converts 3 (an integer) to a float.
* Explanation: Type conversion changes one data type to another, either automatically (implicit) or manually (explicit), such as from int to float.
  - Implicit Conversion: Automatic conversion of data types by the compiler.
  - Explicit Conversion (Casting): Manually converting one data type to another.

**Examples:**

```c
    int x = (int)3.14; (explicit)
    double y = 3; (implicit)
```

***

Type conversion in C++ is the process of converting one data type into another. There are two main types of type conversions in C++:

1. **Implicit Type Conversion (Type Promotion)**:
    - Automatically performed by the compiler when it converts a smaller data type to a larger data type.
    - Also known as **automatic type conversion**.
    - It occurs when there is no risk of data loss.
  
   **Example:**
       Converting an `int` to a `float`, or `char` to an `int`.
    **Example:**
     ```c
    int a = 10;
    float b = a; // Implicit conversion from int to float
     ```

2. **Explicit Type Conversion (Type Casting)**:
  - Done manually by the programmer.
  - It can lead to data loss if converting from a larger to a smaller data type (e.g., `float` to `int`).
  - C++ provides two ways for explicit type conversion:
    1. **C- style cast**

**1. Implicit Type Conversion Example:**
When smaller data types (like `int` or `char`) are converted to larger data types (like `float` or `double`) automatically.

```c
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    float b = a;  // Implicit conversion
    cout << "The value of b: " << b << endl; // Output will be 10.0 (float)
    return 0;
}
```

**2. Explicit Type Conversion (Type Casting):**
        a) C-Style Cast:

```c
int a = 10;
float b = (float)a;  // C-style cast
```

**Type Conversion Risks:**

* **Data Loss**: Explicit conversion from larger to smaller types may result in loss of information.

```c
float a = 10.75;
int b = (int)a;  // Explicit conversion: b = 10, fractional part is lost
```

***

##### Possible Questions:

LOTS:

* What is the role of the assignment operator = in programming?
* Give an example of a logical operator in programming.
* How does the sizeof operator work in C/C++?

HOTS:

* Explain how operator precedence and associativity affect the evaluation of the expression 2 + 3 * 5.
* Describe a scenario where short-circuit operators could be useful in programming.
* Compare and contrast implicit and explicit type conversion, providing examples where each might be preferred.
