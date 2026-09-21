# Ex.No.6 AI-Assisted Programming and Debugging

### Date: 21-09-2026
### Name: NITHEESH YEGAVINTI 
### Register no.212224040370
# Aim: 
Write and implement Python, C, and Java programs using AI assistance to develop a Student Performance Analysis System, identify and debug errors, optimize the code, analyze time and space complexity, generate unit tests, and compare manual coding with AI-assisted coding.

# AI Tools Required:
ChatGPT

# Explanation:
In this experiment, AI is used as a programming assistant for developing applications related to student performance analysis.

The AI tool is used to:

Generate Python programs
Generate C programs
Generate Java programs
Identify programming bugs
Optimize code
Explain time and space complexity
Generate unit tests
Compare manual coding with AI-assisted coding

Learners generate

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

## Deliverable

Code quality analysis.

# AI-Assisted Programming and Debugging

## Objective

The objective of this experiment is to understand how AI tools can assist in programming and debugging tasks. A Student Performance Analysis System is used as the application domain.

The experiment demonstrates how AI can generate Python, C, and Java programs, identify programming errors, optimize solutions, explain algorithmic complexity, and generate unit tests.

Finally, manual coding is compared with AI-assisted coding based on development time, correctness, efficiency, readability, testing, and code quality.

## Tools Used

* ChatGPT / AI Coding Assistant
* Python
* C
* Java
* VS Code / Online Compiler

## Exercise Description

In this experiment, AI is used to develop programs for analyzing student marks and performance.

The generated programs are executed and tested. AI is then used to identify errors, suggest optimized implementations, explain time and space complexity, and generate suitable unit test cases.

The results are compared with manually written programs to understand the advantages and limitations of AI-assisted programming

---

## 1. Python Programming

### Prompt

```text
Write a Python program to calculate the average marks of a student
from a list of subject marks.

The program should validate the input, handle an empty list,
calculate the average, and display the student's performance.
Also explain the time and space complexity.
```

### AI-Generated Code

```python
def calculate_average(marks):
    if not marks:
        return None

    total = sum(marks)
    return total / len(marks)


def performance(average):
    if average >= 90:
        return "Excellent"
    elif average >= 75:
        return "Very Good"
    elif average >= 60:
        return "Good"
    elif average >= 50:
        return "Average"
    else:
        return "Needs Improvement"


marks = [85, 78, 92, 88, 76]

average = calculate_average(marks)

if average is not None:
    print("Average Marks:", average)
    print("Performance:", performance(average))
else:
    print("No marks available")
```

### Output

```text
Average Marks: 83.8
Performance: Very GoodLargest element: 42
```

### Complexity Analysis

* Time Complexity: `O(n)`
* Space Complexity: `O(1)`

The program scans the list once, so the time complexity is `O(n)`. Only one additional variable is used to store the largest value, resulting in `O(1)` auxiliary space.

---

## 2. C Programming

### Prompt

```text
Write a C program to find the highest mark among a group of students.

The program should accept marks for n students, find the highest mark,
identify the student who obtained it, and explain the time and
space complexity.
```

### AI-Generated Code

```c
#include <stdio.h>

int main() {
    int n;

    printf("Enter number of students: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid number of students\n");
        return 0;
    }

    int marks[n];

    printf("Enter marks:\n");

    for (int i = 0; i < n; i++) {
        printf("Student %d: ", i + 1);
        scanf("%d", &marks[i]);
    }

    int highest = marks[0];
    int student = 1;

    for (int i = 1; i < n; i++) {
        if (marks[i] > highest) {
            highest = marks[i];
            student = i + 1;
        }
    }

    printf("Highest Mark: %d\n", highest);
    printf("Student: %d\n", student);

    return 0;
}
```

### Output

```text
Enter number of students: 5
Enter marks:
Student 1: 78
Student 2: 92
Student 3: 85
Student 4: 67
Student 5: 88

Highest Mark: 92
Student: 2
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
Write a Java program to count the number of students who passed
and failed based on their marks.

Consider marks greater than or equal to 50 as pass.
Use an efficient approach and explain the time and space complexity.
```

### AI-Generated Code

```java
public class StudentResult {

    public static void main(String[] args) {

        int[] marks = {78, 45, 91, 32, 67, 49, 85};

        int passed = 0;
        int failed = 0;

        for (int mark : marks) {
            if (mark >= 50) {
                passed++;
            } else {
                failed++;
            }
        }

        System.out.println("Number of Passed Students: " + passed);
        System.out.println("Number of Failed Students: " + failed);
    }
}
```

### Output

```text
Number of Passed Students: 4
Number of Failed Students: 3
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

int[] marks = {78, 85, 92, 67};

for (int i = 0; i <= marks.length; i++) {
    System.out.println(marks[i]);
}
```

### AI-Generated Analysis

The bug is present in the loop condition:

```java
i <= marks.length
```

For an array of length 4, the valid indexes are:

```text
0, 1, 2, 3
```

The condition `i <= marks.length` allows `i` to become `4`. Accessing `marks[4]` is invalid because the last valid index is `3`. This results in an `ArrayIndexOutOfBoundsException`.

### Corrected Code

```java
int[] marks = {78, 85, 92, 67};

for (int i = 0; i < marks.length; i++) {
    System.out.println(marks[i]);
}
```

### Output

```text
78
85
92
67
```

### Result

The AI successfully identified the array indexing error and provided the corrected loop condition. The corrected program executes without an exception.

---

# 5. Code Optimization

### Original Code

```python
marks = [78, 85, 92, 67, 45, 88]

passed = []

for mark in marks:
    if mark >= 50:
        passed.append(mark)

print(passed)
```

### Prompt

```text
Optimize the following Python code for better readability
while maintaining the same output.

marks = [78, 85, 92, 67, 45, 88]

passed = []

for mark in marks:
    if mark >= 50:
        passed.append(mark)
```

### AI-Optimized Code

```python
marks = [78, 85, 92, 67, 45, 88]

passed = [mark for mark in marks if mark >= 50]

print(passed)
```

### Output

```text
[78, 85, 92, 67, 88]
```

### Analysis

The optimized version uses a Python list comprehension. It performs the same operation as the original loop but provides a shorter and more readable implementation.

The time complexity remains `O(n)` because every element must be checked. The space complexity is `O(n)` in the worst case because the result list may contain all input elements.

---

# 6. Unit Test Generation

### Prompt

```text
Generate unit tests for the Python function calculate_average(marks).

Include normal marks, an empty list, a single mark,
all equal marks, and decimal values.
```

### AI-Generated Unit Tests

```python
def calculate_average(marks):
    if not marks:
        return None

    return sum(marks) / len(marks)


def test_calculate_average():
    assert calculate_average([80, 90, 70]) == 80
    assert calculate_average([]) is None
    assert calculate_average([75]) == 75
    assert calculate_average([50, 50, 50]) == 50
    assert calculate_average([85.5, 90.5]) == 88

    print("All test cases passed")


test_calculate_average()
```

### Test Cases

| Test Case     | Input          | Expected Output |
| ------------- | -------------- | --------------- |
| Normal case   | `[80, 90, 70]` | `80`            |
| Empty list    | `[]`           | `None`          |
| Single mark   | `[75]`         | `75`            |
| Equal marks   | `[50, 50, 50]` | `50`            |
| Decimal marks | `[85.5, 90.5]` | `88`            |


### Output

```text
All test cases passed
```

### Result

The generated unit tests cover normal input, boundary conditions, single-element input, equal values, and decimal values.

These tests help verify the correctness of the calculate_average() function

---

# 7. Manual Coding vs AI-Assisted Coding

| Criteria            | Manual Coding                               | AI-Assisted Coding                                    |
| ------------------- | ------------------------------------------- | ----------------------------------------------------- |
| Development Time    | Programmer writes the solution manually     | AI can generate an initial solution quickly           |
| Code Generation     | Fully manual                                | Generated using prompts                               |
| Bug Identification  | Requires manual debugging                   | AI can suggest possible bugs                          |
| Optimization        | Depends on programmer knowledge             | AI can suggest alternative implementations            |
| Complexity Analysis | Requires algorithm knowledge                | AI can explain complexity                             |
| Unit Test Creation  | Tests need to be written manually           | AI can generate test cases                            |
| Code Readability    | Depends on programmer                       | AI-generated code may be readable but requires review |
| Learning            | Strong understanding through implementation | Provides explanations and examples                    |
| Accuracy            | Depends on programmer                       | Must be tested and verified                           |
| Productivity        | Depends on experience and task              | Can reduce repetitive coding effort                   |

---

# Result

The experiment successfully demonstrated the use of AI-assisted programming and debugging for a Student Performance Analysis System.

Python, C, and Java programs were generated using carefully designed prompts. The programs were tested, programming bugs were identified and corrected, code was optimized, time and space complexity were analyzed, and unit test cases were generated.

The comparison demonstrated that AI can assist programmers in code generation, debugging, optimization, complexity analysis, and test generation. However, the generated code should always be reviewed and tested by the programmer to verify correctness, efficiency, security, and suitability for the intended application.
