### 命名空间

```
using namespace std
```

>**std是C++标准命名空间，由于C++标准库几乎都定义在std命名空间中，因此编写的所有C++程序都需要引入下列语句**

#### 匿名命名空间

```
namespace
{
    ...
}
```
编译器在编译阶段会为匿名命名空间生成唯一的名字，这个名字是不可见的。除此之外，编译器还会为这个匿名命名空间生成一条using指令。编译后的匿名命名空间等效于下面的代码：
```
namespace _UNIQUE_NAME_
{

}
using namespace _UNIQUE_NAME_;
```
**匿名命名空间的作用是限制命名空间的内容<font color=red>仅能被当前源文件使用，其他源文件是无法访问的</font>，使用extern声明访问也是无效的。**


#### cin cout

cin，cout定义在头文件iostream中，类似于C中的scanf(),prinf()函数。
```
// 输入单个变量 
char c1,c2; 
cin>>c1; //控制台的输入赋值给c1
cin>>c2; //控制台的输入赋值给c2
// 输入多个变量 
string s; 
float f; 
cin>>s>>f;
```

#### 类型增强
◆ C++对C语言的扩充

>> 常变量类型const使用const修饰的变量称为常变量，C语言中的常变量可以通过指针修改，而C++中的常变量无法通过指针间接修改。

#### string

* *swap()*
>可以通过 string.swap(string)调用
 也可以 swap(string, string)调用
string的成员函数swap()只能交换string类型的字符串，不能交换C语言风格的字符串

* *length()*