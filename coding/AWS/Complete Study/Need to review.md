***
`AWS Organizations`
* Answer
	* Allows management of multiple AWS accounts, enabling centralized billing, account management, and applying policies across accounts for governance.
`IAM User Groups`
* Answer
	* A way to manage IAM users by grouping them, making it easier to assign permissions to multiple users at once.
`IAM Users`
* Answer
	* Represent individuals or applications that interact with AWS services, each having a unique set of credentials and permissions to access and manage AWS resources securely.
`AWS Config`
* Answer
	* Provides a detailed view of the configuration of AWS resources in your account, including changes over time, for security and governance compliance.

#### Storage
`EBS`
* Answer
	* Provides persistent block storage volumes for use with EC2 instances, allowing you to store data beyond the lifecycle of a single EC2 instance.
`Instance store`
* Answer
	* Offers temporary block-level storage directly attached to the host computer for an EC2 instance. Data is lost if the instance is stopped or terminated.
`EFS`
* Answer
	* Offers scalable file storage for use with AWS Cloud services and on-premises resources. It's built to scale on demand to petabytes without disrupting applications, supporting multiple EC2 instances.
`S3`
* Answer
	* Object storage service that offers industry-leading scalability, data availability, security, and performance. It can store and protect any amount of data for a range of use cases.
	* For more general storage cases (not working with ec2)

#### S3 Tiers
`S3 Standard`
* Answer
	* For frequently accessed data, offering high durability, availability, and performance object storage for a wide range of applications.
`S3 Intelligent-Tiering`
* Answer
	* Automatically moves data between two access tiers based on changing access patterns, suitable for data with unknown or changing access patterns.
`S3 Standard-IA`
* Answer
	* For data that is less frequently accessed but requires rapid access when needed. Lower fee than Standard, but with a retrieval fee.
`S3 One Zone-IA`
* Answer
	* Similar to Standard-IA but stored in a single availability zone. Cost-effective for infrequently accessed data that doesn't require the resilience of multiple availability zones.
`S3 Glacier`
* Answer
	* For long-term archiving and backup at very low costs. Retrieval times can range from minutes to hours.
`S3 Glacier Deep Archive`
* Answer
	* The lowest-cost storage option for long-term archive and digital preservation, with retrieval times of 12 hours or longer.
#### Management and Governance Tools
`Elastic Load Balancer`
* Answer
	* Automatically distributes incoming application traffic across multiple targets, such as EC2 instances, ensuring fault tolerance and scalability of your application.
`AWS Budgets`
* Answer
	* Allows you to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount, helping you stay within your cost and usage limits.
`AWS Auto Scaling`
* Answer
	* Monitors your applications and automatically adjusts capacity to maintain steady, predictable performance at the lowest possible cost. It can scale EC2 instances up or down according to conditions you define.
`AWS Cost Explorer`
* Answer
	* An AWS service that enables you to visualize, understand, and manage your AWS costs and usage over time. It provides detailed reports that analyze your costs and usage trends.

#### Database Services
`DynamoDB`
* Answer
	* A fully managed NoSQL database service known for its high performance and scalability. It supports key-value and document data structures, ideal for web, mobile, gaming, ad tech, IoT, and many other applications.
`Aurora`
* Answer
	* A part of Amazon RDS, it's a high-performance managed relational database compatible with MySQL and PostgreSQL. It provides up to five times the performance of MySQL and three times the performance of PostgreSQL, with scalability, durability, and security.
`Redshift`
* Answer
	* A fully managed, petabyte-scale data warehouse service in the cloud. It allows you to analyze all your data using standard SQL and your existing Business Intelligence tools. It's optimized for complex queries (across large datasets) and designed for high performance.
`RDS`
* Answer
	* Makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while managing time-consuming database administration tasks, supporting several database instance types - MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server.

#### Security Services
`AWS Trusted Advisor`
* Answer
	* Offers recommendations to help you follow AWS best practices, focusing on cost optimization, performance, security, and fault tolerance.
`Amazon Inspector`
* Answer
	* Automated security assessment service to help improve the security and compliance of applications deployed on AWS.
`Amazon SNS`
* Answer
	* A fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.
`Amazon CloudWatch`
* Answer
	* Provides data and actionable insights to monitor applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health.

#### AWS Support
`AWS Knowledge Center`
* Answer
	* A repository of informational articles and best practices for using AWS services and features, addressing common user questions and issues.
`AWS Health Dashboard`
* Answer
	* Provides real-time visibility into the health of AWS services and accounts, alerting users to ongoing issues and planned maintenance events.
`Infrastructure Event Management`
* Answer
	* Part of AWS Support, offering planning and support for customers expecting high-traffic events, ensuring their AWS environment is optimized for scale and reliability.
`Concierge Support Team`
* Answer
	* Part of AWS Support that provides account and billing guidance, and specialized attention from AWS to Business and Enterprise support plan customers.