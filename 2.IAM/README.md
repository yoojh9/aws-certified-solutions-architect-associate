## IAM

### 1. What is IAM ?
AWS Identity and Access Management(IAM)는 리소스에 대한 액세스를 안전하게 제어할 수 있는 웹 서비스이다. IAM을 사용하여 리소스를 사용하도록 인증(로그인) 및 권한 부여(권한 있음)된 대상을 제어한다.
AWS 계정을 처음 생성할 때는 해당 계정의 모든 AWS 서비스 및 리소스에 대한 완전한 액세스 권한이 있는 SSO(Single Sign-In) ID로 시작한다. 이를 AWS 계정 **루트 사용자**라고 하며 계정을 생성할 때 사용한 이메일 주소와 암호로 로그인하여 액세스한다. 일상적인 작업은 물론 관리 작업에도 루트 사용자를 사용하지 않는 것이 좋다. 대신 IAM 사용자를 처음 생성할 때만 루트 사용자를 사용하라.
루트 사용자의 자격 증명을 안전하게 보관해 두고 몇 가지 계정 및 서비스 관리 작업을 수행할 때만 해당 작업 증명을 사용한다.

IAM allows you to manage users and their level of access to the AWS console.
It is important to understant IAM and how it works, both for the exam and for administrating a company's AWS account in real life.

- IAM is universal. It does not apply to regions at this time
- The "root account" is simply the account created when first setup your AWS account. It has complete Admin access
- New Usres have No permissions when first created
- New users are assigned **Access Key Id** & **Secret Access Keys** when first created.
- Always setup Multifactor Authentication on your root account.
- You can create and customize your own password rotation policies.

### 2. Identity Access Management(IAM) offers the following features;
- **AWS 계정에 대한 공유 액세스**: 암호나 액세스 키를 공유하지 않고도 AWS 계정의 리소스를 관리하고 사용할 수 있는 권한을 다른 사람에게 부여할 수 있다.
- **세분화된 권한**: 리소스에 따라 여러 사람에게 다양한 권한을 부여할 수 있다. 예를 들어 일부 사용자에게는 Amazon Elastic Compute Cloud(Amazon EC2), Amazon Simple Storage Service(Amazon S3), Amazon DynamoDB, Amazon Redshift 및 기타 AWS 서비스에 대한 전체 액세스 권한을 허용하고 다른 사용자에게는 일부 S3 버킷에 대한 읽기 전용 권한, 일부 EC2 인스턴스를 관리할 수 있는 권한 또는 결제 정보에만 액세스할 수 있는 권한을 허용할 수 있다
- **Amazon EC2에서 실행되는 애플리케이션을 위한 보안 AWS 리소스 액세스**: EC2 인스턴스에서 실행되는 애플리케이션의 경우 IAM 기능을 사용하여 자격 증명을 안전하게 제공할 수 있다. 이러한 자격 증명은 애플리케이션에 다른 AWS 리소스에 액세스할 수 있는 권한을 제공한다. 예를 들면 이러한 리소스에는 S3 버킷 및 DynamoDB 테이블이 있다.
- **멀티 팩터 인증(MFA)**: 보안 강화를 위해 계정과 개별 사용자에게 2팩터 인증을 추가할 수 있다. MFA를 사용할 경우 계정 소유자나 사용자가 계정 작업을 위해 암호나 액세스 키뿐 아니라 특별히 구성된 디바이스의 코드도 제공해야 한다.
- **자격 증명 연동**: 기업 네트워크나 인터넷 자격 증명 공급자와 같은 다른 곳에 이미 암호가 있는 사용자에게 AWS 계정에 대한 임시 액세스 권한을 부여할 수 있다.
- Provied temporary access for users/devices and services where necessary
- Allow you to set up your own password rotation policy
- **많은 AWS 서비스와의 통합**

### 3. Key Terminology for IAM

#### 1) Users

End users such as people, employees of an organization etc.

#### 2) Groups

A collection of users. Each user in the group will inherit the permissions of the group

#### 3) Policies

Policies are made up of documents, called Policy documents.
Thise documents are in a format called JSON and they give permission as to What a User/Group/Role is able to do.

#### 4) Roles

You create roles then assign them to AWS Resources.
