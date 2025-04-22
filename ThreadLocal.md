### 1.
ThreadLocal 是 Java 中的一个类，它提供了线程本地变量（Thread-Local Variables）的功能。线程本地变量是指每个线程都有自己的独立变量副本，这些变量在线程之间是隔离的，无法被其他线程访问。ThreadLocal 类主要用于在多线程环境中为每个线程提供独立的变量实例，从而避免线程安全问题。

### 2.
各个线程分别使用threadLocal.get(),.set()存放和获取本地变量互补干扰

### 3.使用场景
切面通常要用到这个类，普通类属性是被所有线程共享的。在多线程环境下，多个线程同时执行 doBefore 和 doAfterReturning 方法时，会互相覆盖 webLogData 的值。例如，线程 A 设置了 webLogData，但在其执行 doAfterReturning 之前，线程 B 可能已经修改了 webLogData，导致线程 A 获取到错误的数据。
他解决的不是数据并发操作时的一致性问题
