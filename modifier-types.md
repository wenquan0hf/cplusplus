# 修饰符的类型 

C++ 允许 **char**、**int** 和 **double** 类型的数据可以在其前面使用修饰符。修饰符用于更改数据变量的意义以实现变量可以更加精准的运用到其所应用的环境中。  

数据类型的修饰符如下：

1. signed：有符号类型
2. unsigned：无符号类型
3. long：长整型
4. short：短整型

**signed**、**unsigned**、**long** 和 **short** 可以应用到整型基础类型。此外，**signed** 和 **unsigned** 可以应用到char类型，**long** 可以应用到 double 类型。  

**signed** 和 **unsigned** 也可以作为**long** 或 **short** 修饰符的前缀。比如，**unsigned long int**.   

C++ 也允许使用简化字符的方式来声明 **unsigned**、**short** 或 **long** 整数。程序员可以仅使用**unsigned**、**short** 或 **long** 而不使用 int 来定义整型变量。这里的 int 就被简化掉了。比如，下面的两句程序均实现对unsigned整型变量的声明的功能。

```
    unsigned x;
    unsigned int y;
```

为了理解 C++ 中 signed 和 unsigned 整数修饰符的不同。可以尝试着运行下面的程序：

```
    #include <iostream>
    using namespace std;
     
    /* This program shows the difference between
     * signed and unsigned integers.
    */
    int main()
    {
       short int i;   // a signed short integer
       short unsigned int j;  // an unsigned short integer
    
       j = 50000;
    
       i = j;
       cout << i << " " << j;
    
       return 0;
    }
```

上述程序执行结果如下：

```
    -15536 50000
```

上述结果的背后原因是，unsigned 短整型变量的值为5000，当时short类型时，就是-15536了。这和值表示范围有关系。

## C++ 中的类型限定符 

类型限定符提供了关于变量保存值更丰富的信息:

<table>
<tbody>
<tr>
<th width="90">限定符</th>
<th>意义</th>
</tr>
<tr>
<td>const</td> <td> <b>const</B> 类型修饰的对象在起运行周期内不可被改变</td> 
</tr>
</tr>
<tr>
<td>volatile</td> <td><b>volatile</b>修饰符用于提示编译器，程序中某个变量值的改变可能不是程序显式修改的</td> 
</tr>
</tr>
<tr>
<td>restrict</td> <td><b>restrict</b>限定符修饰的指针意味着所有修改该指针所指向内容的操作全部都是基于该指针的。仅在C99标准中增加了这个修饰符。</td> 
</tr>
</tbody>
</table> 
