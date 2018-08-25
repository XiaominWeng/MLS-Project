## Python Basic Assginment 2.1

**学习python中类的使用**

*个人理解，类是实际世界中事物或者事件的抽象，对象是类实例化之后的具体的一个个事物或事件。*

**本节任务：**
新建一个名为Person的class

定义其“构造函数”（初始化函数），实现功能：在实例化一个对象的时候，能同时定义Person的FirstName, LastName, Gender, Age。
用以下代码进行简单测试：

```
# decline a object named SunPei with class Person, meanwhile define its parameters
SunPei = Person(FirstName='Pei', LastName='Sun', Gender='M', Age=18)
# call and print SunPei's age to test 
print("SunPei's age is: ", SunPei.Age)
```
