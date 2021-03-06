# 适配器模式

## 实现功能：

模拟三相插头 插入二相插口，其中适配器相当于插头转换器

## 动机

将一个类的接口，**通过适配器**转换成另外一个期望的接口。（使原本不兼容的接口 而能够相互兼容一起工作）这就是适配器模式的模式动机。

接口A（实际接口）  ===适配器（转换的过程）====》 接口B（不同的，期望的接口）

比如： 三相插头  ===适配器（插口转换器）====》 两相插口

## 定义

适配器模式将一个类的接口转换成期望的另一个接口，使得原本不能一起工作的类可以在一起工作。

## 功能

适配器的实现就是把客户类的请求转化为对适配者的相应接口的调用。也就是说：当客户类调用适配器的方法时，在适配器类的内部将调用适配者类的方法，而这个过程对客户类是透明的，客户类并不直接访问适配者类。因此，适配器可以使由于接口不兼容而不能交互的类可以一起工作。

## 实现(两种)

对象适配器（组合方式）：实现期望接口，内部含有被适配类对象，实现方法中调用被适配类的原始方法

类适配器（继承方式）：实现期望接口，继承被适配类，实现方法中调用父类的原始方法

- Target：目标抽象类 客户端的目标接口
- Adapter：适配器类 实现期望接口，通过内部对被适配类实例的操作，成为期望接口的实例
- Adaptee：适配者类 一个已经实现的不兼容的类
- Client：客户类

## 应用

**只要把不兼容 变成兼容的就是适配器！**

JDBC数据库驱动，JDBC驱动做为数据库引擎（Mysql、Oracle、SQL Server等）与JDBC标准接口的一个桥梁（适配器软件）。

可以让开发人员在开发中，对数据库的操作透明，通过适配器(JDBC驱动)，实例化出目标接口（JDBC标准统一接口），对接口编程，更换不同的被适配类（各种数据库引擎）

*原文：http://www.i3geek.com/archives/1369*
*实现源代码：https://github.com/yangengzhe/coding-guide_i3geek/tree/master/docs/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F*