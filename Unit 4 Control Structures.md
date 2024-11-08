
# Unit 4. Control Structures
***

### **Conditional Statements**

1. **`if` Statement**:
  - **Description**: Evaluates a condition. If the condition is true, the block of code within the `if` statement is executed.
  - **Syntax**:

```c
if (condition) {
    // code to be executed if condition is true
}
```
  - **Example**:

```c
if (x > 0) {
    cout << "x is positive";
}
```
2. **`if-else` Statement**:
  - **Description**: Provides an alternative block of code if the condition is false.
  - **Syntax**:

```c
if (condition) {
    // code to be executed if condition is true
} else {
    // code to be executed if condition is false
}
```
  - **Example**:

```c
if (x > 0) {
    cout << "x is positive";
} else {
    cout << "x is non-positive";
}
```
3. **The `if-else if` Statement**
  - **Description**: The `if-else if` statement is used to test multiple conditions sequentially. The code block associated with the first condition that evaluates to true is executed, and the rest of the conditions are ignored. If none of the conditions are true, the `else` block (if present) is executed.
  - **Syntax of `if-else if` Statement**

```c
  if (condition1) {
  // Code to execute if condition1 is true
  } else if (condition2) {
  // Code to execute if condition2 is true
  } else if (condition3) {
  // Code to execute if condition3 is true
  } else {
  // Code to execute if none of the above conditions are true
  }
```
  - **Example of `if-else if` Statement** : Let's consider an example to determine a student's grade based on their score:

```c
#include <iostream>
using namespace std;
int main() {
int score;
cout << "Enter the student's score: ";
cin >> score;

 if (score >= 90) {
cout << "Grade: A" << endl;
 } 
 else if (score >= 80) {
cout << "Grade: B" << endl;
}
else if (score >= 70) {
cout << "Grade: C" << endl;
} 
else if (score >= 60) {
cout << "Grade: D" << endl;
}
else {
cout << "Grade: F" << endl;
}
return 0;
}
```

```
- If the score is 90 or above, the program outputs "Grade: A".
- If the score is between 80 and 89, "Grade: B" is output.
- If the score is between 70 and 79, "Grade: C" is output.
- If the score is between 60 and 69, "Grade: D" is output.
- If the score is below 60, "Grade: F" is output.
```
4. **Conditional Operator (`?:`)**:
  - **Description**: A shorthand for `if-else`. It evaluates a condition and returns one of two values.
  - **Syntax**:

```
condition ? value_if_true : value_if_false;
```
  - **Example**:

```c
int max = (a > b) ? a : b;
```
5. **`switch` Statement**:
  - **Description**: Allows a variable to be tested for equality against a list of values (cases). When a match is found, the corresponding block of code is executed.
  - **Syntax**:

```c
switch (expression) {
    case value1:
        // code to be executed if expression == value1
        break;
    case value2:
        // code to be executed if expression == value2
        break;
    default:
        // code to be executed if no case matches
}
```
  - **Example**:

```c
switch (day) {
    case 1:
        cout << "Monday";
        break;
    case 2:
        cout << "Tuesday";
        break;
    default:
        cout << "Invalid day";
}
```
6. **Nested Decision Statements**:
  - **Description**: Using one `if` or `switch` statement inside another `if`, `else if`, or `switch` statement.
  - **Example**:

```c
if (x > 0) {
    if (y > 0) {
        cout << "x and y are positive";
    } else {
        cout << "x is positive, but y is not";
    }
}
```

### **Looping Statements**

1. **`for` Loop**:
  - **Description**: Repeats a block of code a specific number of times.
  - **Syntax**:

```c
for (initialization; condition; update) {
    // code to be executed
}
```
  - **Example**:

```c
for (int i = 0; i < 5; i++) {
    cout << i << " ";
}
```
2. **`while` Loop**:
  - **Description**: Repeats a block of code as long as the condition is true.
  - **Syntax**:

```c
while (condition) {
    // code to be executed
}
```
  - **Example**:

```c
int i = 0;
while (i < 5) {
    cout << i << " ";
    i++;
}
```
3. **`do-while` Loop**:
  - **Description**: Similar to the `while` loop, but the block of code is executed at least once before the condition is tested.
  - **Syntax**:

```c
do {
    // code to be executed
} while (condition);
```
  - **Example**:

```c
int i = 0;
do {
    cout << i << " ";
    i++;
} while (i < 5);
```
4. **Nested Loops**:
  - **Description**: A loop inside another loop. Each time the outer loop runs, the inner loop runs its entire cycle.
  - **Example**:

```c
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        cout << i << ", " << j << " ";
    }
}
```

### **Controlling Loop Execution**

1. **`break`**:
  - **Description**: Exits the loop or switch statement immediately.
  - **Example**:

```c
for (int i = 0; i < 5; i++) {
    if (i == 3) break;
    cout << i << " ";
}
// Output: 0 1 2
```
2. **`continue`**:
  - **Description**: Skips the current iteration of the loop and proceeds to the next iteration.
  - **Example**:

```c
for (int i = 0; i < 5; i++) {
    if (i == 3) continue;
    cout << i << " ";
}
// Output: 0 1 2 4
```
3. **`goto` Keyword**:
  - **Description**: Transfers control to a labeled statement elsewhere in the program. Generally discouraged as it can make code harder to read and maintain.
  - **Example**:

```c
int i = 0;
start:
cout << i << " ";
i++;
if (i < 5) goto start;
```

### **Multiple-Selection Keywords**

1. **`switch`**:
  - **Description**: Covered earlier under conditional statements. Allows for multiple selections based on a variable's value.
2. **`case`**:
  - **Description**: Represents a specific value in a `switch` statement that, if matched, will execute the associated code block.
  - **Example**:

```c
switch (choice) {
    case 1:
        cout << "Choice is 1";
        break;
    case 2:
        cout << "Choice is 2";
        break;
}
```
3. **`default`**:
  - **Description**: A fallback case in a `switch` statement, executed if no other `case` matches.
  - **Example**:

```c
switch (choice) {
    case 1:
        cout << "Choice is 1";
        break;
    default:
        cout << "Invalid choice";
}
```

### **Possible Questions**

1. **LOTS**:
  - What is the difference between `if` and `if-else` statements?
  - How does a `for` loop differ from a `while` loop?
  - What is the role of the `break` statement in a loop?
2. **HOTS**:
  - Explain how the `switch` statement can be used for handling multiple conditions and compare it with nested `if-else` statements.
  - Describe a scenario where a `goto` statement might be justified despite its potential drawbacks.
  - How can nested loops be optimized to reduce complexity in a given algorithm?
