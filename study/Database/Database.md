> 采用一问一答的形式，还原面试官提问场景。对于已经重复出现的问题，请参考已给出的相关答案。

- 数据库基础
  - 什么是事务？
  - 事务的四种特性？
  - 并发情况下会出现什么问题？
  - 不可重复读和幻读的区别？
  - 数据库的四种隔离级别？
  - 数据库两种常用的存储引擎？
  - 数据库水平切分和垂直切分是什么？
  - 什么是悲观锁和乐观锁？
  - 数据库锁的粒度、种类、加锁的方式？
  - 数据库的三种范式？
  - 数据库的优化方法？
  - 说一说数据库连接池的工作机制是什么？
  - JOIN 与 UNION 区别？
  - 触发器？
  - SQL 去重？
  - 分库分表如何实现？具体分几个库几个表，主从复制，读写分离？
  - 有哪些常用的 sql 优化方式？
  - 数据库自增主键可能造成的问题？
  - MVCC 的含义，如何实现的？
  - 数据库从单机扩展到分布式会遇到什么问题，怎么解决？
  - SQL 解析顺序？
  - 关系型和非关系型数据库的区别（各自优点）？
  - 数据库的索引类型以及优缺点，什么时候使用索引，什么时候不能使用索引？
  - 数据库隔离性设置不同会出现的问题（脏读、不可重复读、丢失修改、幻读）？
  - 视图的作用与使用方法（如何删除等）？
  - 什么是存储过程？有哪些优缺点？
- MySQL
  - 简单介绍下 MySQL 的架构？
  - 说说 MySQL 的索引，索引的类型有哪些，如何创建合理的索引，索引如何优化，索引什么时候会失效？？
  - 索引创建的规则？
  - 为什么 MySQL 索引要用 B+ 树，为何不采用红黑树或 B 树？
  - 索引最左匹配？
  - 索引失效情况？
  - MySQL 有哪些存储引擎，各自优缺点？
  - 介绍一下什么时候用 InnoDB 什么时候用 MyISAM？
  - MyISAM 和 InnoDB 引擎索引结构有什么区别？
  - MySQL 的主从复制？
  - leftJOIN 和 rightJOIN 的区别？
  - 为什么数据库使用索引查询速度会那么快，是怎样实现的？
  - 除了 MySQL 这种关系型数据库外，还有哪些数据库？
  - MySQL 是怎么在 RR 情况下解决幻读的？
  - MySQL 慢查询优化？
  - MySQL 主从切换过程了解吗？在切换的时候如果有请求过来会怎么做？
  - MySQL 数据存储格式？
  - MySQL 的索引有哪几种，原理以及叶子节点存储数据有什么不同？
  - ⾼并发下，如何做到安全的修改同一行数据？
  - InnoDB 的标准行级锁有哪两种，解释其含义？
  - 数据库会死锁吗？举一个死锁的例⼦，MySQL 怎么解决死锁？
  - 聚集索引和非聚集索引的区别（叶节点存储内容）？
  - 索引为什么要⽤ B+ 树实现，它是怎么分裂的，什么时候分裂，为什么是平衡的？
  - 某个表有近千万数据， CRUD 比较慢，如何优化？
  - MySQL 怎么优化 table scan 的？
  - 如何写 sql 能够有效的使用到复合索引？
  - MySQL 中 in 和 exists 的区别？
  - MySQL 的主从延迟怎么解决？
  - 谈谈 explain 结果中⽐较关键的指标，以及指标的含义？
  - 了解 MySQL 的 redo 和 undo 日志吗？
  - MySQL 的表空间方式，各自特点？
  - 分布式事务了解过吗？
- Redis
  - 什么是 Redis？有什么特点？
  - Redis 支持的数据结构类型？各自都适合什么样的场景？
  - Redis 为什么快？
  - 说一说 Redis 持久化机制，RDB 和 AOF 的区别？
  - Redis 高可用？
  - 说一说 Redis 的锁？
  - 读写分离模型及适用场景？
  - 数据分片模型及适用场景？
  - Redis 的回收策略？
  - 使用 Redis 有哪些好处？
  - Redis 与 Memcached 的区别有哪些？
  - Redis 常见性能问题和解决方案？
  - Redis 的适用场景？
  - 常见的缓存策略有哪些，如何做到缓存(⽐如 Redis)与 DB 里的数据一致性？
  - 如何防止缓存击穿和雪崩？
  - 缓存数据过期后的更新如何设计？
  - Redis 的使⽤要注意什么，内存设置，淘汰策略等？
  - Redis 的并发竞争问题如何解决？
  - 了解 Redis 事务的 CAS 操作吗？
  - Redis 的选举算法和流程是怎样的？
  - Redis 的集群怎么同步的数据的？
  - 知道哪些 Redis 的优化操作？
  - Reids 的主从复制机制原理？
  - Redis 的线程模型是什么？
  - 如何看待缓存的使用（本地缓存，集中式缓存），简述本地缓存和集中式缓存和优缺点？
  - 本地缓存在并发使用时的注意事项？
- 其它
  - JDBC 中如何进行事务处理？
  - JDBC 的反射是什么？
  - JDO 是什么？
  - Statement 和 PreparedStatement 有什么区别？哪个性能更好？
  - 使用 JDBC 操作数据库时，如何提升读取数据的性能？如何提升更新数据的性能？
  - 负载均衡怎么实现？
- 参考

# 数据库基础
## 什么是事务？

**事务**（transaction）是一组原子性的 SQL 查询，或者说是一个独立的工作单元。即在满足 ACID 特性的前提下，如果其中有任何一条语句因为崩溃或其它原因无法成功，那么所有的语句都不会执行。事务内的语句，要么全部执行成功，要么全部执行失败。

## 事务的四种特性？

- **原子性**（atomicity）：根据事务的定义，事务被视为一个不可分割的最小工作单元。事务中包含多条语句，整个事务中的所有操作要么全部提交（commit）成功，要么全部失败回滚(rollback)。
- **一致性**（consistency）：数据库总是从一个一致性的状态转换到另一个一致性的状态。即在事务执行前后都保持一致性状态。例如在事务提交之前，系统出现了错误或崩溃，由于事务还没有提交，所以事务中所做的修改也不会保存到数据库中。
- **隔离性**（isolation）：通常情况下，一个事务所做的修改在最终提交之前，对其它事务都是不可见的。但事务的隔离性很难保证，往往在并发情况下会出现并发一致性问题。
- **持久性**（durability）：一旦事务进行了提交，则其所做的修改就会永远保存到数据库中，即对数据的修改是永久性的。

## 并发情况下会出现什么问题？

多事务并发运行通常会操作（例如“读”）相同的数据来完成各自的工作，因此会带来如下的多事务并发问题： 

- **丢失修改**（Lost to modify）：事务 A 在提交事务之前对数据进行了修改，此时事务 B 也对同一数据进行了修改，由于事务 B 覆盖了之前事务 A 的修改，所以事务 A 的修改就被丢失了。
- **脏读**（Dirty Read）：事务 A 读取到了事务 B 已修改但未提交到数据库中的数据，由于事务 B 还未提交，所以事务 A 读取到的数据被称为脏数据，此行为称为脏读。
  - 一个比较好理解的解释：脏读，就是读取了未提交的数据。A 事务读取 B 事务尚未提交的数据，此时如果 B 事务发生错误并执行回滚操作，那么 A 事务读取到的数据就是脏数据。就好像原本的数据比较干净、纯粹，此时由于 B 事务更改了它，这个数据变得不再纯粹。这个时候 A 事务立即读取了这个脏数据，但事务 B 良心发现，又用回滚把数据恢复成原来干净、纯粹的样子，而事务 A 却什么都不知道，最终结果就是事务 A 读取了此次的脏数据，称为脏读。
- **不可重复读**（Nonrepeatable Read）：指在某一事务内多次读同一数据有可能每次读到的数据是不同的。例如，在事务未提交之前，事务 A 读取了某一数据，此时事务 B 对该数据进行了**修改**，那么事务 A 再次读取该数据的话得到的数据和第一次读的可能是不同的，因此就发生了在同一事务内两次读到的数据是不一样的情况，此时就发生了不可重复读。
  - 一个比较好理解的解释：不可重复读，就是前后多次读取，**数据内容**不一致。事务 A 在执行读取操作，由于整个事务 A 比较大，前后读取同一条数据需要经历很长的时间 。而在事务 A 第一次读取数据，比如此时读取了小明的年龄为 20 岁，事务 B 执行更改操作，将小明的年龄更改为 30 岁，此时事务 A 第二次读取到小明的年龄时，发现其年龄是 30 岁，和之前的数据不一样了，也就是数据不重复了，系统不可以读取到重复的数据，成为不可重复读。
- **幻读**（Phantom Read）：事务 A 读取某个**范围**内的数据，此时事务 B 在该范围内**插入**了新的数据，等到事务 A 再次读取该范围内数据的时候发现多了原本不存在的记录，即此时读取的结果集和第一次读取的结果集不同，就好像发生了幻觉一样，所以称为幻读。
  - 一个比较好理解的解释：幻读，就是前后多次读取，**数据总量**不一致。事务 A 在执行读取操作，需要两次统计数据的总量，前一次查询数据总量后，此时事务 B 执行了新增数据的操作并提交后，这个时候事务 A 读取的数据总量和之前统计的不一样，就像产生了幻觉一样，平白无故的多了几条数据，成为幻读。


## 不可重复读和幻读的区别？

不可重复读和幻读类似，都是针对某一事务前后读取的结果不同从而产生的不同现象。但不可重复读的重点在于对同一数据的修改，而幻读的重点是新增或者删除数据，在于范围。

## 数据库的四种隔离级别？

- **Read Uncommitted**（读未提交）：最低的隔离级别，对于事务中的修改，即使没有提交，则对其它事务也都是可见的，即允许读取尚未提交的数据变更，可能会产生脏读、幻读或不可重复读。
  - 也就是说：在这种隔离级别下，所有事务能够读取其他事务未提交的数据。读取其他事务未提交的数据，会造成脏读。因此在该种隔离级别下，不能解决脏读、不可重复读和幻读。
  - 读未提交可能会产生脏读的现象，那么怎么解决脏读呢？那就是使用读已提交。
- **Read Committed**（读已提交）：允许提交并发事务已经提交的数据，即一个事务只能看见已经提交的事务所做的修改。也就是说，一个事务从开始到提交之前，所做的任何修改对其它事务都是不可见的。可避免脏读。
  - 也就是说：在这种隔离级别下，所有事务只能读取其他事务已经提交的内容。能够彻底解决脏读的现象。但在这种隔离级别下，会出现一个事务的前后多次的查询中却返回了不同内容的数据的现象，也就是出现了不可重复读。
  - 注意：这是大多数数据库系统默认的隔离级别，例如 Oracle 和 SQL Server，但 MySQL 不是。
  - 已提交可能会产生不可重复读的现象，我们可以使用可重复读。
- **Repeatable Read**（可重复读）：该级别可以保证在同一个事务中多次读取同样记录的结果是一致的。MySQL 的默认级别，可避免不可重复读。
  - 也就是说：在这种隔离级别下，所有事务前后多次的读取到的数据内容是不变的。也就是某个事务在执行的过程中，不允许其他事务进行 update 操作，但允许其他事务进行 add 操作，造成某个事务前后多次读取到的数据总量不一致的现象，从而产生幻读。
  - 这才是 MySQL 的默认事务隔离级别。
  - 可重复读依然会产生幻读的现象，此时我们可以使用串行化来解决。但需要注意的是：串行化会产生大量的操作超时和锁的竞争，因此我们一般不适用串行化操作。而我们知道，MySQL 默认使用的是可重复读隔离级别，可是依然会产生幻读的现象，那么 MySQL 是如何解决幻读的呢？
    - 答案是使用**间隙锁（Gap Lock）**，顾名思义，锁的是一段间隙，至于这段间隙有多大，什么时候会触发间隙锁，需要分情况讨论。需要注意的是，只有在可重复读这一隔离级别下，才会有**间隙锁**的产生。
    - 产生幻读的原因是：行锁只能锁住行，但是新插入记录这个动作，需要更新的是记录之间的“间隙”。因此，为了解决幻读问题，InnoDB 只好引入了新的锁，也就是间隙锁。
    - 这里再解释一下 MySQL 中锁的类型，便于区分。
      - 主要是 InnoDB 中行锁的种类：
        - 记录锁（Record Locks）：锁住当前行上的记录；通过聚集索引或二级索引进行查找的时候，会在索引上加记录锁。锁住的是索引，而不是记录本身，即使该表上没有任何索引，那么 InnoDB 会创建一个隐藏的聚集主键索引，那么锁住的就是这个隐藏的聚集主键索引。
        - 间隙锁（Gap Locks）：锁定一个范围，但不包括当前记录本身；也就是按照范围锁定索引记录，例如`SELECT c1 FROM t WHERE c1 BETWEEN 10 and 20 FOR UPDATE;`，为防止其他事务将值 15  插入到 t.c1 列中，无论该列中是否已有这样的值，该范围中所有现有值之间的间隙都会被锁定。
        - 临建锁（Next-key Locks）：临建锁是记录锁和间隙锁的结合，即锁定范围，也锁定记录本身。但是，在唯一索引情况下会降级为记录锁，从而提高并发能力。
          - 所谓的`Next-Key`是指，范围区间划分是包含下一个值。例如索引有 10、11、13、20 四个值时，可被`Next-Key Lock`的范围区间是`(-∞, 10]`、`(10, 11]`、 `(11, 13]`、 `(13, 20]`、 `(20, +∞]`五个区间。而插入新值 12 后，则`(10, 11]`、 `(11, 13]`裂变为`(10, 11]`、 `(11, 12]`、 `(12, 13]`，也就是左开右闭。
- **Serializable**（可串行化）：最高的隔离级别，强制事务串行执行，在读取的每一行数据上多加锁，但有可能导致大量的超时和锁争用的问题。避免了幻读。
  - 也就是说，在这种隔离级别下，所有的事务顺序执行，所以他们之间不存在冲突，从而能有效地解决脏读、不可重复读和幻读的现象。但是安全和效率不能兼得，这样事务隔离级别，会导致大量的操作超时和锁竞争，从而大大降低数据库的性能，一般不使用这样事务隔离级别。

## 数据库两种常用的存储引擎？

常见的有 InnoDB 和 MyISAM： 

- **InnoDB** 是 MySQL 默认的**事务型**引擎，默认的隔离级别是 Repeatable read（可重复读），通过间隙锁（next-key locking）策略防止幻读的出现。其内部做了许多优化，如从磁盘读取数据时采用的可预测性预读，能够自动在内存中创建 hash 索引以加速读操作的自适应哈希索引，以及能够加速插入操作的插入缓冲区等。
- **MyISAM** 不支持事务和行级锁，崩溃后无法安全恢复。其对整张表进行加锁，读取时会对需要读到的所有表加共享锁，写入时则对表加排他锁。

**如何选择合适的存储引擎？**

除非需要用到某些 InnoDB 不具备的特性，否则都应该优先选择 InnoDB 引擎。如果不在乎可扩展能力和并发能力，也不在乎崩溃后的数据丢失问题，而对 InnoDB 的空间占用过多比较敏感的话，则建议选择 MyISAM。

- 如果想要支持**事务**，则 InnoDB 是目前最稳定的；
- 如果考虑到**备份**，则 InnoDB 满足在线热备份的需求；
- 如果考虑到**奔溃恢复**的能力，MyISAM 崩溃后发生损坏的概率比 InnoDB 要高很多，而且恢复速度也要慢；
- 如果考虑到存储引擎**特有的一些特性**，例如只有 MyISAM 支持地理空间索引。

## 数据库的水平切分和垂直切分是什么？

通过某种特定的条件，按照某个维度，将存放在同一数据库中的数据分散到多个数据库中，以实现分散主库负载的目的。
- 垂直分表：将含有多个列的表拆分成多个表，解决表的宽度问题，可分为： 
  - 将不常用的字段单独放在一个表中；
  - 将大字段独立放在一个表中；
  - 将经常使用的字段放在一起；
  - 优点：
    - 由于每个表对应的是不同的业务，垂直切分是按照业务将表进行分类，分不到不同的数据库上。
    - 所以拆分后业务更加清晰、拆分规则明确、系统之间整合或扩展容易、数据维护简单。
  - 缺点： 
    - 部分业务表无法 JOIN，只能通过接口的方式解决，系统的复杂度上升了；
    - 存在单库性能瓶颈；
    - 事务处理复杂。
- 垂直分库：
  - 按照业务规模划分出不同的数据库。
  - 存在跨库 JOIN 问题。
    - 通过全局表进行解决，有可能系统中存在所有的模块都会依赖的一些表，可将这类的表在其它每个数据库中均保存一份。
    - 通过字段冗余进行解决。
- 水平分表：将表中不同的数据行按照一定规律分不到不同的数据库表中，这些表保存在**同一个**数据库中。水平分表用于解决数据表中数据过大的问题，水平分表每一个表的结构是完全一致的。常用的方式有： 
  - 对 ID 进行 hash 计算，例如要拆分成 5 个表，则 ID % 5 可以拆分到 0、1、2、3、4 上；
  - 针对不同的 hashID 将数据存入不同的表中。
  - 优点：
    - 表拆分后可以降低在查询时需要读的数据和索引的页数，同时也降低了索引的层数，提高查询速度；
    - 不存在单库大数据、高并发的性能瓶颈；
    - 按照合理的拆分规则进行拆分的话，JOIN 操作基本避免跨库。
  - 缺点：
      - 拆分规则难以抽象；
      - 分片事务一致性难以解决。
- 水平分库分表：
  - 将表中不同的数据行按照一定规律分不到不同的数据库表中，这些表保存在**不同的**数据库中。

## 什么是悲观锁和乐观锁？

悲观锁和乐观锁是两种常见的资源并发锁设计思路，适用于并发编程。

**悲观锁**：先获得锁，然后再进行业务操作，即“悲观”的认为所有的操作都会造成并发安全问题，因此要先确保获取锁成功以后再进行相应的业务。
  - 适用于**数据更新比较频繁**，即**写多读少**的场景。

**乐观锁**：先进行业务操作，只有在最后更新数据时进行检查数据是否被其它事务修改过，若没有被修改过，则更新成功，否则失败重试。
  - 该锁认为当前的操作不会产生并发问题，即当前不会有其它线程对数据进行修改，因此不会上锁。
  - 适用于**读多写少**的场景，由于乐观锁在发生失败回滚的时候开销比较大，因此适用于在取锁失败概率较小的场景，从而提高系统的并发性能。
  - 实现方式如下： 
    - 在需要锁的数据上增加一个版本号或者时间戳，每次数据更新的同时也更新该字段；
    - 先读取想要更新的字段，在实际更新的时候检查一下，若该字段没有变化，则不更新；若变化了，则更新。

## 数据库锁的粒度、种类、加锁的方式？

**封锁的粒度**： 

MySQL 提供了两种封锁的粒度：**行级锁（row lock）**和**表级锁（table lock）**。

  - **行级锁（row lock）**：
    - 只有在存储引擎实现，而 MySQL 服务器层没有实现。
  - **表级锁（table lock）**：
    - 表锁是 MySQL 中最基本的锁策略，开销最小。
    - 一个用户对表进行写操作（插入、删除、更新等）前，会先获得写锁。这会阻塞其他用户对该表的所有读写操作。
    - 当没有写锁时，其他读取的用户才能获得读锁，读锁之间不相互阻塞。

**锁粒度的选择**：
  - 让锁定的对象更具有选择性，尽量只锁定需要修改的部分数据，而不是所有的资源。更理想的情况是，只会对修改的数据片进行精确的锁定。
  - 在锁的开销和数据安全之间寻求平衡，锁定的数据量越小，则发生锁争用的可能性就越小，系统的并发程度就越高。
  - 但加锁也会消耗资源，所的各种操作（获取、释放、检查锁的状态）都会增加系统开销。
  - 封锁粒度越小，越精细，则系统开销就越大。

**锁的类型**：
  - **共享锁（shared lock）/ S 锁**：也叫读锁，如果事务 T1 对数据 A 加了 S 锁，则可以对 A 进行读取操作，但是不能进行更新操作。加锁期间事务 T2 可以读取数据 A，但不能修改数据 A。也就是对于其它事务来说，只能加 S 锁，不能加 X 锁。
      - 总结起来就是：某个事务对某行或某表加了读锁后，**其他事务依然可以读取，但不能修改**。可以同时有多个事务对某行或某表加读锁。
  - **排他锁（exclusive lock）/ X 锁**：也叫写锁（独占锁、排他锁），如果事务 T1 对数据 A 加了 X 锁，则只允许该事务对 A 进行读取和更新操作。加锁期间事务 T2 不能读取数据 A，也不能修改数据 A。也就是对于其它事务来说，既不能加 S 锁，也不能加 X 锁。
  - **意向锁（Intention locks）**：
      - 为什么需要意向锁？
          - 当事务 T1 对表中的**某条记录**加 X 锁后，事务 T2 想对**整张表**加 X 锁，于是事务 T2 需要遍历该表中的所有记录，判断是否有记录存在 X 锁。如果有一条记录被加了 X 锁，则事务 T2 需要等待事务 T1 完成。
          - 然而，这种遍历的方式非常低效，MySQL 在后来引入了意向锁的概念，用来解决这种问题。当事务 T1 对**某条记录**加 X 锁前，首先需要对**表**加 IX 锁。当事务 T2 需要对**表**加 X 锁时，只需要判断表上是否含有 IX 锁，如果有，则进行等待。
          - **当然，意向锁不会和行锁冲突，意向锁只会阻塞对表的 S 锁或 X 锁。**事务 T1 对表加 IX 锁，然后对记录 a 加 X 锁，事务 T2 需要修改记录 b 时，并不需要判断是否存在意向锁。
          - 也就是说，引入意向锁是因为假如事务 T 想要对某张表加 X 锁时，就需要先检测一下是否存在其它事务对该表或该表中的某一行加了锁，在检测的时候都需要对每一行进行检测，非常耗时。这是由于这种耗时，才引出了意向锁。
    - **意向共享锁（IS）**：指一个事务在获取 S 锁之前，一定会先在当前的表上加 IS 锁。
    - **意向排他锁（IX）**：指一个事务在获取 X 锁之前，一定会先在当前的表上加 IX 锁。

有了意向锁之后，事务 T 想要对某张表加 X 锁时，只需要检测是否有其它事务对该表加了 X/IX/S/IS 锁，如果加了就表示有其它的事务在使用该表或表中的某行的锁，因此事务 T 加 X 锁失败。

## 数据库的三种范式？

范式（Normal Form）分为多种，通常用到的三种范式有： 第一范式（1NF）、第二范式（2NF）和第三范式（3NF）。

- **第一范式**：列不可分，即列具有原子性。对于【联系人】表来说，如果存在**姓名、性别、电话**这三列的话，则不属于第一范式。因为还可以将**电话**拆分为**家用电话**和**公司电话**。
- **第二范式**：在 1NF 的基础上，表中还具有主键，并且**没有包含在主键中的列**要完全依赖于主键，**而不能只依赖于主键中的一部分**。
  - 比如一个【订单信息表】，其中存在的列有**订单编号、商品编号、商品名称、商品数量、单位、商品价格、客户、所属单位、联系方式**。这里的**订单编号、商品编号**是联合主键，但这里的**商品名称、单位、商品价格**等信息不与该表的主键完全相关，而是只与**商品编号**相关，即只依赖于主键中的一部分。所以这里违反了第二范式的设计原则。
  - 此时，要想符合第二范式，只需要将【订单信息表】进行拆分，将商品所属的信息拆分到另一个表中，同时把订单项目也分离到另一个表中即可。
- **第三范式**：在 2NF 的基础上，还需要**非主键列必须直接依赖于主键，而不能存在传递依赖**。即不能存在非主键列 A 依赖于非主键列 B，非主键 B 依赖于主键的情况。
  - 例如一个【订单信息表】，存在的列有**订单编号、订单项目、负责人、业务员、订单数量、客户编号、客户姓名**。
  - 由于**客户姓名**与**客户编号**相关，而**客户编号**又与**订单编号**相关，则最终**客户姓名**就与**订单编号**相关了。这就出现了传递依赖，不符合第三范式。

## 数据库的优化方法？

对于如何优化 MySQL 数据库，可以从 **SQL 语句及索引优化**、**数据表结构的优化**、**系统配置的优化**和**硬件优化**四个方面进行说明。

**1. SQL 语句及索引优化**

- 发现有问题的 SQL 语句
  - 通过 MySQL 的慢查询日志，假如语句运行时间（long_query_time）超过默认值 10 秒以上，则可以通过使用慢查询日志分析工具（pt-query-digest）分析 Row examine 属性，从而找出 IO 操作较大的 SQL，针对这样的 SQL 进行下一步优化。
- 分析 SQL 语句的执行计划
  - 使用 EXPLAIN 关键字可以知道 MySQL 是如何对 SQL 语句进行处理的。通过打印出的一些信息来优化 SQL 语句。
- SQL 语句的优化
  - 优化 INSERT 语句，即一次插入多个值；
  - 尽量避免在 WHERE 子句中使用 != 或 <> 或对 NULL 值进行判断等操作，否则引擎会放弃使用索引而进行全表扫描；
  - 优化嵌套查询： 可以使用连接（JOIN）替代子查询；
  - 某些情况下使用 EXISTS 代替 IN。
- 索引的优化
  - 可以在经常需要进行查询、表连接、使用 ORDER BY、GROUP BY 后面的字段中建立索引，但需要注意以下几种可能会**引起索引失效**的情况： 
    - 以 % 开头的 LIKE 语句进行模糊匹配时；
    - OR 语句前后没有同事使用索引时；
    - 数据类型出现隐式转化时（如 varchar 不加单引号的话可能自动转换为 int）；
    - 对于多列索引，必须满足**最左匹配原则**，因为 MySQL 会一直向右匹配直到遇到范围查询（<、>、BETWEEN、LIKE）就停止。比如 `a=1 AND b=2 AND c>3 AND d=4`，如果建立 (a,b,c,d) 顺序的索引，则 d 是用不到索引的；如果建立 (a,b,d,c) 的索引则都可以用到。此外 a、b、d 的顺序可以任意调整。

**2. 数据库表结构优化**

该部分包括选择合适的数据类型、表的范式的优化、表的垂直拆分和水平拆分等。

- 选择合适的数据类型
  - 通常使用较小的数据类型解决问题；
  - 使用简单的数据类型；
  - 使用 not null 定义字段；
  - 尽量避免使用 text 类型。
- 表的范式的优化
  - 应遵循表设计的三大范式
- 表的垂直拆分和水平拆分（上面的问题有提到过）

**3. 系统配置的优化**

- 增加 TCP 支持的队列数；
- InnoDB 缓存池设置和缓存池个数的设置

**4. 硬件的优化**

- CPU的核心数多并且主频高；
- 增大内存；
- 还需要考虑磁盘的性能与配置。

## 说一说数据库连接池的工作机制是什么？

数据库连接池技术主要是用来分配、管理、释放数据库连接的。由于数据库在连接资源的时候，需要进行连接再关闭，等到下次使用完的时候还得需要关闭。所以这样频繁的打开和关闭十分影响数据库的效率，因此可以使用连接池技术。

实现思路：
- 在每次连接数据库时，数据库连接池会给用户分配一个数据库连接，当用户用完之后，连接池再将此连接进行收回，放回到连接池的集合中，以备下次使用。
- 也就是说，在应用程序启动时建立足够的数据库连接，并将这些连接组成一个连接池，由应用程序动态地对池中的连接进行申请、使用和释放。
- 对于多于连接池中连接数的并发请求，应该在请求队列中排队等待。并且应用程序可以根据池中连接的使用率，动态增加或减少池中的连接数。

工作机制：
- 建立连接池。在系统初始化时，连接池会根据系统的配置进行建立，并在池中创建连接对象，以便能够随时从连接池中获取连接。
- 管理连接池。
  - 当用户请求数据库进行连接时，首先查看连接池中是否有空闲连接，若有则分配给用户使用；
  - 如果没有，则查看当前所建立的连接数是否已经达到最大连接数，如果没有达到就重新创建一个连接给用户。
  - 如果达到就按照设定的时间进行等待，如果超过最大等待时间，则抛出异常。
  - 当用户释放连接时，则判断该链接的引用次数是否超过了规定值，如果超过了就从池中删除该连接，否则保留给其它用户。
- 关闭连接池。当应用程序退出时，则关闭连接池中的所有连接，释放相关资源。

## JOIN 与 UNION 区别？

图示：

![image.png](https://i.loli.net/2020/03/03/kvrIobAZ25jRfYF.png)

- **JOIN**：将两张表根据条件相同的部分合并成一个记录。分为以下几种：
  - INNER JOIN：将两张表中满足条件的行组合起来作为结果集，即满足条件的**交集**。
  - FULL OUTER JOIN：查询出两个表的所有数据，即满足条件的**并集**。如果在`WHERE`子句中添加`IS NULL`语句，则表示去除两张表的重复数据。
  - LEFT OUTER JOIN：会产生左边表的**全集**，而右边表有匹配的则显示，没有匹配的则用`NULL`代替。如果在`WHERE`子句中添加右表的`IS NULL`语句，则会产生在左边表存在而在右边表不存在的集合。
  - RIGHT OUTER JOIN：与`LEFT OUTER JOIN`效果相反。
  - Cross Join：交叉连接，返回两个表的笛卡尔积，即对所有数据返回 m * n 的结果。
- **UNION**
  - 使用 UNION 操作符来组合数条 SQL 查询，即给出多条 SELECT 语句，将它们的结果组合成单个结果集；
  - UNION 必须由两条或两条以上的 SELECT 语句组成，语句之间用关键字 UNION 分隔；
  - UNION 中的每个查询必须包含相同的列、表达式或聚集函数；
  - 列数据类型必须兼容，类型不必完全相同，但必须是 DBMS 可以隐含的转换的类型；
  - 使用 UNION 关键字能够将重复的行进行去除，而使用 UNION ALL 则显示所有重复的行。

## 触发器？

触发器是与表相关的数据库对象，在满足条件时触发，并执行触发器中定义的语句集合。它是响应 DELETE、INSERT、UPDATE 语句而自动执行（触发）的一条 MySQL 语句。

创建触发器如下所示（表示在 INSERT 语句执行成功后才执行该触发器）：

```sql
CREATE TRIGGER newproduct AFTER INSERT ON products
FOR EACH ROW SELECT 'Product added';
```

## SQL 去重？

- 在列名之前使用`DISTINCT`关键字，但该关键字只能返回去重的字段，而不能返回其它字段。
- 使用`GROUP BY`关键字对结果集进行聚集，从而去重。

## 分库分表如何实现？具体分几个库几个表，主从复制，读写分离？

在实际的生产环境中，对数据库的读和写都在同一个数据库中，是不能满足实际需求的，通过从复制的方式来同步数据，再通过读写分离来提升数据库的并发负载能力。

**复制类型**：
  - 基于语句的复制。在服务器上执行 SQL 语句，在从服务器上执行同样的语句，MySQL 默认采用基于语句的复制，执行效率高。
  - 基于行的复制。把改变的内容复制过去，而不是把命令在从服务器上执行一遍。
  - 混合类型的复制。默认采用基于语句的复制，一旦发现基于语句无法精确复制时，就会采用基于行的复制。

**读写分离**：读写分离就是在主服务器上修改，数据会同步到从服务器，从服务器只能提供读取数据，不能写入，实现备份的同时也实现了数据库性能的优化，以及提升了服务器安全。可分为：
- 基于程序代码内部实现。根据 SELECT、INSERT 进行路由分类。
- 基于中间代理层实现。代理数据库服务器接收到应用服务器的请求后根据判断后转发到后端数据库。

## 数据库自增主键可能造成的问题？

- 在对使用自增主键的数据库做分库分表时，可能会出现主键重复的问题。

## MVCC 的含义，如何实现的？

**多版本并发控制**（Multi-Version Concurrency Control, MVCC）使得大部分支持行锁的事务引擎，不再单纯的使用行锁来进行数据库的并发控制，而是把数据库的行锁与行的版本结合起来，仅需要很小的开销，就可以实现非锁定的读操作，从而可以提高数据库系统的并发性能。

换句话说，**锁机制可以控制并发操作，但是系统开销较大，而 MVCC 可以在大多数情况下代替行级锁，从而降低系统的开销。**

实现方式：通过在每行记录后面保存两个隐藏的列来实现。

- 一个保存了行的**创建时间**，一个保存了行的**过期时间**。
- 存储的是系统版本号（system version number）而不是实际的值。

每开始一个新的事务，系统版本号都会自动递增。事务开始时刻的系统版本号会作为事务的版本号。所以说，MVCC 是通过保存数据在某个时间点的快照来实现的。不管需要执行多长时间，每个事务看到的数据都是一致的。

MVCC 只在 REPEATABLE READ 和 READ COMMITTED 两个隔离级别下工作。因为 READ UNCOMMITTED 总是会读取最新的行，而不是符合当前事务版本的是数据行，而 SERIALZABLE 则会对所有读取的行都加锁。

相应的操作：
  - SELECT：满足以下两个条件则返回该行的数据。
    - 该行的创建版本号 ≤ 当前版本号，用于保证在 SELECT 操作之前所有的操作已经执行完毕。
    - 该行的删除版本号 ＞ 当前版本或者为空，
  - INSERT：将新插入的行的创建版本号设置为当前系统的版本号。
  - DELETE：将要删除的行的删除版本号设置为当前系统的版本号。
  - UPDATE：转换成 INSERT + DELETE 的方式进行，即将旧行的删除版本号设置为当前版本号，并将新行 INSERT 同时设置创建版本号为当前版本号。

对于写操作（INSERT、DELETE、UPDATE）来说，需要将系统版本号递增。


## SQL 解析顺序？

最先执行的是`FROM`操作，最后执行的是`LIMIT`操作，每一个操作都会产生一张虚拟表，将该表作为下一语句的输入。如下所示：

```sql
(8)  SELECT
(1)  FROM  (9) DISTUNCT
(3)  JOIN
(2)  ON
(4)  WHERE
(5)  GROUP BY
(6)  WITH
(7)  HAVING
(10) ORDER BY
(11) LIMIT
```

## 关系型和非关系型数据库的区别（各自优点）？

- **数据表与数据集**
  - 在数据的存储方式上，关系型数据库是表格式的，数据存储在数据表的行和列中。
  - 而非关系型数据库是将数据大块的组合在一起，存储在数据集中。
- **预定义结构与动态结构**
  - 关系型数据库都有预定义好的结构，该结构描述了数据的形式和内容。
  - 非关系型数据库基于动态结构，适用于数据类型和结构的变化。
- **存储规范化与存储代价**
  - 关系型数据库将数据分割成最小的关系表以避免重复，获得最精简的利用率。
  - 非关系型数据库在数据集中存储数据时，经常存在重复，将其存储成一个整体，易于读写。
- **纵向扩容与横向扩容**
  - 关系型数据库是纵向扩展。
  - 非关系型数据库是横向扩展，适用于分布式。
- **结构化查询与非结构化查询**
  - 关系型数据库通过结构化查询语言来操作数据。
  - 非关系型数据库以块为单元操作数据。
- **ACID 与 CAP**
  - 关系型数据库支持 ACID 属性。
  - 非关系型数据库则满足 CAP（一致性、可用性、分区容忍度）。

## 数据库的索引类型以及优缺点，什么时候使用索引，什么时候不能使用索引？

**什么是索引？**

- 索引是对数据库表中的一个或多个列的值进行排序的数据结构，以协助快速查询、更新数据库表中的数据。
- 索引加速了数据的访问，使用了索引后，存储引擎不会再去扫描整张表得到需要的数据，而是从根节点开始，根节点保存了子节点的指针，存储引擎会根据指针快速查找。

**索引的类型：**

- 普通索引。
- 唯一索引：索引列的值必须唯一，但允许存在空值。
- 主键索引：必须唯一，且不允许存在空值。
- 单列索引和复合索引：索引的列数。
- 覆盖索引：索引包含了满足查询所需要的数据，查询时只需读取索引而不需要进行回表操作。
- 聚簇索引与非聚簇索引：对磁盘上存放数据的物理地址重新组织以使这些数据按照规定排序的一种索引。即聚簇索引是按照数据的物理存储进行划分的。每张表只能创建一个聚簇索引。由于可以直接通过顺序得到数据的物理地址，所以查询速度快。但修改速度较慢。非聚簇索引只记录逻辑顺序，而不改变物理顺序。
  - 这里再详细的解释一下聚簇索引和非聚簇索引，其实就是**聚集索引**和**非聚集索引**，只不过中文翻译过来的叫法不同罢了。
  - 假如有一张表，我现在需要查找 id=5 的记录，按照正常的逻辑，需要去遍历表中的所有数据，在最坏的情况下，需要扫描表中的每一条记录，知道最后一条记录被扫描到，因此最坏的时间复杂度为 O(n) 的。而使用索引后，会将表中的记录按照某种规则转换为平衡树结构，大大减少了查询的次数。但具体是什么结构，那取决于建立的索引的类型。
  - 对于**聚集索引**：
    - 一般情况下，指定 id 为主键，就会生成一个以 id 为基础的聚集索引。在聚集索引的树结构中，所有**节点都会存储主键值，而叶子节点还会多存储主键对应的行记录**。
    - 此外，**真实的数据行会按照主键排序，顺序存储在磁盘上**，比如 id 为 1 和 2 的对应记录在磁盘上相邻存储。
    - 一张表只有一个主键，因此一个表只有一个聚集索引。
  - 对于**非聚集索引**：
    - 它所有的节点都会存储索引列的值，叶子节点还会多存储该值所对应的聚集索引的值，也就是主键的值。
    - 与聚集索引不同的是，真实的数据行不会按照非聚集索引排序存储，但索引项的内容是按照顺序存储的。
    - 一个表可以有多个非主键索引，因此会建立多个非聚集索引，每建立一个非聚集索引，**都会将该非聚集索引关联的字段数据复制出来一份，用于生成以该列为基础的平衡树**。这样的操作会增加表的体积，占用磁盘空间，所以不是索引越多越好。
    - 通过非聚集索引查询数据时，查询到叶子节点上的主键值后，再利用这个主键值查询聚集索引，从而查询到具体的行记录，这个需要遍历两次树。
  - 所以，不管以任何方式查询数据，最后都会利用**聚集索引**查询数据，在我们之前定义的表中，聚集索引是通往真实记录的唯一大道。
  - 也可以这么理解，由于索引是通过二叉树的来描述的，对于聚集索引，叶子节点只存储数据节点；而对于非聚集索引，叶子节点仍然是索引节点，只不过有一个指针指向对应的数据块。
  - 其实，可以用在图书馆找书的例子来理解聚集索引和非聚集索引的概念。比如图书馆进了一批新书，这些书肯定需要一定的规则，分门别类的存放。例如杂志类放在 101 房间，文学类放在 102 房间。这些存储规则决定了每本书应该放到哪里，而这里的书的类别就是聚集索引。而对于非聚集索引来说，如果我们想要在图书馆找一本书，首先应该去的就是检索室，在检索室找到这本书在对应的书架之后，我们的查询结果并没有结束，仅仅是找到了书的位置信息，我们还需要取书。此时，就产生了两个步骤：①查询该记录所在的位置；②通过该位置去取对应的记录。
  - 终极总结：
    - 聚集索引一个表只能有一个，而非聚集索引一个表可以存在多个。
    - 聚集索引存储记录是物理上连续存在，而非聚集索引是逻辑上的连续，物理存储并不连续。
    - 聚集索引：物理存储按照索引排序；聚集索引是一种索引组织形式，索引的键值逻辑顺序决定了表数据行的物理存储顺序。
    - 非聚集索引：物理存储不按照索引排序；非聚集索引则就是普通索引了，仅仅只是对数据列创建相应的索引，不影响整个表的物理存储顺序。
    - 索引是通过二叉树的数据结构来描述的，我们可以这么理解聚簇索引：索引的叶节点就是数据节点。而非聚簇索引的叶节点仍然是索引节点，只不过有一个指针指向对应的数据块。

**索引的优缺点：**

- 优点：
  - 加快了数据的检索速度，提高查找性能，减少表的检索行数；
  - 加速了表和表之间的连接；
  - 在分组和排序的子句中进行数据检索，可减少查询中分组和排序所消耗的时间；
  - 通过创建唯一索引，可以保证数据库表中每一行数据的唯一性。
- 缺点：
  - 创建索引和维护索引需要耗费时间，即对表中的数据进行增、删、改时，索引需要动态维护；
  - 索引需要占用额外的空间。

**使用索引的注意事项：**

- 在经常需要搜索的列上建立索引，可以加快查找速度。
- 在主键列上建立主键索引，可以确保此列数据的唯一性。
- 需要考虑到最左匹配原则，如果是 “ like %name” 或  “like %name%”，那么是不走索引的。而 “like name%” 是走索引的； 
- 应指定索引的列为 NOT NULL，因为在 MySQL 中含有空值的列很难进行查询优化。
- 应取值离散大的字段，通过`count()`函数查看字段的差异值，返回值越大说明字段的唯一值越高，则字段的离散程度越高。（这与 B+ 树的查找有关，离散大了可以使 B+ 树有更多的分支，从而存储更多的节点。）
- 索引字段越小越好，一页存储的数据越多，则一次 IO 操作所获取的数据越大，效率越高。

## 视图的作用与使用方法（如何删除等）？

视图是虚拟的表，与包含数据的表不同的是，视图是包含使用时动态检索数据的查询。其好处有：

- 重用 SQL 语句，简化复杂的 SQL 操作；
- 使用表的组成部分而不是整个表；
- 保护数据、更改数据格式和表示形式。

与视图有关的操作：

```sql
CREATE VIEW viewname;

DROP VIEW viewname;

CREATE OR REPLACE VIEW viewname;

SHOW CREATE VIEW viewname;
```

## 什么是存储过程？有哪些优缺点？

存储过程是事先经过编译并存储在数据库中的一段 SQL 语句的集合。存储过程由一些子 SQL 语句组成的代码块，这些代码块就像方法一样会实现一些功能，然后再对这些代码块起一个名字，在用到这个功能的时候直接调用即可。

优点：
- 存储过程只在创建时进行编译，以后每次执行存储过程都不需再重新编译，而一般 SQL 语句每执行一次就编译一次，所以使用存储过程可提高数据库执行效率；
- 当 SQL 语句有变动时，可以只修改数据库中的存储过程而不必修改代码；
- 减少网络传输，在客户端调用一个存储过程要比执行一串 SQL 传输的数据量要小；
- 通过存储过程能够使没有权限的用户在控制之下间接地存取数据库，从而确保数据的安全。

创建与删除存储过程：
```sql
CREATE PROCEDURE productpricing()
BEGIN
    SELECT Avg(prod_price) AS priceaverage
    FROM products;
END;

DROP PROCEDURE productpricing;
```

# MySQL




# 其它

# 参考

[高性能 MySQL](https://book.douban.com/subject/23008813/)

[面试/笔试第三弹 —— 数据库面试问题集锦](https://blog.csdn.net/justloveyou_/article/details/78308460)

[A Visual Explanation of SQL Joins](https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)

[图解 SQL 的 JOIN](https://coolshell.cn/articles/3463.html)

[CS-Notes](https://github.com/CyC2018/CS-Notes/blob/master/notes/%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B3%BB%E7%BB%9F%E5%8E%9F%E7%90%86.md)

[数据库设计的三大范式](https://www.cnblogs.com/o-andy-o/archive/2012/01/30/2331615.html)

[数据库连接池技术概述](https://juejin.im/post/5b7944c6e51d4538c86cf195)

[java 数据库连接池实现原理](https://blog.csdn.net/frightingforambition/article/details/25464129)

[mysql 主从复制与读写分离](https://blog.51cto.com/13555423/2068071)

[SQL 与 NoSQL（关系型与非关系型）数据库的区别](https://www.cnblogs.com/wanghongyun/p/6193912.html)