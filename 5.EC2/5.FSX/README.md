# FSx

## 1. FSx

### 1) What is FSx?
Amazon FSx for Windows File Server provides fully managed Microsoft Windows file servers, backed by a fully native Windows file system. so you can easily move your Windows-based applications that require file storage to AWS. Amazon FSx is built on Windows Server.

### 2) How is Windows FSx different to EFS?
 #### Windows FSx
  - A managed Windows Server that run Windows Server Message Block (**SMB**) - based file services.
  - Designed for Windows and Windows applications.
  - Supports AD users, access control lists, groups and security policies, along with Distributed File System(DFS, 분산파일시스템) namespaces and replication
 
 #### EFS
  - A managed NAS filter for EC2 instance based on Network File System(NFS) version 4
  - One of the first network file sharing protocols native to Unix and Linux

### 3) Amazon FSx for Lustre
Amazon FSx for Lustre is a fully managed file system that is optimized for compute-intensive workloads, such as high-performance computing, machine learning, media data processing workflows, and electronic design automation(EDA)
With Amazon FSx, you can launch and run a Lustre file system that can process massive data sets at up to hundreds of gigabytes per second of throughput, millions of IOPS, and sub-millisecond latencies.

#### 4) How is Lustre FSx different to EFS?
 #### Lustre FSx
  - Designed specifically for fast processing of workloads such as machine learning, high performance computing(HPC), video processing, financial modeling, and electronic design automation(EDA)
  - Lets you launch and run a file system that provides sub-millisecond access to your data and allows you to read and write data at speeds of up to hundreds of gigabytes per second of throughput and millions of IOPS

 #### EFS
  - A managed Nas filer for EC2 instances based on Network File System (NFS) version 4
  - one of the first network file sharing protocols native to Unix and Linux.


### In the exam You'll be given different scenarios and asked to choose whether you should use an EFS, FSx for Windows or FSx for Lustre.

#### EFS
 When you need distributed, highly resilient storage for Linux instances and Linux-based applications.

#### Amazon FSx for Windows
 When you need centralised storage for Windows-based applications such as Sharepoint, Microsoft SQL Server, Workspace, IIS Web Server or any other native Microsoft Application

#### Amazon FSx for Lustre
 When you need high-speed, high-capacity distributed storage. This will be for applications that do High Performance Compute(HPC), financial modelling etc. Remember that FSx for Lustre can store data directly on S3