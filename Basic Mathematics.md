# Java Programming Assignment

## 1. Check if the Given Number is EVEN or ODD

### **Program Code**
```java
import java.util.Scanner;

public class EvenOddCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        
        if ((num & 1) == 0) {
            System.out.println(num + " is Even.");
        } else {
            System.out.println(num + " is Odd.");
        }
        
        sc.close();
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
         | num & 1 == 0?   |
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

### **Logic Explanation**
- The bitwise AND (`&`) operation with `1` checks if the least significant bit is `0` (even) or `1` (odd).
- This method is more efficient than using modulus (`%`), as bitwise operations are faster.

### **Time and Space Complexity**
- **Time Complexity:** `O(1)` (Constant time operation)
- **Space Complexity:** `O(1)` (Uses a single integer variable)

---

## 2. Find the Factorial of a Given Number

### **Program Code**
```java
import java.util.Scanner;

public class Factorial {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        long fact = 1;

        for (int i = 1; i <= num; i++) {
            fact *= i;
        }

        System.out.println("Factorial of " + num + " is " + fact);
        sc.close();
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
         | Initialize fact=1|
         +-----------------+
                  |
                  v
         +-----------------+
         | Loop from 1 to n |
         | fact *= i        |
         +-----------------+
                  |
                  v
         +-----------------+
         | Print factorial |
         +-----------------+
                  |
                  v
         +-----------------+
         | End             |
         +-----------------+
```

### **Logic Explanation**
- We initialize `fact = 1` and multiply it successively by numbers from `1` to `n`.
- This iterative approach ensures we get the correct factorial.

### **Time and Space Complexity**
- **Time Complexity:** `O(n)` (Iterates `n` times)
- **Space Complexity:** `O(1)` (Uses a constant number of variables)

---

## 3. Find the Factorial of a Number using Recursion

### **Program Code**
```java
import java.util.Scanner;

public class FactorialRecursion {
    static long factorial(int n) {
        if (n == 0 || n == 1)
            return 1;
        return n * factorial(n - 1);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        System.out.println("Factorial of " + num + " is " + factorial(num));
        sc.close();
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
         | Call factorial()|
         +-----------------+
                  |
                  v
         +-----------------+
         | if n <= 1       |
         | return 1        |
         +-----------------+
                  |
                  v
         +-----------------+
         | return n * f(n-1) |
         +-----------------+
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

### **Logic Explanation**
- We use recursion where `factorial(n) = n * factorial(n-1)`, with the base case `factorial(0) = 1`.
- Recursion continues until it reaches the base case.

### **Time and Space Complexity**
- **Time Complexity:** `O(n)` (Recursively calls `n` times)
- **Space Complexity:** `O(n)` (Stack memory used for recursive calls)

---



