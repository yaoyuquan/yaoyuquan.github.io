# Record Classes
record class是一种特殊的类，可以存储不可变对象，在这里我们可以参考python中的元组（tuple）的概念
record的声明语法包括：类名，类型参数（record class 支持泛型），header（包含了record class中的所有字段）和body（类定义）
record class会自动生成如下的类成员
* 对于header中声明的每个成员，自动生成一个private final的字段和public的accessor方法
* 一个构造方法，该构造方法的参数和header中声明的字段保持一一对应。
* 自动生成的equals()和hashCode()方法
* 自动生成的toString()方法，可以返回所有字段的名称和值。
## 构造方法
虽然构造方法可以自动生成，也可以自己去写一个构造方法， 并在方法中加入一些自定义的逻辑。
```java
record User (int userId, String username, String password) {

    public User(int userId, String username, String password) {
        if(username == null) {
            throw new IllegalArgumentException("username can not be null");
        }
        this.userId = userId;
        this.password = password;
        this.username = username;
    }
}

```
构造方法的方法签名和赋值的代码可以省去，如下为简写模式
```java
record User (int userId, String username, String password) {

    public User {
        if(username == null) {
            throw new IllegalArgumentException("username can not be null");
        }
    }
}
```
## record class的类成员
* record class中可以定义静态方法和静态成员
* record class中可以重写在header中定义的成员accessor方法，注意，签名要保持一致
* record class中不能定义实例方法
* record class中可以定义内部类，或者内部record class