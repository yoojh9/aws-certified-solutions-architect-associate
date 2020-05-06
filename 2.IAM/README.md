## IAM

### 1. What is IAM ?

IAM allows you to manage users and their level of access to the AWS console.
It is important to understant IAM and how it works, both for the exam and for administrating a company's AWS account in real life.

- IAM is universal. It does not apply to regions at this time
- The "root account" is simply the account created when first setup your AWS account. It has complete Admin access
- New Usres have No permissions when first created
- New users are assigned **Access Key Id** & **Secret Access Keys** when first created.
- Always setup Multifactor Authentication on your root account.
- You can create and customize your own password rotation policies.

### 2. Identity Access Management(IAM) offers the following features;

- Centralised control of your AWS account
- Shared Access to your AWS account
- Granular Permissions
- Identity Federation(Including Active Directory, Facebook, Linkedin etc)
- Multifactor Authentication
- Provied temporary access for users/devices and services where necessary
- Allow you to set up your own password rotation policy
- Integrates with many different AWS services.

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
