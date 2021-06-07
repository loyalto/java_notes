happens-before用来阐述多个线程操作共享变量的可见性问题，如果一个操作执行的结果需要对另一个操作可见，那么这两个操作必须要存在happens-before关系。

常见规则如下：

- 程序顺序规则，单线程下执行结果不变
- 传递性规则，A happens-before B，B happens-before C, A happens-before C
- volatile变量规则，volatile修饰的变量的写的操作，一定happens-before后续对于volatile变量的读操作
- 监视器锁规则，用synchronized修饰的
- start规则，start之前的写操作一定生效
- join规则，保证了可见性
- final规则，使用了内存屏障

