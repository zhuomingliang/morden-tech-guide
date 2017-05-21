HBase 深入浅出
来自：https://www.ibm.com/developerworks/cn/analytics/library/ba-cn-bigdata-hbase/index.html

HBase 在大数据生态圈中的位置

提到大数据的存储，大多数人首先联想到的是 Hadoop 和 Hadoop 中的 HDFS 模块。大家熟知的 Spark、以及 Hadoop 的 MapReduce，可以理解为一种计算框架。而 HDFS，我们可以认为是为计算框架服务的存储层。因此不管是 Spark 还是 MapReduce，都需要使用 HDFS 作为默认的持久化存储层。那么 HBase 又是什么，可以用在哪里，解决什么样的问题？简单地，我们可以认为 HBase 是一种类似于数据库的存储层，也就是说 HBase 适用于结构化的存储。并且 HBase 是一种列式的分布式数据库，是由当年的 Google 公布的 BigTable 的论文而生。不过这里也要注意 HBase 底层依旧依赖 HDFS 来作为其物理存储，这点类似于 Hive。

可能有的读者会好奇 HBase 于 Hive 的区别，我们简单的梳理一下 Hive 和 HBase 的应用场景：

Hive 适合用来对一段时间内的数据进行分析查询，例如，用来计算趋势或者网站的日志。Hive 不应该用来进行实时的查询（Hive 的设计目的，也不是支持实时的查询）。因为它需要很长时间才可以返回结果；HBase 则非常适合用来进行大数据的实时查询，例如 Facebook 用 HBase 进行消息和实时的分析。对于 Hive 和 HBase 的部署来说，也有一些区别，Hive 一般只要有 Hadoop 便可以工作。而 HBase 则还需要 Zookeeper 的帮助（Zookeeper，是一个用来进行分布式协调的服务，这些服务包括配置服务，维护元信息和命名空间服务）。再而，HBase 本身只提供了 Java 的 API 接口，并不直接支持 SQL 的语句查询，而 Hive 则可以直接使用 HQL（一种类 SQL 语言）。如果想要在 HBase 上使用 SQL，则需要联合使用 Apache Phonenix，或者联合使用 Hive 和 HBase。但是和上面提到的一样，如果集成使用 Hive 查询 HBase 的数据，则无法绕过 MapReduce，那么实时性还是有一定的损失。Phoenix 加 HBase 的组合则不经过 MapReduce 的框架，因此当使用 Phoneix 加 HBase 的组成，实时性上会优于 Hive 加 HBase 的组合，我们后续也会示例性介绍如何使用两者。最后我们再提下 Hive 和 HBase 所使用的存储层，默认情况下 Hive 和 HBase 的存储层都是 HDFS。但是 HBase 在一些特殊的情况下也可以直接使用本机的文件系统。例如 Ambari 中的 AMS 服务直接在本地文件系统上运行 HBase。