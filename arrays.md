# 数组

C++ 提供了一种数据结构，**数组**，它存储了一个固定大小的相同类型的有序集合的元素。一个数组通常被用来存储大量的数据，但往往将数组看作是一个相同类型的变量的集合更有用。  

不是声明单独的变量，例如数字 0，数字  1,...,和数字 99，你可以声明一个数组变量，例如numbers,并且使用 number[0]，number[1] 和 ...,number[99] 来表示单个变量。数组中的特定元素是通过索引访问的。  

所有的数组组成连续的内存位置。最低地址对应于第一个元素，最高地址对应最后一个元素。  

## 声明数组

要在 C++ 中声明一个数组，程序员需要指定元素的类型和一个数组需要的元素的数目，如下所示：  

```
    type arrayName [ arraySize ];
```

这就是所谓的一维数组。其中 **arraySize** 必须是一个大于零的整数常量，而且 **type** 可以是任何有效的 C++ 数据类型。例如，若要声称一个 double 类型的 10 元素的 balance 数组，需要使用如下语句。  

```
    double balance[10];
```

## 初始化数组

你可以一个接着一个或者是使用一个单独的语句来初始化一个 C++ 数组，如下所示：  

```
    double balance[5] = {1000.0, 2.0, 3.4, 17.0, 50.0};
```

大括号 { } 之间的值的数量不能比我们为数组声明时的方括号 [ ] 中的数目大。以下是一个指定数组单个元素的例子。  

如果你省略了数组的大小，我们将创建一个足够容纳初始化的一个数组。因此，如果你写了如下代码：  
    
```
    double balance[] = {1000.0, 2.0, 3.4, 17.0, 50.0};
```

就像之前的示例一样，你将创建一个完全相同的数组。  
    
```
    balance[4] = 50.0;
```

上面的语句将数组中的第五个元素定义为 50.0，第四个数组索引即第五个元素，即最后一个元素，因为所有的数组都使用 0 作为它们第一个元素的索引，称为基索引，下面是我们之前讨论的同一个数组的图案表示：  

![](images/array_presentation.jpg)

## 访问数组元素

一个元素通过索引数组名称被访问。这是通过将元素的索引放置在数组名字后面的方括号中来完成的，举例：  

```
    double salary = balance[9];
```

上面的语句将第 10 个元素从数组中取出来，并将该值赋给 salary 变量。以下是一个例子，即使用所有上述提到的三个概念，即声明，初始化和访问数组：  

```
    #include <iostream>
    using namespace std;
     
    #include <iomanip>
    using std::setw;
     
    int main ()
    {
       int n[ 10 ]; // n is an array of 10 integers
     
       // initialize elements of array n to 0  
       for ( int i = 0; i < 10; i++ )
       {
     		n[ i ] = i + 100; // set element at location i to i + 100
       }
       cout << "Element" << setw( 13 ) << "Value" << endl;
     
       // output each array element's value  
       for ( int j = 0; j < 10; j++ )
       {
      		cout << setw( 7 )<< j << setw( 13 ) << n[ j ] << endl;
       }
     
       return 0;
    }
```

这个程序使用 **setw()** 函数来格式化输出。当上述代码编译执行时，它将生成以下结果：  

```
    ElementValue
      0  100
      1  101
      2  102
      3  103
      4  104
      5  105
      6  106
      7  107
      8  108
      9  109
```

## 详细的 C++ 数组

数组对 C++ 非常重要,而且应该需要大量的详细信息。这里有以下几个 C++ 程序员应该清楚的重要的概念。  

<table border="1">
<tr>
<th>概念</th>
<th> 描述</th>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_multi_dimensional_arrays.htm">多维数组</a></td>
<td>C++ 支持多维数组。多维数组最简单的形式是二维数组。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_to_an_array.htm">指向数组的指针</a></td>
<td>你可以通过简单的指定数组的名字来生成这个数组的第一个元素的指针，并不需要任何索引的。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_passing_arrays_to_functions.htm">将数组传递给函数</a></td>
<td>你可以不使用索引直接通过指定数组的名字将一个指向数组的指针传递给函数。</td>
</tr>
<tr>
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_return_arrays_from_functions.htm">从函数中返回数组</a></td>
<td>C++ 允许函数返回一个数组。</td>
</tr>
</table>             
         
     
        
