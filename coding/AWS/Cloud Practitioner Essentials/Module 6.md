*** 
#### AWS Shared Responsibility Model
`Customers: Security in the cloud`: Responsible for the security of everything they create and put in the AWS Cloud

`AWS: Security of the cloud`: Responsible for security of the cloud

***
#### User Permissions and Access

###### AWS Identity and Access Management (IAM)
* Enables you to manage access to AWS services and resources securely
###### AWS account root user
* When you first create an AWS account, you begin with an identity known as the `root user`.
* The `root user` is accessed by signing in with the email address and password that you used to create your WS account

**Best Practice**: Do *not* use the root user for everyday tasks
* Create an IAM user and assign it permissions to create other users

###### IAM users
`IAM user`: An identity that you create in AWS that represents the person or application that interacts with AWS services and resources
* By default it has no permissions associated with it

###### IAM policies
`IAM Policy`: A document that allows or denies permission to AWS services and resources
