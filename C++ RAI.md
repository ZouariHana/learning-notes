RAII: Resource Acquisistion is initialition
It is used to avoid undefined behavior and double delete/free/ memory leaks. How?
If you have to manage a resource: (allocate and free) creating a class for it will automate the management process. 
Destructor: It is called whenever a an object goes out of scope.
# Rule of Three:
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


