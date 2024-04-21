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

