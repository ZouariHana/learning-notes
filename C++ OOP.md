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
