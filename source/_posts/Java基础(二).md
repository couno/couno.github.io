---
title: Java基础(二)
date: 2022-10-10 16:55:31
tags: java
---

# java 对象和类

> 那么什么是类，什么是对象呢？

Java作为一种面向对象语言。支持以下基本概念：

- 多态
- 继承
- 封装
- 抽象
- 类
- 对象
- 实例
- 方法
- 重载

什么是**对象**：对于对象的理解，对象是类的一个实例，有状态和行为。它是创造出来的，实现某个类

**类**：类是一个一个模板，它描述对象的行为和状态

比如：dog类。那么哈士奇就是它的一个对象。它有着dog类的行为和特点



![image-20221010170038631](C:\Users\mo\AppData\Roaming\Typora\typora-user-images\image-20221010170038631.png)



## java类

一个类可以包含以下类型变量：

- **局部变量**：在方法、构造方法或者语句块中定义的变量被称为局部变量。变量声明和初始化都是在方法中，方法结束后，变量就会自动销毁。
- **成员变量**：成员变量是定义在类中，方法体之外的变量。这种变量在创建对象的时候实例化。成员变量可以被类中方法、构造方法和特定类的语句块访问。
- **类变量**：类变量也声明在类中，方法体之外，但必须声明为 static 类型。

一个类可以拥有多个方法，在上面的例子中：eat()、run()、sleep() 和 name() 都是 Dog 类的方法。

对于类的理解，相当于模板的使用，不仅使代码更为简单明了，也为了让代码执行效率大幅度提升。

对于代码的冗余和bug的排除，做出了巨大贡献



### 构造方法

每个类都有构造方法。如果没有显式地为类定义构造方法，Java 编译器将会为该类提供一个默认构造方法。

在创建一个对象的时候，至少要调用一个构造方法。<span style="color:red">构造方法的名称必须与类同名，**一个类可以有多个构造方法**。</span>

下面是一个构造方法示例：

```java
public class Puppy{
    public Puppy(){
    }
 
    public Puppy(String name){
        // 这个构造器仅有一个参数：name
    }
}
```

### 创建对象

对象是根据类创建的。在Java中，使用关键字 new 来创建一个新的对象。创建对象需要以下三步：

- **声明**：声明一个对象，包括对象名称和对象类型。
- **实例化**：使用关键字 new 来创建一个对象。
- **初始化**：使用 new 创建对象时，会调用构造方法初始化对象。

```java
public class Puppy{
   public Puppy(String name){
      //这个构造器仅有一个参数：name
      System.out.println("小狗的名字是 : " + name ); 
   }
   public static void main(String[] args){
      // 下面的语句将创建一个Puppy对象
      Puppy myPuppy = new Puppy( "tommy" );
   }
}
```

调用时：

- 关于构造函数，当对象实例创建时，这时候，将会首先调用类中的构造函数，然后调用实例中的构造函数。

## 源文件声明规则

在本节的最后部分，我们将学习源文件的声明规则。当在一个源文件中定义多个类，并且还有import语句和package语句时，要特别注意这些规则。

- 一个源文件中只能有一个 public 类
- 一个源文件可以有多个非 public 类
- 源文件的名称应该和 public 类的类名保持一致。例如：源文件中 public 类的类名是 Employee，那么源文件应该命名为Employee.java。
- 如果一个类定义在某个包中，那么 package 语句应该在源文件的首行。
- 如果源文件包含 import 语句，那么应该放在 package 语句和类定义之间。如果没有 package 语句，那么 import 语句应该在源文件中最前面。
- import 语句和 package 语句对源文件中定义的所有类都有效。在同一源文件中，不能给不同的类不同的包声明。

类有若干种访问级别，并且类也分不同的类型：抽象类和 final 类等。这些将在访问控制章节介绍。

除了上面提到的几种类型，Java 还有一些特殊的类，如：[内部类](https://www.runoob.com/java/java-inner-class.html)、[匿名类](https://www.runoob.com/java/java-anonymous-class.html)。

## Java 包

包主要用来对类和接口进行分类。当开发 Java 程序时，可能编写成百上千的类，因此很有必要对类和接口进行分类。

## import 语句

在 Java 中，如果给出一个完整的限定名，包括包名、类名，那么 Java 编译器就可以很容易地定位到源代码或者类。import 语句就是用来提供一个合理的路径，使得编译器可以找到某个类。

例如，下面的命令行将会命令编译器载入 java_installation/java/io 路径下的所有类

```
import java.io.*;
```



---

# java基本数据类型

## Java 的两大数据类型:

- 内置数据类型
- 引用数据类型

## 内置数据类型

java中提供了8种数据类型

1. byte（8位）
2. short（16位）
3. int（32位）
4. long（64位）
5. float（32位，单精度）
6. double（64位，双精度）
7. boolean（1位）
8. char（16位）



## java常量

常量在运行时不能更改

格式：

```java
final double PI = 3.1415927;
```

## Java中自动类型转换

**整型、实型（常量）、字符型数据可以混合运算。运算中，不同类型的数据先转化为同一类型，然后进行运算。**

转换从低级到高级。

```
低  ------------------------------------>  高

byte,short,char—> int —> long—> float —> double 
```

 在把容量大的类型转换为容量小的类型时必须使用强制类型转换。

- 转换的过程可能会导致精度损失。就比如说

	```java
	int i =128;   
	byte b = (byte)i;
	```

	

因为 byte 类型是 8 位，最大值为127，所以当 int 强制转换为 byte 类型时，值 128 时候就会导致溢出。

- 浮点数到整数是舍去小数部分，而不是四舍五入

<span style="color:red">自动转换只能小转大，大转小需要强制转换</span>

```java
public class ZiDongLeiZhuan{
        public static void main(String[] args){
            char c1='a';//定义一个char类型
            int i1 = c1;//char自动类型转换为int
            System.out.println("char自动类型转换为int后的值等于"+i1);
            char c2 = 'A';//定义一个char类型
            int i2 = c2+1;//char 类型和 int 类型计算
            System.out.println("char类型和int计算后的值等于"+i2);
        }
}
```



# 变量类型

在Java语言中，所有的变量在使用前必须声明

Java语言支持的变量类型有：

- 类变量：独立于方法之外的变量，用 static 修饰。
- 实例变量：独立于方法之外的变量，不过没有 static 修饰。
- 局部变量：类的方法中的变量。

```java
public class Variable{
    static int allClicks=0;    // 类变量
 
    String str="hello world";  // 实例变量
 
    public void method(){
 
        int i =0;  // 局部变量
 
    }
}		
	
```

### 局部变量

声明在方法中，构造方法，或语句块中。只有当方法，构造方法，或语句块被调用，局部变量才会被创建，并且当它执行完毕，变量将会被销毁、<span style="color:red">局部变量没有默认值，所以局部变量被声明后必须经过初始化，才能被使用</span>

错误案例：

```java
package com.runoob.test;
 
public class Test{ 
   public void pupAge(){
      int age;
      // 这里的age没有被初始化，所以报错
      age = age + 7;
      System.out.println("小狗的年龄是 : " + age);
   }
   
   public static void main(String[] args){
      Test test = new Test();
      test.pupAge();
   }
}
```

### 实例变量

- 实例变量在对象创建的时候创建，在对象被销毁的时候销毁；

实例：

```java
import java.io.*;
public class Employee{
   // 这个实例变量对子类可见
   public String name;
   // 私有变量，仅在该类可见
   private double salary;
   //在构造器中对name赋值
   public Employee (String empName){
      name = empName;
   }
   //设定salary的值
   public void setSalary(double empSal){
      salary = empSal;
   }  
   // 打印信息
   public void printEmp(){
      System.out.println("名字 : " + name );
      System.out.println("薪水 : " + salary);
   }
 
   public static void main(String[] args){
      Employee empOne = new Employee("RUNOOB");
      empOne.setSalary(1000.0);
      empOne.printEmp();
   }
}
```

### 类变量（静态变量）

类变量也称为静态变量，在类中以 static 关键字声明，但必须在方法之外。

**无论一个类创建了多少个对象，类只拥有类变量的一份拷贝**

静态变量在第一次被访问时创建，在程序结束时销毁

静态变量可以通过：*ClassName.VariableName*的方式访问。

```java
private static double salary;
public static final String DEPARTMENT = "开发人员";
其他类访问如果想访问DEPARTMENT
    使用  类名.DEPARTMENT
```

# 修饰符

java主要提供两种修饰符

- 访问修饰符
- 非访问修饰符

> 四个访问修饰符

Java中，可以使用访问控制符来保护对类、变量、方法和构造方法的访问。Java 支持 4 种不同的访问权限。

- **default** (即默认，什么也不写）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。
- **private** : 在同一类内可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**
- **public** : 对所有类可见。使用对象：类、接口、变量、方法
- **protected** : 对同一包内的类和所有子类可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**。

![image-20221010222631305](https://blog-img-1309454986.cos.ap-nanjing.myqcloud.com/image-20221010222631305.png)



**私有访问修饰符-private**：私有访问修饰符是最严格的访问级别，所以被声明为 **private** 的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为 **private**。

声明为私有访问类型的变量只能通过类中公共的 getter 方法被外部类访问。

**公有访问修饰符-public**：被声明为 public 的类、方法、构造方法和接口能够被任何其他类访问。

**受保护的访问修饰符-protected**：

protected 需要从以下两个点来分析说明：

- **子类与基类在同一包中**：被声明为 protected 的变量、方法和构造器能被同一个包中的任何其他类访问；
- **子类与基类不在同一包中**：那么在子类中，子类实例可以访问其从基类继承而来的 protected 方法，而不能访问基类实例的protected方法。

### 访问控制和继承

请注意以下方法继承的规则：

- 父类中声明为 public 的方法在子类中也必须为 public。
- 父类中声明为 protected 的方法在子类中要么声明为 protected，要么声明为 public，不能声明为 private。
- 父类中声明为 private 的方法，不能够被子类继承。



## static修饰符

静态变量：无论一个类实例化多少对象，它的静态变量只有一份拷贝。静态变量也被称为类变量。局部变量不能被声明为static变量

静态方法：static关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法在数据列表中拿到数据，然后计算数据



## final修饰符

final表示“最后的；最终的”含义，变量一旦赋值后，不能被重新赋值。

父类中的**final方法**可以被子类继承，但不能重写

声明 final 方法的主要目的是防止该方法的内容被修改。



**final 类**不能被继承，没有类能够继承final类的任何特性



## abstract修饰符

抽象类不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充

一个 类不能同时被abstract和final修饰。

如果一个类有抽象方法，那么这个类也必须是抽象类。否则会编译失败

抽象类可以包含抽象方法和非抽象方法

### 抽象方法

抽象方法不能被声明成 final 和 static。

任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。

如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。

抽象方法是一种没有任何实现的方法，该方法的具体实现由子类提供。

抽象方法的声明以分号结尾

## synchronize修饰符

synchronized 关键字声明的方法同一时间只能被一个线程访问

## transient修饰符

序列化的对象包含被 transient 修饰的实例变量时，java 虚拟机(JVM)跳过该特定的变量。

该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型。

```java
public transient int limit = 55;   // 不会持久化
public int b; // 持久化
```

## volatile修饰符

volatile 修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。而且，当成员变量发生变化时，会强制线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值。

一个 volatile 对象引用可能是 null。

```java
public class MyRunnable implements Runnable
{
    private volatile boolean active;
    public void run()
    {
        active = true;
        while (active) // 第一行
        {
            // 代码
        }
    }
    public void stop()
    {
        active = false; // 第二行
    }
}
```

通常情况下，在一个线程调用 run() 方法（在 Runnable 开启的线程），在另一个线程调用 stop() 方法。 如果 ***第一行\*** 中缓冲区的 active 值被使用，那么在 ***第二行\*** 的 active 值为 false 时循环不会停止。

但是以上代码中我们使用了 volatile 修饰 active，所以该循环会停止。
