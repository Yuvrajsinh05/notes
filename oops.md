# Interview Questions

## Q1. Why do we use OOPs?

- It gives clarity in programming and allows simplicity in solving complex problems.
- Data and code are bound together by encapsulation.
- Code can be reused, and it reduces redundancy.
- It also helps to hide unnecessary details with the help of Data Abstraction.
- Problems can be divided into subparts.
- It increases the readability, understandability, and maintainability of the code.

## Q2. What are the differences between the constructor and the method?

### Constructor
- It is a block of code that initializes a newly created object.
- It has the same name as the class name.
- It has no return type.
- It is called implicitly at the time of object creation.

### Method
- It is a group of statements that can be called at any point in the program using its name to perform a specific task.
- It should have a different name than the class name.
- It needs a valid return type if it returns a value; otherwise void.
- It is called explicitly by the programmer by making a method call.

## Q3. What are the main features of OOPs?

- Inheritance
- Encapsulation
- Polymorphism
- Data Abstraction

## Q4. The disadvantage of OOPs?

- Requires pre-work and proper planning.
- In certain scenarios, programs can consume a large amount of memory.
- Not suitable for a small problem.
- Proper documentation is required for later use.

## Q5. What is the difference between class and structure?

In C++, both classes and structures serve as blueprints for creating user-defined data types. While they share similarities, they have distinct characteristics that set them apart. Let's delve into these differences more comprehensively.

1. **Class**:
   - **Definition**: A class is a fundamental concept in object-oriented programming (OOP) that encapsulates data for the object and functions to operate on that data.
   - **Access Level**: By default, the members (variables and functions) of a class are private, meaning they can only be accessed within the class. However, you can explicitly specify different access levels like public, protected, or private using access specifiers.
   - **Usage**: Classes are commonly used to model real-world entities with complex behavior and data interactions. They often encapsulate both data and behavior (methods) within a single entity.
   - **Example**:
     ```cpp
     class MyClass {
     private:
         int privateVar;

     public:
         void setPrivateVar(int value) {
             privateVar = value;
         }

         int getPrivateVar() {
             return privateVar;
         }
     };
     ```

2. **Structure**:
   - **Definition**: A structure is a user-defined data type that groups together variables of different data types under a single name. It's similar to a class but with some key differences, notably in the default access level and inheritance behavior.
   - **Access Level**: By default, all members of a structure are public, meaning they can be accessed from outside the structure without any restrictions. However, like classes, you can explicitly specify access levels for members using access specifiers.
   - **Usage**: Structures are often used for simple data representation, such as holding related data items together. They are less focused on encapsulation and behavior and more on organizing data.
   - **Example**:
     ```cpp
     struct MyStruct {
         int publicVar;
     };
     ```

### Key Differences:
- **Default Access Level**: In classes, members are private by default, while in structures, members are public by default.
- **Encapsulation**: Classes emphasize encapsulation, encapsulating data and behavior into a single unit. Structures, on the other hand, typically focus more on data organization without the same level of encapsulation.
- **Inheritance**: In C++, classes support inheritance, allowing one class to inherit properties and behaviors from another. Structures, however, don't support inheritance prior to C++11.
- **Typical Usage**: Classes are commonly used for modeling complex entities with behaviors, while structures are often used for simple data aggregation.

In summary, while both classes and structures serve as user-defined data types in C++, their default access levels and typical usage scenarios differ, making each suitable for distinct programming needs. Understanding these differences is essential for choosing the appropriate construct for designing software systems effectively.

## Q6. What is the difference between a class and an object?

### Class
- Class is the blueprint of an object. It is used to create objects.
- No memory is allocated when a class is declared.
- A class is a group of similar objects.
- Class is a logical entity.
- A class can only be declared once.
- An example of class can be a car.

### Object
- An object is an instance of the class.
- Memory is allocated as soon as an object is created.
- An object is a real-world entity such as a book, car, etc.
- An object is a physical entity.
- Objects can be created many times as per requirement.
- Objects of the class car can be BMW, Mercedes, Ferrari, etc.




## Q7. Does C++ compiler create a default constructor when we write our own?

In C++, the compiler by default creates a default constructor for every class. However, if we define our own constructor, the compiler doesn’t create the default constructor.

## Q8. Explain constructor in C++

A constructor is a special member function automatically called when an object is created. It initializes the class data members, assigning them garbage values if no explicit values are provided.

## Q9 What do you mean by constructor overloading?

Constructor overloading refers to the concept of having more than one constructor with different parameters to perform different tasks.

## Q10 Explain Destructor in C++

A destructor is a special member function that destructs or deletes an object. Unlike constructors, which initialize objects, destructors free resources acquired by the object during its lifetime.

## Q11 What is a copy constructor?

A copy constructor is a special constructor that takes an object as an argument and copies its data members into another object of the same class.

## Q12 How many types of constructors are there?

There are three types of constructors in C++:

1. Default constructor
2. Parameterized constructor
3. Copy constructor

## Q13 When should the destructor use delete to free the memory?

The destructor should use `delete` to free memory in the following cases:

- If the object is created using `new`.
- If the constructor uses `new` to allocate memory from the heap or free store.

## Q14 What is the return type of constructor and destructor?

Constructors and destructors have no return type, not even `void`.



## Q15 What is this pointer?

The `this` pointer is accessible only inside the member functions of a class and points to the object which has called this member function.

## Q16 When is it necessary to use the this pointer?

It is necessary to use the `this` pointer when local variables have the same name as data members' names. Without the `this` pointer, the compiler wouldn’t know whether to refer to the local variable or the object's data member.

## Q17 What is similar between deep copy and shallow copy?

Both deep copy and shallow copy are used to copy data between objects.

## Q18 What is the difference between deep copy and shallow copy?

The difference between deep copy and shallow copy lies in how they handle copying of dynamic memory. 

- Shallow Copy: In shallow copy, only the memory address of the dynamically allocated memory is copied. Both the original object and the copied object will share the same memory, which can lead to issues if one object modifies the shared memory.
  
- Deep Copy: In deep copy, a new memory block is allocated for the copied object, and the contents are copied into this new memory. This ensures that the original and copied objects are entirely independent and modifications to one won’t affect the other.


## Q20. What is the difference between deep copy and shallow copy?

### Shallow Copy
- Shallow Copy stores the references of objects to the original memory address.  
- Shallow Copy reflects changes made to the new/copied object in the original object.
- Shallow Copy stores the copy of the original object and points the references to the objects.
- Shallow copy is faster.

### Deep Copy
- Deep copy stores copies of the object’s value.
- Deep copy doesn’t reflect changes made to the new/copied object in the original object.
- Deep copy stores the copy of the original object and recursively copies the objects as well.
- Deep copy is comparatively slower.



# Pillars of OOPs

## Q21 What is Encapsulation in C++? Why is it called Data hiding?

Encapsulation in C++ refers to the process of binding data and corresponding methods (behavior) into a single unit. In other words, encapsulation is a programming technique that binds the class members (variables and methods) together and prevents them from being accessed by other classes. This technique keeps variables and methods safe from outside interference and misuse.

If a field is declared private in the class, it cannot be accessed by anyone outside the class, thereby hiding the fields. Therefore, encapsulation is also referred to as data hiding.

## Q22 What is the difference between Abstraction and Encapsulation?

### Abstraction
- Abstraction is the method of hiding unnecessary details from the necessary ones.
- Achieved through encapsulation.
- Abstraction allows you to focus on what the object does instead of how it does it.
- In abstraction, problems are solved at the design or interface level.

### Encapsulation
- Encapsulation is the process of binding data members and methods of a program together to perform a specific job without revealing unnecessary details.
- You can implement encapsulation using Access Modifiers (Public, Protected & Private).
- Encapsulation enables you to hide the code and data into a single unit to secure the data from the outside world.
- Problems are solved at the implementation level.

## Q23 How much memory does a class occupy?

Classes do not consume any memory. They are merely blueprints based on which objects are created. When objects are created, they initialize the class members and methods, thereby consuming memory.

## Q24 Are there any limitations of Inheritance?

Yes, there are limitations to inheritance. While it is a powerful feature in Object-Oriented Programming (OOP), it comes with complexities. Inheritance may require more processing time as it navigates through multiple classes for its implementation. Also, the classes involved in inheritance are tightly coupled, meaning changes in one class may necessitate changes in related classes. Incorrect implementation of inheritance can lead to unexpected errors or incorrect outputs.

## Q25 What is the difference between overloading and overriding?

Overloading is a compile-time polymorphism feature where an entity has multiple implementations with the same name, such as Method overloading and Operator overloading.

Overriding is a runtime polymorphism feature where an entity has the same name, but its implementation changes during execution, such as Method overriding.

## Q26 What are the various types of inheritance?

The various types of inheritance include:
- Single inheritance
- Multiple inheritances
- Multi-level inheritance
- Hierarchical inheritance
- Hybrid inheritance

## Q27 What are the advantages of Polymorphism?

There are several advantages of polymorphism in C++:
- Achieving flexibility in code by performing various operations using methods with the same names according to requirements.
- Providing implementation to an abstract base class or an interface.

## Q28 What are the differences between Polymorphism and Inheritance in C++?

- Inheritance represents the parent-child relationship between two classes. Polymorphism takes advantage of this relationship to make the program more dynamic.
- Inheritance facilitates code reusability in child classes by inheriting behavior from the parent class, while polymorphism enables child classes to redefine already defined behavior inside the parent class. Without polymorphism, a child class can’t execute its own behavior.


## Q29. Does every virtual function need to be always overridden?
   - No, It is not always mandatory to redefine a virtual function. It can be used as it is in the base class.

## Q30. What is an abstract class?
   - An abstract class is a class that has at least one pure virtual function in its definition. An abstract class can never be instanced (creating an object). It can only be inherited, and the methods could be overwritten.

## Q31. Can we have a constructor as Virtual?
   - Constructors cannot be virtual because they need to be defined in the class.

## Q32. What is a pure virtual function?
   - A pure virtual function (or abstract function) in C++ is a virtual function for which we don’t have an implementation. We only declare it. A pure virtual function is declared by assigning 0 in the declaration. See the following example.

## Q33. What are the characteristics of Friend Function?
   - A friend function is not in the scope of the class, in which it has been declared as friend.
   - It cannot be called using the object of that class.
   - It can be invoked like a normal function without any object.
   - Unlike member functions, it cannot use the member names directly.
   - It can be declared in public or private parts without affecting its meaning.
   - Usually, it has objects as arguments.

## Q34. What is the output of this program?

```cpp
#include <iostream>
using namespace std;

class Box {
    double width;
public:
    friend void printWidth( Box box );
    void setWidth( double wid );
};

void Box::setWidth( double wid ) {
    width = wid;
}

void printWidth( Box box ) {
    box.width = box.width * 2;
    cout << "Width of box : " << box.width << endl;
}

int main() {
    Box box;
    box.setWidth(10.0);
    printWidth( box );
    return 0;
}
```



## Problem Statement 

### Question : 1 (Complex Number Class)

A `ComplexNumber` class contains two data members: one is the real part (`R`) and the other is imaginary (`I`) (both integers).

Implement the Complex numbers class that contains the following functions:

1. **Constructor**: You need to create the appropriate constructor.
2. **plus**: This function adds two given complex numbers and updates the first complex number.

   e.g., if `C1 = 4 + i5` and `C2 = 3 + i1`, `C1.plus(C2)` results in: `C1 = 7 + i6` and `C2 = 3 + i1`.
   
3. **multiply**: This function multiplies two given complex numbers and updates the first complex number.

   e.g., if `C1 = 4 + i5` and `C2 = 1 + i2`, `C1.multiply(C2)` results in: `C1 = -6 + i13` and `C2 = 1 + i2`.

4. **print**: This function prints the given complex number in the following format: `a + ib`. Note: There is space before and after '+' (plus sign) and no space between 'i' (iota symbol) and `b`.

## Answer

```cpp
#include <iostream>
using namespace std;

class ComplexNumbers {
private:
    int real;
    int imaginary;

public:
    // Constructor
    ComplexNumbers(int r, int i) {
        real = r;
        imaginary = i;
    }

    // Plus method
    void plus(ComplexNumbers &other) {
        real += other.real;
        imaginary += other.imaginary;
    }

    // Multiply method
    void multiply(ComplexNumbers &other) {
        int tempReal = real * other.real - imaginary * other.imaginary;
        imaginary = real * other.imaginary + imaginary * other.real;
        real = tempReal;
    }

    // Print method
    void print() {
        cout << real << " + i" << imaginary << endl;
    }
};

int main() {
    int real1, imaginary1, real2, imaginary2;

    // Input
    cin >> real1 >> imaginary1;
    cin >> real2 >> imaginary2;

    // Create complex numbers
    ComplexNumbers c1(real1, imaginary1);
    ComplexNumbers c2(real2, imaginary2);

    int choice;
    cin >> choice;

    // Perform operation based on choice
    if (choice == 1) {
        c1.plus(c2);
        c1.print();
    } else if (choice == 2) {
        c1.multiply(c2);
        c1.print();
    }

    return 0;
}
```

### Question : 2 (Polynomial Class)

Implement a polynomial class with the following properties and functions:

**Properties**:
1. An integer (let's say `A`) which holds the coefficient and degrees. Use array indices as degree and `A[i]` as the coefficient of the ith degree.
2. An integer holding the total size of array `A`.

**Functions**:
1. **Default constructor**
2. **Copy constructor**
3. **setCoefficient**: This function sets the coefficient for a particular degree value. If the given degree is greater than the current polynomial capacity, increase the capacity accordingly and set the required coefficient. If the degree is within limits, the previous coefficient value is replaced by the given coefficient value.
4. **Overload "+" operator** (`P3 = P1 + P2`): Adds two polynomials and returns a new polynomial that has the result.
5. **Overload "-" operator** (`P3 = P1 - P2`): Subtracts two polynomials and returns a new polynomial which has the result.
6. **Overload "*" operator** (`P3 = P1 * P2`): Multiplies two polynomials and returns a new polynomial which has the result.
7. **Overload "=" operator (Copy assignment operator)**: Assigns all values of one polynomial to another.
8. **print()**: Prints all the terms (only terms with non-zero coefficients are to be printed) in increasing order of degree. Print pattern for a single term: `<coefficient>"x"<degree>`. Multiple terms should be printed separated by space. After printing one polynomial, print a new line. For more clarity, refer to sample test cases.

## Answer

```cpp
#include<iostream>

using namespace std;

class Polynomial {
public:
    int * degCoeff;
    int capacity;

    Polynomial() {
        degCoeff = new int[10];
        capacity = 10;
        for (int i = 0; i < 10; i++) {
            degCoeff[i] = 0;
        }
    }

    Polynomial(const Polynomial & p) {
        degCoeff = new int[p.capacity];
        for (int i = 0; i < p.capacity; i++) {
            degCoeff[i] = p.degCoeff[i];
        }
        capacity = p.capacity;
    }

    void operator=(Polynomial const & p) {
        delete[] degCoeff;
        degCoeff = new int[p.capacity];
        for (int i = 0; i < p.capacity; i++) {
            degCoeff[i] = p.degCoeff[i];
        }
        capacity = p.capacity;
    }

    void setCoefficient(int degree, int coeff) {
        if (degree >= capacity) {
            int size = 2 * capacity;
            while (size <= degree) {
                size *= 2;
            }
            int * newDegCoeff = new int[size];
            for (int i = 0; i < size; i++) {
                newDegCoeff[i] = 0;
            }
            for (int i = 0; i < capacity; i++) {
                newDegCoeff[i] = degCoeff[i];
            }
            capacity = size;
            delete[] degCoeff;
            degCoeff = newDegCoeff;
        }
        degCoeff[degree] = coeff;
    }

    void print() {
        for (int i = 0; i < capacity; i++) {
            if (degCoeff[i] != 0) {
                cout << degCoeff[i] << "x" << i << " ";
            }
        }
        cout << endl;
    }

    Polynomial operator+(Polynomial const & p) {
        Polynomial pNew;
        int i = 0, j = 0;
        while (i < this->capacity && j < p.capacity) {
            int deg = i;
            int coeff = this->degCoeff[i] + p.degCoeff[j];
            pNew.setCoefficient(deg, coeff);
            i++;
            j++;
        }
        while (i < capacity) {
            pNew.setCoefficient(i, degCoeff[i]);
            i++;
        }
        while (j < p.capacity) {
            pNew.setCoefficient(j, p.degCoeff[j]);
            j++;
        }
        return pNew;
    }

    Polynomial operator-(Polynomial p) {
        Polynomial pNew;
        int i = 0, j = 0;
        while (i < this->capacity && j < p.capacity) {
            int deg = i;
            int coeff = this->degCoeff[i] - p.degCoeff[j];
            pNew.setCoefficient(deg, coeff);
            i++;
            j++;
        }
        while (i < capacity) {
            pNew.setCoefficient(i, degCoeff[i]);
            i++;
        }
        while (j < p.capacity) {
            pNew.setCoefficient(j, (-1 * p.degCoeff[j]));
            j++;
        }
        return pNew;
    }

    int getCoefficient(int degree) {
        if (degree >= capacity) {
            return 0;
        }
        return degCoeff[degree];
    }

    Polynomial operator*(Polynomial p) {
        Polynomial pNew;

        for (int j = 0; j < p.capacity; j++) {
            for (int i = 0; i < capacity; i++) {
                int deg = i + j;
                int coeff = pNew.getCoefficient(deg) + (this->degCoeff[i] * p.degCoeff[j]);
                pNew.setCoefficient(deg, coeff);
            }
        }
        return pNew;
    }
};

int main() {
    int count1, count2, choice;
    cin >> count1;

    int * degree1 = new int[count1];
    int * coeff1 = new int[count1];

    for (int i = 0; i < count1; i++) {
        cin >> degree1[i];
    }

    for (int i = 0; i < count1; i++) {
        cin >> coeff1[i];
    }

    Polynomial first;
    for (int i = 0; i < count1; i++) {
        first.setCoefficient(degree1[i], coeff1[i]);
    }

    cin >> count2;

    int * degree2 = new int[count2];
    int * coeff2 = new int[count2];

    for (int i = 0; i < count2; i++) {
        cin >> degree2[i];
    }

    for (int i = 0; i < count2; i++) {
        cin >> coeff2[i];
    }

    Polynomial second;
    for (int i = 0; i < count2; i++) {
        second.setCoefficient(degree2[i], coeff2[i]);
    }

    cin >> choice;

    Polynomial result;
    switch (choice) {
        // Add
    case 1:
        result = first + second;
        result.print();
        break;
        // Subtract
    case 2:
        result = first - second;
        result.print();
        break;
        // Multiply
    case 3:
        result = first * second;
        result.print();
        break;

    case 4: // Copy constructor
    {
        Polynomial third(first);
        if (third.degCoeff == first.degCoeff) {
            cout << "false" << endl;
        } else {
            cout << "true" << endl;
        }
        break;
    }

    case 5: // Copy assignment operator
    {
        Polynomial fourth(first);
        if (fourth.degCoeff == first.degCoeff) {
            cout << "false" << endl;
        } else {
            cout << "true" << endl;
        }
        break;
    }

    }

    return 0;
}
```

## Question : 3 (Fraction Class)

Implement a Fraction Class with the following properties and functions:

**Properties**:
1. Numerator
2. Denominator

**Functions**:
1. **Parametrized constructor**: Sets the numerator and denominator values.
2. **add**: This function adds the two fractions following the rules of fraction addition and updates the first fractional number.
   - e.g., if `f1 = 1/4` and `f2 = 3/5`, `f1.add(f2)` results in: `f1 = 17/20` and `f2 = 3/5`.
3. **multiply**: This function multiplies the two fractions and updates the first fractional number.
   - e.g., if `f1 = 1/4` and `f2 = 3/5`, `f1.multiply(f2)` results in: `f1 = 3/20` and `f2 = 3/5`.
4. **simplify**: This function simplifies the fractional value using the inbuilt `__gcd()` function.
   - e.g., if `f1 = 5/20`, which can be further simplified as `1/4`, `simplify` will perform this.
5. **print()**: Prints the final answer in the numerator/denominator form.

## Answer

```cpp
#include <iostream>
#include <algorithm>

using namespace std;

class Fraction {
private:
    int numerator;
    int denominator;

    int gcd(int a, int b) {
        if (b == 0)
            return a;
        return gcd(b, a % b);
    }

public:
    // Parametrized constructor
    Fraction(int num = 0, int denom = 1) : numerator(num), denominator(denom) {}

    // Addition
    void add(const Fraction &other) {
        numerator = numerator * other.denominator + other.numerator * denominator;
        denominator *= other.denominator;
        simplify();
    }

    // Multiplication
    void multiply(const Fraction &other) {
        numerator *= other.numerator;
        denominator *= other.denominator;
        simplify();
    }

    // Simplify the fraction
    void simplify() {
        int common = gcd(numerator, denominator);
        numerator /= common;
        denominator /= common;
    }

    // Print the fraction
    void print() const {
        cout << numerator << "/" << denominator << endl;
    }
};

int main() {
    int num, denom, queries;
    cin >> num >> denom >> queries;
    
    Fraction f1(num, denom);

    for (int i = 0; i < queries; ++i) {
        int type, n, d;
        cin >> type >> n >> d;
        Fraction f2(n, d);

        if (type == 1) {
            f1.add(f2);
        } else if (type == 2) {
            f1.multiply(f2);
        }

        f1.print();
    }

    return 0;
}
```


## Question 4 (Print Name and Age)

Create a class named `Person` with a string variable 'name' and an integer variable 'age,' such that these variables are not accessible outside the class and implement a way to initialize the variables and print the variables.

**Functions**:
1. **setValue**: Sets the variables value.
2. **getValue**: Prints the variables value.

## Answer
```cpp
#include <iostream>
using namespace std;

class Person {
private:
    string name;
    int age;

public:
    void setValue(string n, int a) {
        name = n;
        age = a;
    }

    void getValue() {
        cout << "The name of the person is " << name << " and the age is " << age << "." << endl;
    }
};

int main() {
    Person p;
    string name;
    int age;

    // Input name and age
    cin >> name >> age;

    // Set values for name and age
    p.setValue(name, age);

    // Print name and age
    p.getValue();

    return 0;
}
```




## Question 5 ( Area of a Rectangle)

Design a class called `Rectangle`. It contains two data members as length (L) and breadth (B), and a member function `getArea()`. The member function computes the area of the given rectangle and returns it to the caller.

**Note**:
Area of a rectangle = length x breadth

**Data Members**:
1. `length`: Length of the rectangle
2. `breadth`: Breadth of the rectangle 

**Member Functions**:
1. `getArea()`: Calculates the area of the rectangle and returns the value.
## Answer
```cpp
#include <bits/stdc++.h> 

class Rectangle {
public:
    int length;
    int breadth;

    int getArea() {
        int area = length * breadth;
        return area;
    }
};
```




