1. Write a program to input a positive integer and calculate its factorial using a loop.
2. Write a program to input a positive integer and count the number of digits using a loop.
3. Write a program to input a positive integer and calculate the sum of its digits using a loop.
4. Write a program to input a positive integer and check if it is a prime number using a loop.
5. Write a program to input a positive integer and print all its divisors using a loop.
6. Write a program to print the first N terms of the Fibonacci sequence using a loop.
7. Write a program to input two positive integers and calculate their GCD (Greatest Common Divisor) using a loop.
8. Write a program to input two positive integers and calculate their LCM (Least Common Multiple) using a loop.
9. Write a program to input a positive integer N and calculate the sum of even and odd numbers from 1 to N using a loop.
10. Write a program to check if a given number is an Armstrong number using a loop.
 _________________
 Here are the C++ programs for each of the specified tasks:

---

### 1. Calculate the Factorial of a Number
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    long long factorial = 1;
    cout << "Enter a positive integer: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        factorial *= i;
    }

    cout << "Factorial of " << n << " is " << factorial << endl;
    return 0;
}
```

---

### 2. Count the Number of Digits
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, count = 0;
    cout << "Enter a positive integer: ";
    cin >> n;

    while (n > 0) {
        n /= 10;
        ++count;
    }

    cout << "Number of digits: " << count << endl;
    return 0;
}
```

---

### 3. Calculate the Sum of Digits
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;
    cout << "Enter a positive integer: ";
    cin >> n;

    while (n > 0) {
        sum += n % 10;
        n /= 10;
    }

    cout << "Sum of digits: " << sum << endl;
    return 0;
}
```

---

### 4. Check if a Number is Prime
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    bool isPrime = true;
    cout << "Enter a positive integer: ";
    cin >> n;

    if (n <= 1) isPrime = false;
    for (int i = 2; i * i <= n; ++i) {
        if (n % i == 0) {
            isPrime = false;
            break;
        }
    }

    cout << (isPrime ? "Prime" : "Not Prime") << endl;
    return 0;
}
```

---

### 5. Print All Divisors of a Number
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter a positive integer: ";
    cin >> n;

    cout << "Divisors of " << n << ": ";
    for (int i = 1; i <= n; ++i) {
        if (n % i == 0) {
            cout << i << " ";
        }
    }
    cout << endl;
    return 0;
}
```

---

### 6. Print First N Fibonacci Terms
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the number of terms: ";
    cin >> n;

    int a = 0, b = 1;
    cout << "Fibonacci Sequence: " << a << " " << b << " ";

    for (int i = 3; i <= n; ++i) {
        int next = a + b;
        cout << next << " ";
        a = b;
        b = next;
    }
    cout << endl;
    return 0;
}
```

---

### 7. Calculate GCD (Greatest Common Divisor)
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cout << "Enter two positive integers: ";
    cin >> a >> b;

    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }

    cout << "GCD: " << a << endl;
    return 0;
}
```

---

### 8. Calculate LCM (Least Common Multiple)
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b, gcd, lcm;
    cout << "Enter two positive integers: ";
    cin >> a >> b;

    int x = a, y = b;

    while (y != 0) {
        int temp = y;
        y = x % temp;
        x = temp;
    }
    gcd = x;
    lcm = (a * b) / gcd;

    cout << "LCM: " << lcm << endl;
    return 0;
}
```

---

### 9. Calculate Sum of Even and Odd Numbers up to N
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sumEven = 0, sumOdd = 0;
    cout << "Enter a positive integer: ";
    cin >> n;

    for (int i = 1; i <= n; ++i) {
        if (i % 2 == 0) sumEven += i;
        else sumOdd += i;
    }

    cout << "Sum of even numbers: " << sumEven << endl;
    cout << "Sum of odd numbers: " << sumOdd << endl;
    return 0;
}
```

---

### 10. Check if a Number is an Armstrong Number
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    int n, original, sum = 0;
    cout << "Enter a positive integer: ";
    cin >> n;
    original = n;

    int digits = 0;
    int temp = n;
    while (temp > 0) {
        digits++;
        temp /= 10;
    }

    while (n > 0) {
        int digit = n % 10;
        sum += pow(digit, digits);
        n /= 10;
    }

    cout << (sum == original ? "Armstrong" : "Not Armstrong") << endl;
    return 0;
}
```

---

