# S3

S3 provides developers and IT teams with secure, durable, highly-scalable object storage. Amazon S3 is easy to use, with a simple web services interface to store and retrieve any amount of data from anywhere on the web

- S3 is a safe place to store your files
- It is Object-based storage
- The data is spread across multiple devices and facilities

## 1. The basics of S3
- S3 is **Object-based** \-\- i.e. allows you to upload files
- Files can be form 0 Bytes to 5TB.
- There is unlimited storage
- Files are stored in Buckets.
- S3 is a universal namespace. That is, names must be unique globally
- When you upload a file to S3, you willl receive a HTTP 200 code if the upload was successful

### 1) S3 is Object based. Think of Objects just as files.

Objects consist of the following:

- Key (This is simply the name of the object)
- Value (This is simply the data and is made up of a sequence of bytes)
- Version ID (Important for versioning)
- Metadata (Data about data you are storing)
- Subresources (Access Control Lists, Torrent)

### 2) How does data consistency work for S3?

- If you write a new file and read it immediately afterwards, you will be able to view that data
- If you update AN EXISTING file or delete a file and read it immediately, you may get the older version, or you may not. Basically changes to objects can take a little bit of time to propagate.

### 3) S3 has the following features

- Tiered Storage Available
- Lifecycle Management
- Versioning
- Encryption
- MFA Delete
- Secure your data using **Access Control Lists** and **Bucket Policies**

### 4) S3 Storage Classes

#### (1) S3 Standard

- 99.99% availability 99.999999999% durability, stored redundantly across multiple devices in multiple facilities, and is designed to sustain the loss of 2 facilities concurrently

#### (2) S3 - IA (Infrequently Accessed)

- For data that is accessed less frequently, but requires rapid access when needed. Lower fee than S3, but you charged a retrieval fee.

#### (3) S3 One Zone - IA

- For where you wnat a lower-cost option for infrequently accessed data, but do not require the multiple Availability Zone data resilience.

#### (4) S3 - Intelligent Tiering

- Designed to optimize costs by automatically moving data to the most cost-effective access tier, without performance impact or operational overhead.

#### (5) S3 Glacier

- S3 Glacier is a secure, durable, and low-cost storage class for data archiving. You can reliably store any amount of data at costs that are competitive with or cheaper than on-premises solutions. Retrieval times configurable from minutes to hours

#### (6) S3 Glacier Deep Archive

- S3 Glacier Deep Archive is Amazon S3's lowest-cost storage class where a retrieval time of 12 hours is acceptable

### 5) You are charged for S3 in the following ways

- Storage
- Requests
- Storage Managment Pricing
- Data Transfer Pricing
- Transfer Acceleration (Permission of object)
- Cross Region Replication Pricing

### 6) S3 Transfer Acceleration

Amazon S3 Transfer Acceleration enables fast, easy, and secure transfer of files over long distances between your end users and an s3 bucket.

Transfer Acceleration takes advantage of Amazon CloudFront's globally distributed edge location. As the data arrives at an edge location, data is routes to Amazon S3 over an optimized network path.


## 2. S3 Bucket
 - control access to buckets using either a **bucket ACL** or using **Bucket Polices**


## 3. S3 Pricing Tiers

### 1) What makes up the cost of S3?
 - Storage
 - Request and Data Retrievals
 - Data Transfer
 - Management & Replication

### 2) What are the different Tiers?
 - S3 Standard
 - S3 - IA
 - S3 One Zone - IA
 - S3 - Intelligent Tiering
 - S3 Glacier
 - S3 Glacier Deep Archive


## 4. S3 Security & Encryption
 By default, all newly created buckets are PRIVATE. You can setup access control to your buckets using;
  - Bucket Policies (Bucket Level)
  - Access Control Lists (individual objects)

 S3 buckets can be configured to create access logs which log all requests made to the S3 bucket. This can be sent to another bucket and event another bucket in another account

 Encryption In Transit is achieved by
  - SSL/TLS

 Encryption At Rest(Server Side) is achieved by
  - S3 Managed Keys - SSE-S3
  - AWS Key Managements Service, Managed Keys - SSE-KMS
  - Server Side Encryption With Customer Proviede Keys - SSE-C

 Client Side Encryption
  
## 5. S3 Version Control
 Using **Versioning** With S3;
  - Stores all versions of an object (including all writes and even if you delete an object)
  - Great backup tool
  - Once enabled, Versioning cannot be disabled, only suspended.
  - Integrates with Lifecycle rules
  - Versioning's **MFA Delete** capability, which uses multi-factor, can be used to provide an additional layer of security.

## 6. S3 Lifecycle Management and Glacier
 - Automates moving your objects between the different storage tier
 - Can be used in conjunction with versioning
 - Can be applied to current versions and previous versions

---

# AWS Organizations & Consolidated Billing
 
 ## 1. What is AWS Organizations?
  AWS Organizations is an account management service that enables you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

