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
