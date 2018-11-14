一.基础知识：

1）集合类：List和Set比较，各自的子类比较（ArrayList，Vector，LinkedList；HashSet，TreeSet）；

2）HashMap的底层实现，之后会问ConcurrentHashMap的底层实现；

3）如何实现HashMap顺序存储：可以参考LinkedHashMap的底层实现；

4）HashTable和ConcurrentHashMap的区别；

5）String,StringBuffer和StringBuilder的区别；

6）Object的方法有哪些：比如有wait方法，为什么会有；

7）wait和sleep的区别，必须理解；

8）JVM的内存结构，JVM的算法；

9）强引用，软引用和弱引用的区别；

10）数组在内存中如何分配；

11）用过哪些设计模式，手写一个（除单例）；

12）springmvc的核心是什么，请求的流程是怎么处理的，控制反转怎么实现的；

13）spring里面的aop的原理是什么；

14）mybatis如何处理结果集：反射，建议看看源码；

15）java的多态表现在哪里；

16）接口有什么用；

17）说说http,https协议；

18）tcp/ip协议簇；

19）osi五层网络协议；

20）tcp，udp区别；

21）用过哪些加密算法：对称加密，非对称加密算法；

22）说说tcp三次握手，四次挥手；

23）cookie和session的区别，分布式环境怎么保存用户状态；

24）git，svn区别；

25）请写一段栈溢出、堆溢出的代码；

26）ThreadLocal可以用来共享数据吗；



二.IO:

1）bio，nio，aio的区别；

2）nio框架：dubbo的实现原理；

3）京东内部的jsf是使用的什么协议通讯：可参见dubbo的协议；





三.算法：

1）java中常说的堆和栈，分别是什么数据结构；另外，为什么要分为堆和栈来存储数据。

2）TreeMap如何插入数据：二叉树的左旋，右旋，双旋；

3）一个排序之后的数组，插入数据，可以使用什么方法？答：二分法；问：时间复杂度是多少？

4）平衡二叉树的时间复杂度；

5）Hash算法和二叉树算法分别什么时候用；

6）图的广度优先算法和深度优先算法：详见jvm中垃圾回收实现；





三.多线程相关：

1）说说阻塞队列的实现：可以参考ArrayBlockingQueue的底层实现（锁和同步都行）；

2）进程通讯的方式：消息队列，共享内存，信号量，socket通讯等；

3）用过并发包的哪些类；

4）什么地方用了多线程；

5）Excutors可以产生哪些线程池；

6）为什么要用线程池；

7）volatile关键字的用法：使多线程中的变量可见；



四.数据库相关（mysql）：

1）msyql优化经验：

2）mysql的语句优化，使用什么工具；

3）mysql的索引分类：B+，hash；什么情况用什么索引；

4）mysql的存储引擎有哪些，区别是什么；

5）说说事务的特性和隔离级别；

6）悲观锁和乐观锁的区别，怎么实现；





五.mq：

1）mq的原理是什么：有点大。。都可以说；

2）mq如何保证实时性；

3）mq的持久化是怎么做的；



六.nosql相关（主要是redis）:

1）redis和memcache的区别；

2）用redis做过什么；

3）redis是如何持久化的：rdb和aof；

4）redis集群如何同步；

5）redis的数据添加过程是怎样的：哈希槽；

6）redis的淘汰策略有哪些；

7）redis有哪些数据结构；



七.zookeeper:

1）zookeeper是什么；

2）zookeeper哪里用到；

3）zookeeper的选主过程；

4）zookeeper集群之间如何通讯；

5）你们的zookeeper的节点加密是用的什么方式；

6）分布式锁的实现过程；





八.linux相关：

1）linux常用的命令有哪些；

2）如何获取java进程的pid；

3）如何获取某个进程的网络端口号；

4）如何实时打印日志；

5）如何统计某个字符串行数；





九.设计与思想：

1）重构过代码没有？说说经验；

2）一千万的用户实时排名如何实现；

3）五万人并发抢票怎么实现；