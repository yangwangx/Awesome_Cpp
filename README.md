# Awesome C++
## Reading List

### Books

* [The Definitive C++ Book Guide and List](https://stackoverflow.com/questions/388242/the-definitive-c-book-guide-and-list)   
* [A Tour of C++](https://www.amazon.com/Tour-C-Depth-ebook/dp/B07FW7P3D3/ref=sr_1_1?crid=258SFPMIRD2L9&dchild=1&keywords=tour+of+c%2B%2B+second+edition&qid=1587085685&s=books&sprefix=A+Tour+of+C%2B%2B+second%2Cstripbooks%2C149&sr=1-1)  
* [Inside the C++ Object Model](https://www.amazon.com/Inside-Object-Model-Stanley-Lippman/dp/0201834545/ref=sr_1_1?dchild=1&keywords=Inside+the+C%2B%2B+Object+Model&qid=1587085658&s=books&sr=1-1)   [`中文笔记`](https://www.iteye.com/blog/dsqiu-1669614)   
* [Effective Modern C++](https://www.amazon.com/Effective-Modern-Specific-Ways-Improve/dp/1491903996)  
* [Effective STL](https://www.amazon.com/Effective-STL-Addison-Wesley-Professional-Computing-ebook/dp/B004V4432W/ref=sr_1_1?dchild=1&keywords=Effective+STL&qid=1587086496&s=books&sr=1-1)  

### Google
* [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html) [`中文版`](https://zh-google-styleguide.readthedocs.io/en/latest/)  
* [How To Use gflags](https://gflags.github.io/gflags/)   
* [C++ Tips of the Week](https://abseil.io/tips/)  
* [cpp-project-template](https://code.google.com/archive/p/cpp-project-template/downloads)  

### Links


* [LearnCpp.com](https://www.learncpp.com)   
* [C++ FAQ](https://isocpp.org/wiki/faq)  


## C++ is a compiled language
[<img width="300" src="images/cpp_is_a_compiled_language.jpeg">](https://www.youtube.com/watch?v=SfGuIVzE_Os&t=341s)






## C++ is a statically typed language
* `auto` use `type inference`

## Google C++ Style Guide
[<img width="800" src="images/google_cpp_style_guide.png">](https://google.github.io/styleguide/cppguide.html)

## World map of STL algorithms
[<img width="800" src="images/world_map_of_cpp_STL_algorithms.png">](https://www.fluentcpp.com/getthemap/)

## Self-contained Headers
* In general, every `.cc` file should have an associated `.h` file
* The `.h` files contain the declarations, while the `.cc` files contain the definitions 
* Place the declarations/definitions for `template` and `inline functions` in the same file

* All header files should be self-contained (compile on their own)  
* All header files should have `#define guards` to prevent multiple inclusion  

```cpp
#ifndef FOO_BAR_BAZ_H_  // <PROJECT>_<PATH>_<FILE>_H_
#define FOO_BAR_BAZ_H_
...
#endif  // FOO_BAR_BAZ_H_
```

* `#include` the headers you need; avoid using `forward declarations`  

## Keyword `virtual`

* `virtual` member function is to support polymorphism;  
  - A `class` stores virtual functions in a virtual function table (`vtbl`), if any   
  - Derived classes can inherit, override, and introduce virtual functions    
  - Derived classes must implement the pure virtual functions   
* `virtual inheritance` is to avoid the duplicated base class subobject that occurs with the “dreaded diamond”. 
  - Where in a hierarchy should I use virtual inheritance? 
  - Just below the top of the diamond, not at the join-class.  

## Some Tips

* Read Types Backwards

>> For people having trouble remembering the order in which const keyword is to be used, here's a quick tip. 
You have to read it backward, like the compiler does. For instance : 
>>
>> `const int* A;` // A is a pointer to an int that is constant  
>> `int const* A;` // A is a pointer to a const int   
>> `int* const A;` // A is a const pointer to an int  
>> `const int* const A;` // A is a const pointer to an int that is constant  
>> `T a[n];` // a is an array of n T  
>> `T* a;`   // a is a pointer to a T  
>> `T& a;`   // a is a reference to a T  
>> `T f(A);` // f takes an A, and returns a T  
>> `T* f(const A&);` // f takes an referece to a const A, and returns a pointer to a T  
 
* OO (Polymorphic) vs OB (Nonpolymorphic): Use Pointers/References for Polymorphism        

>> <img width="600" src="images/OO_vs_OB.jpeg">

* `non-static` member function uses `this` pointer; `static` member function is `this`-less  

