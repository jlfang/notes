# 你应该知道的JAVA面试题

## 基础题目

### 1. Java线程的状态

- 新建（NEW）
- 可运行（RUNNABLE）
- 运行（RUNNING）
- 阻塞（BLOCKED）
- 死亡（DEAD）

### 10. JVM如何加载字节码文件

加载->连接(验证->准备->解析)->初始化->使用->卸载

### 11. JVM GC， GC算法

- GC算法
  - 标记清除
  - 复制
  - 标记整理
- JVM GC
  - Serial（Young）
  - ParNew（Young）
  - Parallel Scavenge（Young）
  - Serial Old （Tenured）
  - Parallel Old （Tenured）
  - CMS （Tenured）
  - G1

### 12. 什么情况会出现Full GC，什么情况会出现yong GC。

Full GC:

- 老年代空间不足
- Permanet Generation（永久代）空间满
- CMS GC时出现promotion failed和concurrent mode failure
  - promotion failed: 进行Minor GC时，survivor space 放不下，只能放入老年代，而此时老年代也放不下
  - concurrent mode failure: 执行CMS GC的过程中同时由对象要放入老年代，而此时老年代空间不足
- 统计得到的Minor GC晋升到老年代的平均大小大于老年代的剩余空间
- 使用远程方法调用-RMI（Remote Method Invocation）来实现远程过程调用-RPC（Remote Process Call），默认的情况会1个小时执行1次Full GC

### 13. JVM内存模型（JMM）

  JMM的目的是为了解决Java多线程对共享数据的读写一致性问题，通过Happens-Before语义定义了Java程序对数据的访问规则，修正之前由于读写冲突导致的Cache数据不一致的问题。具体到Hotspot VM的实现，主要是由OrderAccess类定义的一些列的读写屏障来实现JMM的语义。

### 14. Java运行时数据区

- 程序计数器
- 虚拟机栈
- 本地方法栈
- 方法区
  - 运行时常量池
- 堆
- 直接内存（不是虚拟机运行时数据区的一部分，也不是Java虚拟机规范中定义的内存区域）

### 15. 事务的实现原理

