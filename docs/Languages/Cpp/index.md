# C++

## Program Compilation

```bash
c++ -o program program.cpp
```

## Class Layout

Example show public and private members and methods of a class.

```cpp
class MyClass {
    public:
        int publicMember;
        void publicMethod();

    private:
        int privateMember;
        void privateMethod();
};
```

## Datatypes

### Strings

```cpp
#include <string>
std::string myString = "Hello, World!";
```

### Structs (Custom Compound Types)

It can be helpful to encapsulate related data into a singular container. Structs are a way to build up a custom compound type. We can build deeply nested structures by including structs within structs which allows us to make complex representations. We add instance variables to a struct to create the custom type. We can instantiate a struct by declaring a variable of that type, and access its members/fields/instance variables using the dot operator.

```cpp
struct Person {
    std::string name;
    int age;
    bool isStudent;
};

Person person1;
person1.name = "John Doe";
person1.age = 25;
person1.isStudent = true;

Person person2 = {"Jane Doe", 23, false}; // Alternative way to initialize

Person person3 = Person(); // Initialize with default values
person3 = {"Alice", 30, true}; // BAD!! This form of initialization only works during declaration unless you add a typecast.
person3 = (Person){"Alice", 30, true}; // GOOD!! This form of initialization works after declaration.
```

We can define member functions for structs which can be invoked using the dot syntax.

```cpp
void Person::sayHello() {
    cout << "Hello";
}

person1.hello();
```

Classes are basically syntactic sugar to wrap up member properties and methods.

## Operators

### Addressing and Reference Operators

```cpp
int x = 5;
int *ptr = &x; // Address of x
int &ref = x; // Reference to x
n
*ptr = 10; // x = 10
ref = 15; // x = 15

std::cout << x << std::endl; // 15
```

### New operator

The new operator is used to allocate memory for a new object. It returns a pointer to the object.

```cpp
class MyClass {
    int value;
public:
    MyClass(int val) : value(val) {}
    int getValue() { return value; }
};

MyClass* obj = new MyClass(10);
std::cout << obj->getValue() << std::endl; // 10
delete obj; // Free memory
```

The `delete` operator must be used when we make allocations with `new`. This is because the memory is not automatically freed when the object goes out of scope. A few different problems may arise when we have not freed the memory.

## Call by Reference and Call by Value (Reference parameters or value parameters)

Logic and data are often encapsulated by function calls. When we make a function
call and pass in params, we are no longer refering to the original values and
are now working with copies of those values.

We have two approaches we can use when working with function calls. We can work
with the value of the passed parameter, or we can use the address of the passed
parameter. If we use the address, then we are able to refer to the location of
the data from any scope and make changes to it.

The below function takes two integers as arguments. When I call `add(i, j)` the values of
i and j are copied into the scope of the function call and we are no longer
working with i and j, but a and b.

```cpp
int i = 1;
int j = 10;

void add(int a, int b) {
    return a + b;
}

add(i, j);
```

Alternatively, if I modify the argument signature of add(). We can specify that
we want to use the addresses of the arguments. The ampersand says, "can you please get me the address of the variable?" and
then in the body of the function, the asterisk operator says, "lets use that address reference to get the actual value at that location".

```cpp
int i = 1;
int j = 10

void add(int &a, int &b) {
    return *a + *b;
}

add(i, j);
```

## Vectors

We can use vectors to create collections of primitives or objects. Generally, the
collection is formed from the same type but you can use polymorphism to store
collections of types inheriting from the same ancestry.

The `apvector` header is needed to be able to make a vector of objects. These classes are
not generally available and are from some advanced placement CS classes. Will need to
find something that is more modern.

```cpp
// not sure but the code to add the vector type to the header
vector<int> numbers(4); // vector with 4 spots
numbers[0] = 123;
numbers[1] = 22;
numbers[2] = 23;
numbers[3] = 69;
vector<int> twos(4, 2); // vector with 4 spots all filled with 2's.

// make a copy
vector<int> copyOfNumbers(numbers);
//or
vector<int> copyOfNumbers2 = numbers;

// make a vector of objects
apvector<Cards> deck(52);
```

We can use `vectorname.size()` to get the count of items in a vector.
We can use `vectorname.pushback(object)` to add a new item of the same type to the vector.

### Objects with vectors

When we create structs or classes, we may use vectors as member properties.

```cpp
struct Citizen {
    vector<int> votes (2)
};
```

## Functions

There are a few different ways of implementing functions that can be helpful to understand the difference about.

### Pure functions

These functions do not modify their arguments, and will alsways return the same thing when given the same arguments.

Pure functions are easier to test because of these deterministic pre-conditions.

### Modifier functions

Typically an argument is passed in by reference so that it can be modified in some way.

### Fill in functions

This a more extensive variation of a modifer function, where an empty object is provided (or the expectation that an existing object will be overwritten), and then that object is prepared/filled in the function.

### Parameter Notes

Something like `const vector<Point>& points` means that the vector is passed by reference, but the function will not modify the vector.

The const keyword is used to indicate that the function will not modify the object, and attempts to will result in a compile time error.

The ampersand is used to pass the object by reference, so that the function can refer to the original object.

## Objects

### Object Initialization

I was generally considering only ever using `MyObj obj = MyObj()` to create my objects, but there are a few different ways to initialize objects. This way is called the `copy initialization` method. `MyObj()` creates a temporary object and then the copy constructor is invoked to create the object from the temporary object.

There are many alternatives to this, and one of them is direct initialization which would be `MyObj obj()`.

## Lambda Functions

Lambda functions are a concise anonymous way to define functions and are used in multiple places as arguments to higher order functions. They are composed of a few pieces.

- The capture clause
  - The capture clause defines what is pulled in from the outside scope. There are few syntatical sugar ways of defining a range of things to pull in.
    - `[&]` - Pull in everything by reference. This is not a pointer though, and is more of an alias to the original object.
    - `[=]` - Pull in everything by value
    - `[x, &y]` - Pull in x by value and y by reference
- The parameter list
  - The parameters are defined in the same way as a normal function.
- The return type (optional)
- The body

```cpp


# To Write
- [x] Structs
- [x] Call by reference, call by value
- [x] Vectors
 - [x] Vectors of objects
 - [x] Objects with vectors
- [x] Classes
- [x] Operators
- [x] Functions (pure, modifier, fill in)(const params)
```
