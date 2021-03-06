# 命名空间

考虑一个情况，在同一个班有两个同名的人，Zara 。每当我们需要区分他们的时候，除了它们的名字我们肯定会使用一些额外的信息，就像如果他们住在不同的区域或他们的母亲或父亲的名字，等等。

同样的情况会出现在你的 C++ 应用程序中。例如，你可能会编写一些代码，有一个名为 xyz() 的函数，在另一个库中也有同样的函数 xyz() 。现在编译器不知道在你的代码中指定的是哪个版本的 xyz() 函数。

**namespace**就是用来克服这个困难的，而且作为附加信息来区分在不同的库中具有相同名称的函数，类、变量等。使用命名空间，你可以定义名字已经定义的上下文。从本质上讲，一个命名空间定义了一个范围。

## 定义命名空间

一个命名空间的定义由关键字 **namespace** 加它的名称组成，如下所示：

```
	namespace namespace_name {
   		// code declarations
	}
```

调用任何函数或变量的命名空间启用版本，前面加上命名空间名字如下：

```
    name::code;  // code could be variable or function.
```

让我们看看命名空间如何限定实体（包括变量和函数）使用范围：

```
    #include <iostream>
    using namespace std;
    
    // first name space
    namespace first_space{
       void func(){
      cout << "Inside first_space" << endl;
       }
    }
    // second name space
    namespace second_space{
       void func(){
      cout << "Inside second_space" << endl;
       }
    }
    int main ()
    {
     
       // Calls function from first name space.
       first_space::func();
       
       // Calls function from second name space.
       second_space::func(); 
    
       return 0;
    }
```

如果我们编译和运行上面的代码，这将产生以下结果：

```
    Inside first_space
    Inside second_space
```

## using 指令

你可以通过使用 **using namespace** 指令来避免在头部添加命名空间。这个指令告诉编译器，随后代码要使用指定命名空间中的名称。因此名称空间隐含下面的代码：

```
    #include <iostream>
    using namespace std;
    
    // first name space
    namespace first_space{
       void func(){
      cout << "Inside first_space" << endl;
       }
    }
    // second name space
    namespace second_space{
       void func(){
      cout << "Inside second_space" << endl;
       }
    }
    using namespace first_space;
    int main ()
    {
     
       // This calls function from first name space.
       func();
       
       return 0;
    }
```

如果我们编译和运行上面的代码，这将产生以下结果：

```
    Inside first_space
```

using 指令也可以用来指一个名称空间中的特定的项目。例如，如果你打算只是用 std 名称空间的一部分cout，你可以进行如下操作：

```
    using std::cout;
```

后续的代码可以调用 cout 而不用在前面加上命名空间名字，但命名空间中的其他项目仍需要作如下说明：

```
    #include <iostream>
    using std::cout;
    
    int main ()
    {
     
       cout << "std::endl is used with std!" << std::endl;
       
       return 0;
    }
```

如果我们编译和运行上面的代码，这将产生以下结果：
   
``` 
    std::endl is used with std!
```

using 指令引入的名字遵循正常的检测规则。这个名字相对于从 **using** 指令的指针到范围的结束是可见的，并且在这个范围中指令可以被找到。定义在外部范围的有相同名字的实体是被隐藏的。

## 不连续的命名空间

一个命名空间可以被分别定义为若干个不同部分，因此命名空间是由这些部分的合集组成。这些被分开定义的命名空间可以分散在多个文件中。一个命名空间的分离的部分可以分散在多个文件。

所以，如果命名空间的一部分需要定义在另一个文件中的名字，仍然必须声明这个名字。定义以下命名空间实现定义一种新的命名空间或添加新的元素到一个现有的命名空间：

```
    namespace namespace_name {
       // code declarations
    }
```

## 嵌套的命名空间

命名空间可以被嵌套，你可以在一个命名空间内定义另一个命名空间，如下：

```
    namespace namespace_name1 {
       // code declarations
       namespace namespace_name2 {
      // code declarations
       }
    }
```

在上面的语句中如果你使用的是 namespace _ name1 ，那么它将使 namespace _ name2 的元素在整个范围内可用，如下：

```
    #include <iostream>
    using namespace std;
    
    // first name space
    namespace first_space{
       void func(){
      cout << "Inside first_space" << endl;
       }
       // second name space
       namespace second_space{
      void func(){
     cout << "Inside second_space" << endl;
      }
       }
    }
    using namespace first_space::second_space;
    int main ()
    {
     
       // This calls function from second name space.
       func();
       
       return 0;
    }
```

如果我们编译和运行上面的代码，这将产生以下结果：

```
    Inside second_space
```
