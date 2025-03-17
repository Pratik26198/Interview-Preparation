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


