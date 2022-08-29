---
description: ⭐️⭐️⭐️⭐️
---

# 【2022-08-24】Scala中的final和sealed有什么区别？

1. final：禁止继承，重写，可用于类，字段，方法/函数。
2. sealed：允许同文件内继承，禁止被外部任何地方继承。可用于类，抽象类，特质。
3. 从整体上讲，如果将类型系统当作一个树，sealed主要用于构建ADTs，sealed trait是ADTs的根，而final case class是ADTs的叶子，这意味着该ADTs具有有限个数的子类，同时编译器能在编译期正确分析类型关系，故模式匹配是通常是安全的，而不安全的模式匹配通常会有编译警告。（排除编译器bug）这也是为什么要尽可能使用match而不是if的原因之一。if不具备模式分析（match analysis）。

谈到1.2点及格

能从类型系统的层次结构看，答到叶子+模式匹配，满分
