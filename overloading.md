##C++重载(运算符和函数)

C++允许在同一范围内对一个函数名或一个操作符指定多个定义，分别被称为函数重载和操作符重载。

重载声明是在同一的范围内对先前已经声明的相同函数名的声明，除非这两个声明有不同的参数和明显不同的定义（实现方式）。

当你调用一个重载的函数或操作符时，编译器通过比较用来调用函数或操作符的指定的参数类型来确定使用最合适的定义。选择最合适的重载函数或操作符的过程被称为重载决议。

###C++中的函数重载：

你可以在同一范围内对同一函数名有多个定义。函数的定义必须在参数列表中参数类型和/或参数的数量不同于彼此。你不能重载只有返回类型不同的函数声明。

下面是一个相同的函数**print()**函数被用来打印不同的数据类型的例子：

    #include <iostream>
    using namespace std;
     
    class printData 
    {
       public:
      void print(int i) {
    cout << "Printing int: " << i << endl;
      }
    
      void print(double  f) {
    cout << "Printing float: " << f << endl;
      }
    
      void print(char* c) {
    cout << "Printing character: " << c << endl;
      }
    };
    
    int main(void)
    {
       printData pd;
     
       // Call print to print integer
       pd.print(5);
       // Call print to print float
       pd.print(500.263);
       // Call print to print character
       pd.print("Hello C++");
     
       return 0;
    }

上面的代码编译和执行时，它产生以下结果：

    Printing int: 5
    Printing float: 500.263
    Printing character: Hello C++

　
###C++中的运算符重载: 　

你可以重新定义或重载的大部分C++已有的操作符。因此，程序员可以像使用用户自定义类型一样使用操作符。　
　　　

重载操作符是一类函数，它们就是对已有的运算符重新进行定义，赋予其另一种功能，以适应不同的数据类型。像任何其它函数,重载运算符也有返回类型和参数列表。

    Box operator+(const Box&);

声明加法运算符可以用来使两个Box对象相加并返回最终Box对象。大多数重载运算符可以被定义为普通非成员函数或类成员函数。如果我们把上面的函数定义为一个类的非成员函数,那么我们就必须为每个操作数传两个参数如下：

    Box operator+(const Box&, const Box&);

下面是通过使用成员函数来展示运算符重载的概念的示例。这里一个对象作为一个参数被传递，通过访问这个对象可以获得参数的属性，将调用这个操作符的对象可以通过使用**this**操作符获得，下面这个例子展示了这一点：

    #include <iostream>
    using namespace std;
    
    class Box
    {
       public:
    
      double getVolume(void)
      {
     return length * breadth * height;
      }
      void setLength( double len )
      {
      length = len;
      }
    
      void setBreadth( double bre )
      {
      breadth = bre;
      }
    
      void setHeight( double hei )
      {
      height = hei;
      }
      // Overload + operator to add two Box objects.
      Box operator+(const Box& b)
      {
     Box box;
     box.length = this->length + b.length;
     box.breadth = this->breadth + b.breadth;
     box.height = this->height + b.height;
     return box;
      }
       private:
      double length;  // Length of a box
      double breadth; // Breadth of a box
      double height;  // Height of a box
    };
    // Main function for the program
    int main( )
    {
       Box Box1;// Declare Box1 of type Box
       Box Box2;// Declare Box2 of type Box
       Box Box3;// Declare Box3 of type Box
       double volume = 0.0; // Store the volume of a box here
     
       // box 1 specification
       Box1.setLength(6.0); 
       Box1.setBreadth(7.0); 
       Box1.setHeight(5.0);
     
       // box 2 specification
       Box2.setLength(12.0); 
       Box2.setBreadth(13.0); 
       Box2.setHeight(10.0);
     
       // volume of box 1
       volume = Box1.getVolume();
       cout << "Volume of Box1 : " << volume <<endl;
     
       // volume of box 2
       volume = Box2.getVolume();
       cout << "Volume of Box2 : " << volume <<endl;
    
       // Add two object as follows:
       Box3 = Box1 + Box2;
    
       // volume of box 3
       volume = Box3.getVolume();
       cout << "Volume of Box3 : " << volume <<endl;
    
       return 0;
    }

上面的代码编译和执行时，它产生以下结果：

    Volume of Box1 : 210
    Volume of Box2 : 1560
    Volume of Box3 : 5400

###可重载/不可重载的运算符

下面这张表列举了可以重载的运算符：

<table>
  <tr>
    <td>+</td><td>-</td><td>*</td><td>/</td><td>%</td><td>^</td>
  </tr>
  <tr>
    <td>&</td><td>|</td><td>~</td><td>!</td><td>,</td><td>=</td>
  </tr>
  <tr>
    <td><</td><td>></td><td><=</td><td>>=/td><td>++</td><td>--</td>
  </tr>
  <tr>
    <td><<</td><td>>></td><td>==</td><td>!=</td><td>&&</td><td>||</td>
  </tr>
  <tr>
    <td>+=</td><td>-=</td><td>/=</td><td><%=/td><td>^=</td><td>&=</td>
  </tr>
  <tr>
    <td>|=</td><td>*=</td><td><<=</td><td>>>=</td><td>[]</td><td>()</td>
  </tr>
  <tr>
    <td>-></td><td>->*</td><td>new</td><td>new[]</td><td>delete</td><td>delete[]</td>
  </tr>
</table>

下面这张表列举了不可以重载的运算符：
<table>
  <tr>
    <td>::</td><td>.*</td><td>.</td><td>?=</td>
  </tr>
</table>

###运算符重载例子：

这里有各种操作符重载的例子来帮助你理解这一概念。
<table>
  <tr>
     <td>序号</td><td>运算符和例子</td>
  </tr>
  <tr>
     <td>1</td><td><a herf="http://www.tutorialspoint.com/cplusplus/unary_operators_overloading.htm">一元运算符重载</a></td>
  </tr>
  <tr>
     <td>2</td><td><a herf="http://www.tutorialspoint.com/cplusplus/binary_operators_overloading.htm">二元运算符重载</a></td>
  </tr>
  <tr>
     <td>3</td><td><a herf="http://www.tutorialspoint.com/cplusplus/relational_operators_overloading.htm">关系运算符重载</a></td>
  </tr>
  <tr>
     <td>4</td><td><a herf="http://www.tutorialspoint.com/cplusplus/input_output_operators_overloading.htm">输入/输出运算符重载</a></td>
  </tr>
  <tr>
     <td>5</td><td><a herf="http://www.tutorialspoint.com/cplusplus/unary_operators_overloading.htm>++和--运算符重载</a></td>
  </tr>
 <tr>
     <td>6</td><td><a herf="http://www.tutorialspoint.com/cplusplus/assignment_operators_overloading.htm">赋值运算符重载</a></td>
 </tr>
 <tr>
     <td>7</td><td><a herf="http://www.tutorialspoint.com/cplusplus/cpp_overloading.htm">函数call()运算符重载</a></td>
 </tr>
 <tr>
     <td>8</td><td><a herf="http://www.tutorialspoint.com/cplusplus/subscripting_operator_overloading.htm">下标[]运算符重载</a></td>
 <tr>
     <td>9</td><td><a herf="http://www.tutorialspoint.com/cplusplus/class_member_access_operator_overloading.htm">类成员获取运算符(->)重载</a></td>
  </tr>
</table>