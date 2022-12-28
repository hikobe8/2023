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