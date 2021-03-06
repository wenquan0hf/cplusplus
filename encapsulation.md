# 数据封装

所有的 C++ 程序是由以下两个基本要素组成：

- 程序语句(代码)：这是程序执行行为的一部分，他们被称为函数。　　　　
- 程序数据：数据是受程序函数影响的信息。

封装是一个面向对象编程的概念，它将数据和操作数据的函数结合在一起，并使其免受外部干扰和误用。数据封装是**数据隐藏**的重要面向对象编程概念。

数据封装是一种将数据和使用数据的函数结合在一起的机制；数据抽象是一种只将接口公开并且向用户隐藏实现细节的机制。

C++ 支持封装的属性和通过创建用户定义类型实现的数据隐藏，这称为类。我们已经研究过，一个类可以包含私有、保护和公有成员。默认情况下，所有定义在一个类中的成员是私有的。例如：

```
    class Box
    {
       public:
      double getVolume(void)
      {
     return length * breadth * height;
      }
       private:
      double length;  // Length of a box
      double breadth; // Breadth of a box
      double height;  // Height of a box
    };
```

变量 length 、breadth 和 height 都是私有的。这意味着只有 box 类的其他成员可以访问它们，而程序的任何其它的部分不能访问它们。这是一个封装的实现方式。　　　　

要想使类的某个部分成为共有的(即访问您的程序的其他部分)，你必须在 **public** 关键字后声明它们。公有说明符后定义的所有变量或函数可以被程序中的其它函数访问。　　　　

使一个类成为其它类的友元类就可以获得实现细节，降低封装。这个思想就是获得尽可能多的每个类的对其它类隐藏的细节。

## 数据封装的例子

任何一个实现有公有和私有成员的类的 C++ 程序都是一个数据封装和数据抽象的例子。考虑下面的例子：

```
    #include <iostream>
    using namespace std;
    
    class Adder{
       public:
      // constructor
      Adder(int i = 0)
      {
    total = i;
      }
      // interface to outside world
      void addNum(int number)
      {
      total += number;
      }
      // interface to outside world
      int getTotal()
      {
      return total;
      };
       private:
      // hidden data from outside world
      int total;
    };
    int main( )
    {
       Adder a;
       
       a.addNum(10);
       a.addNum(20);
       a.addNum(30);
    
       cout << "Total " << a.getTotal() <<endl;
       return 0;
    }
```

编译和执行上面的代码时，它产生以下结果：

```
    Total 60
```

上面的类实现了把数字加起来，并且返回总和。公有成员 **addNum** 和 **getTotal** 是对外的接口，用户需要知道他们才能使用的类。私有成员 **total** 是用户不需要知道的，但是它是为保证程序正常运行类所必要的。

## 设计策略

经过一段痛苦的经历,我们大多数人已经学会了使类成员在默认情况下是私有的,除非我们真的需要使它们变成公有的。这就是一个好的的封装。　　　　

这个知识被频繁的应用于数据成员,它同样适用于所有成员，包括虚函数。
