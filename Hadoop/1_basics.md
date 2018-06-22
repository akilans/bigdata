# Basics of Hadoop

  * Hadoop came to solve some of Big Data problems
  
  * Hadoop has 3 main parts 
    * Hadoop Distributed File System- HDFS
    * Distributed Programmming Framework - Mapreduce
    * YARN
    
  * HDFS - Special Network based File system [Distributed File System]. Data stored across multiple servers [Clusters]. HDFS stores the big data in multiple servers
  
  * Hadoop Architecture
    * Hadoop Client - Sends CRUD files/Direcotries request
    * Hadoop Name node - Master server to store Directories/Files Namespaces
    * Hadoop Data Nodes - Slave servers to store data blocks. It Grouped in RACKS.
    
  * Once the request comes from Hadoop client , Name node provides the information about where to store, retrive data. Then It's write/retrive data from data nodes directly
  
  * Blocks of data [128MB] stored in diffrent data nodes.Replication of data blocks will be there in other nodes/RACKS to avoid losing of data.It helps to achieve High Availablity. Replication factor can be increased based on the requirements. Each replication will be stored in separate data nodes with separate RACKS
  
  * 
