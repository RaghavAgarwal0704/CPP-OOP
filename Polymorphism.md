```cpp
#include<iostream>
using namespace std;

int main(){
    // Polymorphism
    //  - one name and multiple forms
    //  - eg. Function overloading, operator overloading
    //  - eg. Virtual Functions
    /*
    Polymorphism in C++ can be of two types:
    1. Compile time polymorphism
       Compile time polymorphism in C++ is acheived using:
        1.1 - Function overloading
        1.2 - Operator Overloading
    2. Run time polymorphism
       Run time polymorphism in C++ is acheived using:
        2.1 - Virtual functions

        */
    return 0;
}
```
```cpp
#include<iostream>
using namespace std;
class BaseClass{
    public:
        int var_base;
        void display(){
            cout<<"Dispalying Base class variable var_base "<<var_base<<endl;
        }
};

class DerivedClass : public BaseClass{
    public:
            int var_derived;
            void display(){
                cout<<"Dispalying Base class variable var_base "<<var_base<<endl;
                cout<<"Dispalying Derived class variable var_derived "<<var_derived<<endl;
            }
};

int main(){
    BaseClass * base_class_pointer;
    BaseClass obj_base;
    DerivedClass obj_derived;
    base_class_pointer = &obj_derived; // Pointing base class pointer to derived class

    base_class_pointer->var_base = 34;
    // base_class_pointer->var_derived= 134; // Will throw an error
    base_class_pointer->display();

    base_class_pointer->var_base = 3400; 
    base_class_pointer->display();

    DerivedClass * derived_class_pointer;
    derived_class_pointer = &obj_derived;
    derived_class_pointer->var_base = 9448;
    derived_class_pointer->var_derived = 98;
    derived_class_pointer->display();

    return 0;
}
```
````
$g++ -o main *.cpp
$main
Dispalying Base class variable var_base 34
Dispalying Base class variable var_base 3400
Dispalying Base class variable var_base 9448
Dispalying Derived class variable var_derived 98
````
```cpp
#include<iostream>
using namespace std;

class BaseClass{
    public:
        int var_base=1;
        virtual void display(){
            cout<<"1 Dispalying Base class variable var_base "<<var_base<<endl;
        }
};

class DerivedClass : public BaseClass{
    public:
            int var_derived=2;
            void display(){
                cout<<"2 Dispalying Base class variable var_base "<<var_base<<endl;
                cout<<"2 Dispalying Derived class variable var_derived "<<var_derived<<endl;
            }
};
int main(){
    BaseClass * base_class_pointer;
    BaseClass obj_base;
    DerivedClass obj_derived;

    base_class_pointer = &obj_derived;
    base_class_pointer->display();
    return 0;
}
```
