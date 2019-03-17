# C++创建类对象方法和动态对象数组

> 最近在学C++，在内存管理这里遇到几个点，记录一下加深记忆。

## 创建类对象的方法

C++中有两种创建对象的方法，一种是直接声明，另一种则是使用`new`关键字，虽然作用相同，但是它们底层的存储方式却完全不同。在此之前，我们先了解一下C++程序的存储形式。  
C++程序的内存格局通常分为四个区：  
**1. data area（全局数据区）**  
**2. code area （代码区）**  
**3. stack area （栈区）**  
**4. heap area （堆区）**

其中，堆区就是“自由存储区”，我们的`new`就是在堆区中申请内存的。回归正题，C++的第一种类对象的创建方法，直接声明：

```C++
#include <iostream>
using namespace std;

class Demo{
public:
    Demo(char* str)
    {
        name = str;
        cout << this->name << " come out"  << endl;
    }
private:
    string name;
};

int main(){
    Demo object1("object1");
}

```

![](.)

这种方法创建时，会在栈区开辟内存空间，这时内存管理由C++自己处理。但是，我们的栈区是有限的，而且一般空间不大，所以**new**就派上用场了！  
一般来说，堆区的空间是足够大的，而在其中申请的内存空间，要由程序员自己管理。也就是说，当我们new一个变量之后，如果之后不用了，就必须手动delete，否则，就会造成内存泄漏。

用new方法创建对象的方法如下：

```c++
int main(){
    //Demo object1("object1"); 
    Demo *object2 = new Demo("object2");
    delete object2;
}

```

![](.)

## 创建动态对象数组

C++中，创建对象数组很简单，方法如下：

```c++
#include <iostream>
using namespace std;

class Demo{
public:
    Demo(){
        cout << "A Demo..." << endl; 
    }
    Demo(char* str)
    {
        name = str;
        cout << this->name << " come out"  << endl; 
    }
private:
    string name;
};

int main(){
    Demo objs[10];
}

```

但是，如果类没有默认构造方法，上面的方法就会报错，面对没有默认构造方法的类的对象数组的构造方法如下：

```c++
#include <iostream>
using namespace std;

class Demo{
public:
    /* Demo(){
        cout << "A Demo..." << endl; 
    } */
    Demo(char* str)
    {
        name = str;
        cout << this->name << " come out"  << endl; 
    }
private:
    string name;
};

int main(){
    // Demo objs[10]; // error;
    Demo *objs = new Demo[10];
    Demo **objs = new Demo *[10];
    for (int i = 0; i < 10; i++)
    {
        objs[i] = new Demo("object");
    }
}

```

