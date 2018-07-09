# Flink Internals

flink version: 1.5.0, commit: a702ca4

先来一段废话------  
不知不觉已经接触flink快一年了，对flink的内部原理还是一知半解。  
为了改变这个现状，我觉得记笔记是很有必要的，尽管刚开始可能会记录大量的流水账，但是到后面随着对flink的内部结构越来越熟悉，

## 学习原则

+ 遇到任何问题一定要刨根问底，不要停留在现象和一些浅层次的直观原因上，一定要找到本质。一个比较好的判定标志是你能不能一句话给别人讲清楚。要做到这个可能会让你一开始花更多的实践，甚至觉得自己学得比别人慢很多，但是你学过的每一东西都是完全吃透的，而很多东西的原理是相通的，在一段时间的积累后你会发现学任何新东西就像看说明书一样了。

+ 欲速则不达，贪多嚼不烂！

+ 横向对比类似的框架storm, spark, kafka, hadoop的设计的异同，优劣

+ 为何如此设计架构（整体的架构，核心机制）

+ 为何如此拆分模块（模块划分的粒度，模块的归类）

+ 为何如此抽象方法（方法的粒度，哪些方法应该被抽象）

+ 有趣的代码，为何用此种写法（性能，兼容性，安全，可维护性，设计模式，炫技）



## 将会对flink的设计有更新的体会。

本笔记主要讨论Apache Spark的设计与实现，重点关注其设计思想、运行原理、实现架构及性能调优，附带讨论其与spark在设计与实现上的区别。  
不喜欢将改文档称之为"源码分析"，因为本文的主要目的不是去解读实现代码，而是尽量有逻辑地，从设计与实现原理角度，来理解job从产生到执行的整个过程，  
进而去理解整个系统。

讨论系统的设计与实现有很多方式，本笔记选择问题驱动的方式，一开始引入问题，然后分问题逐步深入。从一个典型的job例子入手，逐渐讨论job生成及执行过程  
中所需要的系统功能支持，然后又选择地深入讨论一些功能模块的设计原理与实现方式。也许这样的方式比一开始就分模块讨论更加主线。

由于本人接触分布式领域不深，且本人技术水平，经验不足，如有谬论还请斧正！

## Contents

### storm, flink 对比

### overview总览 ， flink集群架构

### job逻辑执行图（数据依赖图）

### job的物理执行图

### flink的任务调度

### architecture 介绍系统模块如何协调完成整个job的执行

### job scheduling

### Fault-tolerance

## References

* &lt;[https://github.com/JerryLead/SparkInternals/tree/master/markdown](https://github.com/JerryLead/SparkInternals/tree/master/markdown)&gt;
* _循序渐进学Spark _&lt;[https://yuedu.163.com/source/b766363446c544fc9b487803baf1a8e7\_4](https://yuedu.163.com/source/b766363446c544fc9b487803baf1a8e7_4)&gt; 



