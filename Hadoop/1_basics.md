# Hadoop Tutorials - https://www.youtube.com/watch?v=KZwb-QTmxks&list=PLkz1SCf5iB4dw3jbRo0SYCk2urRESUA3v 

# Basics of Hadoop

  * Hadoop came to solve some of Big Data problems
  
  * Hadoop has 3 main parts 
    * Hadoop Distributed File System- HDFS
    * Distributed Programmming Framework - Mapreduce
    * YARN
    
  * HDFS - Special Network based File system [Distributed File System]. Data stored across multiple servers [Clusters]. HDFS stores the big data in multiple servers
  
  * Hadoop Architecture
    * Hadoop Client - Sends CRUD files/Direcotries request
    * Hadoop Name node - Master server to store Directories/Files Namespaces in InMemory [ FsImage & EditLogs ]
    * Hadoop Data Nodes - Slave servers to store data blocks. It Grouped in RACKS.
    
  * Once the request comes from Hadoop client , Name node provides the information about where to store, retrive data. Then It's write/retrive data from data nodes directly
  
  * Blocks of data [128MB] stored in diffrent data nodes.Replication of data blocks will be there in other nodes/RACKS to avoid losing of data.It helps to achieve High Availablity. Replication factor can be increased based on the requirements. Each replication will be stored in separate data nodes with separate RACKS
  
  * Name node is Single point of Failure. To make High availability to take back up of EditLog [Stored Namespace information about all data]. It can be achieved by QJM[Quorum General Manager - Small Software ]. Setup 3 QJM nodes and write EditLog there instead of Hard Disk. QJM nodes can be increased based on your requirement. 
  
  * Add one more "Stand By Name Node". It keeps on synch EditLogs form QJM. In case of failure of Active Name Node this Standby Name node will become Active. It can be done via ZooKeeper and placing Failover Controller on both Name Nodes
  
  * Standby Name Node tries to Log from ZooKeeper. As active Name Node available it will not get. Once Active node fails zoopkeeper sends log to StandByNode node and it becomes Active Name Node
  
  * Secondary Name Node - In case if Active Name node restarts it will lose all the FsImage [Namespaces od Directories & Files ].It can be regenerated from EditLogs but it will take time bacause of EditLog becomes large when you keep on writing data. So Secondary Name Node came to solve this issue
  
  * Secondary Name node performs check point activity every hour.Reads EditLog and create FsImage file on disk. It is same as InMemory FsImage in Active name node. After creating FsImage on disk it truncates EditLog and adding FsImage on that. 
  
  * After one hour next Check point activity starts. It reads from on disk FsImage file and accumulate with last one hour EditLog and create creates new On Disk FsImage file [Merging of On Disk FsImage and EditLog] 
  
  * Secondary Name node is not required when we configure High Availability Hadoop Cluster. Because StandBy Name node has all the necessary FsImage in memory and ready to play active role. Secondary Name node is just for non high availabilty  Active node get  restarted
  
# Configure Hadoop Cluster

  * 
