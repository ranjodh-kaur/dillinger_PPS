
# Unit 4. Control Structures

***

### **Conditional Statements**

1. **`if` Statement**:
  - **Description**: Evaluates a condition. If the condition is true, the block of code within the `if` statement is executed.
  - **Syntax**:

```
<span class="hljs-keyword">if</span> (condition) {
    <span class="hljs-comment">// code to be executed if condition is true</span>
}
```
  - **Example**:

```
<span class="hljs-keyword">if</span> (x > <span class="hljs-number">0</span>) {
    <span class="hljs-built_in">cout</span> << <span class="hljs-string">"x is positive"</span>;
}
```
2. **`if-else` Statement**:
  - **Description**: Provides an alternative block of code if the condition is false.
  - **Syntax**:

```
<span class="hljs-keyword">if</span> (condition) {
    <span class="hljs-comment">// code to be executed if condition is true</span>
} <span class="hljs-keyword">else</span> {
    <span class="hljs-comment">// code to be executed if condition is false</span>
}
```
  - **Example**:

```
<span class="hljs-keyword">if</span> (x > <span class="hljs-number">0</span>) {
    <span class="hljs-built_in">cout</span> << <span class="hljs-string">"x is positive"</span>;
} <span class="hljs-keyword">else</span> {
    <span class="hljs-built_in">cout</span> << <span class="hljs-string">"x is non-positive"</span>;
}
```
3. **The `if-else if` Statement**
  - **Description**: The `if-else if` statement is used to test multiple conditions sequentially. The code block associated with the first condition that evaluates to true is executed, and the rest of the conditions are ignored. If none of the conditions are true, the `else` block (if present) is executed.
  - **Syntax of `if-else if` Statement**

```
  <span class="hljs-keyword">if</span> (condition1) {
  <span class="hljs-comment">// Code to execute if condition1 is true</span>
  } <span class="hljs-keyword">else</span> <span class="hljs-keyword">if</span> (condition2) {
  <span class="hljs-comment">// Code to execute if condition2 is true</span>
  } <span class="hljs-keyword">else</span> <span class="hljs-keyword">if</span> (condition3) {
  <span class="hljs-comment">// Code to execute if condition3 is true</span>
  } <span class="hljs-keyword">else</span> {
  <span class="hljs-comment">// Code to execute if none of the above conditions are true</span>
  }
```
  - **Example of `if-else if` Statement** : Let's consider an example to determine a student's grade based on their score:

```
<span class="hljs-preprocessor">#<span class="hljs-keyword">include</span> <span class="hljs-string"><iostream></span></span>
<span class="hljs-keyword">using</span> <span class="hljs-keyword">namespace</span> <span class="hljs-built_in">std</span>;
<span class="hljs-function"><span class="hljs-keyword">int</span> <span class="hljs-title">main</span><span class="hljs-params">()</span> </span>{
<span class="hljs-keyword">int</span> score;
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Enter the student's score: "</span>;
<span class="hljs-built_in">cin</span> >> score;

 <span class="hljs-keyword">if</span> (score >= <span class="hljs-number">90</span>) {
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Grade: A"</span> << endl;
 }
 <span class="hljs-keyword">else</span> <span class="hljs-keyword">if</span> (score >= <span class="hljs-number">80</span>) {
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Grade: B"</span> << endl;
}
<span class="hljs-keyword">else</span> <span class="hljs-keyword">if</span> (score >= <span class="hljs-number">70</span>) {
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Grade: C"</span> << endl;
}
<span class="hljs-keyword">else</span> <span class="hljs-keyword">if</span> (score >= <span class="hljs-number">60</span>) {
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Grade: D"</span> << endl;
}
<span class="hljs-keyword">else</span> {
<span class="hljs-built_in">cout</span> << <span class="hljs-string">"Grade: F"</span> << endl;
}
<span class="hljs-keyword">return</span> <span class="hljs-number">0</span>;
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

```
<span class="hljs-keyword">int</span> max = (a > b) ? a : b;
```
5. **`switch` Statement**:
  - **Description**: Allows a variable to be tested for equality against a list of values (cases). When a match is found, the corresponding block of code is executed.
  - **Syntax**:

```
<span class="hljs-keyword">switch</span> (expression) {
    <span class="hljs-keyword">case</span> value1:
        <span class="hljs-comment">// code to be executed if expression == value1</span>
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">case</span> value2:
        <span class="hljs-comment">// code to be executed if expression == value2</span>
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">default</span>:
        <span class="hljs-comment">// code to be executed if no case matches</span>
}
```
  - **Example**:

```
<span class="hljs-keyword">switch</span> (day) {
    <span class="hljs-keyword">case</span> <span class="hljs-number">1</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Monday"</span>;
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">case</span> <span class="hljs-number">2</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Tuesday"</span>;
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">default</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Invalid day"</span>;
}
```
6. **Nested Decision Statements**:
  - **Description**: Using one `if` or `switch` statement inside another `if`, `else if`, or `switch` statement.
  - **Example**:

```
<span class="hljs-keyword">if</span> (x > <span class="hljs-number">0</span>) {
    <span class="hljs-keyword">if</span> (y > <span class="hljs-number">0</span>) {
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"x and y are positive"</span>;
    } <span class="hljs-keyword">else</span> {
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"x is positive, but y is not"</span>;
    }
}
```

### **Looping Statements**

1. **`for` Loop**:
  - **Description**: Repeats a block of code a specific number of times.
  - **Syntax**:

```
<span class="hljs-keyword">for</span> (initialization; condition; update) {
    <span class="hljs-comment">// code to be executed</span>
}
```
  - **Example**:

```
<span class="hljs-keyword">for</span> (<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>; i < <span class="hljs-number">5</span>; i++) {
    <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
}
```
2. **`while` Loop**:
  - **Description**: Repeats a block of code as long as the condition is true.
  - **Syntax**:

```
<span class="hljs-keyword">while</span> (condition) {
    <span class="hljs-comment">// code to be executed</span>
}
```
  - **Example**:

```
<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>;
<span class="hljs-keyword">while</span> (i < <span class="hljs-number">5</span>) {
    <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
    i++;
}
```
3. **`do-while` Loop**:
  - **Description**: Similar to the `while` loop, but the block of code is executed at least once before the condition is tested.
  - **Syntax**:

```
<span class="hljs-keyword">do</span> {
    <span class="hljs-comment">// code to be executed</span>
} <span class="hljs-keyword">while</span> (condition);
```
  - **Example**:

```
<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>;
<span class="hljs-keyword">do</span> {
    <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
    i++;
} <span class="hljs-keyword">while</span> (i < <span class="hljs-number">5</span>);
```
4. **Nested Loops**:
  - **Description**: A loop inside another loop. Each time the outer loop runs, the inner loop runs its entire cycle.
  - **Example**:

```
<span class="hljs-keyword">for</span> (<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>; i < <span class="hljs-number">3</span>; i++) {
    <span class="hljs-keyword">for</span> (<span class="hljs-keyword">int</span> j = <span class="hljs-number">0</span>; j < <span class="hljs-number">3</span>; j++) {
        <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">", "</span> << j << <span class="hljs-string">" "</span>;
    }
}
```

### **Controlling Loop Execution**

1. **`break`**:
  - **Description**: Exits the loop or switch statement immediately.
  - **Example**:

```
<span class="hljs-keyword">for</span> (<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>; i < <span class="hljs-number">5</span>; i++) {
    <span class="hljs-keyword">if</span> (i == <span class="hljs-number">3</span>) <span class="hljs-keyword">break</span>;
    <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
}
<span class="hljs-comment">// Output: 0 1 2</span>
```
2. **`continue`**:
  - **Description**: Skips the current iteration of the loop and proceeds to the next iteration.
  - **Example**:

```
<span class="hljs-keyword">for</span> (<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>; i < <span class="hljs-number">5</span>; i++) {
    <span class="hljs-keyword">if</span> (i == <span class="hljs-number">3</span>) <span class="hljs-keyword">continue</span>;
    <span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
}
<span class="hljs-comment">// Output: 0 1 2 4</span>
```
3. **`goto` Keyword**:
  - **Description**: Transfers control to a labeled statement elsewhere in the program. Generally discouraged as it can make code harder to read and maintain.
  - **Example**:

```
<span class="hljs-keyword">int</span> i = <span class="hljs-number">0</span>;
start:
<span class="hljs-built_in">cout</span> << i << <span class="hljs-string">" "</span>;
i++;
<span class="hljs-keyword">if</span> (i < <span class="hljs-number">5</span>) <span class="hljs-keyword">goto</span> start;
```

### **Multiple-Selection Keywords**

1. **`switch`**:
  - **Description**: Covered earlier under conditional statements. Allows for multiple selections based on a variable's value.
2. **`case`**:
  - **Description**: Represents a specific value in a `switch` statement that, if matched, will execute the associated code block.
  - **Example**:

```
<span class="hljs-keyword">switch</span> (choice) {
    <span class="hljs-keyword">case</span> <span class="hljs-number">1</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Choice is 1"</span>;
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">case</span> <span class="hljs-number">2</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Choice is 2"</span>;
        <span class="hljs-keyword">break</span>;
}
```
3. **`default`**:
  - **Description**: A fallback case in a `switch` statement, executed if no other `case` matches.
  - **Example**:

```
<span class="hljs-keyword">switch</span> (choice) {
    <span class="hljs-keyword">case</span> <span class="hljs-number">1</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Choice is 1"</span>;
        <span class="hljs-keyword">break</span>;
    <span class="hljs-keyword">default</span>:
        <span class="hljs-built_in">cout</span> << <span class="hljs-string">"Invalid choice"</span>;
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
