# const after a member function parameter list

A `const` after a member function’s parameter list (e.g. `int get() const;`) means “this function promises not to modify the object it is called on”, not that its arguments are const. 

## What `const` on a member function means

```cpp
class Foo {
public:
    int value() const;      // promise: won't change *this
    void set(int v);        // may change *this
};
```

- Inside `value() const`, the implicit `this` pointer has type `Foo const*`.
- You cannot modify non-`mutable` data members of `Foo` in that function.
- You can call other `const` member functions, but not non-`const` ones.

Example:

```cpp
int Foo::value() const {
    // x = 5;        // ERROR if x is a non-mutable member
    return x;        // OK: reading is allowed
}
```

## How this differs from `const` on parameters

```cpp
void Foo::set(const int v);  // v cannot be modified inside set
int Foo::get() const;        // *this cannot be modified inside get
```

- `const` on a parameter (`const int v`, `const std::string& s`) protects that parameter.
- `const` after the parameter list protects the object (`*this`).

So:

- Use `const` on parameters to say “I won’t change this argument”.
- Use `const` on the member function to say “I won’t change the object’s state”.
