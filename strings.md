# 字符串

C++ 提供了以下两种类型的字符串表示形式：  

- C 样式字符串 
- 用标准 C++ 介绍的标准字符串类型  

## C 样式字符串  

C 样式字符串源于 C 语言，在 C++ 中仍然被支持。这个串实际是一个字符的一维数组，这个数组以一个**空**字符 ‘\0’ 结束。因此以 null 结尾的字符串包含由字符组成的字符串，此字符串后跟着一个 **null**。  

接下来声明和初始化创建一个字符串，这个字符串组成一个单词 "hello"。为了包含数组末尾的空字符，包含该字符串的字符数组的大小应该比单词 "hello" 中的字符的数目多一个。  

```
    char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
```

如果你遵循数组初始化的规则，你可以像下面一样书写上面的语句：  

```
    char greeting[] = "Hello";
```

以下是在 C/C++ 中定义上面的字符串的内存演示：

![](http://www.tutorialspoint.com/cplusplus/images/string_representation.jpg)

实际上，你不需要在字符串常量的末尾放置一个空字符。 C++ 编译器在初始化数组时自动在串的末尾放置一个 '\0'。让我们尝试打印上述字符串：  

```
    #include <iostream>
    
    using namespace std;
    
    int main ()
    {
       char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
    
       cout << "Greeting message: ";
       cout << greeting << endl;
    
       return 0;
    }
```

当上述代码被编译执行时，它将产生如下结果：  

```
    Greeting message: Hello
```

C++ 支持广泛的函数来操作以空字符终止的字符串：  

<table border="1">
<tr>
<th>自然数</th>
<th>函数和功能</th>
</tr>
<tr>
<td>1</td>
<td><strong>strcpy(s1,s2);</strong>  
将字符串 s2 复制到字符串 s1 中。</td>
</tr>
<tr>
<td>2</td>
<td><strong>strcat(s1,s2);</strong>   
 将字符串 s2 串联到字符串 s1 的结尾。</td>
</tr>
<tr>
<td>3</td>
<td><strong>strlen(s1);</strong>  
 返回字符串 s1 的长度。</td>
</tr>
<tr>
<td>4</td>
<td><strong>strcmp(s1,s2);</strong>  
 如果 s1 和 s2 相同，返回 0；如果 s1≥s2，返回大于 0 的数；如果 s1<s2，返回小于 0 的数。</td>
</tr>
<tr>
<td>5</td>
<td><strong>strchr(s1,ch);</strong>  
返回在字符串 s1 中指向第一次出现字符 ch 的指针。</td>
</tr>
<tr>
<td>6</td>
<td><strong>strstr(s1,s2);</strong>  
返回在字符串 s1 中指向第一次出现字符串 s2 的指针。</td>
</tr>
</table>

以下是应用了一些上述函数的示例：  

```
    #include <iostream>
    #include <cstring>
    
    using namespace std;
    
    int main ()
    {
       char str1[10] = "Hello";
       char str2[10] = "World";
       char str3[10];
       int  len ;
    
       // copy str1 into str3
       strcpy( str3, str1);
       cout << "strcpy( str3, str1) : " << str3 << endl;
    
       // concatenates str1 and str2
       strcat( str1, str2);
       cout << "strcat( str1, str2): " << str1 << endl;
    
       // total lenghth of str1 after concatenation
       len = strlen(str1);
       cout << "strlen(str1) : " << len << endl;
    
       return 0;
    }
```

当上述代码被编译执行时，它将产生如下结果：  

```
    strcpy( str3, str1) : Hello
    strcat( str1, str2): HelloWorld
    strlen(str1) : 10
```

## C++ 中的字符串类 

标准的 C++ 库中提供了一个 **string** 类，它支持上面提到的所有的操作，另外它还有更多的功能。我们会研究 C++ 标准库中的这个类，但现在我们先检查以下示例：  
   
在这点上，你可能还没有明白这个例子，因为到目前为止我们还没有讨论类和对象。所以直到你理解了面向对象的概念你才可以继续进行下去。

```
    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main ()
    {
       string str1 = "Hello";
       string str2 = "World";
       string str3;
       int  len ;
    
       // copy str1 into str3
       str3 = str1;
       cout << "str3 : " << str3 << endl;
    
       // concatenates str1 and str2
       str3 = str1 + str2;
       cout << "str1 + str2 : " << str3 << endl;
    
       // total lenghth of str3 after concatenation
       len = str3.size();
       cout << "str3.size() :  " << len << endl;
    
       return 0;
    }
```

当上述代码被编译执行时，它将产生如下结果：
 
```   
    str3 : Hello
    str1 + str2 : HelloWorld
    str3.size() :  10
```
