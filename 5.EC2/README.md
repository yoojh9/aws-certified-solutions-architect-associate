# EC2

## 1. What is EC2?

Amazon Elastic Compute Cloud(Amazon EC2) is a web service that provieds resizable compute capacity in the cloud. Amazon EC2 reduces the time required to obtain and boot new server instances to minutes, allowing you to quickly scale capacity, both up and down, as your computing requirements change.

- Termination Protection is turned off by default, you must turn in on
- On an EBs-backed instance, the default action is for the root EBS volume to be deleted when the instance is terminated.
- EBS Root Volumes of your DEFAULT AMI's CAN be encrypted. you can also use a third pary tool (Such as bit locker etc) to encrypt the root volume, or this can be done when creating AMI's in the AWS console or using the API.
- Additional volumes can be encrypted.

<br>

## 2. EC2 요금

### 1) 온디맨드

온디맨드 인스턴스에서는 실행하는 인스턴스에 따라 시간당 또는 초당 컴퓨팅 파워에 대한 비용을 지불합니다. 장기 약정이나 선결제 금액은 필요 없습니다. 애플리케이션 수요에 따라 컴퓨팅 파워를 늘리거나 줄일 수 있으며 사용한 인스턴스에 대해 지정된 시간당 요금만 지불하면 됩니다.

- 선결제 금액이나 장기 약정 없이 저렴하고 유연하게 Amazon EC2를 사용하기 원하는 사용자
- 단기의 갑작스럽거나 예측할 수 없는 워크로드가 있으며, 중단되어서는 안 되는 애플리케이션
- Amazon EC2에서 처음으로 개발 또는 시험 중인 애플리케이션

### 2) 스팟 인스턴스

Amazon EC2 스팟 인스턴스를 사용하면 온디맨드 요금보다 최대 90% 할인된 가격으로 예비 Amazon EC2 컴퓨팅 용량을 요청할 수 있습니다.

- 시작 및 종료 시간이 자유로운 애플리케이션
- 컴퓨팅 가격이 매우 저렴해야만 수익이 나는 애플리케이션
- 대량의 서버 용량 추가로 긴급히 컴퓨팅 파워가 필요한 사용자

### 3) 예약 인스턴스

예약 인스턴스는 온디맨드 인스턴스 요금과 비교하여 상당한 할인 혜택(최대 75%)을 제공합니다. 또한, 예약 인스턴스를 특정 가용 영역에 지정하면 용량 예약이 제공되므로 필요할 때 예약한 인스턴스를 시작할 수 있다는 확신을 가질 수 있습니다.
수요가 꾸준하거나 예측 가능한 애플리케이션의 경우, 예약 인스턴스를 사용하면 온디맨드 인스턴스 사용과 비교하여 상당한 비용을 절감할 수 있습니다.

- 수요가 꾸준한 애플리케이션
- 예약 용량이 필요할 수 있는 애플리케이션
- 총 컴퓨팅 비용을 절감하기 위해 1년 또는 3년 동안 EC2를 사용하기로 약정할 수 있는 고객

#### 예약 인스턴스 구매 옵션

- **표준 예약 인스턴스**: 표준 예약 인스턴스는 온디맨드 인스턴스 요금과 비교하여 상당한 할인 혜택(최대 75%)을 제공하며 1년 또는 3년 약정으로 구매할 수 있습니다. 고객은 표준 예약 인스턴스의 가용 영역, 인스턴스 크기 및 네트워킹 유형을 유연하게 변경할 수 있습니다.

- **컨버터블 예약 인스턴스**: 약정 기간에 다른 인스턴스 패밀리, 운영 체제 또는 테넌시를 사용할 수 있는 추가적인 유연성이 필요한 경우 컨버터블 예약 인스턴스를 구매할 수 있다. 컨버터블 예약 인스턴스는 온디맨드 인스턴스와 비교하여 상당한 할인 혜택(최대 54%)을 제공하며 1년 또는 3년 약정으로 구매할 수 있습니다.

- **예정된 예약 인스턴스**: 반복적인 일정에 따라 예약 인스턴스를 구매하면, 시간당 컴퓨팅 파워에 대한 요금을 지불하고 필요한 시간 기간에 대해서만 미리 용량을 예약할 수 있습니다.

### 4) 전용 호스팅

전용 호스팅은 고객 전용의 물리적 EC2 서버입니다. 전용 호스팅을 사용하면 Windows Server, SQL Server, SUSE Linux Enterprise Server(라이선스 약관에 따름)를 비롯한 기존 서버 한정 소프트웨어 라이선스를 사용할 수 있으므로 비용을 절감할 뿐 아니라 규정 준수 요구 사항도 충족할 수 있습니다

- 온디맨드로 구매 가능(시간당).
- 온디맨드 요금과 비교하여 최대 70% 할인된 예약 인스턴스로 구매 가능.

<br>

## 3. EC2 인스턴스 타입

- **F**: For FPGA
- **I**: For IOPS
- **G**: Graphics
- **H**: High Disk Throughput
- **T**: Cheap general purpose(think T2 Micro)
- **D**: For Density
- **R**: For RAM
- **M**: Main choice for general purpose apps
- **C**: For Compute
- **P**: Graphics(thick Pics)
- **X**: Extreme Memory
- **Z**: Extreme Memory and CPU
- **A**: Arm-based workloads
- **U**: Bare Metal

<br>

## 4. Security Group

보안 그룹은 인스턴스에 대한 인바운드 및 아웃바운드 트래픽을 제어하는 가상 방화벽 역할을 합니다.

- All Inbound traffic is blocked by default.
- All Outbound traffic is allowed.
- Changes to Security Groups take effect immediately
- You can have any number of EC2 instances within a security group
- You can have multiple security groups attached to EC2 instances.
- Security Groups are STATEFUL.
- If you create an inbound rule allowing traffic in, that traffic is automatically allowed back out again.
- You caannot block sepecific IP addresses using Security Groups, instead use Network Access Control Lists.
- 허용 규칙을 지정할 수 있지만 거부 규칙은 지정할 수 없습니다.
- 인바운드 트래픽과 아웃바운드 트래픽에 별도의 규칙을 지정할 수 있습니다.
- 기본적으로 보안 그룹은 모든 아웃바운드 트래픽을 허용하는 아웃바운드 규칙을 포함합니다. 규칙을 제거할 수 있으며 특정 아웃바운드 트래픽만 허용하는 아웃바운드 규칙을 추가할 수 있습니다. 보안 그룹에 아웃바운드 규칙이 없는 경우 인스턴스에서 시작하는 아웃바운드 트래픽이 허용되지 않습니다.
