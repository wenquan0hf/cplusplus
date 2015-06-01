# 循环的类型 

程序员都会遇到需要多次执行同一代码段的情况。一般情况下，代码会顺序执行：函数中的第一句代码首先会被执行，后面的语句依次执行。  

编程语言往往可以提供多种控制结构来实现更复杂的程序执行流程。  

循环语句以执行单个语句或一组语句。下面是大部分编程语言中循环语句的一般模式:

![](http://www.tutorialspoint.com/cplusplus/images/loop_architecture.jpg)


C++ 语言支持下方的循环类型来满足循环的需求。点击链接查看详细情况。

<table border="1">  
<tr>  
<th>循环类型</th>
<th>描述</th>   
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_while_loop.htm">While 循环</a></td>  
<td>当给定条件为true时，执行循环体。在每次执行循环体前都检查条件是否为true。</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_for_loop.htm">for 循环</a></td>  
<td>按照条件执行循环体，可以简化循环体的结构</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_if_else_statement.htm">switch 语句</a></td>  
<td>一个 switch 语句允许一个变量针对多个不同的值分别进行验证是否满足条件。</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_do_while_loop.htm">do…while 循环</a></td>  
<td>与 loop 循环类似，不同的是在循环体后检查条件</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_nested_loops.htm">嵌套循环</a></td>  
<td>可以嵌套 for 或 loop 循环来多次执行循环体</td>  
</tr>  
</table>  

## 循环控制语句 

循环控制语句可以改变原有循环执行顺序。当循环体执行结束后，其范围内定义的对象都会被销毁。

C++ 语言支持下方的循环控制语句。点击链接查看详细情况。

<table border="1">  
<tr>  
<th>循环语句</th>
<th>描述</th>   
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_break_statement.htm">break</a></td>  
<td>终止当前 loop 或 switch 代码块，并且跳出后执行后续代码。</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_continue_statement.htm">continue</a></td>  
<td>跳出当前循环体，检测循环执行条件</td>  
</tr>  
<tr>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_goto_statement.htm">goto</a></td>  
<td>跳转到指定的代码标签处，不建议在程序中大量使用该功能。</td>  
</tr>  
</table>

## 无穷循环 

如果循环条件无法变为 false 的话，那么该训话那就是无穷循环。**for** 循环就是实现无穷循环。**for** 循环条件中的三个表达式并不是必须的，所以只要将条件判断语句置空就可以实现无穷循环。  

```
    #include <iostream>
    using namespace std;
     
    int main ()
    {
    
       for( ; ; )
       {
      printf("This loop will run forever.\n");
       }
    
       return 0;
    }
```

当条件判断语句置空后，就默认是 true. 程序员也可以保留初始化和递增表达式，但是 C++ 工程师一般都是使用 for（;;）来表达无穷循环。

**注意：**可以通过 Ctrl + C 的方式来终止无穷循环。

