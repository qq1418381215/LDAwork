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

