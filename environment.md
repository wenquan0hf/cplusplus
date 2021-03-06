# 开发环境

## 在线体验操作

为了学习 C++ 编程语言你不需要设置你的编程环境。原因很简单，因为我们已经通过在线的方式设置了 C++ 编程环境，因此当你做一些理论工作上的研究时，你可以通过在线的方式同时体验编译和执行所有可用的示例程序。这个能够让你对你所读的拥有更多的自信，同时能够检查不同操作的结果。在线的方式让你感觉到修改和执行任何示例都是如此的容易。

```
	#include <iostream>
	using namespace std;

	int main()
	{
		cout << "Hello World";
		return 0;
	}
```

## 本地开发环境设置

如果你仍然想要本地的 C++ 开发环境，你应该确保如下的两个软件已经安装在你的电脑上：

## 文本编辑器

文本编辑器用来编写程序。举几个编辑器的例子： Windows 的 NotePad，一些操作系统提供的 Edit 命令，Brief，Epsilon,EMACS，和 vim 或者 vi。

文本编辑器的名称和版本在不同的操作系统上可能有差异。例如，Windows 操作系统上可用 NotePad，在 windows 和 Linux 或者 UNIX 上均可以使用 vim 或者 vi。

你用编辑器创建的文件称为源文件，对于 C++ 而言，这些文件的很明显都是用 .cpp，.cp，或者 .c为扩展名(后缀名)。

在开始编程之前，请确保你有一个文本编辑器可用，并且你有足够的经验编写 C++ 程序。

## C++ 编译器

C++ 编译器的作用是编译你的源代码，最终将它转换成可执行程序。

大多数 C++ 编译器并不在意你的源代码文件的扩展名，如果你没有指定它的扩展名，许多编译器都会用 .cpp 作为文件的默认扩展名。

最常用并且免费的编译器是 GNU C/C++ 编译器，另外如果你有其他的操作系统，你也可以使用 HP 或者 Solaris 的编译器。

## Installing GNU C/C++ 编译器

### UNIX/Linux 安装

如果你使用 Linux 或者 UNIX 系统，通过在命令行中输入如下的命令检查你的系统是否已经安装了 GCC：

```
	$ g++ -v
```

如果已经安装了 GCC， 那么在控制台中应该输出类似如下的信息：

```
	Using built-in specs.
	Target: i386-redhat-linux
	Configured with: ../configure --prefix=/usr .......
	Thread model: posix
	gcc version 4.1.2 20080704 (Red Hat 4.1.2-46)
```

如果 GCC 没有安装，那么你需要自己手动安装，你可以从 [http://gcc.gnu.org/install/](http://gcc.gnu.org/install/) 这里获得更详细的说明。

### Mac OS X 安装

如果你使用 Mac OS X 系统，那么得到 GCC 最方便的方式是从苹果的网站上下载 Xcode 开发环境， 按照如下的链接中的说明进行安装。

Xcode 现在可用的链接是： [ developer.apple.com/technologies/tools/]( developer.apple.com/technologies/tools/)

### Windows 安装 

为了在 Windows 上安装 GCC， 你需要安装 MinGW。为了安装 MinGW，你可以访问 MinGW 的主页 
[www.mingw.org](www.mingw.org)
 
接着访问 MinGW 下载页那个链接。下载最新版的 MinGW 安装程序，这个程序的名称应该是类似于 MinGW-<版本号>.exe 这样的形式。

在安装 MinGW 的时候，最低限度，你必须要安装 gcc-core，gcc-g++，binutils，和 MinGW 运行时环境，当然你也可以选择更多进行安装。

添加你安装 MinGW 的子目录 bin 的路径到你的 **PATH** 环境变量中，这样你就可以通过在命令行中输入 MinGW 提供的工具的名称来使用这些工具。
 
当安装完成之后，你可以在 Windows 的命令行中运行 GNU 提供的几个工具，类似于：gcc，g++，ar，ranlib，dlltool 等。


