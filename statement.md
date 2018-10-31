# description: 
 20000 is output.
All sub-objects representing virtual base classes are initialized by the constructor of the most derived class.  If the constructor of the most derived class does not specify a mem-initializer for a virtual base class V, then V's default construtor is called to initialize the virtual base class subobject.
```C++ runnable
#include <iostream>

struct Car
{
  Car() : price(20000) {}
  Car(double b) : price(b*1.1) {}
  double price;
};

struct Toyota : public virtual Car
{
  Toyota(double b) : Car(b) {}
};

struct Prius : public Toyota
{
  Prius(double b) : Toyota(b)  {}
};

int main(int argc, char** argv)
{
  Prius p(30000);

  std::cout << p.price << std::endl;

  return 0;
}
```
