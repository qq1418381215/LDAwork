一些从写LDA代码学到的课外知识

万能文件头

```c++
#include<bits/stdc++.h>
using namespace std;
```

c++里的hash

```c++
// 定义一个map对象
map<int, string> mapStudent;
 
// 第一种 用insert函數插入pair
mapStudent.insert(pair<int, string>(000, "student_zero"));
 
// 第二种 用insert函数插入value_type数据
mapStudent.insert(map<int, string>::value_type(001, "student_one"));
 
// 第三种 用"array"方式插入
mapStudent[123] = "student_first";
mapStudent[456] = "student_second";

```

动态数组（向量

```c++
//定义具有10个整型元素的向量，且给出的每个元素初值为1
vector<int>a(10,1);

```

初始化数组简写

```c++
#define ms(i,j) memset(i, j, sizeof(i)); 
```

函数不加括号

```
不加括号的，都是把函数名称作为函数的指针，一个函数的名称就是这个函数的指针，此时不是得到函数的结果，因为不会运行函数体代码。它只是传递了函数体所在的地址位置，在需要的时候好找到函数体去执行。
```

命名规则

```
3、匈牙利命名法

变量名前面加上相应的小写字母的符号标识作为前缀，标识出变量的作用域，类型等这些符号可以多个同时使用，基本原则是：变量名=属性+类型+对象描述。

匈牙利命名法关键是：标识符的名字以一个或者多个小写字母开头作为前缀；前缀之后的是首字母大写的一个单词或多个单词组合，该单词要指明变量的用途。

但是类比较特殊，类的名称一般以大写字母“C”开头

函数的名称由一个或多个单词组成。为便于界定，建议采用帕斯卡（Pascal）命名法，即每个单词的首字母要大写。

常量、宏定义和枚举一般都是所有字母大写，特别是宏定义，在不同字母之间，可以加上下划线，也可以不加。
```

