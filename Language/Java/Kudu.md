https://kudu.apache.org 

Kudu is a columnar storage manager developed for the Apache Hadoop platform. Kudu shares the common technical properties of Hadoop ecosystem applications: it runs on commodity hardware, is horizontally scalable, and supports highly available operation.

Kudu’s design sets it apart. Some of Kudu’s benefits include:

Fast processing of OLAP workloads.

Integration with MapReduce, Spark and other Hadoop ecosystem components.

Tight integration with Apache Impala (incubating), making it a good, mutable alternative to using HDFS with Apache Parquet.

Strong but flexible consistency model, allowing you to choose consistency requirements on a per-request basis, including the option for strict-serializable consistency.

Strong performance for running sequential and random workloads simultaneously.

Easy to administer and manage with Cloudera Manager.

High availability. Tablet Servers and Masters use the Raft Consensus Algorithm, which ensures that as long as more than half the total number of replicas is available, the tablet is available for reads and writes. For instance, if 2 out of 3 replicas or 3 out of 5 replicas are available, the tablet is available.

Reads can be serviced by read-only follower tablets, even in the event of a leader tablet failure.

Structured data model.

By combining all of these properties, Kudu targets support for families of applications that are difficult or impossible to implement on current generation Hadoop storage technologies. A few examples of applications for which Kudu is a great solution are:

Reporting applications where newly-arrived data needs to be immediately available for end users

Time-series applications that must simultaneously support:

queries across large amounts of historic data

granular queries about an individual entity that must return very quickly

Applications that use predictive models to make real-time decisions with periodic refreshes of the predictive model based on all historic data