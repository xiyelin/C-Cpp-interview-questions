#### 1.变量的声明和定义的区别：

　　为变量分配地址和存储空间的称为定义。不分配地址的称为声明。一个变量可以在多个地方声明，但是只能在一个地方


定义。用extern修饰的变量是变量的声明。说明此变量将在本文件以外或者在文件后面部分定义。
  
	　说明：很多时候一个变量只声明不分配存储空间，在具体使用时才初始化，分配存储空间。如外部变量。

<br>
<br>
#### 2.写出bool、float、int和指针变量与“零值”比较的if语句：

* bool类型与零值比较：

```c
	
		if(flag)
		{
			//do A
		}
		else
		{
			//do B
		}

```

* float类型与零值比较：

```c
	
		const float EPSINON = 0.00001 ;
		
		if((flag >= -EPSINON) && (flag <= EPSINON))
		{
			//do A
		}
		else
		{
			//do B
		}
		
		为什么浮点数(float/double)与零值比较不能直接使用 == 和 != 进行比较。因为计算机处理浮点数是有误差的，
	
	都有精度限制。所以我们认为只要浮点数处于某一区间内我们就认为它们相等。即[-EPSINON, EPSINON]。
	
	
```

* int类型与零值比较：

```c

		if(0 == flag)
		{
			//do A
		}
		else
		{
			//do B
		}

```

* 指针类型与零值比较：


```c

		if(NULL == flag)
		{
			//do A
		}
		else
		{
			//do B
		}
	
```

<br>
<br>
#### 3.sizeof 和 strlen的区别：

- sizeof 是一个操作符，而 strlen 是库函数。

- sizeof 的参数可以是数据类型，可以是变量，而 strlen 的参数只能是以 '\0' 结尾的字符串。

- 编译器在编译时就计算出了 sizeof 的大小，而 strlen 要在运行后才能计算出大小。

- sizeof 计算的是类型所占内存的字节数，而 strlen 计算的是字符串的有效长度。

- 数组做 sizeof 的参数不会退化，而数组做 strlen 的参数会退化成指针。


<br>
<br>
#### 4.C语言关键字 static 和 C++关键字 static 的区别：

	　　在C语言中，static关键字可以修饰局部静态变量，可以修饰全局静态变量和函数。而在C++中，除了以上的功能，它还
	
	可以修饰类的成员变量和成员函数。C++的静态成员可以在多个对象实例间进行通信、传递信息。

<br>
<br>
#### 5.C语言中 malloc 和 C++中 new 的区别：

- new 和 delete 是操作符，可以重载，只能在C++中使用。

- malloc 和 free 是函数，可以覆盖，在C/C++中都可以使用。

- new 可以调用对象相应的构造函数，而 delete 可以调用对象相应的析构函数。

- malloc 仅仅执行分配内存的任务，free 只执行释放内存的任务，不调用构造和析构函数。

- new/delete 返回的是某种具体类型的指针，而 malloc/free 返回的是 void 类型的指针。

- malloc 必须和 free 配对使用，new 和 delete 必须配对使用；（new [] 和 delete[] 配对使用）。

<br>
<br>
#### 6.写一个“标准”宏 MIN：

	说明：使用时要注意宏的副作用，能加上括号的地方一定不能少。
	
```

		# include <stdio.h>

		# define MIN(a,b) ((a)<(b)?(a):(b))
		
		void main()
		{
			int a = 10;
			int b = 20;
		
			printf("a = %d, b = %d, Min: %d \n", a, b, MIN(a, b));
		}
	
		a = 10, b = 20, Min: 10
	    请按任意键继续. . .

```

<br>
<br>
#### 7.一个指针可以是 volatile 的吗？

	













