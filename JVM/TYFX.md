## 逃逸分析

一个对象指针被多个方法或者线程引用时，称为逃逸。

```java
public static Object GLOBAL_OBJECT;//静态变量外部线程可见，发生逃逸

public void method1(){
    return new Object();//外部线程可见，发生逃逸
}

public void method2(){
    Object object = new Object(); //仅创建线程可见，无逃逸
}
```

## 逃逸分析的优化

针对不会逃逸的对象，编译器会做一些优化

- 栈上分配：将堆分配转化为栈分配，随着栈的销毁而销毁，减轻GC压力。
- 同步消除：无逃逸对象不需要同步，会去掉同步锁运行。
- 标量替换：可以将一个对象拆散成它的成员变量使用，原本的对象无需整体分配空间。

## 参考

[JVM之逃逸分析](https://zhuanlan.zhihu.com/p/59215831)

