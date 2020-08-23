1、若操作数具有类型char、unsigned char或signed char，其结果等于1。ANSI C正式规定字符类型为1字节。例如int类型在16位系统中占2个字节，在32位系统中占4个字节。
2、int、unsigned int 、short int、unsigned short 、long int 、unsigned long 、float、double、long double类型的sizeof 在ANSI C中没有具体规定，大小依赖于实现，一般可能分别为2、2、2、2、4、4、4、8、10。

函数前置声明的时候，初始化赋值的变量只最前面的前置声明中，在后面的函数实现中不得赋值

e) 一个有10个指针的数组，该指针是指向一个整型数的。（An array of 10 pointers to integers）
f) 一个指向有10个整型数数组的指针（ A pointer to an array of 10 integers）
g) 一个指向函数的指针，该函数有一个整型参数并返回一个整型数（A pointer to a function that takes an integer as an argument and returns an integer）
h) 一个有10个指针的数组，该指针指向一个函数，该函数有一个整型参数并返回一个整型数（ An array of ten pointers to functions that take an integer argument and return an integer ）

e) int *a[10]; // An array of 10 pointers to integers
f) int (*a)[10]; // A pointer to an array of 10 integers
g) int (*a)(int); // A pointer to a function a that takes an integer argument and returns an integer
h) int (*a[10])(int); // An array of 10 pointers to functions that take an integer argument and return an integer

const int *a;	//a是一个指向常整型数的指针（也就是，整型数是不可修改的，但指针可以）
int * const a;  	//a是一个指向整型数的常指针（也就是说，指针指向的整型数是可以修改的，但指针是不可修改的）
int const * a const;	//a是一个指向常整型数的常指针（也就是说，指针指向的整型数是不可修改的，同时指针也是不可修改的）

*(p++)与*p++ 并不是没有区别，虽然都是赋值与移位，前一个是先指针后移再赋值，后一个是先赋值再移动指针，虽然指针最后都是在原地址的下一个地址，但是赋值的地址是不同。

Qcif（176×144）、CIF（352×288）、HALF D1（704×288）、D1（704×576） 

Interrupt Service Routines 中断服务子程序(ISR)

当表达式中存在有符号类型和无符号类型时所有的操作数都自动转换为无符号类型

assert( int expression );
assert的作用是先计算表达式 expression ，如果其值为假（即为0），那么它先向stderr打印一条出错信息，然后通过调用 abort 来终止程序运行。

13. 评价下面的代码片断：
unsigned int zero = 0;
unsigned int compzero = 0xFFFF;
/*1''s complement of zero */
对于一个int型不是16位的处理器为说，上面的代码是不正确的。应编写如下：
unsigned int compzero = ~0;

头文件中的 #ifndef/#define/#endif 防止该头文件被重复引用


#include< >和#include“ ”的区别：
一、引用的头文件不同
#include< >引用的是编译器的类库路径里面的头文件知。
#include“ ”引用的是你程序目录的相对路径中的头文件。

二、用法不同
#include< >用来包含标准头文件(例如stdio.h或stdlib.h).
#include“ ”用来包含非标准头文件。

三、调用道文件的顺序不同
#include< >编译程序版会先到标准函数库中调用文件。
#include“ ”编译程序会先从当前目录中调用文件。

四、预处理程序的指示不同
#include< >指示预处理程序到预权定义的缺省路径下寻找文件。
#include“ ”指示预处理程序先到当前目录下寻找文件，再到预定义的缺省路径下寻找文件。

## 一、string转char*。

主要有三种方法可以将str转换为char*类型，分别是：data(); c_str(); copy();

1.data()方法，如：

    string str = "hello";
    const char* p = str.data();//加const  或者用char * p=(char*)str.data();的形式

同时有一点需要说明，这里在devc++中编译需要添加const，否则会报错invalid conversion from const char*  to char *，这里可以再前面加上const或者在等号后面给强制转化成char*的类型。

下面解释下该问题，const char*是不能直接赋值到char*的,这样编译都不能通过,理由:假如可以的话,那么通过char*就可以修改const char指向的内容了,这是不允许的。所以char*要另外开辟新的空间，即上面的形式。

2.c_str()方法，如：

    string str=“world”;
    const char *p = str.c_str();//同上，要加const或者等号右边用char*

3.copy()方法，如：

    string str="hmmm";
    char p[50];
    str.copy(p, 5, 0);//这里5代表复制几个字符，0代表复制的位置，
    *(p+5)=‘\0’;//注意手动加结束符！！！

二、char*转string直接转

三、string转char[] 

    string pp = "dagah";
    char p[8];
    int i;
    for( i=0;i<pp.length();i++)
        p[i] = pp[i];
    p[i] = '\0';
    printf("%s\n",p);
    cout<<p;