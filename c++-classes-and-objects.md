## C++ 类和对象
c++编程的主要目的是将面向对象的思想引进到C编程语言中，类是c++的核心特征，用来支持面向对象编程，类通常被称为用户定义的类型。

类是用于指定一个对象的形式，它将数据表示和用于处理数据的方法组合成一个整洁的包。一个类的数据和函数统称为类的成员。

### C++ 类的定义
当你定义了一个类，你就定义一个数据类型的蓝图。这实际上没有定义任何数据，它只是定义了类名是什么意思，也就是意味着，一个类的对象包含什么，在这样一个对象上可以执行哪些操作。

定义一个类，以关键字 **class** 开始，紧随其后的是类名，和类的主体，类的主体由一对大括号封闭。一个类定义必须以分号或者一系类声明结尾。例如，我们通过使用关键字 **class** 定义 Box 数据类型，如下所示：

    class Box
    {
       public:
      double length;   // Length of a box
      double breadth;  // Breadth of a box
      double height;   // Height of a box
    };

关键字 **public** 决定了紧随其后的类的成员的访问属性。一个公共成员可以从类外处于任何一个类对象范围内的地方访问。类对象的范围内的任何地方。您还可以指定一个类的成员为 **private** 或 **public**，我们将在一个小节中讨论它们。

### 定义C++对象

一个类为对象提供了蓝图，对象是由类创建而来。我们声明一个类的对象的方式，用声明其他基本类型变量的方式完全相同。以下语句声明 Box 类的两个对象:

    Box Box1;  // Declare Box1 of type Box
    Box Box2;  // Declare Box2 of type Box

Box1和Box2对象都分别持有其各自的数据副本。

### 访问数据成员:

类的对象的公共数据成员可以使用直接成员访问操作符：(.) 访问。试着执行下面的例子，能更清晰的说明这个问题：

    #include <iostream>
    
    using namespace std;
    
    class Box
    {
       public:
      double length;   // Length of a box
      double breadth;  // Breadth of a box
      double height;   // Height of a box
    };
    
    int main( )
    {
       Box Box1;// Declare Box1 of type Box
       Box Box2;// Declare Box2 of type Box
       double volume = 0.0; // Store the volume of a box here
     
       // box 1 specification
       Box1.height = 5.0; 
       Box1.length = 6.0; 
       Box1.breadth = 7.0;
    
       // box 2 specification
       Box2.height = 10.0;
       Box2.length = 12.0;
       Box2.breadth = 13.0;
       // volume of box 1
       volume = Box1.height * Box1.length * Box1.breadth;
       cout << "Volume of Box1 : " << volume <<endl;
    
       // volume of box 2
       volume = Box2.height * Box2.length * Box2.breadth;
       cout << "Volume of Box2 : " << volume <<endl;
       return 0;
    }

编译和执行上面的代码，执行结果如下：

    Volume of Box1 : 210
    Volume of Box2 : 1560

需要特别加以注意的是，不能使用直接成员访问操作符：(.) 直接访问私有成员和保护成员。我们将在以后学习如何访问私有成员和保护成员。

### 类与对象的细节:

到目前为止，我们已经对c++类和对象有了最基本的了解。还还有更多的与c++类和对象相关的有趣的概念，我们将在下面列出的各个小节中讨论它们：
<table>
<tr>
<th>内容</th>
<th>描述</th>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_class_member_functions.htm" title="C++ 类成员函数">类成员函数</a></td>
<td>类的成员函数是一个函数，像其他变量一样，成员函数在类中有其定义和原型。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_class_access_modifiers.htm" title="C++ Class access modifiers">类的访问修饰符</a></td>
<td>一个类成员可以被定义为公共，私有或保护。默认情况下成员将被假定为私有。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_constructor_destructor.htm" title="C++ Class Constructor and Destructor">构造函数和析构函数</a></td>
<td>一个类的构造函数是一种特殊的函数，在创建一个类的新对象时调用它。析构函数也是一个特殊的函数，当创建对象被删除时调用它。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_copy_constructor.htm" title="C++ Copy Constructor">c++     拷贝构造函数</a></td>
<td>拷贝构造函数是一个构造函数，它创建一个对象并用之前已经创建好的一个同类的对象对其进行初始化。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_friend_functions.htm" title="C++ Friend Functions">c++友函数</a></td>
<td>一个友（<strong>friend</strong>）函数允许完全访问类的私有成员和保护成员。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_inline_functions.htm" title="C++ Inline Functions">C++ 内联函数</a></td>
<td>使用一个内联函数，编译器试图用函数体中的代码替换调用函数的地方的函数名，从而达到消除函数调用时的时间开销的目的。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_this_pointer.htm" title="C++ this Pointer">c++中的 this 指针</a></td>
<td>每个对象都有一个特殊的指针 <strong>this</strong>，它指向对象本身。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_to_class.htm" title="Pointer to C++ classes">指向c++类的指针</a></td>
<td>类指针和一个指向结构的指针是以完全相同的方式实现的。事实上一个类就是一个在其中包含了函数的结构体。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_static_members.htm" title="Static members of a C++ class">类的静态成员</a></td>
<td>类的数据成员和函数成员都可以被声明为静态的。</td>
</tr>
</table>