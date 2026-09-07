# Struct VS Class

What is the difference between **struct** and **class** ? => The __default visibility level__

* A class has by default **private** members(functions and attributes).
* A struct has by default **public** members.

That is the only difference. You can have **virtual member functions**, you can use **access specifiers**, you can use the keyword **private** in a struct.

A personal preference of the presenter is they use struct when the members are not dependent of each other.

struct Point{
  int x;
  int y;
};

And they use class whenever there is some sort of dependency between the members.

class Date {
  Year mYear{};
  Month mMonth{};
  Day mDay{};

  public:
  Date(Year year, Month month, Day day);
};

# Polymorphism

When the same functions and operators have different behavior depending on context or which object they are used with.

This is achieved through **overloading** and **overriding**.

There are two types of polymorphism: **Compile-time polymorphism** and **Runtime polymorphism**

__**Compile-time polymorphism**__ (static polymorphism, early binding) : 

**Function Overloading**: Same name, different parameters

#include <bits/stdc++.h>
using namespace std;

class Geeks {
public:
    
    // Function to add two integers
    void add(int a, int b) {
        cout << "Integer Sum = " << a + b
        << endl;
    }
    
    // Function to add two floating point values
    void add(double a, double b) {
        cout << "Float Sum = " << a + b
        << endl ;
    }
};

int main() {
    Geeks gfg;
    
    // add() called with int values
    gfg.add(10, 2);

    // add() called with double value
    gfg.add(5.3, 6.2);

    return 0;
}

Output

Integer Sum = 12
Float Sum = 11.5


**Operator Overloading** : 

#include <iostream>
using namespace std;

class Complex {
public:
    int real, imag;
    
    Complex(int r, int i) :
    real(r), imag(i) {}

    // Overloading the '+' operator
    Complex operator+(const Complex& obj) {
        return Complex(real + obj.real, imag + obj.imag);
    }
};

int main() {
    Complex c1(10, 5), c2(2, 4);
    
    // Adding c1 and c2 using + operator
    Complex c3 = c1 + c2;  
    cout << c3.real << " + i" << c3.imag;
    return 0;
}

Output

12 + i9

Explanation: The overloaded + operator adds the real and imaginary parts of two Complex objects. When c1 + c2 is used, the overloaded operator function is called automatically.

# Compile-Time vs. Runtime Polymorphism

The major difference between compile-time and runtime polymorphism is:

| Compile-Time Polymorphism | Runtime Polymorphism |
|---|---|
| Also called **static binding** | Also called **dynamic binding** |
| Achieved using function overloading and operator overloading | Achieved using virtual functions and function overriding |
| The decision is made by the compiler at compile time | The decision is made at runtime using vtables |
| Faster due to early binding | More flexible but slightly slower |

# Polymorphic classes

* 3 keywords to deal with polymorphism in C++: **virtual** , **override**, **final**
  
  **Default parameters**: You want to avoid using default parameters with virtual member functions. https://youtu.be/SuubuqI4gVA?t=2709

  Why? 

  Default arguments are bound at compile time using the static type of the expression (the type of the pointer/reference you wrote the call with).

  Virtual dispatch happens at runtime using the dynamic type of the object (the actual derived class).


# Destructor and polymorphism

  In C++, making a base class destructor virtual ensures that deleting a derived object through a base class pointer safely calls both the derived and base destructors, preventing resource leaks.
  
  [1] (https://www.geeksforgeeks.org/cpp/when-to-use-virtual-destructors-in-cpp/), [2] (https://www.youtube.com/watch?v=05CzXZ9IbC8&t=1)

  **How It Works Without a Virtual Destructor**

  If a base class destructor is not virtual, deleting a derived object via a base class pointer causes undefined behavior.
  
  Only the base class destructor runs. The derived class destructor is skipped, which leaves any memory or resources allocated by the derived class unreleased (memory leak).
  [1] (https://stackoverflow.com/questions/29363817/virtual-destructor-in-polymorphic-classes), [2] (https://www.youtube.com/watch?v=05CzXZ9IbC8&t=1), [3] (https://www.geeksforgeeks.org/cpp/when-to-use-virtual-destructors-in-cpp/)

  **How It Works With a Virtual Destructor**

  Prefacing the base destructor with the virtual keyword enables dynamic binding (runtime polymorphism) for destruction. When you delete the pointer, C++ looks at the actual object type at runtime. It runs the derived class destructor first, and then automatically walks down to run the base class destructor.
