# 存储类型  

存储类型定义了变量或函数的作用范围及生命周期。这些说明符也声明了他们的修改方式的类型。有如下几种存储类型：

1. auto  
2. register  
3. static  
4. extern  
5. mutable 


## auto 存储类型  

**auto**存储类型是所有局部变量的默认存储类型。

```
    {
       int mount;
       auto int month;
    }
```

上面的例子中定义了两个相同存储类型的变量，auto 仅能运用于函数内的局部变量。

## register 存储类型 

**register** 存储类型用于定义存储于寄存器中的变量而不是内存中。这意味着该变量的最大尺寸将是寄存器的大小（通常是一个字），并且不能使用 '&' 寻址运算符进行操作（因为它没有内存地址）。

```    
    {
       register int  miles;
    }
```

register类型应该仅应用于需要快速访问的变量，比如计数器。需要注意的是，定义 register 类型的变量并不意味着该变量一定就存储在寄存器中，这仅仅意味着需要按照硬件以及具体实现的限制来判定到底是不是存储在寄存器中。  

## static 存储类型 

**static** 存储类型的变量意味着该变量将会从始至终地存活在程序的整个生命周期内，而不会随着每次访问到它所在的代码块时就建立该变量，离开代码块时就销毁该变量。因此，局部变量静态化可以使他们在函数调用时仍保有其值。  

static 修饰符也可以应用于全局变量。 当全局变量使用该修饰符后， 该全局变量就被限制在其声明的文件内。  

在 C++中，当 static 应用于类的数据成员时，它所起到的作用是多个该类的成员变量都是指的同一个变量。  

```
    #include <iostream>
     
    // Function declaration
    void func(void);
     
    static int count = 10; /* Global variable */
     
    main()
    {
    while(count--)
    {
       func();
    }
    return 0;
    }
    // Function definition
    void func( void )
    {
    static int i = 5; // local static variable
    i++;
    std::cout << "i is " << i ;
    std::cout << " and count is " << count << std::endl;
    }
```

当上述代码被编译后执行，其结果如下：

```
    i is 6 and count is 9
    i is 7 and count is 8
    i is 8 and count is 7
    i is 9 and count is 6
    i is 10 and count is 5
    i is 11 and count is 4
    i is 12 and count is 3
    i is 13 and count is 2
    i is 14 and count is 1
    i is 15 and count is 0
```

## extern 存储类型 

**extern** 存储类型用于使全局变量的引用对所有程序文件可见。如果前面已经定义了一个变量名，那么就不能再使用 extern 来声明同一变量名的变量了。

当你有多个程序文件且需要定义一个可以在其他文件用可以访问到的变量或函数时，就可以在其他文件中使用 *extern* 声明该变量或函数的引用。  

extern 修饰符通常被应用于多个文件中需要共享相同的全局变量或函数的情况。一个例子如下：

第一个文件：main.CPP  

```
    #include <iostream>
     
    int count ;
    extern void write_extern();
     
    main()
    {
       count = 5;
       write_extern();
    }
```

第二个文件：support.cpp

```
    #include <iostream>
     
    extern int count;
     
    void write_extern(void)
    {
       std::cout << "Count is " << count << std::endl;
    }
```

这里的 *extern* 关键用于声明count变量已经在其他文件中定义了。按照下面的方式来编译：


```
    $g++ main.cpp support.cpp -o write
```

这样会生出一个 write 可执行文件，运行它并看他的结果：

```
    $./write
    5
```

## mutable 存储类型  

**mutable** 修饰符应用于类对象，将会在后续章节中详细讨论。它允许对象的成员可以覆盖常量。也即是说，mutable 成员可以被const成员函数所修改。