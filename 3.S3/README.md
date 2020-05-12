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

<br><br>

---

# AWS Organizations & Consolidated Billing
 
 ## 1. What is AWS Organizations?
  AWS organizations는 사용자가 생성해 중앙에서 관리하는 조직으로 여러 AWS 계정을 통합할 수 있는 계정 관리 서비스이다. AWS organizations는 비즈니스의 예산, 보안과 규정 준수 요건을 충족할 수 있는 계정 관리 및 통합 결제 기능을 포함한다. 조직의 관리자로서 조직에서 계정을 생성하고 기존 계정을 조직에 초대할 수 있다.

  <img src="./BasicOrganization.png" width="450px" height="300px">

  - **조직**: AWS 계정을 단일 단위로 관리할 수 있도록 통합하기 위해 생성하는 개체. AWS Organizations 콘솔을 사용하여 조직 내 모든 계정을 중앙에서 확인하고 관리할 수 있다. 조직은 마스터 계정 하나와 0개 이상의 멤버 계정을 갖는다. 위에는 루트가, 아래에는 조직 단위(OU)가 있는 나무형 계층 구조로 계정을 조직할 수 있다.

  - **조직 단위(OU)**: 루트에 있는 계정을 위한 컨테이너. OU는 다른 OU를 포함할 수 있기 때문에 사용자는 위쪽에는 루트가, 아래쪽에는 OU 가지가, 맨 끝에는 나뭇잎에 해당하는 계정이 있는 거꾸로 된 나무 형태의 계층 구조를 만들 수 있다. 정책을 계층 구조 내의 노드 하나에 연결하면, 정책은 아래쪽으로 내려와 모든 가지(OU)와 잎(계정)에 영향을 준다. 각 OU는 상위 OU 하나만 가질 수 있으며 현재 각 계정은 한 OU의 멤버만 될 수 있다.
  
  - **계정**: AWS 리소스를 포함하는 표준 AWS 계정이다. 정책을 계정에 연결해 정책 제어를 해당 계정에만 적용할 수 있다. 조직에는 두 가지 유형의 계정이 있다. 하나는 마스터 계정으로 지정된 단일 계정이며 다른 하나는 멤버 계정이다. 마스터 계정은 조직을 생성하는 계정이다. 마스터 계정은 지급인 계정을 책임지며 멤버 계정에서 발생한 모든 요금을 지불해야 한다. 
  
  - **SCP**: Service Control Policies. SCP의 영향을 받는 계정에서 사용자와 역할이 사용할 수 있는 서비스와 작업을 지정하는 정책이다. SCP는 권한을 부여하지 않는다는 점을 제외하고 IAM 권한 정책과 비슷하다. 대신 SCP는 조직, 조직 단위(OU) 또는 계정에 대한 최대 권한을 지정한다. SCP를 조직 루트 또는 OU에 연결하면 SCP가 멤버 계정의 개체에 대한 권한을 제한한다.
 
 ## 2. Advantages of Consolidated Billing
  AWS Organizations의 통합 결제 기능을 사용하여 여러 AWS 계정의 결제를 통합할 수 있다. AWS Organizations의 모든 조직에는 (연결된) 모든 멤버 계쩡의 비용을 지불하는 마스터 계정이 하나씩 있다.

  통합 결제의 장점:
  - 하나의 청구서: 여러 계정에 대해 하나의 청구서를 받는다
  - 추적 용이: 여러 계정에 걸쳐 요금을 추적하고 비용 및 사용량 데이터 합계를 다운로드 할 수 있다
  - 사용량 통합: 조직 내 모든 계정에 걸쳐 사용량을 통합하여 대량 구매 요금 할인, 예약 인스턴스 할인 및 
  - 추가 비용 없음: 통합 결제는 추가 비용 없이 제공된다.

 ## 3. Some Best Practices With AWS Organizations
  - Always enable multi-factor authentication on root account
  - Always use a strong and complex password on root account
  - Paying account should be used for billing purpose only. Do not deploy resource into the paying account
  - Enable/Disable AWS services using Service Control Policies(SCP) either on OU or on individual accounts.

<br><br>

---

# Sharing S3 Buckets Between Account

## 1. 3 different ways to share S3 buckets across accounts
 - Using Bucket Policies & IAM (applies accross the entire bucket). Programmatic Access Only.
 - Using Bucket ACLs & IAM (individual objects). Programmatic Access Only.
 - Cross-account IAM Roles. Programmatic And Console access.
 


