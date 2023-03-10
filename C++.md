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
>length()函数类似于C语言中的strlen()函数
需要注意的是，计算结果不包括字符串末尾结束标志符“\0”。

###面向对象

#### class关键字
* 类的定义
```
class MyClass
{
    public:
        ...
    priva:
        ...
};
```
**<font color=red>请注意class定义最后的分号！！！</font>**

#### 关键字修饰类成员

* **const**
>在程序设计中有些数据也不希望被改变，只允许读取。对于不希望被改变的数据，可以使用const关键字修饰。在类中，const既可以修饰类的成员变量，也可以修饰类的成员函数

- **变量**
    **使用const修饰的成员变量称为常成员变量。对于常成员变量，仅仅可以读取第一次初始化的数据，之后是不能修改的。常成员变量通常使用有参构造函数进行初始化。**

- **函数**
    1. **使用const修饰的成员函数称为常成员函数。与修饰成员变量不同的是，修饰成员函数时，const位于成员函数的后面，其格式如下**：
        ```
        返回值类型  函数名() const; 
        ```
    2. **在常成员函数内部，只能访问类的成员变量，而不能修改类的成员变量；并且，常成员函数只能调用类的常成员函数，而不能调用类的非常成员函数**



* **static**
    1. **static修饰成员变量static修饰的静态成员变量只能在类内部定义，在类外部初始化。静态成员变量在调用时，可以通过对象和类进行访问。由于static成员变量存储在类的外部，计算类的大小时不包含在内。**
    2. **static修饰成员函数类中定义的普通函数只能通过对象调用，无法使用类调用。使用static修饰的成员函数，同静态成员变量一样，可以通过对象或类调用。**

#### 友元
* 友元函数
    1. 普通函数作为友元函数
    2. 其他类的成员函数作为友元函数
* 友元类
    将一个类声明为友元类，友元类可以声明在类中任意位置。声明友元类之后，友元类中的所有成员函数都是该类的友元函数，能够访问该类的所有成员。


使用友元需要注意以下几点：
1. 友元声明位置由程序设计者决定，且不受类中public、private、protected权限控制符的影响。
2. 友元关系是单向的，即类A是类B的友元，但B不是A的友元。
3. 友元关系不具有传递性，即类C是类D的友元，类E是类C的友元，但类E不是类D的友元。
3. 友元关系不能被继承。