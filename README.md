# Ex.No.6 AI-Assisted Programming and Debugging

### Date: 02-09-2026
### Name: YEGAVINTI NITHEESH 
### Register no.212224040370
# Aim: 
Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools

# AI Tools Required:
ChatGPT

# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that. 
Learnerss generate

Python
C
Java
using AI.

Then

identify bugs
optimise code
explain complexity
generate unit tests
Finally compare manual coding versus AI-assisted coding. 
Deliverable

Code quality analysis.

# AI-Assisted Programming and Debugging

## Objective

The objective of this experiment is to learn how AI tools can assist in programming and debugging tasks related to mini and final year projects. The experiment focuses on using effective prompts to generate Python, C, and Java programs, identify bugs, optimize code, explain time and space complexity, and generate unit tests. Finally, manual coding is compared with AI-assisted coding based on development time, correctness, efficiency, readability, and code quality.

## Tools Used

* ChatGPT / AI Coding Assistant
* Python
* C
* Java
* VS Code / Online Compiler

## Exercise Description

In this experiment, AI is used as a programming assistant to generate programs in Python, C, and Java. The generated programs are tested and analyzed. AI is then used to identify programming errors, suggest optimized solutions, explain algorithmic complexity, and generate unit test cases. The results are compared with manually written code to understand the advantages and limitations of AI-assisted programming.

---

## 1. Python Programming

### Prompt

```text
Write a Python program to find the largest element in a list.
The program should handle an empty list and should be simple and efficient.
Also explain the time and space complexity.
```

### AI-Generated Code

```python
def find_largest(numbers):
    if not numbers:
        return None

    largest = numbers[0]

    for num in numbers:
        if num > largest:
            largest = num

    return largest


numbers = [10, 25, 7, 42, 18]
print("Largest element:", find_largest(numbers))
```

### Output

```text
Largest element: 42
```

### Complexity Analysis

* Time Complexity: `O(n)`
* Space Complexity: `O(1)`

The program scans the list once, so the time complexity is `O(n)`. Only one additional variable is used to store the largest value, resulting in `O(1)` auxiliary space.

---

## 2. C Programming

### Prompt

```text
Write a C program to check whether a given number is prime.
Identify possible bugs, optimize the program, and explain its time and space complexity.
```

### AI-Generated Code

```c
#include <stdio.h>

int isPrime(int n) {
    if (n < 2)
        return 0;

    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0)
            return 0;
    }

    return 1;
}

int main() {
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    if (isPrime(n))
        printf("%d is a prime number\n", n);
    else
        printf("%d is not a prime number\n", n);

    return 0;
}
```

### Output

```text
Enter a number: 29
29 is a prime number
```

### Optimization

A basic prime-checking program may check every number from `2` to `n-1`. The AI suggested an optimized approach that checks only up to the square root of `n`. If a number has a factor greater than its square root, it must also have a corresponding factor smaller than the square root.

Therefore, the optimized solution significantly reduces the number of iterations for large values.

### Complexity Analysis

* Time Complexity: `O(√n)`
* Space Complexity: `O(1)`

---

## 3. Java Programming

### Prompt

```text
Write a Java program to find duplicate elements in an integer array.
Use an efficient approach and explain the time and space complexity.
```

### AI-Generated Code

```java
import java.util.HashSet;

public class DuplicateElements {

    public static void main(String[] args) {

        int[] numbers = {10, 20, 30, 20, 40, 10, 50};

        HashSet<Integer> seen = new HashSet<>();
        HashSet<Integer> duplicates = new HashSet<>();

        for (int num : numbers) {
            if (!seen.add(num)) {
                duplicates.add(num);
            }
        }

        System.out.println("Duplicate elements: " + duplicates);
    }
}
```

### Output

```text
Duplicate elements: [10, 20]
```

### Complexity Analysis

* Average Time Complexity: `O(n)`
* Space Complexity: `O(n)`

The `HashSet` provides approximately constant-time insertion and lookup on average. Therefore, the complete array can be processed in `O(n)` average time.

---

# 4. Bug Identification and Debugging

### Prompt

```text
Analyze the following Java code and identify the bug.
Explain why the bug occurs and provide the corrected version.

int[] arr = {10, 20, 30, 40};

for (int i = 0; i <= arr.length; i++) {
    System.out.println(arr[i]);
}
```

### AI-Generated Analysis

The bug is present in the loop condition:

```java
i <= arr.length
```

For an array of length 4, the valid indexes are:

```text
0, 1, 2, 3
```

The condition `i <= arr.length` allows `i` to become `4`. Accessing `arr[4]` is invalid because the last valid index is `3`. This results in an `ArrayIndexOutOfBoundsException`.

### Corrected Code

```java
int[] arr = {10, 20, 30, 40};

for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

### Output

```text
10
20
30
40
```

### Result

The AI successfully identified the array indexing error and provided the corrected loop condition. The corrected program executes without an exception.

---

# 5. Code Optimization

### Original Code

```python
numbers = [1, 2, 3, 4, 5]
result = []

for i in numbers:
    if i % 2 == 0:
        result.append(i)

print(result)
```

### Prompt

```text
Optimize the following Python code for better readability and performance while maintaining the same output:

numbers = [1, 2, 3, 4, 5]
result = []

for i in numbers:
    if i % 2 == 0:
        result.append(i)
```

### AI-Optimized Code

```python
numbers = [1, 2, 3, 4, 5]

result = [i for i in numbers if i % 2 == 0]

print(result)
```

### Output

```text
[2, 4]
```

### Analysis

The optimized version uses a Python list comprehension. It performs the same operation as the original loop but provides a shorter and more readable implementation.

The time complexity remains `O(n)` because every element must be checked. The space complexity is `O(n)` in the worst case because the result list may contain all input elements.

---

# 6. Unit Test Generation

### Prompt

```text
Generate unit tests for the Python function find_largest(numbers).
Include normal cases, an empty list, negative numbers, duplicate values,
and a single-element list.
```

### AI-Generated Unit Tests

```python
def test_find_largest():
    assert find_largest([10, 20, 30]) == 30
    assert find_largest([-5, -2, -10]) == -2
    assert find_largest([7]) == 7
    assert find_largest([]) is None
    assert find_largest([5, 5, 5]) == 5

print("All test cases passed")
```

### Test Cases

| Test Case        | Input           | Expected Output |
| ---------------- | --------------- | --------------- |
| Normal case      | `[10, 20, 30]`  | `30`            |
| Negative numbers | `[-5, -2, -10]` | `-2`            |
| Single element   | `[7]`           | `7`             |
| Empty list       | `[]`            | `None`          |
| Duplicate values | `[5, 5, 5]`     | `5`             |

### Output

```text
All test cases passed
```

### Result

The generated unit tests successfully cover normal inputs, boundary conditions, negative values, duplicate values, and empty input. This improves the reliability of the program and helps identify potential errors before deployment.

---

# 7. Manual Coding vs AI-Assisted Coding

| Criteria            | Manual Coding                               | AI-Assisted Coding                     |
| ------------------- | ------------------------------------------- | -------------------------------------- |
| Development Time    | Higher                                      | Lower                                  |
| Code Generation     | Fully manual                                | AI-generated with prompts              |
| Bug Identification  | Requires manual debugging                   | Faster with AI assistance              |
| Optimization        | Depends on programmer experience            | AI can suggest alternatives            |
| Complexity Analysis | Requires manual knowledge                   | Quickly explained by AI                |
| Unit Test Creation  | Requires additional effort                  | Can be generated automatically         |
| Code Readability    | Depends on developer                        | Generally readable but requires review |
| Learning            | Strong understanding through implementation | Faster learning through explanations   |
| Accuracy            | Depends on programmer                       | Must be verified                       |
| Productivity        | Moderate                                    | Higher                                 |

---

# Result

The experiment successfully demonstrated the application of AI-assisted programming and debugging. Python, C, and Java programs were generated using carefully designed prompts. The programs were tested for correctness, bugs were identified and fixed, code was optimized, algorithmic complexity was analyzed, and unit tests were generated.

The comparison showed that AI-assisted programming can reduce development time and provide useful suggestions for debugging, optimization, and testing. However, manual verification remains necessary to ensure correctness, efficiency, security, and suitability for the intended application.
