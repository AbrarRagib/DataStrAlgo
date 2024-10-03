Time Complexity Explained with Examples
Time complexity is a fundamental concept in computer science used to evaluate how the runtime of an algorithm increases as the size of the input grows. It helps developers assess the scalability and efficiency of their algorithms. Time complexity is typically expressed using Big O notation, which provides an upper bound on the growth rate of the runtime in relation to the input size.

Compile Time vs. Runtime
Compile time: The phase during which the source code (in languages like C++, Java, Python) is converted into executable machine code by a compiler. This happens before execution.
Runtime: The phase during which the program is actually running and solving a problem after compilation. This is the period when time complexity comes into play.
Common Time Complexities
1. O(1) - Constant Time Complexity
The execution time remains constant regardless of the size of the input. This means the algorithm always takes the same amount of time to execute, no matter how much input it receives.

Example:

python
Copy code
def get_first_element(arr):
    return arr[0]
In this case, accessing the first element of an array takes the same time, regardless of the size of the array.

2. O(n) - Linear Time Complexity
The runtime increases linearly with the size of the input. If the input doubles, the runtime also doubles.

Example:

python
Copy code
def print_all_elements(arr):
    for element in arr:
        print(element)
Here, the time taken to print all elements grows in direct proportion to the size of the input array.

3. O(n²) - Quadratic Time Complexity
The runtime grows quadratically with the size of the input. This typically occurs in algorithms with nested loops, where each loop iterates over the entire input.

Example:

python
Copy code
def print_all_pairs(arr):
    for i in range(len(arr)):
        for j in range(len(arr)):
            print(arr[i], arr[j])
For an array of size n, there are n² possible pairs to print, leading to quadratic time complexity.

4. O(log n) - Logarithmic Time Complexity
The runtime grows logarithmically as the input size increases. Logarithmic complexity occurs when the problem size is divided in half at each step.

Example:

python
Copy code
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
In binary search, the array is halved with each iteration, making it logarithmic in complexity.

5. O(n log n) - Linearithmic Time Complexity
The runtime increases linearly and logarithmically as the input size grows. This occurs in efficient sorting algorithms where the input is divided and then conquered, such as in mergesort.

Example:

python
Copy code
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]
        
        merge_sort(left_half)
        merge_sort(right_half)
        
        i = j = k = 0
        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1
        
        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1
        
        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1
Merge sort is an example of a divide-and-conquer algorithm that divides the array into smaller parts and sorts them, resulting in a time complexity of O(n log n).

6. O(2ⁿ) - Exponential Time Complexity
The runtime doubles with each additional input element, leading to an extremely rapid growth rate. This is common in algorithms that explore all possible combinations using recursion.

Example:

python
Copy code
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n - 1) + fibonacci(n - 2)
Here, the Fibonacci sequence is calculated using a recursive approach, which results in exponential time complexity due to the repeated calculations.

7. O(n!) - Factorial Time Complexity
The runtime grows factorially as the input size increases. This happens when the algorithm generates all possible permutations of the input, as is common with brute-force approaches.

Example:

python
Copy code
from itertools import permutations

def all_permutations(arr):
    return list(permutations(arr))
Generating all permutations of an array of size n requires n! operations, resulting in factorial time complexity.

Additional Time Complexities
O(√n) - Sublinear Time Complexity
The runtime grows with the square root of the input size.
Example: Algorithms that solve certain optimization problems using geometrical methods.
O(log² n) - Polylogarithmic Time Complexity
This occurs when the runtime grows with the square of the logarithm of the input.
Example: Some advanced tree structures like fractional cascading.
Hierarchy of Time Complexities
Ordered from most efficient (slow growth rate) to least efficient (fast growth rate):

O(1) - Constant time
O(log n) - Logarithmic time
O(n) - Linear time
O(n log n) - Linearithmic time
O(n²) - Quadratic time
O(2ⁿ) - Exponential time
O(n!) - Factorial time
Summary
Understanding time complexity is crucial for designing efficient algorithms. Algorithms with lower time complexities like O(1), O(log n), and O(n) scale well with larger inputs, while those with higher time complexities like O(n²), O(2ⁿ), and O(n!) should be avoided for large datasets. Efficient algorithms can greatly improve performance, especially in applications that handle large amounts of data.
