# Basics of Hadoop

  * Hadoop came to solve some of Big Data problems
  * Hadoop has 3 main parts 
    * Hadoop Distributed File System- HDFS
    * Distributed Programmming Framework - Mapreduce
    * YARN
  * HDFS - Special Network based File system [Distributed File System]. Data stored across multiple servers [Clusters]. HDFS stores the big data in multiple servers
  * Hadoop client sends request to Name node [Create,Read,Update files, Directories] Hadoop master machine called "Name Node"[Stores direcory & file namespaces] and slave machines called as "Data Nodes" [Manages Data]
  * Once the request comes from Hadoop client , Name node provides the information about where to store, retrive data. Then It's write/retrive data from data nodes directly
  * 
