# 数据类型

当在使用任何编程语言编程时，您需要使用各种不同的变量来存储不同的信息。变量只是让内存预留位置来存储一些值。这意味着，当你创建一个变量时在内存中会保留一些空间给该变量。


你可能喜欢使用像字符类型，宽字符，整数，浮点数，双精度浮点数，布尔类型等各种数据类型来存储信息。操作系统基于变量的数据类型来分配内存空间和决定什么可以存储在该保留内存区域。

## 基本内置类型

C++ 给程序员提供了一系列丰富的内置类型以及用户定义的数据类型。下表列出了七个基本的 C++ 数据类型:

<table class="table table-bordered">
<tr>
<th width="50%">类型</th>
<th>关键字</th>
</tr>
<tr>
<td>Boolean</td>
<td>bool</td>
</tr>
<tr>
<td>Character</td>
<td>char</td>
</tr>
<tr>
<td>Integer</td>
<td>int</td>
</tr>
<tr>
<td>Floating point</td>
<td>float</td>
</tr>
<tr>
<td>Double floating point</td>
<td>double</td>
</tr>
<tr>
<td>Valueless</td>
<td> void</td>
</tr>
<tr>
<td>Wide character</td>
<td>wchar_t</td>
</tr>
</table>

上面的几个基本类型可以使用一个或多个如下的修饰符这来修饰:

- signed
- unsigned
- short
- long

下面的表显示了变量类型，该类型的值在内存中需要多少内存空间来存储，该类型能够表示的最大值和最小值。

<table class="table table-bordered" border="1" cellpadding="5">
<tr>
<th>类型</th>
<th>长度</th>
<th>范围</th>
</tr>
<tr>
<td>char</td>
<td>1byte</td>
<td>-127 - 127 或者 0 - 255</td>
</tr>
<tr>
<td>unsigned char</td>
<td>1byte</td>
<td>0 - 255</td>
</tr>
<tr>
<td>signed char</td>
<td>1byte</td>
<td>-127 - 127</td>
</tr>
<tr>
<td>int</td>
<td>4bytes</td>
<td>-2147483648 - 2147483647</td>
</tr>
<tr>
<td>unsigned int</td>
<td>4bytes</td>
<td>0 - 4294967295</td>
</tr>
<tr>
<td>signed int</td>
<td>4bytes</td>
<td>-2147483648 - 2147483647</td>
</tr>
<tr>
<td>short int</td>
<td>2bytes</td>
<td>-32768 - 32767</td>
</tr>
<tr>
<td>unsigned short int</td>
<td>Range</td>
<td>0 - 65,535</td>
</tr>
<tr>
<td>signed short int</td>
<td>Range</td>
<td>-32768 - 32767</td>
</tr>
<tr>
<td>long int</td>
<td>4bytes</td>
<td>-2,147,483,647 - 2,147,483,647</td>
</tr>
<tr>
<td>signed long int</td>
<td>4bytes</td>
<td>和 long int 一样</td>
</tr>
<tr>
<td>unsigned long int</td>
<td>4bytes</td>
<td>0 - 4,294,967,295</td>
</tr>
<tr>
<td>float</td>
<td>4bytes</td>
<td>+/- 3.4e +/- 38 (~7 位数字)</td>
</tr>
<tr>
<td>double</td>
<td>8bytes</td>
<td>+/- 1.7e +/- 308 (~15 位数字)</td>
</tr>
<tr>
<td>long double</td>
<td>8bytes</td>
<td>+/- 1.7e +/- 308 (~15 位数字)</td>
</tr>
<tr>
<td>wchar_t</td>
<td>2 或者 4 bytes</td>
<td>1 个宽字符</td>
</tr>
</table>

变量类型占用空间的实际大小可能和上表展示的有些不同,这取决于您所使用的编译器和电脑操作系统。

下面示例将输出各种数据类型在您的计算机上实际占用的内存空间大小。

```
	#include <iostream>
	using namespace std;

	int main()
	{
		cout << "Size of char : " << sizeof(char) << endl;
		cout << "Size of int : " << sizeof(int) << endl;
		cout << "Size of short int : " << sizeof(short int) << endl;
		cout << "Size of long int : " << sizeof(long int) << endl;
		cout << "Size of float : " << sizeof(float) << endl;
		cout << "Size of double : " << sizeof(double) << endl;
		cout << "Size of wchar_t : " << sizeof(wchar_t) << endl;
		return 0;
	}
```

这个示例使用 **endl**，这个表示在每一行之后插入一个换行符，<< 操作符被用来将多个值输出到屏幕上。我们也使用 **sizeof()** 函数来获得各种数据类型的存储大小。


上面的代码编译和执行时,它会产生以下结果，这个可能会随着机器的不同而显示不同的结果:

```
	Size of char : 1
	Size of int : 4
	Size of short int : 2
	Size of long int : 4
	Size of float : 4
	Size of double : 8
	Size of wchar_t : 4
```

## typedef 声明

你可以使用 **typedef** 为已经存在的数据类型起一个新的名称。下面是一个使用 typedef 定义一个新类型的简单语法方式:

```
	typedef type newname;
```

例如,下面告诉编译器，feet 是 int 的另一个名字:

```
	typedef int feet;
```

现在，下面的声明是完全合法和创建一个整数变量称为 distance:

```
	feet distance;
```

## 枚举类型 

枚举类型声明了一个可选的类型名和一组值为零的或多个标识符的类型。每个枚举器是一个常数，它的类型是枚举。

创建一个枚举类型需要使用关键字 **enum**。枚举类型的一般形式是:

```
	enum enum-name { list of names} var-list;
```

在这里，enum-name 是枚举类型名。list of name 是由逗号分隔开的。

例如，下面的代码定义了一个称为 color 的颜色枚举类型，并且变量 c 的是一个 color 类型的枚举变量。最后， c 被赋值为 “blue”。

```
	enum color { red,green,blue} c;
	c = blue;
```

默认情况下,枚举类型花括号中第一个变量被赋值为 0，第二个变量赋值为 1，第三个赋值为 2，依此类推。但是你也可以给某个指定变量一个初始值。例如,在下面的枚举类型, **green** 将会被初始化为 5。

```
	enum color { red, green=5, blue };
```

这里，**blue** 的值将会变成 6，因为每个变量都会比它前一个变量大 1。
