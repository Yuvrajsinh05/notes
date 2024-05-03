# Array

## What is an Array?

An array is a collection of items of the same variable type that are stored at contiguous memory locations. It’s one of the most popular and simple data structures and is often used to implement other data structures. Each item in an array is indexed starting with 0.

## Basic Terminologies of Array

### Array Index
In an array, elements are identified by their indexes. Array index starts from 0.

### Array Element
Elements are items stored in an array and can be accessed by their index.

### Array Length
The length of an array is determined by the number of elements it can contain.

## Representation of Array

The representation of an array can be defined by its declaration. A declaration means allocating memory for an array of a given size.

### Array Declaration

Arrays can be declared in various ways in different languages. Below are some language-specific array declarations for better illustration:

```c
int arr[5];	  // This array will store integer type elements
char arr[10]; // This array will store char type elements
float arr[20]; // This array will store float type elements
```

However, the above declaration is static or compile-time memory allocation. This means that the array element’s memory is allocated when a program is compiled. Here only a fixed size of memory will be allocated for storage. But in scenarios where the size of the array is not known in advance, static memory allocation is not preferred as it can lead to wastage of memory or insufficient memory allocation.

## Why Array Data Structures are Needed?

Assume there is a class of five students, and if we have to keep records of their marks in examinations, we can do this by declaring five variables individually and keeping track of records. However, if the number of students becomes very large, it would be challenging to manipulate and maintain the data.

Arrays come into play here. While we can use normal variables (v1, v2, v3, ...) when dealing with a small number of objects, if we want to store a large number of instances, managing them with normal variables becomes cumbersome. The idea of an array is to represent many instances in one variable.

### Need for Array

Arrays provide a structured and efficient way to store and manipulate a large number of elements, making it easier to manage data and perform operations efficiently.


# Implementing Arrays in C++ using STL

Arrays can also be implemented using some built-in classes available in the C++ Standard Template Library (STL).

## Vector

**Vector** in C++ STL is a class that represents a dynamic array. The advantages of vectors over normal arrays include:

- No need to pass size as an extra parameter when passing vectors.
- Built-in functions for erasing and inserting elements.
- Support for dynamic sizes; vectors do not require initial specification of size and can be resized.
- Other functionalities provided by vectors.

Vectors are similar to dynamic arrays with the ability to resize themselves automatically when an element is inserted or deleted. Vector elements are placed in contiguous storage, allowing them to be accessed and traversed using iterators. 

To use the `vector` class, include the `<vector>` header file in your program.

### Declaration

```cpp
vector<Type_of_element> vector_name;
```

### Important Functions

- `begin()`: Returns an iterator pointing to the first element in the vector.
- `end()`: Returns an iterator pointing to the theoretical element that follows the last element in the vector.
- `size()`: Returns the number of elements in the vector.
- `capacity()`: Returns the size of the storage space currently allocated to the vector expressed as the number of elements.
- `empty()`: Returns whether the container is empty.
- `push_back()`: Pushes elements into a vector from the back.
- `pop_back()`: Removes elements from the back of the vector.
- `insert()`: Inserts new elements before the element at the specified position.
- `erase()`: Removes elements from a container from the specified position or range.
- `swap()`: Swaps the contents of one vector with another vector of the same type and size.
- `clear()`: Removes all the elements of the vector container.
- `emplace()`: Extends the container by inserting a new element at a position.
- `emplace_back()`: Inserts a new element into the vector container at the end.

### Example

```cpp
// C++ program to illustrate the above functions
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector<int> v;

    // Push elements
    for (int i = 1; i <= 5; i++)
        v.push_back(i);

    cout << "Size : " << v.size();

    // Check if the vector is empty or not
    if (!v.empty())
        cout << "\nVector is not empty";
    else
        cout << "\nVector is empty";

    cout << "\nOutput of begin and end: ";
    for (auto i = v.begin(); i != v.end(); ++i)
        cout << *i << " ";

    // Insert at the beginning
    v.emplace(v.begin(), 5);
    cout << "\nThe first element is: " << v[0];

    // Insert at the end
    v.emplace_back(20);
    int n = v.size();
    cout << "\nThe last element is: " << v[n - 1];

    // Erase the vector
    v.clear();
    cout << "\nVector size after erase(): " << v.size();

    return 0;
}
```

## List

**List** in C++ STL implements a doubly linked list, unlike arrays. Lists allow non-contiguous memory allocation. Compared to vectors, lists have slow traversal, but once a position has been found, insertion and deletion are quick. Normally, when we mention a list, we refer to doubly linked lists. For implementing a singly linked list, the `forward_list` class in C++ STL can be used.

To use the `list` class, include the `<list>` header file in your program.

### Declaration

```cpp
list<Type_of_element> list_name;
```

### Important Functions

- `front()`: Returns the value of the first element in the list.
- `back()`: Returns the value of the last element in the list.
- `push_front(g)`: Adds a new element `g` at the beginning of the list.
- `push_back(g)`: Adds a new element `g` at the end of the list.
- `pop_front()`: Removes the first element of the list and reduces the size of the list by 1.
- `pop_back()`: Removes the last element of the list and reduces the size of the list by 1.
- `begin()` and `end()`: `begin()` function returns an iterator pointing to the first element of the list.
- `empty()`: Returns whether the list is empty (1) or not (0).
- `insert()`: Inserts new elements in the list before the element at a specified position.
- `reverse()`: Reverses the list.
- `size()`: Returns the number of elements in the list.
- `sort()`: Sorts the list in increasing order.

### Example

```cpp
#include <iostream>
#include <list>
#include <iterator>

using namespace std;

// Function for printing the elements in a list
void showlist(list<int> g)
{
    list<int>::iterator it;
    for (it = g.begin(); it != g.end(); ++it)
        cout << '\t' << *it;
    cout << '\n';
}

int main()
{
    list<int> gqlist1, gqlist2;

    for (int i = 0; i < 10; ++i)
    {
        gqlist1.push_back(i * 2);
        gqlist2.push_front(i * 3);
    }
    cout << "\nList 1 (gqlist1) is : ";
    showlist(gqlist1);

    cout << "\nList 2 (gqlist2) is : ";
    showlist(gqlist2);

    cout << "\ngqlist1.front() : " << gqlist1.front();
    cout << "\ngqlist1.back() : " << gqlist1.back();

    cout << "\ngqlist1.pop_front() : ";
    gqlist1.pop_front();
    showlist(gqlist1);

    cout << "\ngqlist2.pop_back() : ";
    gqlist2.pop_back();
    showlist(gqlist2);

    cout << "\ngqlist1.reverse() : ";
    gqlist1.reverse();
    showlist(gqlist1);

    cout << "\ngqlist2.sort(): ";
    gqlist2.sort();
    showlist(gqlist2);

    return 0;
}
```

These examples illustrate the usage of vectors and lists in C++ STL for implementing arrays.


## Iterators in C++ STL

Iterators are used to point at the memory addresses of STL containers. They are primarily used in sequences of numbers, characters, etc., reducing the complexity and execution time of programs.

### Operations of Iterators

1. **begin()**: This function returns the beginning position of the container.
   
2. **end()**: This function returns the position after the end of the container.

### Example

```cpp
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;

int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };
      
    // Declaring iterator to a vector
    vector<int>::iterator ptr;
      
    // Displaying vector elements using begin() and end()
    cout << "The vector elements are: ";
    for (ptr = ar.begin(); ptr < ar.end(); ptr++)
        cout << *ptr << " ";
      
    return 0;    
}
```

Output:
```
The vector elements are: 1 2 3 4 5
```

3. **advance()**: This function increments the iterator position till the specified number mentioned in its arguments.

### Example

```cpp
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;

int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };
      
    // Declaring iterator to a vector
    vector<int>::iterator ptr = ar.begin();
      
    // Using advance() to increment iterator position
    // points to 4
    advance(ptr, 3);
      
    // Displaying iterator position
    cout << "The position of iterator after advancing is: ";
    cout << *ptr << " ";
      
    return 0;
}
```

Output:
```
The position of iterator after advancing is: 4
```

4. **next()**: This function returns the new iterator that the iterator would point to after advancing the positions mentioned in its arguments.

5. **prev()**: This function returns the new iterator that the iterator would point to after decrementing the positions mentioned in its arguments.

### Example

```cpp
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;

int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };
      
    // Declaring iterators to a vector
    vector<int>::iterator ptr = ar.begin();
    vector<int>::iterator ftr = ar.end();
     
    // Using next() to return a new iterator
    // points to 4
    auto it = next(ptr, 3);
      
    // Using prev() to return a new iterator
    // points to 3
    auto it1 = prev(ftr, 3);
      
    // Displaying iterator position
    cout << "The position of new iterator using next() is: ";
    cout << *it << " ";
    cout << endl;
      
    // Displaying iterator position
    cout << "The position of new iterator using prev() is: ";
    cout << *it1 << " ";
    cout << endl;
      
    return 0; 
}
```

Output:
```
The position of new iterator using next() is: 4 
The position of new iterator using prev() is: 3 
```

6. **inserter()**: This function inserts elements at any position in the container. It accepts two arguments, the container and the iterator to the position where the elements have to be inserted.

### Example

```cpp
#include<iostream>
#include<iterator> // for iterators
#include<vector> // for vectors
using namespace std;

int main()
{
    vector<int> ar = { 1, 2, 3, 4, 5 };
    vector<int> ar1 = {10, 20, 30}; 
      
    // Declaring iterator to a vector
    vector<int>::iterator ptr = ar.begin();
     
    // Using advance to set position
    advance(ptr, 3);
      
    // copying elements of ar1 into ar using inserter()
    // inserts ar1 after the 3rd position in ar
    copy(ar1.begin(), ar1.end(), inserter(ar,ptr));
      
    // Displaying new vector elements
    cout << "The new vector after inserting elements is: ";
    for (int &x : ar) 
        cout << x << " ";
      
    return 0;    
}
```

Output:
```
The new vector after inserting elements is: 1 2 3 10 20 30 4 5
```

These examples demonstrate the usage of iterators in C++ STL, showcasing their utility in various operations with containers like vectors.

## Operations on Arrays

### Types of Array Operations:

1. **Traversal**: Traversing through the elements of an array.
   
2. **Insertion**: Inserting a new element in an array.

```c
#include <stdio.h>

int insert(int arr[], int n, int x, int cap, int pos)
{
	if(n == cap)
		return n;

	int idx = pos - 1;

	for(int i = n - 1; i >= idx; i--)
	{
		arr[i + 1] = arr[i];
	}

	arr[idx] = x;

	return n + 1;
} 

int main() {
	
    int arr[5], cap = 5, n = 3;

    arr[0] = 5; arr[1] = 10; arr[2] = 20;

    printf("Before Insertion \n");

    for(int i=0; i < n; i++)
    {
    	printf("%d ",arr[i]);
    }

    printf("\n");

    int x = 7, pos = 2;

    n = insert(arr, n, x, cap, pos);

    printf("After Insertion \n");

    for(int i=0; i < n; i++)
    {
       	printf("%d ",arr[i]);
    }
}
```

3. **Deletion**: Deleting an element from the array.

4. **Searching**: Searching for an element in the array.

```c
#include <stdio.h>

int search(int arr[], int n, int x)
{
	for(int i = 0; i < n; i++)
	{
		if(arr[i] == x)
			return i;
	}

	return -1;
} 

int main() {
	
	int arr[] = {20, 5, 7, 25}, x = 5;

    printf("%d ",search(arr, 4, x));
}
```

5. **Sorting**: Maintaining the order of elements in the array.

### Advantages of Using Arrays:

- Arrays allow random access to elements, making accessing elements by position faster.
- Better cache locality improves performance.
- Representing multiple data items of the same type using a single name.
- Storing multiple data of similar types with the same name.
- Used to implement other data structures like linked lists, stacks, queues, trees, graphs, etc.

### Disadvantages of Arrays:

- Fixed size, cannot be increased or decreased after allocation.
- Allocating less memory than required leads to data loss.
- Homogeneous nature restricts storage of values of different data types.
- Insertion and deletion are difficult due to contiguous memory locations.

### Applications of Arrays:

- Implementation of data structures such as array lists, heaps, hash tables, vectors, and matrices.
- Database records.
- Lookup tables.
- Different sorting algorithms like bubble sort, insertion sort, merge sort, and quick sort.



### Insertion and Deletion in Arrays

#### Insertion in Arrays

Inserting elements in an array can be done in two ways:

1. **Inserting at the end of the array**: If there is space left in the array, the new element can be directly inserted at the end. Otherwise, the array is considered full.

    ```c
    // Insert element at end of array
    if (len < N) {
        arr[len] = k; // Insert element
        len++; // Increase array length
    }
    else {
        // Array is full
    }
    ```

    Time complexity: O(1)

2. **Inserting at a specific position in the array**: If there is space left, the element can be inserted at a specified position. This operation might require shifting elements to the right.

    ```c
    // Insert element at specified position
    if (len < N) {
        // Shift elements to the right
        for (i = len - 1; i >= idx; i--) {
            arr[i + 1] = arr[i];
        }
        arr[idx] = K; // Insert element
        len++; // Increase array length
    }
    else {
        // Array is full
    }
    ```

    Time complexity: O(N) in worst case

#### Deletion in Arrays

To delete an element from an array:

1. **Search for the element**: First, search for the element in the array to find its index.

    ```c
    // Search for element K in the array
    for (i = 0; i < N; i++) {
        if (arr[i] == K) {
            idx = i; // Element found
            break;
        }
    }
    ```

2. **Delete the element at the found index**: Left shift all elements after the index by one place and reduce the length of the array by 1.

    ```c
    // Delete element at found index
    for (i = idx + 1; i < len; i++) {
        arr[i - 1] = arr[i];
    }
    len--; // Decrease array length
    ```

    Time complexity: O(N) in worst case


---

**Sample Problems on Array**

---

**Problem #1: Range Sum Queries using Prefix Sum**

**Description:** We are given an Array of n integers and q queries with indices l and r. We have to find the sum between the given range of indices.

**Input:**
```
[4, 5, 3, 2, 5]
3
0 3
2 4
1 3
```

**Output:**
```
14 (4+5+3+2)
10 (3+2+5)
10 (5+3+2)
```

**Solution:** The number of queries is large, iterating over the array for each query is inefficient. We need a solution to find the answer in constant time. We'll use a prefix sum array to store the sum up to each index and calculate the sum for the given range.

```
prefix[]: Array stores the sum (A[0]+A[1]+....A[i]) at index i.
if l == 0 :
    sum(l,r) = prefix[r]
else :
    sum(l,r) = prefix[r] - prefix[l-1]
```

**Pseudo Code:**
```javascript
// n: size of array
// q: Number of queries
// l, r: Finding Sum of range between index l and r
// l and r (inclusive) and 0 based indexing

function rangeSum(arr, n, queries) {
    let prefix = [];
    prefix[0] = arr[0];
    for (let i = 1; i < n; i++) {
        prefix[i] = arr[i] + prefix[i - 1];
    }

    for (let i = 0; i < queries.length; i++) {
        let [l, r] = queries[i];
        let ans = (l === 0) ? prefix[r] : prefix[r] - prefix[l - 1];
        console.log(ans);
    }
}
```

**Time Complexity:** Max(O(n), O(q))

**Auxiliary Space:** O(n)

---

**Problem #2: Equilibrium index of an array**

**Description:** Equilibrium index of an array is an index such that the sum of elements at lower indexes is equal to the sum of elements at higher indexes. We are given an Array of integers, We have to find out the first index i from the left such that:

A[0] + A[1] + ... A[i-1] = A[i+1] + A[i+2] ... A[n-1]

**Input:**
```
[-7, 1, 5, 2, -4, 3, 0]
```
**Output:**
```
3
A[0] + A[1] + A[2] = A[4] + A[5] + A[6]
```

**Naive Solution:** We can iterate for each index i and calculate the leftsum and rightsum and check whether they are equal.

```javascript
// arr: input array
// n: size of array
// Return the equilibrium index or -1 if not found
function equilibriumIndex(arr, n) {
    for (let i = 0; i < n; i++) {
        let leftSum = 0;
        for (let j = 0; j < i; j++)
            leftSum += arr[j];
        let rightSum = 0;
        for (let j = i + 1; j < n; j++)
            rightSum += arr[j];

        if (leftSum === rightSum)
            return i;
    }
    return -1;
}
```

**Time Complexity:** O(n^2)

**Auxiliary Space:** O(1)


**Tricky Solution:** The idea is to first get the total sum of the array. Then iterate through the array and keep updating the left sum, which is initialized as zero. In the loop, we can get the right sum by subtracting the elements one by one. Then check whether the Leftsum and the Rightsum are equal.

**Pseudo Code:**
```javascript
// n: size of array
function eqindex(arr, n) {
    let sum = 0;
    let leftsum = 0;
    for (let i = 0; i < n; i++)
        sum += arr[i];

    for (let i = 0; i < n; i++) {
        sum -= arr[i]; // now sum will be rightsum for index i
        if (sum === leftsum)
            return i;
        leftsum += arr[i];
    }
    return -1; // If no equilibrium index found
}
```

**Time Complexity:** O(n)

**Auxiliary Space:** O(1)

---



Here's the markdown with the provided problem and solution:

---

**Problem #3: Largest Sum Subarray**

**Description:** We are given an array of positive and negative integers. We have to find the subarray having the maximum sum.

**Input:**
```
[-3, 4, -1, -2, 1, 5]
```
**Output:**
```
7
(4+(-1)+(-2)+1+5)
```

**Solution:** A simple idea is to look for all the positive contiguous segments of the array (max_ending_here is used for this), and keep track of the maximum sum contiguous segment among all the positive segments (max_so_far is used for this). Each time we get a positive sum compare it with max_so_far and if it is greater than max_so_far, update max_so_far.

**Pseudo Code:**
```javascript
// n: size of array
function largestSum(arr, n) {
    let max_so_far = Number.MIN_SAFE_INTEGER;
    let max_ending_here = 0;

    for (let i = 0; i < n; i++) {
        max_ending_here += arr[i];
        if (max_so_far < max_ending_here) {
            max_so_far = max_ending_here;
        }

        if (max_ending_here < 0) {
            max_ending_here = 0;
        }
    }

    return max_so_far;
}
```

**Time Complexity:** O(n)

**Auxiliary Space:** O(1)

---

Here's the markdown with the provided problem and solution:

---

**Problem #4: Merge two sorted Arrays**

**Description:** We are given two sorted arrays `arr1[]` and `arr2[]` of size m and n respectively. We have to merge these arrays and store the numbers in `arr3[]` of size m+n.

**Input:**
```
1 3 4 6
2 5 7 8
```
**Output:**
```
1 2 3 4 5 6 7 8
```

**Solution:** The idea is to traverse both the arrays simultaneously and compare the current numbers from both the Arrays. Pick the smaller element and copy it to `arr3[]` and advance the current index of the array from where the smaller element is picked. When we reach the end of one of the arrays, copy the remaining elements of the other array to `arr3[]`.

**Pseudo Code:**
```javascript
// input arrays - arr1(size m), arr2(size n)
function mergeSorted(arr1, arr2, m, n) {
    let arr3 = []; // merged array
    let i = 0, j = 0, k = 0;
    while (i < m && j < n) {
        if (arr1[i] < arr2[j]) {
            arr3[k++] = arr1[i++];
        } else {
            arr3[k++] = arr2[j++];
        }
    }
    while (i < m) {
        arr3[k++] = arr1[i++];
    }
    while (j < n) {
        arr3[k++] = arr2[j++];
    }
    return arr3;
}
```

**Time Complexity:** O(m+n)

**Auxiliary Space:** O(m+n)

---

**Problem #5: Finding the Largest Element in an Array**

**Description:** Given an array `arr` of size `N`, the task is to find the largest element in the given array.

**Example:** 

Input: `arr[] = {10, 20, 4}`
Output: `20`

Input : `arr[] = {20, 10, 20, 4, 100}`
Output : `100`

**Approach 1 - Naive Method:**

```cpp
#include <bits/stdc++.h>
using namespace std;

int getlargest(int arr[], int n)
{
    for (int i = 0; i < n; ++i) {
        bool flag = true;
        for (int j = i; j < n; ++j) {
            if (arr[j] > arr[i]) {
                flag = false;
                break;
            }
        }
        if (flag == true) {
            return arr[i];
        }
    }

    return -1;
}

int main()
{
    int arr[] = { 5, 8, 20, 15 };
    cout << "Largest in given array is "
         << getlargest(arr, 4);
    return 0;
}
```

**Output:**
```
Largest in given array is 20
```

**Approach 2 – Linear Traversal:** One of the simplest and basic approaches to solve this problem is to traverse the whole list and find the maximum among them.

**Steps:**
1. Create a local variable `max` to store the maximum among the list.
2. Initialize `max` with the first element initially, to start the comparison.
3. Then traverse the given array from the second element till the end, and for each element:
   - Compare the current element with `max`.
   - If the current element is greater than `max`, then replace the value of `max` with the current element.
4. At the end, return and print the value of the largest element of array stored in `max`.

```cpp
// C++ program to find maximum
// in arr[] of size n
#include <bits/stdc++.h>
using namespace std;

int largest(int arr[], int n)
{
	int i;
	
	// Initialize maximum element
	int max = arr[0];

	// Traverse array elements
	// from second and compare
	// every element with current max
	for (i = 1; i < n; i++)
		if (arr[i] > max)
			max = arr[i];

	return max;
}

// Driver Code
int main()
{
	int arr[] = {10, 324, 45, 90, 9808};
	int n = sizeof(arr) / sizeof(arr[0]);
	cout << "Largest in given array is "
		<< largest(arr, n);
	return 0;
}
```

**Output:**
```
Largest in given array is 9808
```

---
**Problem #6: Finding the Second Largest Element in Array**

**Description:** Given an array of integers, our task is to write a program that efficiently finds the second largest element present in the array.

**Example:**

Input: `arr[] = {12, 35, 1, 10, 34, 1}`
Output: The second largest element is `34`.
Explanation: The largest element of the array is `35` and the second largest element is `34`.

Input: `arr[] = {10, 5, 10}`
Output: The second largest element is `5`.
Explanation: The largest element of the array is `10` and the second largest element is `5`.

Input: `arr[] = {10, 10, 10}`
Output: The second largest does not exist.
Explanation: Largest element of the array is `10` there is no second largest element.

**Efficient Solution:**

**Approach:** Find the second largest element in a single traversal. 

**Algorithm:**
1. Initialize the first as 0 (i.e., index of `arr[0]` element).
2. Start traversing the array from `array[1]`,
   - If the current element in array say `arr[i]` is greater than `first`, then update `first` and `second` as follows:
     ```
     second = first
     first = arr[i]
     ```
   - If the current element is in between `first` and `second`, then update `second` to store the value of current variable as follows:
     ```
     second = arr[i]
     ```
3. Return the value stored in `second`.

**Implementation:**

```cpp
// C++ program to find the second largest element
#include <iostream>
using namespace std;

// returns the index of second largest
// if second largest didn't exist return -1
int secondLargest(int arr[], int n) {
    int first = 0, second = -1;
    for (int i = 1; i < n; i++) {
        if (arr[i] > arr[first]) {
            second = first;
            first = i;
        }
        else if (arr[i] < arr[first]) {
            if (second == -1 || arr[second] < arr[i])
                second = i;
        }
    }
    return second;
}

int main() {
    int arr[] = {10, 12, 20, 4};
    int index = secondLargest(arr, sizeof(arr)/sizeof(arr[0]));
    if (index == -1)
        cout << "Second Largest didn't exist";
    else
        cout << "Second largest : " << arr[index];
}
```

**Complexity Analysis:**
- Time Complexity: O(n). Only one traversal of the array is needed.
- Auxiliary space: O(1). As no extra space is required.

 ---
 
**Problem #7: Checking if an Array is Sorted**

**Description:** Given an array of size `n`, write a program to check if it is sorted in ascending order or not. Equal values are allowed in an array, and two consecutive equal values are considered sorted.

**Examples:** 

Input: `20 21 45 89 89 90`
Output: Yes

Input: `20 20 45 89 89 90`
Output: Yes

Input: `20 20 78 98 99 97`
Output: No

**Naive Approach:**

```cpp
#include <iostream>
#include <cmath>
using namespace std;

bool isSorted(int arr[], int n)
{
    for(int i = 0; i < n; i++)
    {
        for(int j = i + 1; j < n; j++)
        {
            if(arr[j] < arr[i])
                return false;
        }
    }

    return true;
} 

int main() {
    int arr[] = {7, 2, 30, 10}, n = 4;
    printf("%s", isSorted(arr, n)? "true": "false");
}
```

**Output:**
```
false
```

**Iterative approach:**

```cpp
// C++ program to check if an
// Array is sorted or not
#include <bits/stdc++.h>
using namespace std;

// Function that returns true if array is
// sorted in non-decreasing order.
bool arraySortedOrNot(int arr[], int n)
{
    // Array has one or no element
    if (n == 0 || n == 1)
        return true;

    for (int i = 1; i < n; i++)

        // Unsorted pair found
        if (arr[i - 1] > arr[i])
            return false;

    // No unsorted pair found
    return true;
}

// Driver code
int main()
{
    int arr[] = { 20, 23, 23, 45, 78, 88 };
    int n = sizeof(arr) / sizeof(arr[0]);
    if (arraySortedOrNot(arr, n))
        cout << "Yes\n";
    else
        cout << "No\n";
}
```

**Output:**
```
Yes
```

**Time Complexity:** O(n) 
**Auxiliary Space:** O(1)


---

**Problem #8: Reversing an Array**

**Description:** Given an array (or string), the task is to reverse the array/string.

**Examples:** 

Input: `arr[] = {1, 2, 3}`
Output: `arr[] = {3, 2, 1}`

Input: `arr[] = {4, 5, 1, 2}`
Output: `arr[] = {2, 1, 5, 4}`

**Iterative way:**

1) Initialize start and end indexes as `start = 0`, `end = n-1`.
2) In a loop, swap `arr[start]` with `arr[end]` and change `start` and `end` as follows: 
   `start = start +1`, `end = end – 1`.

Below is the implementation of the above approach:

```cpp
// Iterative C++ program to reverse an array
#include <bits/stdc++.h>
using namespace std;

/* Function to reverse arr[] from start to end*/
void rvereseArray(int arr[], int start, int end)
{
    while (start < end)
    {
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++;
        end--;
    }
}   

/* Utility function to print an array */
void printArray(int arr[], int size)
{
    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";

    cout << endl;
}

/* Driver function to test above functions */
int main()
{
    int arr[] = {1, 2, 3, 4, 5, 6};
    
    int n = sizeof(arr) / sizeof(arr[0]);

    // To print original array
    printArray(arr, n);
    
    // Function calling
    rvereseArray(arr, 0, n-1);
    
    cout << "Reversed array is" << endl;
    
    // To print the Reversed array
    printArray(arr, n);
    
    return 0;
}
```

**Output:** 

```
1 2 3 4 5 6 
Reversed array is 
6 5 4 3 2 1 
```

**Time Complexity:** O(n)
---

**Problem #9: Removing Duplicates from a Sorted Array**

**Description:** Given a sorted array, the task is to remove the duplicate elements from the array.

**Examples:** 

Input: `arr[] = {2, 2, 2, 2, 2}`
Output: `arr[] = {2}`
New size: `1`

Input: `arr[] = {1, 2, 2, 3, 4, 4, 4, 5, 5}`
Output: `arr[] = {1, 2, 3, 4, 5}`
New size: `5`

**Method 1: (Using extra space)** 

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int remDups(int arr[], int n)
{
    int temp[n];
    temp[0] = arr[0];
    int res = 1;
    for(int i = 1; i < n; i++)
    {
        if(temp[res - 1] != arr[i])
        {
            temp[res] = arr[i];
            res++;
        }
    }
    for(int i = 0; i < res; i++)
    {
        arr[i] = temp[i];
    }
    return res;
}

int main() {
    int arr[] = {10, 20, 20, 30, 30, 30}, n = 6;
    cout<<"Before Removal"<<endl;
    for(int i = 0; i < n; i++)
    {
        cout<<arr[i]<<" ";
    }
    cout<<endl;
    n = remDups(arr, n);
    cout<<"After Removal"<<endl;
    for(int i = 0; i < n; i++)
    {
        cout<<arr[i]<<" ";
    }
}
```

**Output:**

```
Before Removal
10 20 20 30 30 30 
After Removal
10 20 30 
```

**Time Complexity:** O(n) 
**Auxiliary Space:** O(n)

**Method 2: (Constant extra space)**

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int remDups(int arr[], int n)
{
    int res = 1;
    for(int i = 1; i < n; i++)
    {
        if(arr[res - 1] != arr[i])
        {
            arr[res] = arr[i];
            res++;
        }
    }
    return res;
}

int main() {
    int arr[] = {10, 20, 20, 30, 30, 30}, n = 6;
    cout<<"Before Removal"<<endl;
    for(int i = 0; i < n; i++)
    {
        cout<<arr[i]<<" ";
    }
    cout<<endl;
    n = remDups(arr, n);
    cout<<"After Removal"<<endl;
    for(int i = 0; i < n; i++)
    {
        cout<<arr[i]<<" ";
    }
}
```

**Output:**

```
Before Removal
10 20 20 30 30 30 
After Removal
10 20 30 
```

**Time Complexity:** O(n) 
**Auxiliary Space:** O(1)

---

**Problem #10: Move Zeros to End**

**Description:** Given an array of n numbers. The problem is to move all the 0’s to the end of the array while maintaining the order of the other elements. Only a single traversal of the array is required.

**Examples:** 

Input: `arr[]  = {1, 2, 0, 0, 0, 3, 6}`
Output: `1 2 3 6 0 0 0`

Input: `arr[] = {0, 1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0, 9}`
Output: `1 9 8 4 2 7 6 9 0 0 0 0 0`

**Algorithm:**

```
moveZerosToEnd(arr, n)
    Initialize count = 0
    for i = 0 to n-1
        if (arr[i] != 0) then
            arr[count++]=arr[i]
    for i = count to n-1
        arr[i] = 0
```

**Implementation:**

```cpp
// C++ implementation to move all zeroes at the end of array
#include <iostream>
using namespace std;

// function to move all zeroes at the end of array
void moveZerosToEnd(int arr[], int n)
{
    // Count of non-zero elements
    int count = 0;

    // Traverse the array. If arr[i] is non-zero, then
    // update the value of arr at index count to arr[i]
    for (int i = 0; i < n; i++)
        if (arr[i] != 0)
            arr[count++] = arr[i];

    // Update all elements at index >=count with value 0
    for (int i = count; i < n; i++)
        arr[i] = 0;
}

// function to print the array elements
void printArray(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
}

// Driver program to test above
int main()
{
    int arr[] = { 0, 1, 9, 8, 4, 0, 0, 2, 7, 0, 6, 0, 9 };
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "Original array: ";
    printArray(arr, n);

    moveZerosToEnd(arr, n);

    cout << "\nModified array: ";
    printArray(arr, n);
    return 0;
}
```

**Output:**

```
Original array: 0 1 9 8 4 0 0 2 7 0 6 0 9 
Modified array: 1 9 8 4 2 7 6 9 0 0 0 0 0 
```

**Time Complexity:** O(n). 
**Auxiliary Space:** O(1).

---


# Problem #11: Left Rotate an Array by D places

## Description
Given an array of integers `arr[]` of size `N` and an integer `d`, the task is to rotate the array elements to the left by `d` positions.

## Examples

Input: 
```
arr[] = {1, 2, 3, 4, 5, 6, 7}, d = 2
```
Output: 
```
3 4 5 6 7 1 2
```

Input: 
```
arr[] = {3, 4, 5, 6, 7, 1, 2}, d = 2
```
Output: 
```
5 6 7 1 2 3 4
```

## Naive Approach

```cpp
#include <iostream>
#include <cmath>
using namespace std;

void lRotateOne(int arr[], int n) {
    int temp = arr[0];

    for(int i = 1; i < n; i++) {
        arr[i - 1] = arr[i];
    }

    arr[n - 1] = temp;
}

void leftRotate(int arr[], int d, int n) {
    for(int i = 0; i < d; i++) {
        lRotateOne(arr, n);
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5}, n = 5, d = 2;

    cout << "Before Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    cout << endl;

    leftRotate(arr, d, n);

    cout << "After Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

Output:

```
Before Rotation
1 2 3 4 5 
After Rotation
3 4 5 1 2 
Time complexity : O(d*n) 
Auxiliary Space : O(1)
```

## Efficient Approach

```cpp
#include <iostream>
#include <cmath>
using namespace std;

void leftRotate(int arr[], int d, int n) {
    int temp[d];

    for(int i = 0; i < d; i++) {
        temp[i] = arr[i];
    }

    for(int i = d; i < n; i++) {
        arr[i - d] = arr[i];
    }

    for(int i = 0; i < d; i++) {
        arr[n - d + i] = temp[i];
    }   
}

int main() {
    int arr[] = {1, 2, 3, 4, 5}, n = 5, d = 2;

    cout << "Before Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    cout << endl;

    leftRotate(arr, d, n);

    cout << "After Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

Output:

```
Before Rotation
1 2 3 4 5 
After Rotation
3 4 5 1 2 
Time complexity : O(n) 
Auxiliary Space : O(d)
```

## Reversal Method

```cpp
#include <iostream>
#include <cmath>
using namespace std;

void reverse(int arr[], int low, int high) {
    while(low < high) {
        swap(arr[high], arr[low]);

        low++;
        high--;
    }
}   

void leftRotate(int arr[], int d, int n) {
    reverse(arr, 0, d - 1);
    reverse(arr, d, n - 1);
    reverse(arr, 0, n - 1);
}

int main() {
    int arr[] = {1, 2, 3, 4, 5}, n = 5, d = 2;

    cout << "Before Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    cout << endl;

    leftRotate(arr, d, n);

    cout << "After Rotation" << endl;

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

Output

```
Before Rotation
1 2 3 4 5 
After Rotation
3 4 5 1 2 

```

Time complexity : O(n) 
Auxiliary Space : O(1)

---

# Problem #12 : Leaders in an Array problem

## Description
Write a program to print all the LEADERS in the array. An element is a leader if it is greater than all the elements to its right side. And the rightmost element is always a leader.

## Examples

Input: `arr[] = {16, 17, 4, 3, 5, 2}`  
Output: `17 5 2`

Input: `arr[] = {1, 2, 3, 4, 5, 2}`  
Output: `5 2`

## Naive Approach

```cpp
#include<iostream>
using namespace std;

void printLeaders(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        int j;
        for (j = i+1; j < size; j++) {
            if (arr[i] <=arr[j])
                break;
        }
        if (j == size)
            cout << arr[i] << " ";
    }
}

int main() {
    int arr[] = {16, 17, 4, 3, 5, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    printLeaders(arr, n);
    return 0;
}
```

Output:

```
17 5 2
Time Complexity: O(N * N)
Auxiliary Space: O(1)
```

## Find Leader by finding suffix maximum

```cpp
#include <iostream>
using namespace std;

void printLeaders(int arr[], int size) {
    int max_from_right = arr[size-1];
    cout << max_from_right << " ";
    
    for (int i = size-2; i >= 0; i--) {
        if (max_from_right < arr[i]) {		
            max_from_right = arr[i];
            cout << max_from_right << " ";
        }
    }
}

int main() {
    int arr[] = {16, 17, 4, 3, 5, 2};
    int n = sizeof(arr)/sizeof(arr[0]);
    printLeaders(arr, n);
    return 0;
}
```

Output:

```
2 5 17
```

Time Complexity: O(n)
Auxiliary Space: O(1)



# Problem 13: Maximum Difference Problem with Order

Given an array `arr[]` of integers, find out the maximum difference between any two elements such that the larger element appears after the smaller number.

## Examples

**Input**: `arr = {2, 3, 10, 6, 4, 8, 1}`  
**Output**: `8`  
**Explanation**: The maximum difference is between 10 and 2.

**Input**: `arr = {7, 9, 5, 6, 3, 2}`  
**Output**: `2`  
**Explanation**: The maximum difference is between 9 and 7.

## Method 1 (Simple)

Use two loops. In the outer loop, pick elements one by one and in the inner loop calculate the difference of the picked element with every other element in the array and compare the difference with the maximum difference calculated so far.

```cpp
// C++ program to find Maximum difference
// between two elements such that larger
// element appears after the smaller number
#include <bits/stdc++.h>
using namespace std;

/* The function assumes that there are
at least two elements in the array. The
function returns a negative value if the
array is sorted in decreasing order and
returns 0 if elements are equal */
int maxDiff(int arr[], int arr_size) {
    int max_diff = arr[1] - arr[0];
    for (int i = 0; i < arr_size; i++) {
        for (int j = i+1; j < arr_size; j++) {	
            if (arr[j] - arr[i] > max_diff)
                max_diff = arr[j] - arr[i];
        }
    }
    return max_diff;
}

/* Driver program to test above function */
int main() {
    int arr[] = {1, 2, 90, 10, 110};
    int n = sizeof(arr) / sizeof(arr[0]);
    // Function calling
    cout << "Maximum difference is " << maxDiff(arr, n);
    return 0;
}
```

**Output**: Maximum difference is 109  
**Time Complexity**: O(n^2)  
**Auxiliary Space**: O(1)

## Method 2 (Tricky and Efficient)

In this method, instead of taking the difference of the picked element with every other element, we take the difference with the minimum element found so far. So we need to keep track of two things:

1) Maximum difference found so far (`max_diff`).
2) Minimum number visited so far (`min_element`).

```cpp
// C++ program to find Maximum difference
// between two elements such that larger
// element appears after the smaller number
#include <bits/stdc++.h>
using namespace std;

/* The function assumes that there are
at least two elements in the array. The
function returns a negative value if the
array is sorted in decreasing order and
returns 0 if elements are equal */
int maxDiff(int arr[], int arr_size) {
    // Maximum difference found so far
    int max_diff = arr[1] - arr[0];
    // Minimum number visited so far
    int min_element = arr[0];
    for(int i = 1; i < arr_size; i++) {	
        if (arr[i] - min_element > max_diff)							
            max_diff = arr[i] - min_element;
        if (arr[i] < min_element)
            min_element = arr[i];					
    }
    return max_diff;
}

/* Driver program to test above function */
int main() {
    int arr[] = {1, 2, 90, 10, 110};
    int n = sizeof(arr) / sizeof(arr[0]);
    // Function calling
    cout << "Maximum difference is " << maxDiff(arr, n);
    return 0;
}
```
```
**Output**: Maximum difference is 109
```
**Time Complexity**: O(n)  
**Auxiliary Space**: O(1)

