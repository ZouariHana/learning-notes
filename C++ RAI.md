RAII: Resource Acquisistion is initialition
It is used to avoid undefined behavior and double delete/free/ memory leaks. How?
If you have to manage a resource: (allocate and free) creating a class for it will automate the management process. 
Destructor: It is called whenever a an object goes out of scope.
# Rule of Three
If you define a destructor you also should define copy constructor and copy assignment operator.

# Copy constructor and Copy Assignement Operator

If a class uses the implicit ones, it will do a shallow copy. Which means only the address of the resource will be copied and not the resource on the heap.
This might lead to undefined behavior and double deletes when the two copies go out of scope.

If the resource is non-copyable then we use the keyword =delete when declaring these special member functions.
Otherwise we use copy and swap idiom

# Rule of Zero

If a class has members that do resource management for themselves like std::vector and std::string etc .. we just default all the special member functions.
We can use the keyword =default to signal that using the default constructors is a deliberate choice (self-documenting code)
This is mostly the case for business-logic classes.

# Rvalues and Lvalues

**int&** is an lvalue reference to an int.
**int&&** is an rvalue reference to an int.

Lvalue reference parameters cannot bind to rvalues and vice versa.

_Exception:_ const lvalue references can bind to rvalues. 

f(const int&); f(i) //OK; f(42) //Also OK!;

Copy constructors take const lvalue references. 

Move constructors take rvalue references.

Move constructors are cheaper because its just about trasferring ownership not about copying the resource and allocating a new one.

That is why all STL containers are move-enabled.

# Move semantics and Rule Of Five

_Rule of Five:_ If your code manages a resource then you may need to hand-write all **five** special member functions for correctness and performance.
_Note:_ For sole correctness, you just need the Rule of Three. 

# The by-value assignment operator

T& operator=(T other) {  // note: by value, not by reference
    swap(*this, other);  // member or non-member swap
    return *this;
}

This can be enough(instead of seperating copy and move). 
It can serve as **both** copy and move assignment, depending on whether the argument is an lvalue or rvalue.

a = b;           // b is an lvalue

a = std::move(b); // b is an rvalue (xvalue)

a = T{};         // temporary (prvalue)

For an lvalue (b):

    other is copy-constructed from b.

    Then you swap *this with that copy.

    Effect: copy assignment.

For an rvalue (std::move(b) or T{}):

    other is move-constructed (if you have a move constructor; otherwise copy-constructed).

    Then you swap *this with that moved-into other.

    Effect: move assignment (if move construction is available).

# Rule of Four (and a half)
If your code manages a resource then you may need to hand-write all **four** special member functions for correctness and performance.

- A destructor
- A copy constructor
- A move constructor
- A by-value assignment operator

  1/2 : write a nonmember **swap** function and ideally a member version too.
  
  (You cannot use std::swap because it calls the move assignment operator of your class which you chose not to write by following this rule.)
