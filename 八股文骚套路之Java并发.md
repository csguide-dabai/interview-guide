并发这部分内容相对来说还是有一些难度的，并且，对于初学者来说最难的就是在项目中去实践。

如果你刚学完 Java 基础的话，我建议你学习并发这部分内容的时候，可以先简单地了解一下基础知识比如线程和进程的对比。到了后面，你对于 Java 了解的更深了之后，再回来仔细看看这部分的内容。

### 救急准备

下面的知识点都是要看的，我通过打星与加粗的方式对知识点的重要性进行评级！难度是针对互联网大厂的。

- ⭐ ：面试中不常问到，如果面试官问到尽量能答出来，答不出来也没关系。
- ⭐⭐ ：面试中不常问到，但是如果面试官问到的话，答不出来对你的印象会减分。
- ⭐⭐⭐：面试中会问到，答不出来面试有点悬。面试官会惊讶为什么你这也不会。
- ⭐⭐⭐⭐：面试高频考点。
- ⭐⭐⭐⭐⭐：面试超高频考点。四星考点和五星考点是参加十场面试，至少能有五场面试问到这些的。大家在准备面试过程中尽量把这些知识点的回答条理梳理清楚，面试官一问就开背。

**Java 并发常见面试题汇总** ：

1. 进程和线程的区别。【⭐⭐⭐⭐⭐】这是一个超高频考点，面试回答时别一句一个进程包含很多线程就没了。要答清楚什么是线程什么是进程，线程和进程各自的`运行状态`、线程的`通信方式`和进程的`通信方式`。
2. 创建线程的方式。【⭐⭐⭐⭐】不仅要把创建线程的方式记熟、记住各种方式的优缺点，还要能写出代码来。有的面试官是会让你写代码创建两个线程然后执行一些操作的，比如两个线程交替输出数字。
3. 什么是死锁，死锁如何产生，死锁如何避免。【⭐⭐⭐⭐⭐】超高频问题，几乎大厂的一面和二面都会问到。
4. 并发编程的三大特性（原子性、可见性以及有序性）。【⭐⭐⭐⭐】
5. `synchronized` 锁升级流程。【⭐⭐⭐⭐⭐】这又是面试八股文的一大考点，锁升级流程记清楚。
6. `volatile` 关键字。【⭐⭐⭐⭐⭐】对比和 `synchronized` 的区别。
7. `JMM`（Java Memory Model，Java 内存模型）和 `happens-before` 原则。【⭐⭐⭐⭐⭐】面试中重点！几乎必问。
8. `ThreadLocal`。【⭐⭐⭐⭐】这也是面试八股文的一个高频考点。我面试到后面不想背这里了，面试过程中就尽可能躲着这个知识点，不提到和这相关的，竟然真的苟过去了。
9. 线程池。【⭐⭐⭐⭐⭐】超高频考点。需要答出线程池有哪几种，各种线程池的优缺点，线程池的重要参数、线程池的`执行流程`、线程池的饱和策略、如何设置线程池的大小等等。这里也能背十几分钟。
10. `ReentrantLock` 和 `AQS`。【⭐⭐⭐⭐⭐】其实我在面试的时候对这里不是很熟，我面试的时候尽量不提到这里，也苟过去了。大家如果时间充足的话还是把这块好好理解一下。如果这里理解透彻了，也能在这里和面试官聊很久。
11. 乐观锁和悲观锁的区别。【⭐⭐⭐⭐⭐】
12. `CAS` 了解么？原理？什么是 ABA 问题？ABA 问题怎么解决？【⭐⭐⭐⭐⭐】`CAS`（Compare-and-Swap）绝对是面试中的高频中的高频，很多地方都用到了 `CAS` 比如 `ConcurrentHashMap` 采用 `CAS` 和 `synchronized` 来保证并发安全，再比如`java.util.concurrent.atomic`包中的类通过 `volatile+CAS` 重试保证线程安全性。和面试官聊 `CAS` 的时候，你可以结合 `CAS` 的一些实际应用来说。
13. `Atomic` 原子类【⭐⭐】
15. ......

由于篇幅问题，我并没有写上面这些问题的答案。你可以自行查阅，你也可以参考 JavaGuide 这个开源项目，涵盖了大部分 Java 程序员所需要掌握的核心知识。背面试八股文，这是一个必看的开源项目（学 Java 基础以及实战也推荐看这个项目）。

- Github 地址：https://github.com/Snailclimb/JavaGuide
- Gitee 地址：https://gitee.com/SnailClimb/JavaGuide（Github 无法访问或者访问速度比较慢的小伙伴可以看码云上的对应内容）
- 在线阅读地址: https://snailclimb.gitee.io/javaguide/#/

![](https://img-blog.csdnimg.cn/4673f6acf9ce45b6900d93a316bc884e.png)

## 系统学习

推荐大家跟着 **[《Java 并发实现原理：JDK 源码剖析》](https://book.douban.com/subject/35013531/)** 这部分来学习 Java 并发相关的知识。

![](https://img-blog.csdnimg.cn/b441699291684d0bbac0637822e1c1f3.png)

总体来说，市面上关于 Java 并发的书籍非常多，但是，大部分都是一些基础入门读物，真正讲原理的很少。然而，真正重要的就是这些原理知识。

这本书的整体内容如下，我简单概括一下：

- **第 1 章 多线程基础** ：讲了 Java 并发中比较重要的一些基础概念比如 `synchronized` 关键、`volatile` 关键字、JMM（Java Memory Model，Java 内存模型）和 happens-before 原则、 内存屏障、final 关键字、无锁编程。都是一些非常重要的概念，不论是对于你学习并发编程，还是说准备 Java 面试。
- **第 2 章 Atomic 类** ：不光讲了 `Atomic` 类（`AtomicInteger`、`AtomicLong` 、 `AtomicBoolean`、`AtomicReference` 、`AtomicStampedReference`、`AtomicMarkable` `Reference` 等等），还提到了悲观锁与乐观锁、Unsafe 的 CAS、自旋与阻塞、ABA 问题与解决办法等等比较重要的并发知识点。
- **第 3 章 Lock 与 Condition** ：主要讲了互斥锁（实现原理、源码分析）、读写锁 （实现原理、AQS、`WriteLock`、`ReadLock`）、`Condition`（使用场景、实现原理、源码分析） 。
- **第 4 章 同步工具类** ：这一张主要介绍了四个非常重要的并发类`Semaphore`、`CountDownLatch`、`CyclicBarrier`、`Exchanger`（用于线程间进行通信、数据交换的多线程交互工）、`Phaser`（和 `CyclicBarrier` 以及 `CountDownLatch` 很像，但是使用上更加的灵活。相关阅读：[Phaser 使用介绍](https://javadoop.com/post/phaser-tutorial)）。
- **第 5 章 并发容器** : 介绍了并发环境下使用的集合，包括 `BlockingQueue`、`BlockingDeque`、`CopyOnWrite`、 `ConcurrentLinkedQueue/ Deque`、`ConcurrentHashMap` 。
- **第 6 章 线程池与 Future** ： 从原理出发来讲解线程池！
- **第 7 章 ForkJoinPool** ：从原理出发来讲解 `ForkJoinPool` （JDK7 引入的线程池，支持将一个任务拆分成多个“小任务”并行计算，再把多个“小任务”的结果合成总的计算结果）。
- **第 8 章 CompletableFuture** ：介绍了 `CompletableFuture` 的常见用法以及原理。

如果你比较喜欢看视频的话，首推尚硅谷 2021 最新的**《JUC 并发编程系列》**。

![](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bf96aed069614714bc4a7048a8f0bfc1~tplv-k3u1fbpfcp-watermark.image)

这门课是我在网上看到的讲解并发编程的课程中最棒的一个！

老师将理论和实践结合，在实践中带你真正搞懂并发编程中的各种知识点。

公众号“**CS 指南**”后台回复“**尚硅谷**”可以领取尚硅谷这个系列完整的视频教程。

![](https://img-blog.csdnimg.cn/3da401c8c8c74e29884d8e39b5d5e378.png)

![](https://img-blog.csdnimg.cn/2021060517454068.png)