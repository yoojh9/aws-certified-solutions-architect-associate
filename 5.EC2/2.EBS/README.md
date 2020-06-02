# EBS

## 1. EBS

### 1) What is EBS?

Amazon Elastic Block Store(EBS) provides persistent block storage volumes for use with Amazon EC2 instances in the AWS cloud. Each Amazon EBS volume is automatically replicated within its Availability Zone to protect you from component failure, offering high availability and durability.

Amazon Elastic Block Store(Amazon EBS)는 EC2 인스턴스에 사용할 수 있는 블록 수준 스토리지 볼륨을 제공합니다. EBS 볼륨은 형식이 지정되지 않은 원시 블록 디바이스처럼 동작합니다. 이러한 볼륨을 인스턴스에 디바이스로 마운트할 수 있습니다. 동일한 인스턴스에 여러 볼륨을 탑재하고 한 번에 여러 인스턴스에 볼륨을 탑재할 수 있습니다. 이러한 볼륨 위에 파일 시스템을 생성하거나 하드 드라이브와 같은 블록 디바이스를 사용하는 것처럼 볼륨을 사용할 수 있습니다. 인스턴스에 연결된 볼륨의 구성을 동적으로 변경할 수 있습니다. EBS 볼륨은 동일한 가용 영역에서 실행 중인 인스턴스에 연결할 수 있는 가용성이 높고 안정적인 스토리지 볼륨입니다.

<br>

### 2) 5 Different Types of EBS Storage

##### SSD

- **범용 SSD(gp2)**: 다양한 워크로드에 사용할 수 있으며 가격 대비 성능이 우수
- **프로비저닝된 IOPS SSD(io1)**: 지연 시간이 짧거나 처리량이 많은 미션 크리티컬 워크로드에 적합한 고성능 SSD 볼륨. Database

##### HDD

- **처리량에 최적화된 HDD(st1)**: 자주 액세스하는 처리량 집약적 워크로드에 적합한 저비용 HDD 볼륨. 저비용으로 일관되고 높은 처리량을 요구하는 스트리밍 워크로드 (빅데이터, 로그 처리, 데이터웨어하우스 )
- **Cold HDD(sc1)**: 자주 액세스하지 않는 워크로드에 적합한 최저 비용 HDD 볼륨. File Servers
- **EBS Magnetic(standard)**: 이전 세대 EBS 볼륨 유형. 데이터에 자주 액세스하지 않는 워크로드

<br>

## 2. Volumes vs Snapshot

- Volumes exist on EBS. Think of EBS as a virtual hard disk
- Snapshots exist on S3. Think of snapshots as a photograph of the disk
- Snapshots are point in time copies of Volumes
- Snapshots are imcremental - this means that only the blocks that have changed since your last snapshot are moved to S3.
- If this is your first snapshot, it may take some time to create.
- To create a snapshot for Amazon EBS volumes that serve as root devices, you should stop the instance before taking the snapshot.
- However you can take a snap while the instance is running
- You can create AMI's from Snapshots.
- You can change EBS volumes sizes on the fly, including changing the size and storage type.
- Volumes will always be in the same availability zone as the EC2 instance.
- To move an EC2 volume from one AZ to another, take a snapshot of it, create an AMI from the snapshot and then use the AMI to launch the EC2 instance in a new AZ.
- To move an EC2 volume from one region to another, take a snapshot of it, create an AMI from the snapshot and then copy the AMI from one region to the other. Then use the copied AMI to launch the new EC2 instance in the new region.

<br>

## 3. AMI types (EBS vs Instance Store)

You can select your AMI based on:

- Region (see Regions and Availability Zones)
- Operation System
- Architecture(32-bit or 64-bit)
- Launch Permissions
- Storage for the Root Device(Root Device Volume)
  - Instance Store(EPHEMERAL STORAGE): Amazon EC2 인스턴스 스토어가 지원하는 AMI
  - EBS Backed Volumes: Amazon EBS에서 지원하는 AMI

사용자는 Amazon EC2 인스턴스 스토어가 지원하는 AMI와 Amazon EBS에서 지원하는 AMI 중에서 선택할 수 있습니다.

### 1) For EBS Volumes

The root device for an instance launched from the AMI is an Amazon EBS volume created from an Amazon EBS snapshot.

- EBS backed instances can be stopped. You will not lose the data on this instance if it is stopped.
- You can reboot both, you will not lose your data.
- By default, both ROOT volumes(EBS, instance) will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volume.
- Amazon EBS 지원 인스턴스는 중지한 후 다시 시작해도 연결된 볼륨에 저장된 데이터에 아무런 영향이 없습니다.
- Amazon EBS 지원 인스턴스가 중지 상태일 때 다양한 인스턴스 및 볼륨 관련 작업을 수행할 수 있습니다. 예를 들어 인스턴스의 속성을 수정하거나, 인스턴스의 크기를 변경하거나, 사용하는 커널을 업데이트하거나, 디버깅 등의 목적으로 루트 볼륨을 실행 중인 다른 인스턴스에 연결할 수 있습니다.

### 2) For Instance Store Volumes

The root device for an instance launched from the AMI is an instance store volume created from a template stored in Amazon S3.

- Instance store Volumes are sometimes called Ephemeral Storage.
- Instance store volumes cannot be stopped. If the Underlying host fails, you will lose your data.
- 인스턴스 스토어 볼륨의 모든 데이터는 인스턴스가 실행되는 동안 유지되지만, 인스턴스가 종료되거나(인스턴스 스토어 지원 인스턴스는 중지 작업을 지원하지 않음) 장애가 발생하면(예: 기본 드라이브에 문제가 있는 경우) 데이터가 삭제됩니다.

<br>

## 4. ENI vs ENA vs EFA

### 1) ENI

Elastic Network Interface - essentially a virtual network card
An ENI is simply a virtual network card for your EC2 instances.

네트워크 인터페이스에는 다음 속성이 포함될 수 있다

- VPC의 IPv4 주소 범위 중 기본 프라이빗 IPv4 주소
- VPC의 IPv4 주소 범위 중 하나 이상의 보조 프라이빗 IPv4 주소
- 프라이빗 IPv4 주소당 한 개의 탄력적 IP 주소(IPv4)
- 한 개의 퍼블릭 IPv4 주소
- 한 개 이상의 IPv6 주소
- 하나 이상의 보안 그룹
- MAC 주소
- 원본/대상 확인 플래그
- 설명

#### 네트워크 인터페이스 시나리오

https://docs.aws.amazon.com/ko_kr/AWSEC2/latest/UserGuide/using-eni.html#scenarios-enis

- 관리 네트워크 생성
- VPC에서 네트워크 및 보안 어플라이언스 사용
- 작업/역할이 개별 서브넷에 지정된 이중 홈 인스턴스 생성
- 저예산 고가용성 솔루션 생성

### 2) EN(Enhanced Networking)

Enhanced Networking. Uses single root I/O virtualization(SR-IOV) to provide high-performance networking capabilities on supported instance types.

- 향상된 네트워킹에서는 지원되는 인스턴스 유형에서 **단일 루트 I/O 가상화(SR-IOV)**를 사용하여 고성능 네트워킹 기능을 제공합니다. SR-IOV는 기존 가상 네트워크 인터페이스에 비해 높은 I/O 성능 및 낮은 CPU 사용률을 제공하는 디바이스 가상화 방법입니다.
- 향상된 네트워킹을 통해 대역폭과 PPS(Packet Per Second) 성능이 높아지고, 인스턴스 간 지연 시간이 지속적으로 낮아집니다. 향상된 네트워킹 사용에 따르는 추가 요금은 없습니다.
- Use where you want good network performance.

#### 향상된 네트워킹 유형

인스턴스 유형에 따라 다음 중 한 가지 메커니즘을 사용하여 향상된 네트워킹을 활성화할 수 있습니다.

- **ENA(Elasic Network Adapter)**
  탄력적 네트워크 어댑터(ENA)는 지원되는 인스턴스 유형에 대해 최대 100Gbps의 네트워크 속도를 지원합니다.
- **intel 82599 Virtual Function(VF) 인터페이스**
  intel 82599 Virtual Function 인터페이스는 지원되는 인스턴스 유형에 대해 최대 10Gbps의 네트워크 속도를 지원합니다. This is typically used on older instances.

In any scenario question, you probably want to choose ENA over VF if given the option.

### 3) Elastic Fabric Adapter

A network device that you can attach to your Amazon EC2 instance to accelerate High Performance Computing(HPC) and machine learning application

Elastic Fabric Adapter(EFA)(EFA)는 네트워크 디바이스로 Amazon EC2 인스턴스에 연결하여 HPC(고성능 컴퓨팅, High Performance Computing) 및 기계 학습 애플리케이션 속도를 높일 수 있습니다. EFA는 AWS 클라우드가 제공하는 확장성, 유연성, 탄력성을 통해 온프레미스 HPC 클러스터의 애플리케이션 성능을 확보합니다.

- EFA는 전통적으로 클라우드 기반 HPC 시스템에서 사용하는 TCP 전송보다 지연율이 낮고 일정하며 더 높은 처리량을 제공합니다.
- EFA는 추가 기능이 있는 ENA(Elastic Network Adapter)입니다. 따라서 추가적인 OS 우회 기능을 포함한 모든 ENA의 기능을 제공합니다. OS 우회는 HPC 및 기계 학습 애플리케이션이 네트워크 인터페이스 하드웨어와 직접 통신하도록 하는 액세스 모델로서 낮은 지연율과 신뢰성 높은 전송 기능을 제공합니다
- EFA can use OS-bypass. OS-bypass enables HPC and machine learning applications to bypass the operating system kernel and to communicate directly with the EFA device. it make it a lot faster with a lot lower latency. Not supported with Windows currently, only Linux

#### In the exam you will be given different scenarios and you will be asked to choose whether you should use an ENI, EN or EFA

- **ENI**
  For basic networking. Perhaps you need a seperate management network to your production network or a separate logging network and you need to do this at low cost. In this scenario use multiple ENIs for each network

- **Enhanced Network**
  For when you need speeds between 10Gbps and 100Gbps. Anywhere you need reliable, high throughput.

- **Elastic Fabric Adaptor**
  For when you need to accelerate High Performance Computing(HPC) and machine learning applications or if you need to do an OS by-pass. If you see a scenario question mentioning HPC or ML and asking what network adaptor you want, choose EFA

<br>

## 5. Encrypted Root Device Volumes & Snapshot
 - Snapshots of encrypted volumes are encrypted automatically
 - Volumes restored from encrypted snapshots are encrypted automatically
 - You can share snapshots, but only if they are unencrypted.
 - These snapshots can be shared with other AWS accounts or made public.
 - You can now encrypt root device volumes upon creation of the EC2 instance.

 - unencrypted root device volume에서 encrypted snapshot을 만들어 encrypted instance 생성하기
    - Create a Snapshot of the unencrypted root device volume
    - Create a copy of the Snapshot and select the encrypt option
    - Create an AMI from the encrypted Snapshot
    - Use that AMI to launch new encrypted instances.
