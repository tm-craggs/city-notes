
**About C++**
- Functions can exist outside the scope of classes, unlike Java
- `<iostream>` is one of the most common system headers
- g++ compiler
- For loops are the same as Java
- To reference a `#include` system header, call it and use a double colon. E.g. `std::cout<<"Hello World"`. This is called a scope resolution. 
- This references the standard name space, and calls the `cout` function. 
- To avoid typing the scope resolution over and over, define it as a namespace at the start of your file. 

```c++
using namespace std

int main(){
	cout << "Hello World";
}

```

- Every function must have a return value. Most functions are defined with an integer return value. Returning 0 means success. 

