# 密封类
密封类用于限制继承，在密封类引入之前，java可以使用final关键字修改class，被final修饰的类不可以被继承，但是如果希望类只能被特定范围的类继承呢？seated class解决了这个问题。

## 密封类的声明和语法
使用sealed和permits关键字声明一个密封类
```java
public sealed class Animal permits Cat, Dog {
    
}
```
代码中的Cat和Dog和Animal在同一个模块或者同一个包下面。


## 对于密封类子类的限制

## 密封类接口

## 作为record类的密封类子类

## Narrowing Reference Conversion and Disjoint Types

## 关于密封类和子类的相关API