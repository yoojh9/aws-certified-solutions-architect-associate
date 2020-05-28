#### Q1. What is an additional way to secure the AWS accounts of both the root account and new users alike?

Implement Multi-Factor Authentication for all accounts.

<br>

#### Q2. Which of the following is not a component of IAM?

- Roles
- Users
- Groups
- **Organizational Units**

<br>

#### Q3. When you create a new user, that user **\_\_\_**.

- Will be able to log in to the console anywhere in the world, using their access key ID and secret key
- **Will be able to interact with AWS using their access key ID and secret access key using the API, CLI, or the AWS SKDs**
- Will only be able to log in to the console in the region in whice that user was created
- Will be able to log in to the console only after multi-factor authentication is enabled on their account

###### → To access the console you use an account and password combination. To access AWS programmatically you use a Key and Secret Key combination.

<br>

#### Q4. Whice statement best describes IAM?

- **IAM allows you to manage users, groups, roles, and their corresponding level of access to the AWS Platform.**
- IAM allows you to manage users' passwords only. AWS staff must create new users for your organization. This is done by raising a ticket.
- IAM allows you to manage permissions for AWS resources only.
- IAM stands for Imporivised Application Management, and it allows you to deploy and manage applications in the AWS Cloud.

<br>

#### Q5. Using SAML (Security Assertion Markup Language 2.0), you can give your federated users single sign-on(SSO) access to the AWS Management Console.

- True

<br>

#### Q6. In What language are policy documents written?

- Python
- **JSON**
- Node.js
- Java

<br>

#### Q7. What is the default level of access a newly created IAM User is granted?

- Read-only access to all AWS services.
- **No access to any AWS services.**
- Administrator access to all AWS service.
- Power user access to all AWS services.

<br>

#### Q8. Which of the following is not a feature of IAM?

- IAM offers centralized control of your AWS account
- IAM integrates with existing active directory account allowing single sign-on
- IAM offers fine-grained access control to AWS resources.
- **IAM allows you to set up biometric authentication, so that no password are required.**

<br>

#### Q9. You have a client who is considering a move to AWS. In establishing a new account, what is the first thing the company should do?

- Set up account using Cloud Search
- **Set up an account using their company email address**
- Set up an account via SQS (Simple Queue Service)
- Set up an account via SNS

<br>

#### Q10. A new employee has just started work, and it is your job to give her administrator access to the AWS console. You have given her a user name, an access key ID, a secret access key, and you have generated a password for her. She is now able to log in to the AWS console, but she is unable to interact with any AWS services. What should you do next?

- **Grant her Administrator access by adding her to the Administrators' group.**
- Require multi-factor authentication for her user account.
- Ensure she is logging in to the AWS console from your corporate network and not the normal internet.
- Tell her to log out and try logging back in again

<br>

#### Q11. What level of access does the "root" account have?

- Read-only Access
- Power User Access
- **Administrator Access**
- No Access

<br>

#### Q12. Power User Access allows **\_\_\_\_**.

- Full Access to all AWS services and resources.
- Read-only access to all AWS services and resources.
- **Access to all AWS services except the management of groups and users within IAM.**
- Users to inspect the source code of the AWS platform.

<br>

#### Q13. You are a solutions architect working for a large engineering company that are moving from a legacy infrastructure to AWS. You have configured the company's first AWS account and you have set up IAM. Your company is based in Andorra, but there will be a small subsidiary operating out of South Korea, so that office will need its own AWS environment. Which of the following statements is true?

- You will then need to configure Users and Policy Documents for each region, respectively.
- **You will need to configure Users and Policy Documents only once, as theses are applied globally**
- You will need to configure your users regionally, however your policy documents are global
- You will need to configure your poclicy documents regionally, however your users are global.

 <br>

#### Q14. You are a security administrator working for a hotel chain. You have a new member of staff who has started as a systems administrator, and she will need full access to the AWS console. You have created the user account and generated the access key id and the secret access key. You have moved this user into the group where the other administrators are, and you have provided the new user with their secret access key and their access key id. However, when she tries to log in to the AWS console, she cannot. Why might that be?

- You have not applied the "log in from console" policy document to the user. You must apply this first so that they can log in.
- Your user is trying to log in from the AWS console from outside the corporate network. This is not possible
- You have not yet activated multi-factor authentication for the user, so by default they will not be able to log in.
- **You cannot log in to the AWS console using the Access Key ID / Secret Access Key pair. Instead, you must generate a password for the user, and supply the user with this password and your organization's unique AWS console login URL.**

<br>

#### Q15. Every user you create in the IAM systems starts with **\_\_\_\_**.

- Full Permissions
- Partial Permissions
- **No Permissions**

<br>

#### Q16. A **\_\_\_** is a document that provides a formal statement of one or more permissions.

- **Policy**
- User
- Group
- Role

###### → Policy(정책): 하나 또는 다수의 Permissions를 정의한 문서로 JSON파일로 되어 있다.

###### → Role(롤) : 생성된 Role은 사용자나 그룹에 할당하는 것이 아니라 EC2 같은 AWS 리소스에 할당된다.

<br>

#### Q17. You have created a new AWS account for your company, and you have also configured multi-factor authentication on the root account. You are about to create your new users. What strategy should you consider in order to ensure that there is good security on this account.

- **Enact a strong password policy: user passwords must be changed every 45 days, with each passwords containing a combination of capital letters, lower case letters, numbers, and special symbols**
- Require users only to be able to log in using biometric authentication.
- Restrict login to the corporate network only.
- Give all users the same password so that if they forget thier password they can just ask their co-workers.

<br>

#### Q18. You have been asked to advise on a scaling concern. The client has an elegant solution that works well. As the information base grows they use CloudFormation to spin up another stack made up of an S3 bucket and supporting compute instances. The trigger for creating a new stack is when the PUT rate approaches 100 PUTs per second. The problem is that as the business grows that number of buckets is growing into the hundreds and will soon be in the thousands. You have been asked what can be done to reduce the number of buckets without changing the basic architecture.

- Refine the key hashing to randomise the name Key to archieve the potential of 300 Puts per second.
- **Change the trigger level to around 3000 as S3 can now accommodate much higher PUT and GET levels**
- Upgrade all buckets to S# provisioned IOPS to archieve better perfomance
- Set up multiple accounts so that per account hard limit on S3 buckets is avoided.

###### AWS CloudFormation → 필요한 모든 AWS 리소스(예: Amazon EC2 인스턴스 또는 Amazon RDS DB 인스턴스)를 설명하는 템플릿을 생성하면 AWS CloudFormation이 해당 리소스의 프로비저닝과 구성을 담당한다.

###### AWS S3 → Amazon S3는 이제 초당 최소 3,500개의 데이터 추가 요청과 초당 5,500개의 데이터 검색 요청을 처리하는 향상된 성능을 제공한다. 따라서 추가 비용 없이 처리 시간을 대폭 단축할 수 있다.

<br>

#### Q19. You run a meme creation website where users can create memes and then download them for use on their own sites. The original images are stored in S3 and each meme's metadata in DynamoDB. You need to decide upon a low-cost storage option for the memes, themselves. If a meme object is unavailable or lost, a Lambda function will automatically recreate it using the original file from S3 and the metadata from DynamoDB. Which storage solution should you use to store the non-critical, easily reproducible memes in the most cost-effective way?

- S3
- S3 - IA
- **S3 - 1Zone-IA**
- S3 - RRS
- Glacier

###### S3 – OneZone-IA is the recommended storage for when you want cheaper storage for infrequently accessed objects. It has the same durability but less availability. There can be cost implications if you use it frequently or use it for short lived storage. Glacier is cheaper, but has a long retrieval time. RRS has effectively been deprecated. It still exists but is not a service that AWS want to sell anymore.

<br>

#### Q20. You have uploaded a file to S3. Which HTTP code would indicate that the upload was successful?

- HTTP 404
- HTTP 501
- **HTTP 200**
- HTTP 307

<br>

#### Q21. S3 has eventual consistency for which HTTP Methods?

- PUTS of new Objects and DELETES
- **Overwrite PUTS and DELETES**
- PUTS of new objects and UPDATES
- UPDATEA and DELETES

###### Amazon S3은 모든 리전의 덮어쓰기 PUT 및 DELETE에 대한 최종 일관성을 제공합니다.

<br>

#### Q22. What is Amazon Glacier?

- A tool that allows you to "freeze" an EBS volume.
- An AWS service designed for long term data archival.
- A highly secure firewall designed to keep everything out.
- It is a tool used to resurrect deleted EC2 snapshots.

<br>

#### Q23. You work for a health insurance company that amasses a large number of patients' health records. Each record will be used once when assessing a customer, and will then need to be securely stored for a period of 7 years. In some rare cases, you may need to retrieve this data within 24 hours of a claim being lodged. Given these requirements, which type of AWS storage would deliver the least expensive solution?

- S3 Standard
- S3 - IA
- S3 One Zone - IA
- **S3 Glacier**

<br>

#### Q24. The difference between S3 and EBS is that EBS is object-based whereas S3 is block-based.

- TRUE
- **FALSE**

<br>

#### Q25. What is the availability of S3 – OneZone-IA?

- 99.90%
- **99.50%**
- 99.99%
- 100%

###### → OneZone-IA is only stored in one Zone. While it has the same Durability, it may be less Available than normal S3 or S3-IA.

<br>

#### Q26. One of your users is trying to upload a 7.5GB file to S3. However, they keep getting the following error message: "Your proposed upload exceeds the maximum allowed object size.". What solution to this problem does AWS recommend?

- **Design your application to use the Multipart Upload API for all objects**
- Design your application to use large object upload API for this object
- Raise a ticket with AWS to increase your maximum object size.
- Log in to the S3 console, click on the bucket and then click properties. You can then increase your maximum object size to 1TB.

<br>

#### Q27. You run a popular photo-sharing website that depends on S3 to store content. Paid advertising is your primary source of revenue. However, you have discovered that other websites are linking directly to the images in your buckets, not to the HTML pages that serve the content. This means that people are not seeing the paid advertising, and you are paying AWS unnecessarily to serve content directly from S3. How might you resolve this issue?

- Use CloudFront to serve the static content
- **Remove the ability for images to be served publicly to the site and then use signed URLs with expiry dates.**
- Use security groups to blacklist the IP addresses of the sites that link directly to your S3 bucket.
- Use EBS rather than S3 to store the content.

<br>

#### Q28. AWS S3 has four different URLs styles that it can be used to access content in S3. The Virtual Hosted Style URL, the Path-Style Access URL, the Static web site URL, and the Legacy Global Endpoint URL. Which of these represents a correct formatting of the Virtual Hosted Style URL style

- https://my-bucket.amazonaws.com/lazycat.docx
- **https://my-bucket.s3.us-west-2.amazonaws.com/fastpuppy.csv**
- https://s3.us-west-2.amazonaws.com/my-bucket/slowpuppy.tar
- http://my-bucket.s3-website.us-east-2.amazonaws.com/index.htm
- http://my-bucket.s3-website-ap-southeast-2.amazonaws.com/index.php

###### → Virtual style puts your bucket name 1st, s3 2nd, and the region 3rd. Path style puts s3 1st and your bucket as a sub domain. Legacy Global endpoint has no region. S3 static hosting can be your own domain or your bucket name 1st, s3-website 2nd, followed by the region. AWS are in the process of phasing out Path style, and support for Legacy Global Endpoint format is limited and discouraged. However it is still useful to be able to recognize them should they show up in logs. https://docs.aws.amazon.com/AmazonS3/latest/dev/VirtualHosting.html

<br>

#### Q29. You work for a major news network in Europe. They have just released a new mobile app that allows users to post their photos of newsworthy events in real-time, which are then reviewed by your editors before being copied to your website and made public. Your organization expects this app to grow very quickly, essentially doubling its user base each month. The app uses S3 to store the images, and you are expecting sudden and sizable increases in traffic to S3 when a major news event takes place (as users will be uploading large amounts of content.) You need to keep your storage costs to a minimum, and it does not matter if some objects are lost. With these factors in mind, which storage media should you use to keep costs as low as possible?

- S3 - Infrequently Accessed Storage
- S3 - One Zone-Infrequent Access
- S3 - Reduced Redundancy Storage(RRS)
- Glacier
- S3 - Provisioned IOPS

###### → The key driver here is cost, so an awareness of cost is necessary to answer this. Full S3 is quite expensive at around $0.023 per GB for the lowest band. S3 standard IA is $0.0125 per GB, S3 One-Zone-IA is $0.01 per GB, and Legacy S3-RRS is around $0.024 per GB for the lowest band. Of the offered solutions SS3 One-Zone-IA is the cheapest suitable option. Glacier cannot be considered as it is not intended for direct access, however it comes in at around \$0.004 per GB. Of course you spotted that RRS is being deprecated, and there is no such thing as S3 – Provisioned IOPS. In this case OneZone

<br>

#### Q30. How many S3 buckets can I have per account by default?

- 10
- 20
- 50
- **100**

<br>

#### Q31. You work for a busy digital marketing company who currently store their data on-premise. They are looking to migrate to AWS S3 and to store their data in buckets. Each bucket will be named after their individual customers, followed by a random series of letters and numbers. Once written to S3 the data is rarely changed, as it has already been sent to the end customer for them to use as they see fit. However, on some occasions, customers may need certain files updated quickly, and this may be for work that has been done months or even years ago. You would need to be able to access this data immediately to make changes in that case, but you must also keep your storage costs extremely low. The data is not easily reproducible if lost. Which S3 storage class should you choose to minimize costs and to maximize retrieval times?

- S3
- **S3 - IA**
- S3 - 1Zone-IA
- S3 - RRS
- Glacier

###### → The need to immediate access is an important requirement along with cost. Glacier has a long recovery time at a low cost or a shorter recovery time at a high cost, and 1Zone-IA has a lower Availability level which means that it may not be available when needed.

<br>

#### Q32. What is the availabillity of objects stored in S3?

- 99%
- 99.90%
- 99.99%
- 100%

<br>

#### Q33. S3 has what consistency model for PUTS of new objects?

- **Read After Write Consistency**
- Write After Read Consistency
- Eventual Consistency
- Usual Consistency

 <br>

#### Q34. What does S3 stand for?

- Simple SQL Service
- **Simple Storage Service**
- Simplified Serial Sequence
- Straight Storage Service

<br>

#### Q35. You are a solutions architect who works with a large digital media company. The company has decided that they want to operate within the Japanese region and they need a bucket called "testbucket" set up immediately to test their web application on. You log in to the AWS console and try to create this bucket in the Japanese region however you are told that the bucket name is already taken. What should you do to resolve this?

- Change your region to Korea and then create the bucket "testbucket".
- Raise a ticker with AWS and ask them to release the name "testbucket" to you.
- Bucket names are global, not regional. This is a popular bucket name and is already taken. You should choose another bucket name.
- Run a WHOIS request on the bucket name and get the registered owners email address. Contact the owner and ask if you can purchase the rights to the bucket.

<br>

#### Q36. What is the minimum file size that I can store on S3?

- 1KB
- 1MB
- **0bytes**
- 1byte

<br>

#### Q37. What is AWS Storage Gateway?

- **It is a physical or virtual appliance that can be used to cache S3 locally at a customer's site.**
- It allows large scale import/exports into the AWS cloud without the use of an internet connection.
- It allows a direct MPLS connection into AWS.
- None of the above.
