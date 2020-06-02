# CloudWatch

## 1. CloudWatch

### 1) What is CloudWatch?
Amazon CloudWatch is a monitoring service to monitor your AWS resources, as well as the applications that you run on AWS.

Amazon CloudWatch는 Amazon Web Services(AWS) 리소스와 AWS에서 실시간으로 실행 중인 애플리케이션을 모니터링합니다.
CloudWatch를 사용하면 시스템 전체의 리소스 사용률, 애플리케이션 성능 및 운영 상태를 파악할 수 있습니다.

 - CloudWatch is used for monitoring performance.
 - CloudWatch can monitor most of AWS as well as your applications that run on AWS.
 - CloudWatch with EC2 will monitor events every 5 minutes by default.
 - You can have 1 minute intervals by turning on detailed monitoring.
 - You can create CloudWatch alarms which trigger notifications.
 - CloudWatch is all abount performance. CloudTrail is all about auditing.

 - Standard Monitoring = 5 Minutes
 - Detailed Monitoring = 1 Minute

### 2) What can CloudWatch monitor?

#### CloudWatch can monitor things like
 - Compute
    - EC2 instance
    - Autoscaling Groups
    - Elastic Load Banlancer
    - Route53 Health Checks
 - Storage & Content Delivery
    - EBS volumes
    - Storage Gateways
    - CloudFront

### 3) Host Level Metrics Consist of:
 - CPU
 - Network
 - Disk
 - Status Check

### 4) What can I do with CloudWatch?
 - Dashboards: Create awesome dashboards to see what is happening with your AWS environment. Amazon CloudWatch 대시보드는 CloudWatch 콘솔에서 사용자 지정이 가능한 홈 페이지로, 다른 리전에 분산되어 있는 리소스들을 단일 뷰에서 모니터링하는 데 사용할 수 있습니다. CloudWatch 대시보드를 사용해 AWS 리소스에 대한 지표 및 경보를 보여주는 사용자 지정 뷰를 생성할 수 있습니다.
 - Alarms: Allows you to set Alarms that notify you when particular thresholds are hit.
 - Events: CloudWatch Events helps you to respond to state changes in your AWS resources.
 - Logs: CloudWatch Logs helps you to aggregate, monitor, and store logs.



<br>

## 2. CloudTrail

### 1) What is AWS Cloud Trail?
AWS CloudTrail increase visiblity into your user and resource activity by recording AWS Management Console actions and API calls. You can identify which users and accounts called AWS, the source IP address from which the calls where made, and when the calls occurred.

AWS CloudTrail은 계정의 거버넌스, 규정 준수, 운영 및 위험 감사를 활성화하도록 도와주는 서비스입니다. 사용자, 역할 또는 AWS 서비스가 수행하는 작업들은 CloudTrail에 이벤트로 기록됩니다. 이벤트에는 AWS Management 콘솔, AWS Command Line Interface 및 AWS SDK, API에서 수행되는 작업들이 포함됩니다.
AWS 계정 활동에 대한 가시성은 보안 및 운영 모범 사례에서 중요한 측면입니다. CloudTrail을 사용하여 AWS 인프라 전반에서 계정 활동을 확인, 검색, 다운로드, 보관 및 응답할 수 있습니다.

### 2) CloudTrail vs CloudWatch
 - CloudWatch monitors performance.
 - CloudTrail monitors API calls in the AWS platform.


