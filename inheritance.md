# 继承

在面向对象编程中最重要的概念之一就是继承。继承允许我们根据一个类来定义另一个类，这使得创建和维护一个应用程序更加的容易。这也提供了一个重用代码功能和快速实现的机会。

当创建一个类，不是写全新的数据成员和成员函数的时候，程序员可以指定新类，这个类可以继承现有类的成员。这个现有的类称为基类，这个新类称为派生类。

继承的概念其实是一种关系。例如，哺乳动物是动物，狗是哺乳动物，因此狗是动物等等。

## 基类和派生类

一个类可以继承多个类，这就意味着它可以从多个基类中继承数据和函数。为了定义一个派生类，我们可以使用一个类继承列表来指定基类。一个类继承列表指定一个或多个基类，类继承列表形式如下：

```
    class derived-class: access-specifier base-class
```

在这里 access-specifier 是 **public** 、 **protected** 或者 **private** ，base-class 是之前定义的类的名称。如果不使用 access-specifier ，那么在默认情况下它是私有的。

考虑一个基类的 **shape** 和其派生类 **Rectangle** 的继承情况如下：

```
    #include <iostream>
     
    using namespace std;
    
    // Base class
    class Shape 
    {
       public:
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
    
    // Derived class
    class Rectangle: public Shape
    {
       public:
      int getArea()
      { 
     return (width * height); 
      }
    };
    
    int main(void)
    {
       Rectangle Rect;
     
       Rect.setWidth(5);
       Rect.setHeight(7);
    
       // Print the area of the object.
       cout << "Total area: " << Rect.getArea() << endl;
    
       return 0;
    }
```

上面的代码编译和执行时，它产生以下结果：

```
    Total area: 35
```

## 访问控制和继承

一个派生类可以访问所有它的基类的非公有类型的成员。因此不希望被派生类的成员函数访问的基类成员应该在基类中声明为私有类型。

我们可以根据谁能访问它们总结出不同的访问类型，如下表格中所示：

<table>
   <tr>
      <th>访问权限</th>
      <th>public</th>
      <th>protected</th>
      <th>private</th>
   </tr>
   <tr>
      <td>同一个类</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
   </tr>
   <tr>
      <td>派生类</td>
      <td>是</td>
      <td>是</td>
      <td>否</td>
   </tr>
   <tr>
      <td>类外成员</td>
      <td>是</td>
      <td>否</td>
      <td>否</td>
   </tr>
</table>

派生类继承了基类的所有方法，以下情况除外：

- 基类的构造函数、析构函数和拷贝构造函数。　　　　
- 基类的重载操作符。　
- 基类的友元函数。

## 继承方式

当从一个基类派生一个子类的时候,公共基类可以通过 **public** ，**protected** ，或者 **private** 方式被继承。继承方式被 access-specifier 指定，正如上面解释的。

我们几乎不使用**protected**或私有**private** 继承，但**public**继承是常用的。在使用不同类型的继承的时候,应用规则如下：

-  **public** 继承：当从一个公有基类派生一个类的时候，基类的公有成员成为派生类的公有成员；基类的保护成员成为派生类的保护成员。一个基类的私有成员不能被派生类直接访问，但可以通过调用基类的公有和保护成员访问基类的私有成员。
-  **protected** 继承：当从一个受保护的基类派生子类的时候,基类的公有和保护成员成为派生类的保护成员。
-  **private**  继承：当从一个私有的基类派生子类的时候,基类的公有和保护成员成为派生类的私有成员。

## 多继承

一个C++类可以继承多个类的成员，多继承语法如下：

```
    class derived-class: access baseA, access baseB....
```

在这里 access 是 **public** ，**protected** ，或者是 **private** ，并且每一个基类将有一个access类型，他们将由逗号分隔开，如上所示。让我们试试下面的例子：

```
    #include <iostream>
    using namespace std;
    
    // Base class Shape
    class Shape 
    {
       public:
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
    
    // Base class PaintCost
    class PaintCost 
    {
       public:
      int getCost(int area)
      {
     return area * 70;
      }
    };
    
    // Derived class
    class Rectangle: public Shape, public PaintCost
    {
       public:
      int getArea()
      { 
     return (width * height); 
      }
    };
    
    int main(void)
    {
       Rectangle Rect;
       int area;
     
       Rect.setWidth(5);
       Rect.setHeight(7);
    
       area = Rect.getArea();
       
       // Print the area of the object.
       cout << "Total area: " << Rect.getArea() << endl;
    
       // Print the total cost of painting
       cout << "Total paint cost: $" << Rect.getCost(area) << endl;
    
       return 0;
    }
```

上面的代码编译和执行时，它产生以下结果：

```
    Total area: 35
    Total paint cost: $2450
```
