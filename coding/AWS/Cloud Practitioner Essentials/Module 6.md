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

**Best Practice**: Follow the security principle of *least privilege* when granting permissions
###### IAM groups
`IAM group`: A collection of IAM users
* When assigning an IAM policy to a group, all users in the group are granted permissions specified by the policy
###### IAM roles
`IAM role`: An identity that you can assume to gain temporary access to permissions
* When someone assumes an IAM role, they abandon all previous permissions that they had under a previous role and assume the permissions of the new role

**Best Practice**: IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term

***
#### AWS Organizations
###### AWS Organizations
`AWS Organizations`: Used to consolidate and manage multiple AWS accounts within a central location
* When you create an organization, AWS Organizations automatically creates a root
* You can centrally control permissions for the accounts in your organization by using `service control policies (SCPs)`
`Service Control Policies`: Enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access

###### Organizational Units
* When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy

***
#### Compliance
###### AWS Artifact
`AWS Artifact`: A service that provides on-demand access to AWS security and compliance reports and select online agreements

`AWS Artifact Agreements`: Allows you to review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations
`AWS Artifact Reports`: Provide compliance reports from third-party auditors

###### Customer Compliance Center
`Customer Compliance Center`: Contains resources to help you learn more about AWS compliance

***

