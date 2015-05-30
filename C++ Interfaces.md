## C++的接口 (抽象类)
一个接口描述一个c++类的行为或功能,但是并不需要对这个类进行实现。  

c++接口是通过抽象类来实现的，这些抽象类不应与数据抽象混淆，数据抽象的概念是保证实现细节和相关数据分离。

一个抽象类的声明里至少要有一个函数作为纯虚函数。指定一个纯虚函数通过像下面一样设置“= 0”

    class Box
    { 
       public:
      // pure virtual function
      virtual double getVolume() = 0;
       private:
      double length;  // Length of a box
      double breadth; // Breadth of a box
      double height;  // Height of a box
    };

抽象类 (通常被称为一个ABC) 的目的是提供一个适当的其他类可以继承的基类。抽象类不能实例化对象并且只使用一个接口。试图实例化一个抽象类的对象会导致编译错误。
因此,如果一个抽象类的子类的需要实例化,它必须实现所有的虚函数,这意味着它支持抽象类声明的接口。在派生类中未能覆盖一个纯虚函数,然后试图实例化该类的对象,是一个编译错误。
可用于实例化对象的类被称为具体类。
抽象类样例:
考虑下面的例子,父类为基类提供了一个接口来实现一个函数 getArea():

    #include <iostream>
     
    using namespace std;
     
    // Base class
    class Shape 
    {
    public:
       // pure virtual function providing interface framework.
       virtual int getArea() = 0;
       void setWidth(int w)
       {
      width = w;
       }
       void setHeight(int h)
       {
      height = h;
       }
    protected:
       int width;
       int height;
    };
     
    // Derived classes
    class Rectangle: public Shape
    {
    public:
       int getArea()
       { 
      return (width * height); 
       }
    };
    class Triangle: public Shape
    {
    public:
       int getArea()
       { 
      return (width * height)/2; 
       }
    };
     
    int main(void)
    {
       Rectangle Rect;
       Triangle  Tri;
     
       Rect.setWidth(5);
       Rect.setHeight(7);
       // Print the area of the object.
       cout << "Total Rectangle area: " << Rect.getArea() << endl;
    
       Tri.setWidth(5);
       Tri.setHeight(7);
       // Print the area of the object.
       cout << "Total Triangle area: " << Tri.getArea() << endl; 
    
       return 0;
    }


上面的代码编译和执行时,它产生以下结果:

    Total Rectangle area: 35
    Total Triangle area: 17

### 设计策略:

一个面向对象的系统可能使用一个抽象基类提供一个共同的和适合所有的外部应用程序的标准化接口。然后,通过继承的抽象基类,派生类形成,所有类似的操作。

 功能(即，,公共函数)，即由外部应用程序提供的，是由抽象基类的纯虚函数提供的。那些纯虚函数是由派生类实现的，派生类对应于特定类型的应用程序。
即使在系统已经定义，这种架构还允许添加新的应用程序系统,。
