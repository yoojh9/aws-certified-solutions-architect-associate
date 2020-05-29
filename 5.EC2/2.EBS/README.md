# EBS

## 1. What is EBS?

Amazon Elastic Block Store(EBS) provides persistent block storage volumes for use with Amazon EC2 instances in the AWS cloud. Each Amazon EBS volume is automatically replicated within its Availability Zone to protect you from component failure, offering high availability and durability.

Amazon Elastic Block Store(Amazon EBS)는 EC2 인스턴스에 사용할 수 있는 블록 수준 스토리지 볼륨을 제공합니다. EBS 볼륨은 형식이 지정되지 않은 원시 블록 디바이스처럼 동작합니다. 이러한 볼륨을 인스턴스에 디바이스로 마운트할 수 있습니다. 동일한 인스턴스에 여러 볼륨을 탑재하고 한 번에 여러 인스턴스에 볼륨을 탑재할 수 있습니다. 이러한 볼륨 위에 파일 시스템을 생성하거나 하드 드라이브와 같은 블록 디바이스를 사용하는 것처럼 볼륨을 사용할 수 있습니다. 인스턴스에 연결된 볼륨의 구성을 동적으로 변경할 수 있습니다. EBS 볼륨은 동일한 가용 영역에서 실행 중인 인스턴스에 연결할 수 있는 가용성이 높고 안정적인 스토리지 볼륨입니다.

<br>

## 2. 5 Different Types of EBS Storage

##### SSD

- **범용 SSD(gp2)**: 다양한 워크로드에 사용할 수 있으며 가격 대비 성능이 우수
- **프로비저닝된 IOPS SSD(io1)**: 지연 시간이 짧거나 처리량이 많은 미션 크리티컬 워크로드에 적합한 고성능 SSD 볼륨. Database

##### HDD

- **처리량에 최적화된 HDD(st1)**: 자주 액세스하는 처리량 집약적 워크로드에 적합한 저비용 HDD 볼륨. 저비용으로 일관되고 높은 처리량을 요구하는 스트리밍 워크로드 (빅데이터, 로그 처리, 데이터웨어하우스 )
- **Cold HDD(sc1)**: 자주 액세스하지 않는 워크로드에 적합한 최저 비용 HDD 볼륨. File Servers
- **EBS Magnetic(standard)**: 이전 세대 EBS 볼륨 유형. 데이터에 자주 액세스하지 않는 워크로드

<br>

## Volumes vs Snapshot

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
