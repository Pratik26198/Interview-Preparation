# Java Assignment

## 1. Check if a Number is Even or Odd

### **Logic Method**
```java
public static boolean isEven(int num) {
    if (num % 2 == 0) {
        return true;
    } else {
        return false;
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | num % 2 == 0?   |
         +-----------------+
         /       \
       Yes       No
       /          \
+-------------+  +-------------+
| Print Even  |  | Print Odd   |
+-------------+  +-------------+
       \          /
        +----------------+
        |     End        |
        +----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Only a single operation is performed.
- **Space Complexity:** \( O(1) \) – Uses a constant amount of extra space.

---

## 2. Find the Factorial of a Given Number

### **Logic Method**
```java
public static int factorial(int num) {
    int fact = 1;
    for (int i = 1; i <= num; i++) {
        fact *= i;
    }
    return fact;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | fact = 1        |
         +-----------------+
                  |
                  v
         +-----------------+
         | i = 1 to num    |
         +-----------------+
                  |
                  v
         +-----------------+
         | fact *= i       |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print fact      |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n) \) – Iterates through all numbers from 1 to n.
- **Space Complexity:** \( O(1) \) – Uses a single integer variable.

---

## 3. Find the Factorial of a Number Using Recursion

### **Logic Method**
```java
public static int factorialRecursive(int num) {
    if (num == 0 || num == 1) {
        return 1;
    }
    return num * factorialRecursive(num - 1);
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | num == 0 or 1?  |
         +-----------------+
         /       \
       Yes       No
       /          \
+-------------+  +--------------------+
| Return 1    |  | num * factorial(n-1)|
+-------------+  +--------------------+
                           |
                           v
                   +-----------------+
                   | Print result    |
                   +-----------------+
                           |
                           v
                   +-----------------+
                   | End             |
                   +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n) \) – Recursively calls itself until base case.
- **Space Complexity:** \( O(n) \) – Uses stack memory for recursive calls.

---

## 4. Swap Two Numbers Without Using a Third Variable (Approach 1: Using Addition and Subtraction)

### **Logic Method**
```java
public static void swapUsingAddition(int a, int b) {
    a = a + b;
    b = a - b;
    a = a - b;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a + b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | b = a - b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a - b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print a, b      |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Constant operations.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 5. Swap Two Numbers Without Using a Third Variable (Approach 2: Using XOR)

### **Logic Method**
```java
public static void swapUsingXOR(int a, int b) {
    a = a ^ b;
    b = a ^ b;
    a = a ^ b;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a ^ b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | b = a ^ b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a ^ b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print a, b      |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Constant number of operations.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 6. Swap Two Numbers Without Using a Third Variable (Approach 3: Using Multiplication and Division)

### **Logic Method**
```java
public static void swapUsingMultiplication(int a, int b) {
    if (b != 0) { // To prevent division by zero error
        a = a * b;
        b = a / b;
        a = a / b;
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a * b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | b = a / b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a / b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print a, b      |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Constant number of operations.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 7. Check if a Number is Positive or Negative

### **Logic Method**
```java
public static String checkSign(int num) {
    if (num >= 0) {
        return "Positive";
    } else {
        return "Negative";
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | num >= 0?       |
         +-----------------+
         /       \
       Yes       No
       /          \
+-------------+  +-------------+
| Print Pos.  |  | Print Neg.  |
+-------------+  +-------------+
       \          /
        +----------------+
        |     End        |
        +----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Simple conditional check.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 8. Check if a Year is a Leap Year or Not

### **Logic Method**
```java
public static boolean isLeapYear(int year) {
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
        return true;
    } else {
        return false;
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read year       |
         +-----------------+
                  |
                  v
         +-----------------+
         | year % 4 == 0?  |
         +-----------------+
         /       \
       Yes       No
       /          \
+-----------------+  +----------------+
| year % 100 != 0?|  | Print Not Leap |
+-----------------+  +----------------+
       /      \
     Yes      No
     /         \
+-----------------+  +----------------+
| Print Leap Year |  | year % 400 == 0?|
+-----------------+  +----------------+
                     /       \
                   Yes       No
                   /          \
           +-------------+  +-------------+
           | Print Leap  |  | Print Not   |
           | Year        |  | Leap Year   |
           +-------------+  +-------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Constant conditional checks.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 9. Write a Java Program to Print the Digits of a Given Number

### **Logic Method**
```java
public static void printDigits(int num) {
    while (num > 0) {
        int digit = num % 10;
        System.out.println(digit);
        num = num / 10;
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | num > 0 ?       |
         +-----------------+
         /       \
       Yes       No
       /          \
+-----------------+  +----------------+
| digit = num % 10 |  | End            |
+-----------------+  +----------------+
       |
       v
+-----------------+
| Print digit    |
+-----------------+
       |
       v
+-----------------+
| num = num / 10 |
+-----------------+
       |
       v
   (Loop Back)
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(d) \) – where \( d \) is the number of digits.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 10. Write a Java Program to Print All the Factors of a Given Number

### **Logic Method**
```java
public static void printFactors(int num) {
    for (int i = 1; i <= num; i++) {
        if (num % i == 0) {
            System.out.println(i);
        }
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | i = 1 to num    |
         +-----------------+
                  |
                  v
         +-----------------+
         | num % i == 0 ?  |
         +-----------------+
         /       \
       Yes       No
       /          \
+-----------------+  +----------------+
| Print i         |  | Skip            |
+-----------------+  +----------------+
                  |
                  v
         +-----------------+
         | i++ (Loop Back) |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n) \) – Checking all numbers up to \( n \).
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 11. Write a Java Program to Find the Sum of the Digits of a Given Number

### **Logic Method**
```java
public static int sumOfDigits(int num) {
    int sum = 0;
    while (num > 0) {
        int digit = num % 10;
        sum += digit;
        num = num / 10;
    }
    return sum;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | sum = 0         |
         +-----------------+
                  |
                  v
         +-----------------+
         | num > 0 ?       |
         +-----------------+
         /       \
       Yes       No
       /          \
+-----------------+  +----------------+
| digit = num % 10 |  | Print sum      |
+-----------------+  +----------------+
       |
       v
+-----------------+
| sum += digit   |
+-----------------+
       |
       v
+-----------------+
| num = num / 10 |
+-----------------+
       |
       v
   (Loop Back)
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(d) \) – where \( d \) is the number of digits.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 12. Write a Java Program to Find the Smallest of Three Numbers (a, b, c) Without Using < or > Symbol

### **Logic Method**
```java
public static int smallestOfThree(int a, int b, int c) {
    return Math.min(a, Math.min(b, c));
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b, c    |
         +-----------------+
                  |
                  v
         +-----------------+
         | min = Math.min(a, Math.min(b, c)) |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print min       |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(1) \) – Only a few mathematical operations.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 13. How to Add Two Numbers Without Using Arithmetic Operators in Java?

### **Logic Method**
```java
public static int addWithoutArithmetic(int a, int b) {
    while (b != 0) {
        int carry = a & b;
        a = a ^ b;
        b = carry << 1;
    }
    return a;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | while (b != 0)  |
         +-----------------+
                  |
                  v
         +-----------------+
         | carry = a & b   |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = a ^ b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | b = carry << 1  |
         +-----------------+
                  |
                  v
           (Loop Back)
                  |
                  v
         +-----------------+
         | Print a         |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(log(n)) \) – The number of bits in the numbers.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 14. Write a Java Program to Reverse a Given Number

### **Logic Method**
```java
public static int reverseNumber(int num) {
    int reversed = 0;
    while (num > 0) {
        int digit = num % 10;
        reversed = reversed * 10 + digit;
        num = num / 10;
    }
    return reversed;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | reversed = 0    |
         +-----------------+
                  |
                  v
         +-----------------+
         | num > 0 ?       |
         +-----------------+
         /       \
       Yes       No
       /          \
+-----------------+  +----------------+
| digit = num % 10 |  | Print reversed |
+-----------------+  +----------------+
       |
       v
+-----------------+
| reversed = reversed * 10 + digit |
+-----------------+
       |
       v
+-----------------+
| num = num / 10 |
+-----------------+
       |
       v
   (Loop Back)
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(d) \) – where \( d \) is the number of digits.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 15. Write a Java Program to Find GCD of Two Given Numbers

### **Logic Method**
```java
public static int findGCD(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | while (b != 0)  |
         +-----------------+
                  |
                  v
         +-----------------+
         | temp = b        |
         +-----------------+
                  |
                  v
         +-----------------+
         | b = a % b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | a = temp        |
         +-----------------+
                  |
                  v
           (Loop Back)
                  |
                  v
         +-----------------+
         | Print a         |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(log(n)) \) – Euclidean algorithm.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 16. Write a Java Program to Find LCM of Two Given Numbers

### **Logic Method**
```java
public static int findLCM(int a, int b) {
    return (a * b) / findGCD(a, b);
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | Compute GCD     |
         +-----------------+
                  |
                  v
         +-----------------+
         | LCM = (a * b) / GCD |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print LCM       |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(log(n)) \) – Uses GCD computation.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 17. Write a Java Program to Find LCM of Two Given Numbers using Prime Factors Method

### **Logic Method**
```java
public static int findLCMUsingPrimeFactors(int a, int b) {
    int max = Math.max(a, b);
    int lcm = max;
    
    while (true) {
        if (lcm % a == 0 && lcm % b == 0) {
            return lcm;
        }
        lcm += max;
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read a, b       |
         +-----------------+
                  |
                  v
         +-----------------+
         | max = max(a, b) |
         +-----------------+
                  |
                  v
         +-----------------+
         | lcm = max       |
         +-----------------+
                  |
                  v
         | while (true)    |
         +-----------------+
                  |
                  v
         +-----------------+
         | if lcm % a == 0 && lcm % b == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | lcm += max       |
          |  lcm   |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n) \) – Worst case linear search.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 18. Check whether the Given Number is a Palindrome or NOT

### **Logic Method**
```java
public static boolean isPalindrome(int num) {
    int originalNum = num;
    int reversedNum = 0;
    
    while (num > 0) {
        int digit = num % 10;
        reversedNum = reversedNum * 10 + digit;
        num /= 10;
    }
    
    return originalNum == reversedNum;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         +-----------------+
         | originalNum = num |
         +-----------------+
                  |
                  v
         | reversedNum = 0  |
         +-----------------+
                  |
                  v
         | while (num > 0)  |
         +-----------------+
                  |
                  v
         +-----------------+
         | digit = num % 10 |
         +-----------------+
                  |
                  v
         +-----------------+
         | reversedNum = reversedNum * 10 + digit |
         +-----------------+
                  |
                  v
         +-----------------+
         | num /= 10       |
         +-----------------+
                  |
                  v
            (Loop Back)
                  |
                  v
         +-----------------+
         | if originalNum == reversedNum |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +--------+
          | return |  | return |
          |  true  |  | false  |
          +--------+  +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(d) \) – Where d is the number of digits in num.
- **Space Complexity:** \( O(1) \) – No extra space used.

---

## 19. Write a Java Program to Print All the Prime Factors of the Given Number

### **Logic Method**
```java
public static void printPrimeFactors(int num) {
    while (num % 2 == 0) {
        System.out.print(2 + " ");
        num /= 2;
    }
    
    for (int i = 3; i <= Math.sqrt(num); i += 2) {
        while (num % i == 0) {
            System.out.print(i + " ");
            num /= i;
        }
    }
    
    if (num > 2) {
        System.out.print(num);
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         | while num % 2 == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | Print 2 |  | i = 3           |
          | num /=2 |  | While i <= sqrt(num) |
          +--------+  +-----------------+
                  |
                  v
         | while num % i == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | Print i |  | if num > 2      |
          | num /=i |  | Print num       |
          +--------+  +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(\sqrt{n}) \)
- **Space Complexity:** \( O(1) \)

---

## 20. Write a Java Program to Check Whether the Given Number is a Prime Number or NOT

### **Logic Method**
```java
public static boolean isPrime(int num) {
    if (num <= 1) {
        return false;
    }
    if (num <= 3) {
        return true;
    }
    if (num % 2 == 0 || num % 3 == 0) {
        return false;
    }
    for (int i = 5; i * i <= num; i += 6) {
        if (num % i == 0 || num % (i + 2) == 0) {
            return false;
        }
    }
    return true;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         | if num <= 1     |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | if num <= 3      |
          | false  |  +-----------------+
          +--------+        |
                  v
         | return true if num <= 3 |
         +-----------------+
                  |
                  v
         | if num % 2 == 0 || num % 3 == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | for i = 5 to sqrt(num) |
          | false  |  +-----------------+
          +--------+        |
                            v
         | if num % i == 0 or num % (i+2) == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | return true      |
          | false  |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(\sqrt{n}) \)
- **Space Complexity:** \( O(1) \)

---

## 21. Write a Java Program to Print Prime Numbers from 1 to N

### **Logic Method**
```java
public static void printPrimes(int n) {
    for (int num = 2; num <= n; num++) {
        boolean isPrime = true;
        for (int i = 2; i * i <= num; i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
        if (isPrime) {
            System.out.print(num + " ");
        }
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read n          |
         +-----------------+
                  |
                  v
         | for num = 2 to n |
         +-----------------+
                  |
                  v
         | isPrime = true  |
         +-----------------+
                  |
                  v
         | for i = 2 to sqrt(num) |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | isPrime = false; break |
          +--------+  | if isPrime print num |
          +--------+  +-----------------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n \sqrt{n}) \)
- **Space Complexity:** \( O(1) \)

---

## 22. Write a Java Program to Check Whether the Given Number is an Armstrong Number or NOT

### **Logic Method**
```java
public static boolean isArmstrong(int num) {
    int originalNum = num, sum = 0, digits = 0;
    int temp = num;
    
    while (temp > 0) {
        temp /= 10;
        digits++;
    }
    
    temp = num;
    while (temp > 0) {
        int remainder = temp % 10;
        sum += Math.pow(remainder, digits);
        temp /= 10;
    }
    
    return sum == originalNum;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         +-----------------+
         | Read num        |
         +-----------------+
                  |
                  v
         | Count digits    |
         +-----------------+
                  |
                  v
         | sum = 0         |
         +-----------------+
                  |
                  v
         | while temp > 0  |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +------------------+  +-----------------+
          | remainder = temp % 10 |
          | sum += remainder^digits |
          | temp /= 10 |
          +------------------+  +-----------------+
                  |
                  v
         | if sum == num    |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | return false    |
          | true   |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(d) \) where \( d \) is the number of digits.
- **Space Complexity:** \( O(1) \)

---

## 23. Write a Java Program to Print Armstrong Numbers Between 1 to 1000

### **Logic Method**
```java
public static void printArmstrongNumbers(int limit) {
    for (int num = 1; num <= limit; num++) {
        int sum = 0, temp = num, digits = 0;
        int originalNum = num;
        
        while (temp > 0) {
            temp /= 10;
            digits++;
        }
        
        temp = num;
        while (temp > 0) {
            int remainder = temp % 10;
            sum += Math.pow(remainder, digits);
            temp /= 10;
        }
        
        if (sum == originalNum) {
            System.out.print(num + " ");
        }
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         | for num = 1 to limit |
         +-----------------+
                  |
                  v
         | Count digits    |
         +-----------------+
                  |
                  v
         | sum = 0         |
         +-----------------+
                  |
                  v
         | while temp > 0  |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +------------------+  +-----------------+
          | remainder = temp % 10 |
          | sum += remainder^digits |
          | temp /= 10 |
          +------------------+  +-----------------+
                  |
                  v
         | if sum == num    |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | print  |  | Continue Loop   |
          | num    |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n \cdot d) \) where \( d \) is the number of digits in \( n \).
- **Space Complexity:** \( O(1) \)

---

## 24. Write a Java Program to Check Whether the Given Number is a Perfect Number or NOT

### **Logic Method**
```java
public static boolean isPerfectNumber(int num) {
    int sum = 0;
    for (int i = 1; i <= num / 2; i++) {
        if (num % i == 0) {
            sum += i;
        }
    }
    return sum == num;
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         | Read num        |
         +-----------------+
                  |
                  v
         | sum = 0         |
         +-----------------+
                  |
                  v
         | for i = 1 to num/2 |
         +-----------------+
                  |
                  v
         | if num % i == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +-----------------+
          | sum += i        |
          +-----------------+
                  |
                  v
         | if sum == num    |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | return |  | return false    |
          | true   |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n) \)
- **Space Complexity:** \( O(1) \)

---

## 25. Write a Java Program to Print Perfect Numbers Between 1 to 1000

### **Logic Method**
```java
public static void printPerfectNumbers(int limit) {
    for (int num = 1; num <= limit; num++) {
        int sum = 0;
        for (int i = 1; i <= num / 2; i++) {
            if (num % i == 0) {
                sum += i;
            }
        }
        if (sum == num) {
            System.out.print(num + " ");
        }
    }
}
```

### **Flowchart**
```
         +-----------------+
         | Start           |
         +-----------------+
                  |
                  v
         | for num = 1 to limit |
         +-----------------+
                  |
                  v
         | sum = 0         |
         +-----------------+
                  |
                  v
         | for i = 1 to num/2 |
         +-----------------+
                  |
                  v
         | if num % i == 0 |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +-----------------+
          | sum += i        |
          +-----------------+
                  |
                  v
         | if sum == num    |
         +-----------------+
                  |
            Yes /    \ No
                |      |
                v      v
          +--------+  +-----------------+
          | print  |  | Continue Loop   |
          | num    |  +-----------------+
          +--------+
```

### **Time and Space Complexity**
- **Time Complexity:** \( O(n^2) \)
- **Space Complexity:** \( O(1) \)

---




















