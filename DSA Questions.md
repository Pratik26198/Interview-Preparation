## 1. Find Missing Number in an Array

### Program Code:
```java
public static int findMissingNumber(int[] arr, int n) {
    int totalSum = (n * (n + 1)) / 2;
    int arraySum = 0;
    for (int num : arr) {
        arraySum += num;
    }
    return totalSum - arraySum;
}
```

### Flowchart:
```
    Start
      |
      V
    Compute total sum using formula
      |
      V
    Compute array sum by iterating over elements
      |
      V
    Return totalSum - arraySum
      |
      V
    End
```

### Logic:
The sum of first `n` natural numbers is calculated using the formula `n*(n+1)/2`. The sum of the given array elements is then subtracted from this total sum to get the missing number.

### Time Complexity:
- **O(n)** (single pass to compute sum)

### Space Complexity:
- **O(1)** (only integer variables used)

---

## 2. Search an Element in a Sorted and Rotated Array

### Program Code:
```java
public static int searchElement(int[] arr, int low, int high, int key) {
    while (low <= high) {
        int mid = (low + high) / 2;

        if (arr[mid] == key) {
            return mid;
        }

        if (arr[low] <= arr[mid]) { // Left half is sorted
            if (key >= arr[low] && key < arr[mid]) {
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        } else { // Right half is sorted
            if (key > arr[mid] && key <= arr[high]) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
    }
    return -1;
}
```

### Flowchart:
```
    Start
      |
      V
    Set low = 0, high = n-1
      |
      V
    While low <= high:
      |
      V
    Find mid = (low + high) / 2
      |
      V
    If arr[mid] == key, return mid
      |
      V
    If left half sorted, search in left else search in right
      |
      V
    Repeat until found or return -1
      |
      V
    End
```

### Logic:
Since the array is rotated, we use binary search by checking which half is sorted and then determine whether the key lies in the sorted or unsorted half.

### Time Complexity:
- **O(log n)** (Binary search approach)

### Space Complexity:
- **O(1)** (No extra space used)

---

## 3. Find Second Largest Number in Array

### Program Code:
```java
public static int findSecondLargest(int[] arr) {
    int first = Integer.MIN_VALUE, second = Integer.MIN_VALUE;
    for (int num : arr) {
        if (num > first) {
            second = first;
            first = num;
        } else if (num > second && num != first) {
            second = num;
        }
    }
    return second;
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize first & second as MIN_VALUE
      |
      V
    Iterate through array
      |
      V
    If element > first, update first & second
      |
      V
    If element > second and not equal to first, update second
      |
      V
    Return second
      |
      V
    End
```

### Logic:
We traverse the array while keeping track of the largest and second largest numbers encountered so far.

### Time Complexity:
- **O(n)** (Single traversal)

### Space Complexity:
- **O(1)** (Only variables used)

---

## 4. Find Number Occurring Odd Number of Times in Array

### Program Code:
```java
public static int findOddOccurrence(int[] arr) {
    int result = 0;
    for (int num : arr) {
        result ^= num;
    }
    return result;
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize result = 0
      |
      V
    Traverse array and XOR each element with result
      |
      V
    Return result
      |
      V
    End
```

### Logic:
Using XOR operation, all even occurrences cancel out, leaving the only element occurring odd times.

### Time Complexity:
- **O(n)** (Single traversal)

### Space Complexity:
- **O(1)** (No extra space used)

---

## 5. Minimum Number of Platforms Required for Railway Station

### Program Code:
```java
import java.util.Arrays;

public static int findPlatforms(int[] arrival, int[] departure, int n) {
    Arrays.sort(arrival);
    Arrays.sort(departure);
    
    int platforms = 1, maxPlatforms = 1;
    int i = 1, j = 0;
    
    while (i < n && j < n) {
        if (arrival[i] <= departure[j]) {
            platforms++;
            i++;
        } else {
            platforms--;
            j++;
        }
        maxPlatforms = Math.max(maxPlatforms, platforms);
    }
    return maxPlatforms;
}
```

### Flowchart:
```
    Start
      |
      V
    Sort arrival and departure times
      |
      V
    Initialize platform count
      |
      V
    Traverse arrival and departure arrays
      |
      V
    Increment or decrement platform count
      |
      V
    Keep track of max platforms required
      |
      V
    Return maxPlatforms
      |
      V
    End
```

### Logic:
We sort arrival and departure times and use a two-pointer technique to find the maximum number of platforms required at any time.

### Time Complexity:
- **O(n log n)** (Sorting dominates)

### Space Complexity:
- **O(1)** (Only variables used)

---

## 6. Find Pair Whose Sum is Closest to Zero

### Program Code:
```java
import java.util.Arrays;

public static void closestSumToZero(int[] arr) {
    Arrays.sort(arr);
    int left = 0, right = arr.length - 1;
    int minSum = Integer.MAX_VALUE;
    int num1 = 0, num2 = 0;

    while (left < right) {
        int sum = arr[left] + arr[right];
        if (Math.abs(sum) < Math.abs(minSum)) {
            minSum = sum;
            num1 = arr[left];
            num2 = arr[right];
        }
        if (sum < 0) left++;
        else right--;
    }
    System.out.println("Pair: " + num1 + " " + num2);
}
```

### Flowchart:
```
    Start
      |
      V
    Sort array
      |
      V
    Initialize left and right pointers
      |
      V
    Iterate while left < right
      |
      V
    Check sum and update minSum if necessary
      |
      V
    Adjust pointers based on sum
      |
      V
    Print closest pair
      |
      V
    End
```

### Logic:
Sorting helps use two pointers to find the closest sum efficiently by moving towards zero.

### Time Complexity:
- **O(n log n)** (Sorting)

### Space Complexity:
- **O(1)** (No extra space)

---

## 7. Find Pair Whose Sum is Closest to X

### Program Code:
```java
import java.util.Arrays;

public static void closestSumToX(int[] arr, int X) {
    Arrays.sort(arr);
    int left = 0, right = arr.length - 1;
    int minDiff = Integer.MAX_VALUE;
    int num1 = 0, num2 = 0;

    while (left < right) {
        int sum = arr[left] + arr[right];
        int diff = Math.abs(X - sum);
        
        if (diff < minDiff) {
            minDiff = diff;
            num1 = arr[left];
            num2 = arr[right];
        }
        
        if (sum < X) left++;
        else right--;
    }
    System.out.println("Pair: " + num1 + " " + num2);
}
```

### Flowchart:
```
    Start
      |
      V
    Sort array
      |
      V
    Initialize left and right pointers
      |
      V
    Iterate while left < right
      |
      V
    Check sum difference with X
      |
      V
    Update minDiff if necessary
      |
      V
    Adjust pointers based on sum
      |
      V
    Print closest pair
      |
      V
    End
```

### Logic:
Sorting helps use two pointers to efficiently find the closest sum to X by moving towards the target value.

### Time Complexity:
- **O(n log n)** (Sorting dominates)

### Space Complexity:
- **O(1)** (No extra space used)

---

## 8. Find All Pairs of Elements Whose Sum is Equal to a Given Number

### Program Code:
```java
import java.util.HashSet;

public static void findPairsWithSum(int[] arr, int target) {
    HashSet<Integer> set = new HashSet<>();
    
    for (int num : arr) {
        int complement = target - num;
        if (set.contains(complement)) {
            System.out.println("Pair: " + num + " " + complement);
        }
        set.add(num);
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize HashSet
      |
      V
    Traverse array
      |
      V
    Check if complement exists in set
      |
      V
    If found, print pair
      |
      V
    Add number to set
      |
      V
    End
```

### Logic:
Using a HashSet allows quick lookup to check if a number’s complement exists, avoiding nested loops.

### Time Complexity:
- **O(n)** (Single pass using HashSet)

### Space Complexity:
- **O(n)** (Storage for HashSet)

---

## 9. Search Element in Row-Wise and Column-Wise Sorted Matrix

### Program Code:
```java
public static boolean searchInMatrix(int[][] matrix, int target) {
    int rows = matrix.length;
    int cols = matrix[0].length;
    int i = 0, j = cols - 1;
    
    while (i < rows && j >= 0) {
        if (matrix[i][j] == target) {
            return true;
        } else if (matrix[i][j] > target) {
            j--;
        } else {
            i++;
        }
    }
    return false;
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize row = 0, col = last column
      |
      V
    While within matrix bounds:
      |
      V
    Check if current element is target
      |
      | Yes → Return true
      |
      | No → Move left if greater, move down if smaller
      |
      V
    Return false if not found
      |
      V
    End
```

### Logic:
Start from the top-right corner and move left for larger values or down for smaller values.

### Time Complexity:
- **O(m + n)** (At most `m+n` steps)

### Space Complexity:
- **O(1)** (No extra space used)

---

## 10. Program to Implement Stack Using Array

### Program Code:
```java
class StackArray {
    private int[] arr;
    private int top;
    private int capacity;
    
    public StackArray(int size) {
        arr = new int[size];
        capacity = size;
        top = -1;
    }
    
    public void push(int value) {
        if (top == capacity - 1) {
            System.out.println("Stack Overflow");
            return;
        }
        arr[++top] = value;
    }
    
    public int pop() {
        if (top == -1) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return arr[top--];
    }
    
    public int peek() {
        if (top == -1) {
            System.out.println("Stack is empty");
            return -1;
        }
        return arr[top];
    }
    
    public boolean isEmpty() {
        return top == -1;
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize stack array
      |
      V
    Perform push, pop, peek, and isEmpty operations
      |
      V
    Handle overflow and underflow conditions
      |
      V
    End
```

### Logic:
Use an array to store stack elements and maintain a `top` pointer for operations.

### Time Complexity:
- **O(1)** (All operations run in constant time)

### Space Complexity:
- **O(n)** (Space required for stack storage)

---


## 11. Program to Implement Stack Using Linked List

### Program Code:
```java
class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class StackLinkedList {
    private Node top;
    
    public StackLinkedList() {
        this.top = null;
    }
    
    public void push(int value) {
        Node newNode = new Node(value);
        newNode.next = top;
        top = newNode;
    }
    
    public int pop() {
        if (top == null) {
            System.out.println("Stack Underflow");
            return -1;
        }
        int value = top.data;
        top = top.next;
        return value;
    }
    
    public int peek() {
        if (top == null) {
            System.out.println("Stack is empty");
            return -1;
        }
        return top.data;
    }
    
    public boolean isEmpty() {
        return top == null;
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize stack (top = null)
      |
      V
    Perform push, pop, peek, and isEmpty operations
      |
      V
    Handle underflow conditions
      |
      V
    End
```

### Logic:
Using a linked list allows dynamic memory allocation for the stack, avoiding fixed-size constraints of an array.

### Time Complexity:
- **O(1)** (All operations run in constant time)

### Space Complexity:
- **O(n)** (Space required for stack storage)

---

## 12. Program to Implement Stack Using Two Queues

### Program Code:
```java
import java.util.LinkedList;
import java.util.Queue;

class StackUsingQueues {
    private Queue<Integer> q1;
    private Queue<Integer> q2;
    
    public StackUsingQueues() {
        q1 = new LinkedList<>();
        q2 = new LinkedList<>();
    }
    
    public void push(int value) {
        q2.add(value);
        while (!q1.isEmpty()) {
            q2.add(q1.remove());
        }
        Queue<Integer> temp = q1;
        q1 = q2;
        q2 = temp;
    }
    
    public int pop() {
        if (q1.isEmpty()) {
            System.out.println("Stack Underflow");
            return -1;
        }
        return q1.remove();
    }
    
    public int peek() {
        if (q1.isEmpty()) {
            System.out.println("Stack is empty");
            return -1;
        }
        return q1.peek();
    }
    
    public boolean isEmpty() {
        return q1.isEmpty();
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize two queues
      |
      V
    Push: Move elements to q2 and swap queues
      |
      V
    Pop: Remove front of q1
      |
      V
    Peek: Check front of q1
      |
      V
    Handle underflow conditions
      |
      V
    End
```

### Logic:
Use two queues to implement stack operations by maintaining order during `push` operations.

### Time Complexity:
- **Push: O(n)** (Rearranging elements)
- **Pop: O(1)** (Direct removal)

### Space Complexity:
- **O(n)** (Storage for queues)

---

## 13. Sort a Stack Using Another Stack

### Program Code:
```java
import java.util.Stack;

class SortStack {
    public static void sortStack(Stack<Integer> stack) {
        Stack<Integer> tempStack = new Stack<>();
        while (!stack.isEmpty()) {
            int temp = stack.pop();
            while (!tempStack.isEmpty() && tempStack.peek() > temp) {
                stack.push(tempStack.pop());
            }
            tempStack.push(temp);
        }
        while (!tempStack.isEmpty()) {
            stack.push(tempStack.pop());
        }
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize two stacks
      |
      V
    Pop element from original stack
      |
      V
    Compare and insert into temp stack in sorted order
      |
      V
    Move elements back to original stack
      |
      V
    End
```

### Logic:
We use a temporary stack to sort the given stack by maintaining order while transferring elements.

### Time Complexity:
- **O(n²)** (Nested loop for sorting)

### Space Complexity:
- **O(n)** (Extra stack storage)

---

## 14. Implement Queue Using Arrays

### Program Code:
```java
class QueueArray {
    private int front, rear, size;
    private int capacity;
    private int[] queue;

    public QueueArray(int capacity) {
        this.capacity = capacity;
        this.front = this.size = 0;
        this.rear = capacity - 1;
        this.queue = new int[capacity];
    }
    
    public void enqueue(int value) {
        if (size == capacity) {
            System.out.println("Queue Overflow");
            return;
        }
        rear = (rear + 1) % capacity;
        queue[rear] = value;
        size++;
    }
    
    public int dequeue() {
        if (size == 0) {
            System.out.println("Queue Underflow");
            return -1;
        }
        int item = queue[front];
        front = (front + 1) % capacity;
        size--;
        return item;
    }
    
    public int front() {
        if (size == 0) return -1;
        return queue[front];
    }
    
    public int rear() {
        if (size == 0) return -1;
        return queue[rear];
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize queue with array
      |
      V
    Enqueue: Add element at rear
      |
      V
    Dequeue: Remove element from front
      |
      V
    Handle overflow and underflow
      |
      V
    End
```

### Logic:
Queue operations are performed using a circular array approach to optimize space usage.

### Time Complexity:
- **O(1)** (Enqueue and Dequeue operations)

### Space Complexity:
- **O(n)** (Fixed array size)

---

## 15. Implement Queue Using Linked List

### Program Code:
```java
class Node {
    int data;
    Node next;
    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class QueueLinkedList {
    private Node front, rear;
    
    public QueueLinkedList() {
        this.front = this.rear = null;
    }
    
    public void enqueue(int value) {
        Node newNode = new Node(value);
        if (rear == null) {
            front = rear = newNode;
            return;
        }
        rear.next = newNode;
        rear = newNode;
    }
    
    public int dequeue() {
        if (front == null) {
            System.out.println("Queue Underflow");
            return -1;
        }
        int item = front.data;
        front = front.next;
        if (front == null) {
            rear = null;
        }
        return item;
    }
    
    public int front() {
        return (front != null) ? front.data : -1;
    }
    
    public int rear() {
        return (rear != null) ? rear.data : -1;
    }
}
```

### Flowchart:
```
    Start
      |
      V
    Initialize front and rear as null
      |
      V
    Enqueue: Insert element at rear
      |
      V
    Dequeue: Remove element from front
      |
      V
    Handle underflow condition
      |
      V
    End
```

### Logic:
Queue is implemented using a singly linked list, where elements are inserted at the rear and removed from the front.

### Time Complexity:
- **O(1)** (Enqueue and Dequeue operations)

### Space Complexity:
- **O(n)** (Linked list storage)

---















