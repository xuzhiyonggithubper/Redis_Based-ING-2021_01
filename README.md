# Java_Interview_Review-ING-2021_01
### 1.Java线程的状态

- **初始(NEW)**：新创建了一个线程对象，但还没有调用start()方法。

- **运行(RUNNABLE)**：Java线程中将就绪（ready）和运行中（running）两种状态笼统的称为“运行”。
  线程对象创建后，其他线程(比如main线程）调用了该对象的start()方法。该状态的线程位于可运行线程池中，等待被线程调度选中，获取CPU的使用权，此时处于就绪状态（ready）。就绪状态的线程在获得CPU时间片后变为运行中状态（running）。

- **阻塞(BLOCKED)**：表示线程阻塞于锁。

- **等待(WAITING)**：进入该状态的线程需要等待其他线程做出一些特定动作（通知或中断）。

- **超时等待(TIMED_WAITING)**：该状态不同于WAITING，它可以在指定的时间后自行返回。

- **终止(TERMINATED)**：表示该线程已经执行完毕。

### 2.进程和线程的区别，进程间如何通讯，线程间如何通讯
- **进程和线程定义**：一个程序至少有一个进程，一个进程至少有一个线程。
- **进程间通信原理**
  - **管道( pipe )** ： 管道是一种半双工的通信方式，数据只能单向流动，而且只能在具有亲缘关系的进程间使用。进程的亲缘关系通常是指父子进程关系 。
  -  **有名管道 (namedpipe)** ： 有名管道也是半双工的通信方式，但是它允许无亲缘关系进程间的通信。 
  - **信号量(semophore )**  ： 信号量是一个计数器，可以用来控制多个进程对共享资源的访问。它常作为一种锁机制，防止某进程正在访问共享资源时，其他进程也访问该资源。因此，主要作为进程间以及同一进程内不同线程之间的同步手段。 
  - **消息队列( messagequeue )** ： 消息队列是由消息的链表，存放在内核中并由消息队列标识符标识。消息队列克服了信号传递信息少、管道只能承载无格式字节流以及缓冲区大小受限等缺点。 
  - **信号 (sinal )**  ： 信号是一种比较复杂的通信方式，用于通知接收进程某个事件已经发生。 
  - **共享内存(shared memory )** ： 共享内存就是映射一段能被其他进程所访问的内存，这段共享内存由一个进程创建，但多个进程都可以访问。共享内存是最快的 IPC 方式，它是针对其他进程间通信方式运行效率低而专门设计的。它往往与其他通信机制，如信号两，配合使用，来实现进程间的同步和通信。 
  - **套接字(socket )**  ： 套接口也是一种进程间通信机制，与其他通信机制不同的是，它可用于不同设备及其间的进程通信。  
- **线程间通信原理**
  - **锁机制**：包括互斥锁、条件变量、读写锁 。互斥锁提供了以排他方式防止数据结构被并发修改的方法；读写锁允许多个线程同时读共享数据，而对写操作是互斥的；条件变量可以以原子的方式阻塞进程，直到某个特定条件为真为止。对条件的测试是在互斥锁的保护下进行的。条件变量始终与互斥锁一起使用。
  - **信号量机制(Semaphore)**：包括无名线程信号量和命名线程信号量 
  - **信号机制(Signal)**：类似进程间的信号处理线程间的通信目的主要是用于线程同步，所以线程没有像进程通信中的用于数据交换的通信机制。 

### 3.HashMap、HashTable、ConcurrentHashMap

- **HashMap**
  - **数据结构**：JDK1.8之前数组+链表，JDK1.8后数组+链表（红黑树），哈希碰撞本质由链表或树结构进行解决。
- **HashTable**
  - **数据结构**：链表。
- **ConcurrentHashMap**
  - **数据结构JDK1.7**： Segment + HashEntry + Unsafe 
  - **数据结构JDK1.8**： Synchronized + CAS + Node + Unsafe 

### 4.Cookie和Session的区别

### 5.索引有什么用？如何建索引？索引类型有哪些？
### 6.ArrayList是如何实现的，ArrayList和LinkedList的区别？ArrayList如何实现扩容。
### 7.equals方法实现
### 8.面向对象
1. 封装
2. 继承
3. 多态
### 9.线程状态，BLOCKED和WAITING有什么区别
### 10.JVM如何加载字节码文件
### 11.JVM GC，GC算法。
### 12.什么情况会出现Full GC，什么情况会出现yong GC
### 13.JVM内存模型
### 14.Java运行时数据区
### 15.事务的实现原理
### 16.有没有看过JDK源码，看过的类实现原理是什么。
### 17.HTTP协议
### 18.TCP协议
### 19.一致性Hash算法
### 20.JVM如何加载字节码文件
### 21.类加载器如何卸载字节码
### 22.IO和NIO的区别，NIO优点
### 23.Java线程池的实现原理，keepAliveTime等参数的作用。
### 24.HTTP连接池实现原理
### 25.数据库连接池实现原理
### 26.数据库的实现原理
### 27.看过哪些开源框架的源码
### 28.为什么要用Redis，Redis有哪些优缺点？Redis如何实现扩容？
### 29.Netty是如何使用线程池的，为什么这么使用
### 30.为什么要使用Spring，Spring的优缺点有哪些
### 31.Spring的IOC容器初始化流程
### 32.Spring的IOC容器实现原理，为什么可以通过byName和ByType找到Bean
### 33.Spring AOP实现原理
### 34.消息中间件是如何实现的，技术难点有哪些
### 35.如何搭建一个高可用系统
### 36.哪些设计模式可以增加系统的可扩展性
### 37.介绍设计模式，如模板模式，命令模式，策略模式，适配器模式、桥接模式、装饰模式，观察者模式，状态模式，访问者模式。
### 38.抽象能力，怎么提高研发效率。
### 39.什么是高内聚低耦合，请举例子如何实现
### 40.什么情况用接口，什么情况用消息
### 41.如果AB两个系统互相依赖，如何解除依赖
### 42.如何写一篇设计文档，目录是什么
### 43.什么场景应该拆分系统，什么场景应该合并系统
### 44.系统和模块的区别，分别在什么场景下使用
### 45.分布式事务，两阶段提交
### 46.如何实现分布式锁
### 47.如何实现分布式Session
### 48.如何保证消息的一致性
### 49.负载均衡
### 50.正向代理（客户端代理）和反向代理（服务器端代理）
### 51.CDN实现原理
### 52.怎么提升系统的QPS和吞吐量
### 53.有没有处理过线上问题？出现内存泄露，CPU利用率标高，应用无响应时如何处理的。
### 54.开发中有没有遇到什么技术问题？如何解决的
### 55.如果有几十亿的白名单，每天白天需要高并发查询，晚上需要更新一次，如何设计这个功能。
### 56.新浪微博是如何实现把微博推给订阅者
### 57.Google是如何在一秒内把搜索结果返回给用户的。
### 58.12306网站的订票系统如何实现，如何保证不会票不被超卖。
### 59.如何实现一个秒杀系统，保证只有几位用户能买到某件商品。
### 60.如何学习一项新技术，比如如何学习Java的，重点学习什么
### 61.有关注哪些新的技术
### 62.工作任务非常多非常杂时如何处理
### 63.项目出现延迟如何处理
### 64.和同事的设计思路不一样怎么处理
### 65.如何保证开发质量
### 66.职业规划是什么？短期，长期目标是什么
### 67.团队的规划是什么
### 68.能介绍下从工作到现在自己的成长在那里