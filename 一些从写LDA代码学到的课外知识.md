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

```
int   argc,   char*   argv[]里

输入
F:\MYDOCU~1\TEMPCODE\D1\DEBUG\D1.EXE   aaaa   bbb   ccc   ddd  

则
argc=5
argv[0]=F:\MYDOCU~1\TEMPCODE\D1\DEBUG\D1.EXE
argv[1]=aaaa
```

```
getline(cin, inputLine);

相当于cin>>inputLine;
但是中间可以输入空格，只有换行的时候才会停止输入
也可以放文件句柄：
fstream fin(file);
getline(fin, rule);
```

STL

容器，算法，迭代器

容器，算法，迭代器，仿函数，适配器，空间配置器

容器：序列式，关联式

算法：质变，非质变

迭代器：用于访问容器里的东西

输入，输出，前向，双向，随机访问



vector

```c++
#include <vector>
vector<int> V;
V.push_back(10);

vector<int>::iterator itBegin=V.begin();
#itBegin是指针
vector<int>::iterator itEnd=V.end();
#指向最后一个的后面一个

while(itBegin!=itEnd){
    itBegin++;
}

for(vector<int>::iterator itBegin=V.begin();itBegin!=V.end();itBegin++){
    
}

#include <algorithm>
for_each(V.begin(),V.end(),要运行的函数,参数默认为V里的每个数);

技巧：*it为尖括号里面的东西
int等价于*it
    
vector<vector<int>> VV;
vector<vector<int> V;

VV.push_back(V);
VV的*it为vector
所以:
for(it){
    for(vit=it->begin()){

    }
}


```

string

```c++
const char* str=""
string s(str);
s=str;
s.assign(str);
s.assign(str,3);#前几个
s.assign(s1);
    
string s1(s);
s1=s;
string s2(10,'a');

s+=s1;
s+=str;

s.append(s1,3,2)#拼接从3开始，往后2个的字符
    
int pos=s.find(str);#返回第一个位置，位置从0开始算
if(pos==-1){
    cout<<"没有找到"<<endl;
}

int pos=s.rfind(str);#从右往左查找
s.replace(1,3,"1111");#从1开始替换，后面三个字符串替换为后面的东西
    
int res=s.compare(s1)
res==0：相等
res==1：s大
```



set（关联式容器：二叉树）

multiset（允许有重复）

只有insert

```c++
set<int>se;
se.insert(10);

printSet(se);
void printSet(set<int>&se){
	for(set<int>::iterator it=se.begin();it!=s.end();it++){
		cout<<*it<<endl;
	}
}

set<int>se1(se);#拷贝构造
se1=se;#这样也可以

if(se.empty()){
	cout<<"为空"<<endl;
}
se.size();
se.swap(se1);#两个里面的东西会交换
se.erase(se.begin());#此处的begin()是排序后的第一个
se.erase(se.begin(),se.end());#清空
se.clear();#清空
se.erase(30);

set<int>::iterator pos=se.find(30);
if(pos!=se.end()){
    cout<<*pos<<endl;
}

int num=se.count(30);#统计30的个数，都是1或者0

    
自定义：
class CPerson{
public:
    CPerson(string name,int age){
		this->inName=name;
         this->inAge=age;
    }
    string inName;
    int inAge;
}
    
class CSortPerson{
public:
    bool operator()(const CPerson & CP2,const CPerson & CP3){
        return CP2.inAge>CP3.inAge;
    }
}
#安装年龄排序
set<CPerson,CSortPerson>se;
CPerson CP1("Tom",18);
se.insert(CP1);
for(set<CPerson,CSortPerson>::iterator it=se.begin()...){
    cout<<it->inName;
}
```

pair

```c++
pair<str,int>p("tom",20);
pair<str,int>p2=make_pair("tom",20);
cout<<p.first<<endl;

p.second

```

仿函数更改排序

```
class CSort{
public:
	bool operator()(int v1,int v2){
		return v1>v2;
	}
}

set<int,CSort>se;

for(set<int,CSort>::iterator it=se.begin...){

}
#可能需要加const

```

模板：

```c++
template<class T>
    void mySort(T arr[],int len){
    for(int i=0;i<len;i++){
		int max=i;
         for(int j=i+1;j<len;j++){
             if(arr[max]<arr[j]){
                 max=j;
             }
         }
         if(max!=i){
             
         }
    }
}
```

函数模板

```c++
template<class T>
T myfunc(T a,T b){
	return a+b;
}

myfunc<int>(a,b);//a和b可以不是一种类型（含有隐式类型转换）
myfunc(a,b);//a和b必须是一种类型，因为有二义性
//但是都不能传引用
```

