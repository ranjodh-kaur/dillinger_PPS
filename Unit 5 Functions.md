
# Unit-5 Functions

| TOPICS | DETAILS |
| --- | --- |
| Functions: | Need of functions, Components of Functions, Built-in and User Defined |
| Functions, Parameter passing in function: | Call by value, Call by reference, Scope rules, Default Arguments, Function Overloading |
| Recursion: | Base case and recursive case, Recursion versus Iteration. |

# Functions:

***

### **1. Need for Functions**

* **Analogy**: Imagine a restaurant where the chef does _every_ task individually for every order (chopping, cooking, plating). It would be slow and inefficient.
* **Explanation**: Without functions, you would need to repeat the same code over and over. Functions help you avoid repetition by organizing tasks into reusable pieces of code, like how a kitchen might divide tasks into specialized stations (chopping, cooking, etc.).

**Why we need functions:**

* **Code reuse:** Write once, use many times.
* **Code organization:** Makes programs easier to read and manage.
* **Reduces errors:** Fix issues in one place (inside the function) rather than multiple locations.
* **Modularity:** Breaks down big problems into smaller chunks.

***

### **2. Components of Functions**

* **Analogy**: Each kitchen station (like the grill station or dessert station) has its setup (ingredients and tools) and produces a specific dish.
* **Explanation**: A function has the following components:
  1. **Return type**: What the station (function) outputs (like "void" means no return, or "int" means it returns a number).
  2. **Function name**: The name of the dish or task (like `makePizza` or `fryEggs`).
  3. **Parameters**: Ingredients needed (e.g., `flour`, `eggs`).
  4. **Body**: The cooking process (what happens in the function).
  5. **Return statement**: The final product returned (the dish ready to serve).

- **Function Declaration (Prototype):** 
A blueprint or signature of the function that tells the compiler its name, return type, and parameters.
    ```c
     int add(int a, int b); 
     // This tells the compiler there’s a function called `add` that takes two `int` parameters and returns an `int`.
    ```

- **Function Definition:** The actual body of the function where we write what the function does.

    ```c
        int add(int a, int b) {
            return a + b;  // Function that adds two numbers
        }
    ```

- **Function Call:** The place where we invoke (run) the function.
    ```c
    int sum = add(5, 10);  // Calling the function and using its result
    ```

- **Example**
    ```c
    #include<iostream>
    int add(int a, int b);  //Function Declaration (Prototype)
    int main()
    {
      int sum = add(5, 10); //Function Call
    }
    int add(int a, int b) {    //Function Definition
        return a + b;  // Function that adds two numbers
    }
    ```

***

### **3. Built-in and User-Defined Functions**

* **Analogy**: The kitchen has both _standard dishes_ (like pasta or salad) and _customized dishes_ that customers request.
* **Explanation**:
  - **Built-in functions** are like standard menu items (predefined tasks in C++, such as `sqrt()` for square root or `cout` for printing).
  - **User-defined functions** are custom dishes where the chef (programmer) creates their own recipe (code) for a new task. Functions that you create yourself to perform specific tasks, like calculating the sum of two numbers.

***

### **4. Parameter Passing in Functions**

#### **a. Call by Value**

* **Analogy**: It's like giving a copy of the recipe card to a chef. The chef works on the copy, so the original card isn't changed.
  - Think of lending a photocopy of a document. If someone scribbles on the photocopy, your original stays unchanged.
* **Explanation**: In _call by value_, the function receives a copy of the argument, and any changes inside the function don't affect the original value.
- **Example:** 
    ```c
    #include<iostream>
    using namespace std;
    void addFive(int x);
    int main()
    {
    addFive(5);
    return 0;
    }
    void addFive(int x) {
    x = x + 5;
    }
    ```

#### **b. Call by Reference**

* **Analogy**: It's like telling the chef to use the _actual ingredients_ from the storage, not a copy. Changes affect the main storage directly.
* **Explanation**: In _call by reference_, the function works with the original argument itself, so any changes made inside the function will affect the original value.
- **Example:** 
    ```c
    #include<iostream>
    using namespace std;
    void change(int &x) {
    x = 5;
    }
    int main()
    {   int a=30;
    change(a);
    cout<<a;
    return 0;
    }
    ```

***

### **5. Scope Rules**

* **Analogy**: Different kitchen stations have their own set of ingredients, and some ingredients are shared across stations.
* **Explanation**: In C++, variables have a scope. **Local variables** exist only inside the function (like ingredients available only at a specific station), while **global variables** exist outside the function and are accessible throughout the program (like ingredients available to every station).

***

### **6. Default Arguments**

* **Analogy**: If a customer doesn't specify something (like the amount of sugar in a dish), the chef uses a _default_ amount.
* **Explanation**: In C++, you can set _default arguments_ for functions. If the user doesn't provide a value for that parameter, the function uses the default value.
- **Example:** 
    ```c
    #include<iostream>
    using namespace std;
    int add(int a, int b = 10) {
    return a + b;
    }
    int main() {
    cout << add(5);  // Outputs 15 because `b` uses its default value of 10.
    cout << add(5, 20);  // Outputs 25 because we provided both values.
    }
    ```

Functions can have default values for parameters. If the caller does not provide a value, the default is used.

***

### **7. Function Overloading**

* **Analogy**: You can have different variations of the same dish on the menu (like a small, medium, or large pizza), but the kitchen knows which version to prepare based on the order.
* **Explanation**: In C++, you can have multiple functions with the same name but different parameter types or numbers. The compiler decides which function to call based on the arguments passed.

**Example**
> int myFunction ( int x );
float myFunction ( float x );
double myFunction ( double x , double y );

- **Example:** You can have multiple add() functions that can add integers, floats, or strings.

    ```c
    #include<iostream>
    using namespace std;
    int add(int a, int b)
    { 
    return a + b; 
    }
    int add(double a, double b) 
    { 
    return a + b; 
    }
    int main()
    {
    cout<<  add(5.4,5.4);
    cout<< add(6,5);
    return 0;
    }
    ```

***

### **8. Recursion: Base Case and Recursive Case**

#### **a. Base Case**

* **Analogy**:
  - Imagine a chef who repeats a task (like chopping vegetables) until there are none left. The _base case_ is when the chef stops chopping because there are no more vegetables.
  - Imagine standing in front of two mirrors. You see endless reflections of yourself, but each one gets smaller. Recursion works similarly by breaking down a problem into smaller versions of itself.
* **Explanation**: In recursion, the _base case_ is the condition where the function stops calling itself, preventing infinite loops.
* **Example:** A recursive function to calculate the factorial of a number.
    ```c
    int factorial(int n) {
    if (n == 0) return 1;  // Base case
    return n * factorial(n - 1);  // Recursive case
    }
    ```

#### **b. Recursive Case**

* **Analogy**: The chef keeps chopping as long as there are vegetables. Each time the chef chops, the remaining amount decreases.
* **Explanation**: In recursion, the _recursive case_ is the step where the function calls itself again with a modified argument, working towards the base case. The part where the function calls itself with a smaller input.

***

### **9. Recursion versus Iteration**

* **Analogy**: _Recursion_ is like a chef who chops one vegetable at a time and then checks if more are left (calling themselves repeatedly).  **Iteration** is like a chef who uses a food processor to chop all vegetables in one go.
* **Explanation**: Recursion solves problems by breaking them down into smaller instances of the same problem, while **iteration** (using loops) solves problems by repeating a block of code.
* **Recursion:** A function that calls itself to solve smaller instances of a problem.
  - Example: Factorial using recursion.
* **Iteration:** Using loops (like for or while) to repeatedly execute a block of code.
  - Example: Factorial using a loop.

**Comparison:**
- **Recursion** is more elegant and sometimes simpler for problems that can be divided into smaller sub-problems (like tree traversal or factorial).
- **Iteration** is generally faster and uses less memory, as recursion can lead to stack overflow if too deep.

Here's a comparison of **Recursion vs Iteration** in a tabular format:

| **Aspect** | **Recursion** | **Iteration** |
| --- | --- | --- |
| **Definition** | A function calls itself to solve a problem. | Repeatedly executes a block of code using loops (e.g., `for`, `while`). |
| **Basic Idea** | Breaks a problem into smaller sub-problems. | Repeats the same steps until a condition is met. |
| **Base Case** | Requires a base case to stop recursion, or it leads to infinite recursion. | Stops when the loop condition fails. |
| **Memory Usage** | Uses more memory due to the function call stack. Each recursive call adds a new layer to the stack. | Uses less memory, as it doesn't involve a call stack (just maintains loop variables). |
| **Performance** | Can be slower due to overhead of function calls. | Typically faster as it avoids the overhead of multiple function calls. |
| **Ease of Understanding** | More intuitive for problems that have a recursive nature (e.g., tree traversal, factorial). | Easier to understand and use for problems that involve repetitive processes (e.g., summing numbers, iterating over arrays). |
| **Termination** | Terminated by reaching the base case. | Terminated by satisfying the loop condition (e.g., `i < n`). |
| **Use Cases** | Best suited for problems that can be divided into sub-problems, like tree traversal, factorial, Fibonacci series, etc. | Best suited for tasks where the same operation is performed repeatedly, like iterating over a range or list. |
| **Function Call Overhead** | High – multiple recursive function calls can add overhead. | Low – loop constructs execute sequentially without overhead from function calls. |
| **Complexity** | Can be simpler and more elegant for problems with recursive structure. | More complex for recursive-like problems but straightforward for repetitive tasks. |
| **Stack Overflow Risk** | Risk of stack overflow if recursion depth is too high (e.g., very large inputs). | No risk of stack overflow, as it doesn't rely on a call stack. |
| **Code Style** | May result in shorter, cleaner code for certain problems. | May result in longer code for problems that would otherwise be recursively handled. |

### Example:

* **Recursion** (Factorial):
    ```c
    int factorial(int n) {
    if (n == 0) return 1;  // Base case
    return n * factorial(n - 1);  // Recursive call
    }
    ```
* **Iteration** (Factorial):

    ```c
    int factorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
    }
    ```

Both approaches solve the same problem but differ in how they approach it.
