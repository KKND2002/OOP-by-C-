Objected Oriented Programming by C++
01)Objectives
•	What is OOP?
•	Structure of C++ program.
•	Data types, Variables, Keywords, Identifiers
•	Operators
•	Control Structures
•	Functions, Inline function, Overloading
•	Concepts:-  Clauses, Objects
•	Constructor, Destructor, types of constructor, Overloading
•	Inheritance(types)
•	Polymerphisms
•	Friend fun, Friend class
•	Pointer, Virtual Function, Virtual classes
•	File Management
•	Exception Handling
•	Templates
•	STL 
02)OOPs Concepts
•	Class
•	Object
•	Abstraction
•	Inheritance
•	Exception
•	Polymerphism


Object-Oriented Programming (OOP) is a programming paradigm that organizes software design around objects and classes. It aims to structure code in a way that is modular, reusable, and easier to maintain. Let's go over the key OOP concepts and provide examples in C++.

1. Class
A class is a blueprint or template for creating objects. It defines the properties (attributes) and methods (functions) that an object of that class will have. A class encapsulates data and the operations that manipulate that data.

Example:

#include <iostream>
using namespace std;

class Car {
public:
    string brand;
    string model;
    int year;

    // Constructor
    Car(string b, string m, int y) {
        brand = b;
        model = m;
        year = y;
    }

    // Method to display car details
    void displayDetails() {
        cout << "Brand: " << brand << endl;
        cout << "Model: " << model << endl;
        cout << "Year: " << year << endl;
    }
};

In this example, Car is a class with attributes like brand, model, and year. The class also has a method displayDetails() to print the car details.

2. Object
An object is an instance of a class. When a class is defined, you can create objects based on that class. Objects hold data and interact with methods defined in the class.

Example:

int main() {
    // Create an object of class Car
    Car car1("Toyota", "Corolla", 2020);
    
    // Access the method to display the car details
    car1.displayDetails();
}
Here, car1 is an object of the class Car. When you create an object, it automatically initializes with the constructor, and you can use the methods to interact with the object's data.

3. Abstraction
Abstraction is the concept of hiding the complex implementation details and exposing only the essential parts to the user. In C++, this can be achieved by using abstract classes or by defining methods that don’t require the user to understand the internal workings.

Abstraction hides unnecessary implementation details and only shows the necessary functionality.

Example:
#include <iostream>
using namespace std;

class Shape {
public:
    // Pure virtual function (abstract method)
    virtual void draw() = 0;  
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing a circle!" << endl;
    }
};

class Square : public Shape {
public:
    void draw() override {
        cout << "Drawing a square!" << endl;
    }
};

int main() {
    Shape* shape1 = new Circle();
    Shape* shape2 = new Square();
    
    shape1->draw();  // Output: Drawing a circle!
    shape2->draw();  // Output: Drawing a square!
    
    delete shape1;
    delete shape2;
}
In this example, Shape is an abstract class with a pure virtual function draw(). Circle and Square implement this function, hiding the internal details of drawing, which is abstracted away from the user.

4. Inheritance
Inheritance allows a class (called a derived class) to inherit attributes and methods from another class (called a base class). This promotes code reuse and establishes a hierarchical relationship between classes.

Example:
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "Animal is eating." << endl;
    }
};

class Dog : public Animal {  // Dog is derived from Animal
public:
    void bark() {
        cout << "Dog is barking." << endl;
    }
};

int main() {
    Dog myDog;
    myDog.eat();  // Inherited from Animal
    myDog.bark(); // Unique to Dog
}
In this example, the Dog class inherits from the Animal class. This means that Dog objects can access the eat() method from the Animal class, promoting code reuse.

5. Exception Handling
Exception handling in C++ is used to handle runtime errors, which allows the program to continue execution even after encountering unexpected issues. The primary keywords are try, catch, and throw.

Example:
#include <iostream>
using namespace std;

void divide(int a, int b) {
    if (b == 0) {
        throw "Error: Division by zero!";
    }
    cout << "Result: " << a / b << endl;
}

int main() {
    try {
        divide(10, 0);  // This will throw an exception
    } catch (const char* msg) {
        cout << msg << endl;  // Handling the exception
    }
}
In this example, the function divide() checks if b is zero before performing division. If b is zero, it throws an exception. The exception is caught in the catch block and the error message is displayed.

6. Polymorphism
Polymorphism means "many forms" and allows objects of different classes to be treated as objects of a common base class. There are two types of polymorphism in C++: compile-time (method overloading) and runtime (method overriding).

Example: Method Overloading (Compile-time Polymorphism)
Method overloading occurs when you define multiple functions with the same name but with different parameters.
#include <iostream>
using namespace std;

class Printer {
public:
    void print(int i) {
        cout << "Printing integer: " << i << endl;
    }

    void print(double d) {
        cout << "Printing double: " << d << endl;
    }

    void print(string s) {
        cout << "Printing string: " << s << endl;
    }
};

int main() {
    Printer p;
    p.print(10);     // Calls print(int)
    p.print(3.14);   // Calls print(double)
    p.print("Hello"); // Calls print(string)
}
Here, the print() method is overloaded with different parameter types. This is an example of compile-time polymorphism.

Example: Method Overriding (Runtime Polymorphism)
Method overriding allows a derived class to provide a specific implementation of a method that is already defined in the base class.
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void sound() {  // Virtual function for runtime polymorphism
        cout << "Animal makes a sound" << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {  // Override the base class method
        cout << "Dog barks" << endl;
    }
};

int main() {
    Animal* animalPtr;
    Dog myDog;
    
    animalPtr = &myDog;
    animalPtr->sound();  // Calls Dog's overridden method
}
In this example, Animal has a sound() method, and the Dog class overrides it. By using a pointer of type Animal, we demonstrate runtime polymorphism as the appropriate sound() method for the object (Dog) is called.

Summary of OOP Concepts:
Class: Blueprint for creating objects (defines properties and methods).
Object: Instance of a class (holds data and interacts with methods).
Abstraction: Hiding complex details and exposing only essential functionality (via abstract classes or interfaces).
Inheritance: A class can inherit attributes and methods from another class, enabling code reuse.
Exception Handling: A mechanism for dealing with runtime errors using try, catch, and throw.
Polymorphism: The ability for different classes to be treated as instances of a common base class, allowing different behaviors for the same method (either at compile time or runtime).
These concepts work together to create modular, maintainable, and reusable code in Object-Oriented Programming.






