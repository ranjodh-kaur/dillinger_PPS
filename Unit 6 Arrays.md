
# Unit-6 Arrays

| TOPICS | DETAILS |
| --- | --- |
| Arrays | Single-Dimensional and Multi-Dimensional arrays, Array operations |
| Strings | Character array and strings literals, string literals declaring, initializing, and using strings basic string operations, comparing strings |
| Pointers | declaring and initializing pointers |

***

### **Arrays**

Think of **arrays** as a row of containers where you store items. In C++, arrays help us store and organize data efficiently.

#### **1. Single-Dimensional Array**

Imagine a row of boxes, each with a number. Each box (or element) holds one piece of data, like a number or a word.

* **Declaring**: `int scores[5];` — This line creates an array called `scores` that can hold 5 integer numbers.
* **Initializing**: `int scores[5] = {90, 85, 78, 92, 88};` — Here, each score fills one box (element) in the array.
* **Accessing**: Use `scores[2]` to access the 3rd box in the row (remember, arrays start at 0), which would be `78`.
* A single-dimensional array is a linear collection of elements of the same type. You can think of it as a list.
* **Example:**
    ```c
    #include <iostream>
    using namespace std;
    int main() {
    // Declaration
    int arr[5];
    // Initialization
    arr[0] = 10;
    arr[1] = 20;
    arr[2] = 30;
    arr[3] = 40;
    arr[4] = 50;
    // Accessing elements
    for (int i = 0; i < 5; i++) {
    cout << "Element at index " << i << ": " << arr[i] << endl;
    }
    return 0;
    }
    ```

#### **2. Multi-Dimensional Array**

A multi-dimensional array is like a grid, or a table, where you have rows and columns. Often used for matrices.
A multi-dimensional array is an array of arrays. The most common form is the two-dimensional array.

* **2D Array (Matrix)**: `int matrix[3][3];` creates a 3x3 grid where each cell can hold an integer.
* **Example Initialization**:
    ```c
    int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
    };
    ```
Here, `matrix[1][2]` accesses the item in the 2nd row and 3rd column (which is `6`).<br>
- **Example**
    ```c
    #include <iostream>
    using namespace std;

    int main() {
    // Declaration and initialization of a 2D array
    int matrix[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };

    // Accessing elements
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            cout << "Element at [" << i << "][" << j << "]: " << matrix[i][j] << endl;
            }
    }
    return 0;
    }
    ```

### **Array Operations**

With arrays, you can:

* **Access elements** by index, like `array[index]`.  (like opening a locker by its number).
* **Update elements** by assigning new values to indexes.
* **Loop through** the array using loops to perform actions on all elements.

Array operations encompass a range of activities you can perform on arrays, including accessing, traversing, modifying, searching, and sorting. Below are some common operations with detailed explanations and examples in C++.

### Array Operations

* **Accessing Elements:** Retrieve values using indices.
* **Traversing:** Loop through elements.
* **Modifying:** Change values at specific indices.
* **Searching:** Find elements using algorithms like linear search.
* **Sorting:** Arrange elements in order (e.g., using bubble sort).
* **Sum and Average:** Calculate the total and mean of elements.
* **Copying:** Duplicate the contents of one array to another.

These operations form the basis for working with arrays in C++. Let me know if you need further explanations or examples!

### 1. Accessing Array Elements

You can access individual elements of an array using their index. Indexing in C++ starts at 0.

- **Example:**
    ```c
    #include <iostream>
    using namespace std;

    int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    // Accessing elements
    cout << "First element: " << arr[0] << endl; // Output: 10
    cout << "Second element: " << arr[1] << endl; // Output: 20

    return 0;
    }
    ```
### 2. Traversing an Array

Traversing involves iterating through each element of the array, often to display them or perform operations.

- **Example:**
    ```c
    #include <iostream>
    using namespace std;

    int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    cout << "Elements in the array: ";
    for (int i = 0; i < 5; i++) {
        cout << arr[i] << " ";  // Output: 10 20 30 40 50
    }
    cout << endl;

    return 0;
    }
    ```

### 3. Modifying Array Elements

You can change the value of an element at a specific index.
- **Example:**
    ```c
    #include <iostream>
    using namespace std;

    int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    // Modifying an element
    arr[2] = 35; // Changing 30 to 35
    cout << "Modified third element: " << arr[2] << endl; // Output: 35

    return 0;
    }
    ```

### 4. Searching for an Element

You can search for a specific element in an array using a linear search or binary search (if the array is sorted).

**Linear Search Example:**

```
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int searchValue = 30;
    bool found = false;

    for (int i = 0; i < 5; i++) {
        if (arr[i] == searchValue) {
            found = true;
            cout << searchValue << " found at index: " << i << endl; // Output: 30 found at index: 2
            break;
        }
    }

    if (!found) {
        cout << searchValue << " not found in the array." << endl;
    }

    return 0;
}
```

### 5. Sorting an Array

You can sort an array using various algorithms. Below is an example using the bubble sort algorithm.

**Bubble Sort Example:**

```
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {40, 10, 30, 20, 50};
    int n = 5;

    // Bubble Sort
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                // Swap arr[j] and arr[j+1]
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " "; // Output: 10 20 30 40 50
    }
    cout << endl;

    return 0;
}
```

### 6. Finding the Sum and Average of Array Elements

You can compute the sum and average of the elements in an array.

**Example:**

```
#include <iostream>
using namespace std;

int main() {
    int arr[5] = {10, 20, 30, 40, 50};
    int sum = 0;

    // Calculating sum
    for (int i = 0; i < 5; i++) {
        sum += arr[i]; // Sum of elements
    }

    double average = sum / 5.0; // Average calculation

    cout << "Sum: " << sum << endl; // Output: Sum: 150
    cout << "Average: " << average << endl; // Output: Average: 30

    return 0;
}
```

### 7. Copying an Array

You can copy the contents of one array to another.

**Example:**

```
#include <iostream>
using namespace std;

int main() {
    int arr1[5] = {1, 2, 3, 4, 5};
    int arr2[5];

    // Copying arr1 to arr2
    for (int i = 0; i < 5; i++) {
        arr2[i] = arr1[i];
    }

    cout << "Elements of arr2: ";
    for (int i = 0; i < 5; i++) {
        cout << arr2[i] << " "; // Output: 1 2 3 4 5
    }
    cout << endl;

    return 0;
}
```

***

### **Character Arrays and String Literals**

In C++, a **character array** (or `char` array) holds a sequence of characters, like a word or sentence.<br>

A character array can be used to store a string in C++. Strings are null-terminated arrays of characters.

#### **Character Arrays**

* **Declaring**: `char name[6] = "Alice";` — Here, each character (`A`, `l`, `i`, `c`, `e`) is stored in its own spot, ending with a `\0` (null character) to show the end of the word.
* **Example**

```
 #include <iostream>
  using namespace std;
  int main() {
  // Character array
  char name[20] = "Hello, World!";
  // Printing the character array
  cout << "Character Array: " << name << endl;
  // Accessing individual characters
  cout << "First character: " << name[0] << endl;
  return 0;
  }
```

#### **String Literals**

A **string literal** is a series of characters enclosed in quotes, like `"Hello"`.

* **Declaring** a C++ string: `string greeting = "Hello";`
* **Basic String Operations**:
  - `str.length()` gives the length of the string.
  - `str1 + str2` joins two strings together.
  - `str1 == str2` compares two strings to check if they're the same.
* **Example**

```
#include <iostream>
#include <string>  // Include string library
using namespace std;
int main() {
// String literals
string str1 = "Hello";
string str2 = "World";
// Concatenation
string result = str1 + " " + str2;
cout << "Concatenated String: " << result << endl;
// Comparing strings
if (str1 == str2) {
    cout << "Strings are equal." << endl;
} else {
    cout << "Strings are not equal." << endl;
}
// Accessing characters
cout << "First character of str1: " << str1[0] << endl;
return 0;
}
```

### **Pointers**

A **pointer** in C++ is like a label that remembers where something is stored rather than storing the item itself.<br>

**Pointers are variables that store the address of another variable.**<br>

Pointers are like a friend who remembers the locker number of an item rather than holding the item directly. They don't store the value themselves, just the address (or locker number) where it's located.

#### **Declaring a Pointer**

To create a pointer, use `*`:

```cpp
int num = 10;
int *ptr = &num;  // 'ptr' holds the address of 'num'
```

Here, `ptr` points to the address where `num` is stored in memory.<br>

Here, `ptr` is like a friend who remembers the "locker number" where `number` is stored.<br>

**Example:**

```cpp
#include <iostream>
 using namespace std;
 int main() {
 int var = 42;  // Regular variable
 int* ptr = &var;  // Pointer declaration and initialization
 cout << "Value of var: " << var << endl;
 cout << "Address of var: " << &var << endl;
 cout << "Value of ptr (address of var): " << ptr << endl;
 cout << "Value pointed to by ptr: " << *ptr << endl;  // Dereferencing
 return 0;
 }
```

#### **Using a Pointer**

* **Dereferencing**: `*ptr` allows you to access the actual value at the address. You can access or update the value in the locker by using the pointer:

```
cout << *ptr;  // This gives the value stored at the address stored in 'ptr'
```

```
cout << *ptr;  // Outputs 10, the value of 'num'
```

Pointers are useful because they let you manage data memory efficiently, especially when passing data to functions or working with large data sets.

***


#### Programs:

**Subtraction of Two Matrices**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;

    // Input number of rows and columns
    cout << "Enter number of rows: ";
    cin >> rows;
    cout << "Enter number of columns: ";
    cin >> cols;

    int A[10][10], B[10][10], C[10][10];

    // Input elements for Matrix A
    cout << "Enter elements of Matrix A:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "A[" << i << "][" << j << "]: ";
            cin >> A[i][j];
        }
    }

    // Input elements for Matrix B
    cout << "Enter elements of Matrix B:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "B[" << i << "][" << j << "]: ";
            cin >> B[i][j];
        }
    }

    // Subtract matrices A and B -> store in C
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            C[i][j] = A[i][j] - B[i][j];
        }
    }

    // Display the result
    cout << "\nResultant Matrix (A - B):\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << C[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output:**
```
Resultant Matrix (A - B):
-3 -1
1 3
```

**Addition of Two Matrices**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;

    // Input number of rows and columns
    cout << "Enter number of rows: ";
    cin >> rows;
    cout << "Enter number of columns: ";
    cin >> cols;

    int A[10][10], B[10][10], C[10][10];

    // Input elements for Matrix A
    cout << "Enter elements of Matrix A:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "A[" << i << "][" << j << "]: ";
            cin >> A[i][j];
        }
    }

    // Input elements for Matrix B
    cout << "Enter elements of Matrix B:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << "B[" << i << "][" << j << "]: ";
            cin >> B[i][j];
        }
    }

    // Add matrices A and B -> store in C
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            C[i][j] = A[i][j] + B[i][j];
        }
    }

    // Display the result
    cout << "\nResultant Matrix (A + B):\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

**Output:**

```
Resultant Matrix (A + B):
6 8
10 12
```

**Multiplication of Two Matrices**

```cpp
#include <iostream>
using namespace std;

int main() {
    int r1, c1, r2, c2;

    // Input dimensions of the first matrix
    cout << "Enter rows and columns of first matrix: ";
    cin >> r1 >> c1;

    // Input dimensions of the second matrix
    cout << "Enter rows and columns of second matrix: ";
    cin >> r2 >> c2;

    // Check if matrix multiplication is possible
    if (c1 != r2) {
        cout << "Matrix multiplication not possible! (Columns of A must equal rows of B)";
        return 0;
    }

    int A[10][10], B[10][10], C[10][10] = {0};

    // Input elements for Matrix A
    cout << "Enter elements of Matrix A:\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c1; j++) {
            cout << "A[" << i << "][" << j << "]: ";
            cin >> A[i][j];
        }
    }

    // Input elements for Matrix B
    cout << "Enter elements of Matrix B:\n";
    for (int i = 0; i < r2; i++) {
        for (int j = 0; j < c2; j++) {
            cout << "B[" << i << "][" << j << "]: ";
            cin >> B[i][j];
        }
    }

    // Multiply matrices A and B -> store in C
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < c1; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    // Display the result
    cout << "\nResultant Matrix (A × B):\n";
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            cout << C[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

**Output: **

```cpp
Resultant Matrix (A × B):
58 64
139 154
```
