# 指针

C++ 指针学起来非常容易和有趣。一些 C++ 的任务用指针执行非常容易，诸如动态分配内存的 C++ 工作，如果没有指针将无法执行。  

如你所知，每个变量是一个内存位置，每个内存位置都有它的地址定义，这个地址定义可以使用表示内存中地址的和运算符 (&) 进行访问。下面我们将打印定义的变量的地址：  

```
    #include <iostream>
    
    using namespace std;
    
    int main ()
    {
       int  var1;
       char var2[10];
    
       cout << "Address of var1 variable: ";
       cout << &var1 << endl;
    
       cout << "Address of var2 variable: ";
       cout << &var2 << endl;
    
       return 0;
    }
```

当上述代码被编译执行时，它将产生如下结果:  

```
    Address of var1 variable: 0xbfebd5c0
    Address of var2 variable: 0xbfebd5b6
```

## 指针是什么？

**指针**是一个变量，它的值是另一个变量的地址。像任何变量或常量一样，你必须在使用它之前声明一个指针。指针变量声明的一般形式为：  

```
    type *var-name;
```

在这里，**type** 是指针的基类型；它必须是一个有效的 C++ 类型，**var-name** 是指针变量的名称。用来声明一个指针的星号与你用于乘法的星号是一样的。然而，在这个语句中，这个星号用来指定一个变量作为一个指针。以下是有效的指针声明：  

```
    int*ip;// pointer to an integer
    double *dp;// pointer to a double
    float  *fp;// pointer to a float
    char   *ch // pointer to character
```

所有指针的值的实际的数据类型，或者是整数，浮点数，字符或者是其他，同样的一个长十六进制数表示一个内存地址。不同的数据类型的指针之间的唯一区别在于指针指向的变量或常量的数据类型。   

## 在 C++ 中使用指针  

这里有几个我们将非常频繁的使用指针的重要的操作。**(a)** 我们定义一个指针变量； **(b)** 将一个变量的地址分配给指针； **(c)** 最后使用在指针变量中的地址来访问这个值。这是通过使用一元运算符 * 完成的，返回位于通过运算符指定地址的变量的值。以下示例使用这些操作：  

```
    #include <iostream>
    
    using namespace std;
    
    int main ()
    {
       int  var = 20;   // actual variable declaration.
       int  *ip;// pointer variable 
    
       ip = &var;   // store address of var in pointer variable
    
       cout << "Value of var variable: ";
       cout << var << endl;
    
       // print the address stored in ip pointer variable
       cout << "Address stored in ip variable: ";
       cout << ip << endl;
    
       // access the value at the address available in pointer
       cout << "Value of *ip variable: ";
       cout << *ip << endl;
    
       return 0;
    }
```
    
当上述代码被编译执行时，它将产生如下结果：  

```
    Value of var variable: 20
    Address stored in ip variable: 0xbfc601ac
    Value of *ip variable: 20
```

## 详细的 C++ 指针

指针有很多但是很容易的概念，它们对 C++ 的编程非常重要。这里有一些 C++ 程序员应该必须清楚的重要的指针概念：

<table border="1">
<tr>
<th>概念</th>
<th>描述</th>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_null_pointers.htm">C++ 空指针</a></td>
<td>C++ 支持空指针，它是在几个标准库中被定义值为零的一个常量。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_arithmatic.htm">C++ 指针算法</a></td>
<td> 这里有四种可用于指针的算术运算符：++,--,+,-</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointers_vs_arrays.htm">C++ 指针与数组</a></td>
<td> 指针与数组之间有着密切的关系。让我们看一看？</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_array_of_pointers.htm">C++ 指针数组</a></td>
<td>你可以定义保存大量指针的数组。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_to_pointer.htm">C++ 指针的指针</a> </td>
<td>C++ 允许您有指针的指针，等等。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_passing_pointers_to_functions.htm">将指针传递给函数</a></td>
<td>通过引用或通过地址传递参数，两种方法都可以使被调用的函数在调用函数中传递的参数发生更改。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_return_pointer_from_functions.htm">从函数返回指针</a></td>
<td>C++ 允许函数返回一个指向本地变量的指针，同样也允许返回指向静态变量和动态分配内存的指针。</td>
</tr>
</table>        
     
    
   
      
