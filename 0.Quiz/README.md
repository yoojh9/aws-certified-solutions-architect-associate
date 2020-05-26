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
