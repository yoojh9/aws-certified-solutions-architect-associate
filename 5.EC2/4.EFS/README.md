# EFS

## 1. EFS

### 1) What is EFS?
Amazon Elastic File System(Amazon EFS) is a file storage service for Amazon Elastic Compute Cloud(Amazon EC2) instance. Amazon EFS is easy to use and provides a simple interface that allows you to create and configure file systems quickly and easily. With Amazon EFS, storage capacity is elastic, growing and shirinking automatically as you add and remove files, so your applications have the storage they need, when they need it.
It's a greate way to share files between different 2 instances.

Amazon EFS는 Amazon EC2에 사용할 수 있는 파일 스토리지 서비스이다. 자동으로 확장 가능한 스토리지이며, 분산 데이터 스토리지 설계가 가능하여 멀티스레드 application과 여러 EC2 인스턴스에서 데이터에 동시에 액세스 가능하다. 상당한 수준의 IOPS 및 처리량을 이끌어 낼 수 있다.
또한 EFS의 데이터는 여러 가용영역(AZ)에 분산되어 있어 높은 수준의 내구성 및 가용성을 제공한다. (EBS는 여러 가용영역에 분산할 수 없다.)

 - Supports the Network File System version 4 (NFSv4) protocol
 - You only pay for the storage you use (no pre-provisioning required)
 - Can scale up to the petabytes
 - Can support thousands of concurrent NFS connections
 - Data is stored across multiple AZ's within a region
 - Read After Write Consistency

### 2) S3 vs EFS vs EBS

#### (1) S3
 - 객체로 저장. S3에서 GET을 통해 객체를 추출하기 전까지 object의 content에 접근할 수 없음(GET). 
 - 객체를 바로 저장된 공간에서는 편집할 수 없고 추출하여 변경한 다음 원래 객체를 대체하기 위해 다시 넣어야한다. (PUT)
 - S3의 객체는 고유 식별자(key)와 연결됨으로 어디서나 웹을 통해 액세스 가능.
 - 정적인 웹사이트 콘텐츠 호스팅도 허용.(S3 버킷이나 CDN AWS Cloud Front를 통해 액세스 가능)

#### (2) EFS
 - EFS는 기본적으로 유닉스 기술인 NFS(Network File System) 기반이다.
 - 이름에서 알 수 있듯이 파일 시스템이며 오브젝트 스토리지보다 더 많은 기능을 제공한다
 - 공유 네트워크 파일 시스템에 적합하다.
 - 확장 가능한 스토리지
 - 여러 가용영역에 분산 가능

#### (3) EBS
 - 데이터를 동일한 크기의 블록으로 저장하고 기존 파일 시스템과 유사한 계층을 통해 데이터를 구성.
 - 독립형 스토리지가 아님! EC2와 함께 사용해야함.
 - 물리적 머신의 로컬 디스크 드라이브와 유사하게 EC2 인스턴스에 연결된, 프로비저닝 된 크기의 볼륨에 데이터를 저장하도록 설계 됨.
 - 볼륨을 구성한 후에는 쉽게 확장할 수 없음. 더 많은 저장공간이 필요한 경우 더 큰 크기의 볼륨을 구입하고 구성해야 함.
 