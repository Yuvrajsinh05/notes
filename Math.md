# Count Digits

## Problem
Given a number \( N \), the task is to return the count of digits in this number.

## Example
Program to count digits in an integer.

### Program Description
This solution provides a simple iterative method to count digits in an integer:
- The integer entered by the user is stored in the variable `n`.
- A while loop is iterated until the test expression `n !== 0` evaluates to false.
- For instance, considering the input integer as 3456.

### Iteration Steps
1. After the first iteration, the value of `n` will be updated to 345, and the count is incremented to 1.
2. After the second iteration, the value of `n` will be updated to 34, and the count is incremented to 2.
3. After the third iteration, the value of `n` will be updated to 3, and the count is incremented to 3.
4. In the fourth iteration, the value of `n` will be updated to zero, and the count will be incremented to 4.  
5. The loop terminates with the final count as 4 when the test expression (`n !== 0`) evaluates as false.

### Implementation (JavaScript)
```javascript
// Function to count the number of digits in a given number
function countDigits(n) {
    if (n === 0)
        return 1;
    let count = 0;
    while (n !== 0) {
        n = Math.floor(n / 10);
        ++count;
    }
    return count;
}

// Example usage
let n = 345289467;
console.log("Number of digits:", countDigits(n));
```

### Output
```
Number of digits: 9
```

### Complexity Analysis
- Time Complexity: \( O(\log_{10}(n)) \) or \( θ(\text{num digits}) \)
- Auxiliary Space: \( O(1) \) or constant

---

# Palindrome Check

## Problem
Given an integer, write a function that returns true if the given number is a palindrome, else false. For example, 12321 is palindrome, but 1451 is not palindrome.

## Simple Approach
To check whether the given number is a palindrome or not, we will reverse the digits of the given number and compare it with the original number. If they are equal, the number is a palindrome; otherwise, it is not.

### Implementation (JavaScript)
```javascript
// Function to check if a number is palindrome
function checkPalindrome(n) {
    let reverse = 0;
    let temp = n;
    while (temp !== 0) {
        reverse = (reverse * 10) + (temp % 10);
        temp = Math.floor(temp / 10);
    }
    return reverse === n;
}

// Example usage
let num = 7007;
console.log(checkPalindrome(num) ? "Yes" : "No");
```

### Output
```
Yes
```

### Complexity Analysis
- Time Complexity: \( O(\log(n)) \) or \( O(\text{Number of digits in a given number}) \)
- Auxiliary Space: \( O(1) \) or constant

---

# Factorial of a Number

## Problem
What is the factorial of a number?
Factorial of a non-negative integer is the multiplication of all positive integers smaller than or equal to \( n \). For example, the factorial of 6 is \( 6 \times 5 \times 4 \times 3 \times 2 \times 1 \), which is 720. 
A factorial is represented by a number and a "!" mark at the end. It is widely used in permutations and combinations to calculate the total possible outcomes. A French mathematician Christian Kramp firstly used the exclamation.

## Recursive Solution
Let's create a factorial program using recursive functions. Until the value is not equal to zero, the recursive function will call itself. Factorial can be calculated using the following recursive formula:
\( n! = n \times (n – 1)! \)
\( n == 1 \) if \( n = 0 \) or \( n = 1 \)

### Implementation (C++)
```cpp
// C++ program to find factorial of given number
#include <iostream>
using namespace std;

// Function to find factorial of given number
unsigned int factorial(unsigned int n)
{
	if (n == 0 || n == 1)
		return 1;
	return n * factorial(n - 1);
}

// Driver code
int main()
{
	int num = 5;
	cout << "Factorial of "
		<< num << " is " << factorial(num) << endl;
	return 0;
}
```

### Output
```
Factorial of 5 is 120
```

### Complexity Analysis
- Time Complexity: \( O(n) \)
- Auxiliary Space: \( O(n) \)

## Iterative Solution
Factorial can also be calculated iteratively as recursion can be costly for large numbers.

Follow the steps to solve the problem:
1. Using a for loop, we will write a program for finding the factorial of a number. 
2. An integer variable with a value of 1 will be used in the program. 
3. With each iteration, the value will increase by 1 until it equals the value entered by the user. 
4. The factorial of the number entered by the user will be the final value in the fact variable.

### Implementation (C++)
```cpp
// C++ program for factorial of a number
#include <iostream>
using namespace std;

// Function to find factorial of given number
unsigned int factorial(unsigned int n)
{
	int res = 1, i;
	for (i = 2; i <= n; i++)
		res *= i;
	return res;
}

// Driver code
int main()
{
	int num = 5;
	cout << "Factorial of "
		<< num << " is "
		<< factorial(num) << endl;
	return 0;
}
```

### Output
```
Factorial of 5 is 120
```

### Complexity Analysis
- Time Complexity: \( O(n) \)
- Auxiliary Space: \( O(1) \)

---

# Trailing Zeros in Factorial

In a realm where numbers hold secrets, a captivating challenge awaits, which is to, Count Trailing Zeros in Factorial!

## Problem

Given a number, the task is to find the number of trailing zeros in the factorial of the number. Trailing zeros are the zeros that appear at the end of a number (factorial in this case).

### Examples

- Input: 5
  Output: 1
  - Factorial of 5 = 5 \times 4 \times 3 \times 2 \times 1 = 120, which has one trailing 0.

- Input: 20
  Output: 4
  - Factorial of 20 = 20 \times 19 \times 18 \times ... \times 3 \times 2 \times 1 = 2432902008176640000, which has 4 trailing zeroes.

- Input: 100


  Output: 24

## Approaches

We have 2 approaches to solve the problem: Naive Approach & Efficient Approach

1. **Naive Approach**: A simple method is to first calculate the factorial of \( n \), then count trailing 0s in the result (We can count trailing 0s by repeatedly dividing the factorial by 10 till the remainder is not 0). But, this method can cause overflow for slightly bigger numbers as the factorial of a number is a big number. So, we prefer the Efficient Approach.

2. **Efficient Approach**: The idea is to consider prime factors of a factorial \( n \). A trailing zero is always produced by prime factors 2 and 5. Our task is done if we can count the number of 5s and 2s. Consider the following examples:  
   - \( n = 5 \): There is one 5 and three 2s in prime factors of \( 5! \) (\( 2 \times 2 \times 2 \times 3 \times 5 \)). So a count of trailing 0s is 1.
   - \( n = 11 \): There are two 5s and eight 2s in prime factors of \( 11! \) (\( 2^8 \times 3^4 \times 5^2 \times 7 \times 11 \)). So the count of trailing 0s is 2.  
   We can easily observe that the number of 2s in prime factors is always more than or equal to the number of 5s. So if we count 5s in prime factors, we are done.  
   The summarized formula for counting trailing 0s is:  
   Trailing 0s in \( n! = \text{Count of 5s in prime factors of } n! = \lfloor n/5 \rfloor + \lfloor n/25 \rfloor + \lfloor n/125 \rfloor + \ldots \).

## Implementation (JavaScript)

```javascript
/**
 * Function to return trailing 0s in factorial of n
 * @param {number} n - The number
 * @returns {number} - Count of trailing 0s
 */
function findTrailingZeros(n) {
    if (n < 0) // Negative Number Edge Case
        return -1;

    // Initialize result
    let count = 0;

    // Keep dividing n by powers of 5 and update count
    for (let i = 5; Math.floor(n / i) >= 1; i *= 5)
        count += Math.floor(n / i);

    return count;
}
```

// Driver Code
const n = 100;
console.log(`Count of trailing 0s in ${n}! is ${findTrailingZeros(n)}`);

**Output:**  
Count of trailing 0s in 100! is 24

**Time Complexity:** \( O(\log_5n) \)  
**Auxiliary Space:** \( O(1) \)


# GCD (Greatest Common Divisor) or HCF (Highest Common Factor) of Two Numbers

GCD or HCF of two numbers is the largest number that divides both of them.

For example, GCD of 20 and 28 is 4 and GCD of 98 and 56 is 14.

## Naive Approach

A simple and old approach is the Euclidean algorithm by subtraction. It is a process of repeat subtraction, carrying the result forward each time until the result is equal to any one number being subtracted. If the answer is greater than 1, there is a GCD (besides 1). If the answer is 1, there is no common divisor (besides 1), and so both numbers are coprime.

### Pseudo Code:

```
def gcd(a, b):
  if a == b:
    return a
  if a > b:
    gcd(a – b, b)
  else:
    gcd(a, b – a)
```

## Better Approach

Instead of Euclidean algorithm by subtraction, a better approach is present. We continuously divide the bigger number by the smaller number.

## Implementation (Javascript)

### Recursive Function for GCD:

```javascript
/**
 * Recursive function to return GCD of a and b
 * @param {number} a - The first number
 * @param {number} b - The second number
 * @returns {number} - The GCD of a and b
 */
function gcd(a, b) {
    return b === 0 ? a : gcd(b, a % b);	
}

// Driver program to test above function
const a = 98, b = 56;
console.log(`GCD of ${a} and ${b} is ${gcd(a, b)}`);
```

**Output:**  
GCD of 98 and 56 is 14

**Time Complexity:** \( O(\log(\min(a, b))) \)  
**Auxiliary Space:** \( O(\log(\min(a, b))) \)

The time complexity for the above algorithm is \( O(\log(\min(a, b))) \). The derivation for this is obtained from the analysis of the worst-case scenario. We observe that for the nth step, the numbers would be \( (fib(n), fib(n+1)) \), where Fibonacci series grows exponentially. Hence, the time complexity is logarithmic.



# LCM of Two Numbers

LCM (Least Common Multiple) of two numbers is the smallest number which can be divided by both numbers.

For example, LCM of 15 and 20 is 60, and LCM of 5 and 7 is 35.

## Approaches

### Naive Approach
A simple solution is to find all prime factors of both numbers, then find the union of all factors present in both numbers. Finally, return the product of elements in the union.

### Efficient Approach
An efficient solution is based on the formula for LCM of two numbers 'a' and 'b':
```
LCM(a, b) = (a x b) / GCD(a, b)
```
We have a function to find the GCD of two numbers. Using GCD, we can find LCM.

## Implementation (Javascript)

```javascript
/**
 * Recursive function to return gcd of a and b
 * @param {number} a - The first number
 * @param {number} b - The second number
 * @returns {number} - The gcd of a and b
 */
function gcd(a, b) {
    if (b === 0)
        return a;
    return gcd(b, a % b);
}

/**
 * Function to return LCM of two numbers
 * @param {number} a - The first number
 * @param {number} b - The second number
 * @returns {number} - The LCM of a and b
 */
function lcm(a, b) {
    return (a * b) / gcd(a, b);
}

// Driver program to test above function
const a = 15, b = 20;
console.log(`LCM of ${a} and ${b} is ${lcm(a, b)}`);
```

**Output:**  
LCM of 15 and 20 is 60


## Prime Numbers

A prime number is a natural number greater than 1, which is only divisible by 1 and itself. First few prime numbers are: 2 3 5 7 11 13 17 19 23…..

In other words, the prime number is a positive integer greater than 1 that has exactly two factors, 1 and the number itself.
There are many prime numbers, such as 2, 3, 5, 7, 11, 13, etc. 
Keep in mind that 1 cannot be either prime or composite. 
The remaining numbers, except for 1, are classified as prime and composite numbers. 

### Some interesting facts about Prime numbers:

- Except for 2, which is the smallest prime number and the only even prime number, all prime numbers are odd numbers.
- Every prime number can be represented in form of \(6n + 1\) or \(6n – 1\) except the prime numbers 2 and 3, where \(n\) is a natural number.
- 2 and 3 are only two consecutive natural numbers that are prime.
- **Goldbach Conjecture**: Every even integer greater than 2 can be expressed as the sum of two primes.
- **Wilson Theorem**: Wilson’s theorem states that a natural number \(p > 1\) is a prime number if and only if
    \((p - 1) ! ≡  -1\)   mod \(p\) 
    OR  \((p - 1) ! ≡  (p-1)\) mod \(p\)
- **Fermat’s Little Theorem**: If \(n\) is a prime number, then for every \(a\), \(1 <= a < n\),
	\(a^{n-1} ≡ 1 \mod n\)
		OR 
	\(a^{n-1} \mod n = 1\)
- **Prime Number Theorem**: The probability that a given, randomly chosen number \(n\) is prime is inversely proportional to its number of digits, or to the logarithm of \(n\).
- **Lemoine’s Conjecture**: Any odd integer greater than 5 can be expressed as a sum of an odd prime (all primes other than 2 are odd) and an even semiprime. A semiprime number is a product of two prime numbers. This is called Lemoine’s conjecture.

### Properties of prime numbers:

- Every number greater than 1 can be divided by at least one prime number.
- Every even positive integer greater than 2 can be expressed as the sum of two primes.
- Except 2, all other prime numbers are odd. In other words, we can say that 2 is the only even prime number.
- Two prime numbers are always coprime to each other.
- Each composite number can be factored into prime factors and individually all of these are unique in nature.

### Prime numbers and co-prime numbers:

It is important to distinguish between prime numbers and co-prime numbers. Listed below are the differences between prime and co-prime numbers.

- A coprime number is always considered as a pair, whereas a prime number is considered as a single number.
- Co-prime numbers are numbers that have no common factor except 1. In contrast, prime numbers do not have such a condition.
- A co-prime number can be either prime or composite, but its greatest common factor (GCF) must always be 1. Unlike composite numbers, prime numbers have only two factors, 1 and the number itself.
- Example of co-prime: 13 and 15 are co-primes. The factors of 13 are 1 and 13 and the factors of 15 are 1, 3 and 5. We can see that they have only 1 as their common factor, therefore, they are coprime numbers.
- Example of prime: A few examples of prime numbers are 2, 3, 5, 7 and 11 etc.

## How do we check whether a number is Prime or not?

### Naive Approach:

A naive solution is to iterate through all numbers from 2 to sqrt(n) and for every number check if it divides n. If we find any number that divides, we return false.

Below is the implementation:

```javascript
/**
 * Function to check whether a number is prime or not
 * @param {number} n - The number to check
 * @returns {boolean} - true if prime, false otherwise
 */
function isPrime(n) {
    // Corner case
    if (n <= 1)
        return false;

    // Check from 2 to square root of n
    for (let i = 2; i <= Math.sqrt(n); i++)
        if (n % i === 0)
            return false;

    return true;
}

// Example usage
console.log(isPrime(11)); // Output: true
```

### Output

```
true
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary space:** \( O(1) \)

### Efficient Approach:

To check whether the number is prime or not follow the below idea:

In the previous approach given if the size of the given number is too large then its square root will be also very large, so to deal with large size input we will deal with a few numbers such as 1, 2, 3, and the numbers which are divisible by 2 and 3 in separate cases and for remaining numbers, we will iterate our loop from 5 to sqrt(n) and check for each iteration whether that (iteration) or (that iteration + 2) divides n or not. If we find any number that divides, we return false.

Below is the implementation for the above idea:

```javascript
/**
 * Function to check whether a number is prime or not
 * @param {number} n - The number to check
 * @returns {boolean} - true if prime, false otherwise
 */
function isPrime(n) {
    // Check if n=1 or n=0
    if (n <= 1)
        return false;
    // Check if n=2 or n=3
    if (n === 2 || n === 3)
        return true;
    // Check whether n is divisible by 2 or 3
    if (n % 2 === 0 || n % 3 === 0)
        return false;
    // Check from 5 to square root of n
    // Iterate i by (i+6)
    for (let i = 5; i <= Math.sqrt(n); i = i + 6)
        if (n % i === 0 || n % (i + 2) === 0)
            return false;

    return true;
}

// Example usage
console.log(isPrime(11)); // Output: true
```

### Output

```
true
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary space:** \( O(1) \)




**Time Complexity:** \( O(\log(\min(a, b))) \)  
**Auxiliary Space:** \( O(\log(\min(a, b))) \)



## Prime Factors

Prime factor is the factor of the given number which is a prime number. Factors are the numbers you multiply together to get another number. In simple words, prime factor is finding which prime numbers multiply together to make the original number.

Example: The prime factors of 15 are 3 and 5 (because 3×5=15, and 3 and 5 are prime numbers). 

### Some interesting fact about Prime Factor : 

- There is only one (unique!) set of prime factors for any number.
- In order to maintain this property of unique prime factorizations, it is necessary that the number one, 1, be categorized as neither prime nor composite.
- Prime factorizations can help us with divisibility, simplifying fractions, and finding common denominators for fractions.
- Pollard’s Rho is a prime factorization algorithm, particularly fast for a large composite number with small prime factors.
- Cryptography is the study of secret codes. Prime Factorization is very important to people who try to make (or break) secret codes based on numbers.

### How to print a prime factor of a number?

#### Naive solution: 

Given a number \( n \), write a function to print all prime factors of \( n \). For example, if the input number is 12, then output should be “2 2 3” and if the input number is 315, then output should be “3 3 5 7”.

Following are the steps to find all prime factors: 

1. While \( n \) is divisible by 2, print 2 and divide \( n \) by 2.
2. After step 1, \( n \) must be odd. Now start a loop from \( i = 3 \) to square root of \( n \). While \( i \) divides \( n \), print \( i \) and divide \( n \) by \( i \), increment \( i \) by 2 and continue.
3. If \( n \) is a prime number and is greater than 2, then \( n \) will not become 1 by above two steps. So print \( n \) if it is greater than 2.

```javascript
/**
 * Function to print all prime factors of a given number
 * @param {number} n - The number
 */
function primeFactors(n) {
    // Print the number of 2s that divide n
    while (n % 2 === 0) {
        console.log(2);
        n = n / 2;
    }

    // n must be odd at this point. So we can skip
    // one element (Note i = i +2)
    for (let i = 3; i <= Math.sqrt(n); i = i + 2) {
        // While i divides n, print i and divide n
        while (n % i === 0) {
            console.log(i);
            n = n / i;
        }
    }

    // This condition is to handle the case when n
    // is a prime number greater than 2
    if (n > 2)
        console.log(n);
}

// Example usage
const n = 315;
primeFactors(n);
```

#### Output: 

```
3
3
5
7
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary Space:** \( O(1) \)

#### More efficient solution:

```javascript
/**
 * Function to print all prime factors of a given number
 * @param {number} n - The number
 */
function printPrimeFactors(n) {
    if (n <= 1)
        return;

    while (n % 2 === 0) {
        console.log(2);
        n = n / 2;
    }

    while (n % 3 === 0) {
        console.log(3);
        n = n / 3;
    }

    for (let i = 5; i * i <= n; i = i + 6) {
        while (n % i === 0) {
            console.log(i);
            n = n / i;
        }

        while (n % (i + 2) === 0) {
            console.log(i + 2);
            n = n / (i + 2);
        }
    }

    if (n > 3)
        console.log(n);
}

// Example usage
const num = 315;
printPrimeFactors(num);
```

#### Output: 

```
3
3
5
7
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary Space:** \( O(1) \)

## All Divisors of a Number

Given a natural number \( n \), print all distinct divisors of it.

### All divisors of a natural number

Examples:

- Input : \( n = 10 \)       
  Output: 1 2 5 10

- Input:  \( n = 100 \)
  Output: 1 2 4 5 10 20 25 50 100

- Input:  \( n = 125 \)
  Output: 1 5 25 125

### A Naive Solution

A Naive Solution would be to iterate all the numbers from 1 to \( n \), checking if that number divides \( n \) and printing it. Below is a program for the same:

```javascript
/**
 * Function to print all divisors of a given number
 * @param {number} n - The number
 */
function printDivisors(n) {
    for (let i = 1; i <= n; i++) {
        if (n % i === 0) {
            console.log(i);
        }
    }
}

// Example usage
console.log("The divisors of 100 are:");
printDivisors(100);
```

#### Output:

```
1
2
4
5
10
20
25
50
100
```

**Time Complexity:** \( O(n) \)  
**Auxiliary Space:** \( O(1) \)

### A Better Solution

If we look carefully, all the divisors are present in pairs. For example if \( n = 100 \), then the various pairs of divisors are: (1,100), (2,50), (4,25), (5,20), (10,10). Using this fact we could speed up our program significantly. We, however, have to be careful if there are two equal divisors as in the case of (10, 10). In such case, we’d print only one of them.

Below is an implementation for the same:

```javascript
/**
 * Function to print all divisors of a given number
 * @param {number} n - The number
 */
function printDivisors(n) {
    // Note that this loop runs till square root
    for (let i = 1; i <= Math.sqrt(n); i++) {
        if (n % i === 0) {
            // If divisors are equal, print only one
            if (n / i === i) {
                console.log(i);
            } else { // Otherwise print both
                console.log(i);
                console.log(n / i);
            }
        }
    }
}

// Example usage
console.log("The divisors of 100 are:");
printDivisors(100);
```

#### Output:

```
1
100
2
50
4
25
5
20
10
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary Space:** \( O(1) \)

### Printing all the divisors in sorted order

```javascript
/**
 * Function to print all divisors of a given number in sorted order
 * @param {number} n - The number
 */
function printDivisorsSorted(n) {
    let i;
    for (i = 1; i * i < n; i++) {
        if (n % i === 0) {
            console.log(i);
        }
    }
    if (i - (n / i) === 1) {
        i--;
    }
    for (; i >= 1; i--) {
        if (n % i === 0) {
            console.log(n / i);
        }
    }
}

// Example usage
console.log("The divisors of 100 in sorted order are:");
printDivisorsSorted(100);
```

#### Output:

```
1
2
4
5
10
20
25
50
100
```

**Time Complexity:** \( O(\sqrt{n}) \)  
**Auxiliary Space:** \( O(1) \)




# Sieve of Eratosthenes

Given a number \( n \), print all primes smaller than or equal to \( n \). It is also given that \( n \) is a small number.

## Example

- **Input:** \( n = 10 \)
  **Output:** 2 3 5 7

- **Input:** \( n = 20 \)
  **Output:** 2 3 5 7 11 13 17 19

The sieve of Eratosthenes is one of the most efficient ways to find all primes smaller than \( n \) when \( n \) is smaller than 10 million or so.

## Algorithm

When the algorithm terminates, all the numbers in the list that are not marked are prime.

### Explanation with Example

Let us take an example when \( n = 50 \). So we need to print all prime numbers smaller than or equal to 50.

1. We create a list of all numbers from 2 to 50.

2. According to the algorithm we will mark all the numbers which are divisible by 2 and are greater than or equal to the square of it.

3. Now we move to our next unmarked number 3 and mark all the numbers which are multiples of 3 and are greater than or equal to the square of it.

4. We move to our next unmarked number 5 and mark all multiples of 5 and are greater than or equal to the square of it.

5. We continue this process and our final table will look like below.

So the prime numbers are the unmarked ones: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47.

## Implementation

```javascript
/**
 * Function to print all primes smaller than or equal to n using Sieve of Eratosthenes
 * @param {number} n - The upper limit
 */
function SieveOfEratosthenes(n) {
    // Create a boolean array "prime[0..n]" and initialize
    // all entries it as true. A value in prime[i] will
    // finally be false if i is Not a prime, else true.
    let prime = new Array(n + 1).fill(true);

    for (let p = 2; p * p <= n; p++) {
        // If prime[p] is not changed, then it is a prime
        if (prime[p] === true) {
            // Update all multiples of p greater than or equal to the square of it
            // numbers which are multiple of p and are less than p^2 are already been marked.
            for (let i = p * p; i <= n; i += p) {
                prime[i] = false;
            }
        }
    }

    // Print all prime numbers
    for (let p = 2; p <= n; p++) {
        if (prime[p]) {
            console.log(p);
        }
    }
}

// Example usage
const n = 30;
console.log("Following are the prime numbers smaller than or equal to " + n);
SieveOfEratosthenes(n);
```

**Output:**

Following are the prime numbers smaller than or equal to 30  
2  
3  
5  
7  
11  
13  
17  
19  
23  
29  

**Time Complexity:** \( O(n \cdot \log(\log(n))) \)  
**Auxiliary Space:** \( O(n) \)


## Computing Power: Explained and Implemented

### Naive Approach

Calculating \(x^n\) using a straightforward approach involves multiplying \(x\) by itself exactly \(n\) times. This method, implemented through a simple loop, iterates \(n\) times and accumulates the result.

```javascript
/**
 * Naive iterative solution to calculate power(x, n)
 * @param {number} x - Base number
 * @param {number} n - Exponent
 * @returns {number} - Result of x^n
 */
function power(x, n) {
    let pow = 1;
    for (let i = 0; i < n; i++) {
        pow *= x;
    }
    return pow;
}

// Example usage:
const x = 2;
const n = 3;
console.log(power(x, n)); // Output: 8
```

This method exhibits a time complexity of \(O(n)\) and requires \(O(1)\) auxiliary space.

### Optimized Divide and Conquer Solution

A more efficient approach leverages a divide-and-conquer strategy. The problem of computing \(x^n\) can be recursively defined, reducing the computational load.

#### Recurrence Relation:

- For even \(n\), \(x^n = (x^{n/2}) \times (x^{n/2})\)
- For odd \(n\), \(x^n = x \times (x^{(n-1)/2}) \times (x^{(n-1)/2})\)

However, the initial implementation recalculates the same subproblem for each recursive call, leading to inefficiency. To mitigate this, we optimize the algorithm by computing the solution of the subproblem only once.

```javascript
/**
 * Function to calculate x raised to the power y
 * @param {number} x - Base number
 * @param {number} y - Exponent
 * @returns {number} - Result of x^y
 */
function power(x, y) {
    if (y === 0) return 1;
    const temp = power(x, Math.floor(y / 2));
    if (y % 2 === 0) return temp * temp;
    else return x * temp * temp;
}

// Example usage:
const x = 2;
const y = 3;
console.log(power(x, y)); // Output: 8
```

This optimized approach significantly reduces the time complexity to \(O(\log n)\) while maintaining \(O(\log n)\) auxiliary space for the recursive call stack.



# Modular Arithmetic

Modular arithmetic, an essential branch of mathematics, revolves around the "mod" operation. Essentially, it deals with computations involving the remainder of expressions. These expressions can consist of digits and various computational symbols such as addition, subtraction, multiplication, and division. Here, we will delve into various operations within modular arithmetic.

## Quotient Remainder Theorem

The Quotient Remainder Theorem states that for any pair of integers **a** and **b** (where **b** is positive), there exist two unique integers **q** and **r** such that:

\[ a = b \times q + r \quad \text{where} \quad 0 \leq r < b \]

### Example:

If **a** = 20 and **b** = 6, then **q** = 3, **r** = 2, yielding \( 20 = 6 \times 3 + 2 \).

## Modular Addition

The rule for modular addition is given as:

\[ (a + b) \mod m = ((a \mod m) + (b \mod m)) \mod m \]

### Example:

\[ (15 + 17) \% 7 = ((15 \% 7) + (17 \% 7)) \% 7 = (1 + 3) \% 7 = 4 \% 7 = 4 \]

The same rule applies to modular subtraction.

## Modular Multiplication

The rule for modular multiplication is expressed as:

\[ (a \times b) \mod m = ((a \mod m) \times (b \mod m)) \mod m \]

### Example:

\[ (12 \times 13) \% 5 = ((12 \% 5) \times (13 \% 5)) \% 5 = (2 \times 3) \% 5 = 6 \% 5 = 1 \]

## Modular Division

Modular division operates differently from addition, subtraction, and multiplication. It may not always be feasible. The formula for modular division is as follows:

\[ (a / b) \mod m = (a \times (\text{inverse of } b \text{ if exists})) \mod m \]

## Modular Inverse

The modular inverse of \( a \mod m \) exists only if **a** and **m** are relatively prime (i.e., \( \text{gcd}(a, m) = 1 \)). If \( (a \times b) \mod m = 1 \), then **b** is the modular inverse of **a**.

### Example:

For \( a = 5 \) and \( m = 7 \), \( (5 \times 3) \% 7 = 1 \), thus 3 is the modular inverse of 5 under 7.

## Modular Exponentiation

Modular exponentiation involves finding \( a^b \mod m \). Two approaches for this are recursive and iterative.

### Example:

For \( a = 5 \), \( b = 2 \), and \( m = 7 \), \( (5^2) \% 7 = 25 \% 7 = 4 \)

Efficient calculation of \( x^n \mod m \) can be achieved in \( O(\log n) \) time using recursion. It's crucial to calculate \( x^{n/2} \) only once for even **n** to maintain \( O(\log n) \) time complexity.

The following function calculates \( x^n \mod m \):

```cpp
int modpower(int x, int n, int m) {
   if (n == 0) 
       return 1 % m;
   long long u = modpower(x, n / 2, m);                                              
   u = (u * u) % m;
   if (n % 2 == 1) 
       u = (u * x) % m;
   return u;
}
```

Time Complexity: \( O(\log n) \), because **n** is halved whenever it's even.

Fermat’s theorem states that \( x^{m−1} \mod m = 1 \) when **m** is prime and **x** and **m** are coprime. This also implies \( x^k \mod m = x^{k \mod (m−1)} \mod m \).



# Iterative Power

Given an integer `x` and a positive number `y`, write a function that computes `x^y` under the following conditions.
- Time complexity of the function should be `O(log y)`.
- Extra Space is `O(1)`.

## Examples:

- Input: `x = 3`, `y = 5`
  Output: `243`

- Input: `x = 2`, `y = 5`
  Output: `32`

The recursive solutions are generally not preferred as they require space on call stack and they involve function call overhead.

Following is the implementation to compute `x^y`.

## Implementation:

```cpp
// Iterative C program to implement pow(x, n)
#include <iostream>
using namespace std;

/* Iterative Function to calculate (x^y) in O(log y) */
int power(int x, unsigned int y)
{
    int res = 1; // Initialize result

    while (y > 0) {
        // If y is odd, multiply x with result
        if (y & 1)
            res = res * x;

        // y must be even now
        y = y >> 1; // y = y/2
        x = x * x; // Change x to x^2
    }
    return res;
}

// Driver program to test above functions
int main()
{
    int x = 3;
    unsigned int y = 5;

    cout<<"Power is "<<power(x, y);

    return 0;
}
```

## Output:

```
Power is 243
```

## Complexity Analysis:

- **Time Complexity:** `O(log y)`, since in the loop, each time the value of `y` decreases by half its current value.
- **Auxiliary Space:** `O(1)`, since no extra space has been taken.
