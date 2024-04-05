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

- **Class**: User-defined blueprint from which objects are created. It consists of methods or sets of instructions that are to be performed on the objects.
- **Structure**: A structure is basically a user-defined collection of variables of different data types.

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


