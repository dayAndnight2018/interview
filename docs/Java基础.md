# Java基础
`by: 程序员·小李`

> JRE和JDK有什么异同？

JRE是Java运行时环境(Java Runtime Environment)的简称，是Java程序运行所需要的必要工具。JDK是Java开发包(Java Development Kit)的简称，是开发Java程序所需要的环境。一般，JDK中包含JRE。

> ==与equals有什么区别？

双等号判断在值类型中比较的是值的大小，对引用类型比较的是引用，也就是内存地址。而equals方法本质上等价于双等号，但是可以重写来达到自己的目的，例如String类型的equals方法就是比较两个字符串是否完全一致，而不是内存地址。而使用intern方法获取到的字符串是从常量池中取到的，常量池中不存在时，也会从堆中加载一份到常量池。

通过重写hashCode和equals方法可以实现equals个性化判断，也便于HashMap和HashSet的使用。

> hashCode与equals的关系

hashCode相同是无法保证equals方法返回true的，因为hash值很大程度上会重合。反过来，equals返回true，那么hashCode是一定相同的。

> 代码块的优先级关系

单个类中，静态代码块 > 普通代码块 > 构造方法，并且静态代码块在类加载的时候执行，仅执行一次。

包含继承关系的类中，父类静态代码块 > 子类静态代码块 > 父类代码块 > 父类构造器 > 子类代码块 > 子类构造器

> final关键字有什么作用？

1. 修饰类，防止被继承

2. 修饰方法，防止被重写

3. 修饰变量，防止重复赋值

> Math. round中，1.5和-1.5的结果是多少？

2和-1.

> 八大基本数据类型？

byte、boolean、char、 short、int、float、long、double

> 字符串操作类有哪些？

String，StringBuilder，StringBuffer。因为字符串类型是不可变的，因此String在操作时，会生成新的对象。StringBuilder和StringBuffer适合操作字符串的拼接操作，其中StringBuilder是非线程安全的，StringBuffer是线程安全的。

> String str="i"与 String str=new String("i")一样吗?

前者分配到常量池，后者分配到堆内存，二者内存地址不同。

> 普通类和抽象类有哪些区别?

普通类不能包含抽象方法，抽象类可以包含抽象方法。
  
抽象类不能直接实例化，普通类可以直接实例化。

> 接口和抽象类有什么区别?

1. 抽象类可以有构造函数;接口不能有。

2. 类可以实现很多个接口;但是只能继承一个抽象类。

3. 接口中的方法默认使用 public 修饰;抽象类中的方法可以是任意访问修饰符。

> BIO、NIO、AIO 有什么区别?

BIO:同步阻塞式IO，就是我们平常使用的传统IO，它的特点是模式简单使用方便，并发处理能力低。

NIO:同步非阻塞IO，是传统IO的升级，客户端和服务器端通过Channel(通道)通讯，实现了多路复用。

AIO:是NIO的升级，也叫NIO2，实现了异步非堵塞IO，异步IO的操作基于事件和回调机制。



