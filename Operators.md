# 操作符 

操作符就是告诉编译器来执行数学或逻辑运算操作的符号。C++ 有非常丰富的内置操作符。提供如下几类的操作符：  
  
1. 数学运算操作符  
2. 关系运算操作符  
3. 逻辑运算操作符  
4. 位运算操作符  
5. 赋值运算操作符  
6. 复合运算操作符  

下面的章节将一一介绍数学、关系、逻辑、位运算、赋值和其他操作符。  

## 数学运算操作符

下面的就是 C++语言所支持的数学运算操作符：
假设变量 A 存储 10，变量 B 存储 20，那么：

[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_arithmatic_operators.htm)

<table>
<tbody>
<tr>
<th>运算符</th>  <th>描述</th> <th>例子</th>
</tr>
<tr>
<td>+</td>
<td>两个运算数相加</td>
<td>A + B = 30</td>
</tr>
<tr>
<td>-</td>
<td>第一个运算数减去第二个运算数</td>
<td>A - B = -10</td>
</tr>
<tr>
<td>*</td>
<td>运算数相乘   </td>
<td>A * B = 200</td>
</tr>
<tr>
<td>/</td>
<td>分子除以分母</td>
<td>B / A = 2</td>
</tr>
<tr>
<td>%</td>
<td>模数运算符，整除后的余数</td>
<td>B % A = 0</td>
</tr>
<tr>
<td>++</td>
<td>增量运算符，整数值逐次加1</td>
<td>A++ = 11</td>
</tr>
<tr>
<td>--</td>
<td>减量运算符，整数值逐次减1</td>
<td>A-- = 9</td> </tr> 
</tbody>
</table>

## 关系运算符 

下面的就是 C++语言所支持的关系运算操作符：
假设变量 A 存储 10，变量 B 存储 20，那么：

[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_relational_operators.htm)

<table>
<tbody>
<tr>
<th>运算符</th>
<th>描述</th>
<th>例子</th>
</tr>
<tr>
<td>==</td> <td>检查两个运算数的值是否相等，如果是，则结果为true</td> <td>A == B 为false</td>
</tr>
<tr>
<td>!=</td> <td>检查两个运算数的值是否相等，如果不相等，则结果为true    </td>
<td>A != B 为true</td>
</tr>
<tr>
<td>&gt;</td>  <td>检查左边运算数是否大于右边运算数，如果是，则结果为true </td>
<td>A &gt; B 为false</td>
</tr>
<tr>
<td>&lt;   </td>
<td>检查左边运算数是否小于右边运算数，如果是，则结果为true</td>
<td>   A &lt; B 为true</td>
</tr>
<tr>
<td>&gt;=</td> <td>检查左边运算数是否大于或者等于右边运算数，如果是，则结果为true</td>    <td>A &gt;= B 为false</td>
</tr>
<tr>
<td>&lt;=</td>
<td> 检查左边运算数是否小于或者等于运算数，如果是，则结果为true</td>  <td>A &lt;= B 为true</td>
</tr>
</tbody>
</table>

## 逻辑运算符 

下面的就是 C++语言所支持的逻辑运算操作符：
假设变量 A 存储 1，变量 B 存储 0，那么：

[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_logical_operators.htm)

<table>
<tbody>
<tr>
<th>运算符</th>  <th>描述</th> <th>例子</th>
</tr>
<tr>
<td>&amp;&amp;  </td>
<td>称为逻辑与运算符。如果两个运算数都非零，则结果为true。</td>
<td>   A &amp;&amp; B 为true</td>
</tr>
<tr>
<td>||  </td>
<td>称为逻辑或运算符。如果两个运算数中任何一个非零，则结果为true。</td>
<td>   A || B 为 true</td>
</tr>
<tr>
<td>!   </td>
<td>称为逻辑非运算符。用于改变运算数的逻辑状态。如果逻辑状态为true，则通过逻辑非运算符可以使逻辑状态变为false  </td>
<td>!(A &amp;&amp; B) 为false</td>
</tr>  
</tbody>
</table> 

## 位运算符 

位操作运算是按位来进行操作的。与、或、非和异或的真值表如下：

<table>
<tbody>
<tr>
<th>p</th>  <th>q</th> <th>p&q</th> <th>p|q</th> <th>p^q</th>
</tr>
<tr>
<td>0 </td>
<td>0</td>
<td> 0</td>
<td> 0</td>
<td> 0</td>
</tr>
<tr>
<td>0 </td>
<td>1</td>
<td>   0</td>
<td>   1</td>
<td>   1</td>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>1</td>
<td>1</td>
<td>0</td>
</tr> 
<tr>
<td>1</td>
<td>0</td>
<td>0</td>
<td>1</td>
<td>1</td>
</tr> 
</tbody>
</table> 


假设变量 A 存储 60，变量 B 存储 13，那么：

下面的就是 C++语言所支持的位运算操作符：
假设变量 A 存储 60，变量 B 存储 13，那么：


A = 0011 1100

B = 0000 1101

-----------------

A&B = 0000 1100

A|B = 0011 1101

A^B = 0011 0001

~A  = 1100 0011


[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_bitwise_operators.htm)

<table>
<tbody>
<tr>
<th>运算符</th>
<th>描述</th>   <th>例子</th>
</tr>
<tr>
<td>&amp;   </td>
<td>称为按位与运算符。它对整型参数的每一个二进制位进行布尔与操作。</td>
<td> A &amp; B = 12 .</td>
</tr>
<tr>
<td>|   </td>
<td>称为按位或运算符。它对整型参数的每一个二进制位进行布尔或操作。</td>
<td> A | B = 61.</td>
</tr>
<tr>
<td>^</td>  <td>称为按位异或运算符。它对整型参数的每一个二进制位进行布尔异或操作。异或运算是指第一个参数或者第二个参数为true，并且不包括两个参数都为true的情况，则结果为true。</td>
<td>    (A ^ B) = 49.</td>
</tr>
<tr>
<td>~</td>  <td>称为按位非运算符。它是一个单运算符，对运算数的所有二进制位进行取反操作。</td>
<td>   ~B = -61 .</td>
</tr>
<tr>
<td>&lt;&lt;  </td>
<td>称为按位左移运算符。它把第一个运算数的所有二进制位向左移动第二个运算数指定的位数，而新的二进制位补0。将一个数向左移动一个二进制位相当于将该数乘以2，向左移动两个二进制位相当于将该数乘以4，以此类推。</td>    <td>A &lt;&lt; 1 = 4.</td>
</tr>
<tr>
<td>&gt;&gt;</td>
<td> 称为按位右移运算符。它把第一个运算数的所有二进制位向右移动第二个运算数指定的位数。为了保持运算结果的符号不变，左边二进制位补0或1取决于原参数的符号位。如果第一个运算数是正的，运算结果最高位补0；如果第一个运算数是负的，运算结果最高位补1。将一个数向右移动一位相当于将该数乘以2，向右移动两位相当于将该数乘以4，以此类推。</td>    <td>A &gt;&gt; 1 = 240.</td>
</tr>
<tr>
<td>&gt;&gt;&gt; </td>
<td>称为0补最高位无符号右移运算符。这个运算符与&gt;&gt;运算符相像，除了位移后左边总是补0.   </td>
<td>A &gt;&gt;&gt; = 15.</td> </tr> 
</tbody>
</table> 

## 赋值运算符   

下面的就是C++语言所支持的赋值运算操作符：


[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_assignment_operators.htm)

<table>
<tbody>
<tr>
<th>运算符</th>  <th>描述</th>
<th> 例子</th>
</tr>
<tr>
<td>=   </td>
<td>简单赋值运算符，将右边运算数的值赋给左边运算数</td> <td>C = A + B 将A+B的值赋给C</td>
</tr>
<tr>
<td>+=  </td>
<td>加等赋值运算符，将右边运算符与左边运算符相加并将运算结果赋给左边运算数</td>
<td> C += A 相当于 C = C + A</td>
</tr>
<tr>
<td>-=  </td>
<td>减等赋值运算符，将左边运算数减去右边运算数并将运算结果赋给左边运算数 </td>
<td>C -= A 相当于C = C - A</td>
</tr>
<tr>
<td>*=  </td>
<td>乘等赋值运算符，将右边运算数乘以左边运算数并将运算结果赋给左边运算数</td>
<td>    C *= A 相当于C = C * A</td>
</tr>
<tr>
<td>/=  </td> <td>除等赋值运算符， 将左边运算数除以右边运算数并将运算结果赋值给左边运算数</td>
<td>   C /= A 相当于 C = C / A</td>
</tr>
<tr>
<td>%=  </td>
<td>模等赋值运算符，用两个运算数做取模运算并将运算结果赋值给左边运算数    </td>
<td>C %= A 相当于 C = C % A </td>
</tr>



<td><<=  </td>
<td>左移且赋值运算符  </td>
<td>C <<= 2 相当于 C = C << 2 </td>
</tr>

<td>>>=  </td>
<td>右移且赋值运算符</td>
<td>C >>= 2 相当于 C = C >> 2 </td>
</tr>

<td>&=  </td>
<td> 位与且赋值运算符 </td>
<td>C &= 2 相当于 C = C & 2 </td>
</tr>

<td>^=  </td>
<td>位异或且赋值运算符   </td>
<td>C ^= A 相当于 C = C ^ A </td>
</tr>

<td>|=  </td>
<td>位或且赋值运算符  </td>
<td>C |= A 相当于 C = C | A </td>
</tr>


</tbody>
</table>

## 复合运算符 

下面是 C++ 支持的其他运算符：

<table border="1">  
<tr>  
<th>操作符</th>
<th>描述</th>   
</tr>  
<tr>  
<td>sizeof</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_sizeof_operator.htm">sizeof</a> 操作符返回变量占用内存的大小。比如，sizeof（a），a 是一个整数时，返回4</td>  
</tr>  
<tr>  
<td>条件 ？ X ： Y </td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_conditional_operator.htm">条件操作符：</a>如果条件判断为true，则返回 X，否则返回 Y.</td>  
</tr>  
<tr>  
<td>,</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_comma_operator.htm">逗号操作符</a>可以使操作顺序执行。整体逗号表达式的值就是逗号最后表达式的返回结果。</td>  
</tr> 


<tr>  
<td>.(点) 和 ->(箭头)</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_member_operators.htm">成员操作符</a>用于获取类、结构体或联合体成员的引用。</td>  
</tr>

<tr>  
<td>转换</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_casting_operators.htm">转换操作符</a>可以将数值类型转成其他类型，比如，int（2.2000）将返回 2.</td>  
</tr>

<tr>  
<td>&</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_operators.htm">取地操作符</a>可以返回一个变量的地址。比如， &a 将会返回变量实际的内存地址。</td>  
</tr>

<tr>  
<td>*</td>  
<td><a href="http://www.tutorialspoint.com/cplusplus/cpp_pointer_operators.htm">指针操作符</a>指向一个变量。比如 *var 意味着指向变量 var.</td>  
</tr>
</table>

## C++ 中操作符优先级 

运算符优先级确定表达式中项的分组。这会影响如何表达一个表达式。某些操作符比其他有更高的优先级,例如,乘法运算符的优先级高于加法操作符。  

比如 x=7+3*2，这里x的值是13而不是20，因为乘法优先级比加法高。所以应该先执行3乘2，然后再加7.

操作符的优先级如下表，上方的优先级比下方高。较高优先级的操作符优先进行计算。

[显示例子](http://www.tutorialspoint.com/cplusplus/cpp_operators_precedence.htm)

<table>
<tbody>
<tr>
<th>分类</th>  <th>操作符</th> <th> 操作顺序</th>
</tr>
<tr>
<td>后缀运算</td>
<td>() [] -> . ++ - -  </td>
<td>从左到右</td>
</tr>
<tr>
<td>一元运算</td>
<td>+ - ! ~ ++ - - (type)* & sizeof </td>
<td> 从右到左</td>
</tr>
<tr>
<td>乘法</td>
<td>* / % </td>
<td>从左到右</td>
</tr>
<tr>
<td>加法</td>
<td>+ - </td>
<td> 从左到右</td>
</tr>
<tr>
<td>移位 </td> <td><< >> </td>
<td> 从左到右</td>
</tr>
<tr>
<td>比较</td>
<td>< <= > >=  </td>
<td>从左到右</td>

</tr>

<td>位与 </td>
<td>&  </td>
<td>从左到右</td>
</tr>

<td>异或 </td>
<td>^</td>
<td>从左到右</td>
</tr>

<td>位或 </td>
<td> |</td>
<td>从左到右</td>
</tr>

<td>逻辑与 </td>
<td>&& </td>
<td>从左到右</td>
</tr>

<td>||  </td>
<td>逻辑或 </td>
<td>从左到右</td>
</tr>

<td>条件 </td>
<td>?: </td>
<td>从左到右</td>
</tr>

<td>赋值  </td>
<td>= += -= *= /= %=>>= <<= &= ^= |= </td>
<td>从右到左</td>
</tr>

<td>逗号  </td>
<td>， </td>
<td>从到右</td>
</tr>

</tbody>
</table>