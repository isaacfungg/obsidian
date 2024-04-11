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
	* Designed with native multi-AZ fault tolerance in mind

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
	* Designed with native multi-AZ fault tolerance in mind
`Aurora`
* Answer
	* A part of Amazon RDS, it's a high-performance managed relational database compatible with MySQL and PostgreSQL. It provides up to five times the performance of MySQL and three times the performance of PostgreSQL, with scalability, durability, and security.
`Redshift`
* Answer
	* A fully managed, petabyte-scale data warehouse service in the cloud. It allows you to analyze all your data using standard SQL and your existing Business Intelligence tools. It's optimized for complex queries (across large datasets) and designed for high performance.
`RDS`
* Answer
	* Makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while managing time-consuming database administration tasks, supporting several database instance types - MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server.
	* It's primary storage is EBS

 `Read Replicas`:
 * Answer
	 * These are copies of your primary database that can serve read traffic. While their primary purpose is to scale out beyond the capacity of a single database for read-heavy database workloads, they can also be promoted to become standalone databases in the event of a failure.
	 * For **Aurora**, **DynamoDB** and **ElastiCache**

#### Security Services
`AWS Trusted Advisor`
* Answer
	* Offers recommendations to help you follow AWS best practices, focusing on cost optimization, performance, security, and fault tolerance.
`Amazon Inspector`
* Answer
	* Automated security assessment service to help improve the security and compliance of applications deployed on AWS.
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

#### Communication and Networking Services
`Amazon SQS`
* Answer
	* A fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. It provides a reliable, highly scalable, hosted queue for storing messages as they travel between computers.
`Amazon SES`
* Answer
	* A cloud-based email sending service designed to help digital marketers and application developers send marketing, notification, and transactional emails. It's a cost-effective, flexible, and scalable way to send emails.
`Amazon SNS`
* Answer
	* A fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.x
`AWS Direct Connect`
* Answer
	* A cloud service solution that makes it easy to establish a dedicated network connection from your premises to AWS. This can reduce network costs, increase bandwidth throughput, and provide a more consistent network experience than internet-based connections.
`AWS Connect`
* Answer
	* A cloud-based contact center service that makes it easy for any business to deliver better customer service at lower cost. It's easy to set up, scalable, and flexible, allowing you to create a contact center in minutes and easily manage it.

#### Networking and Infrastructure Services
`AWS VPN`
* Answer
	* Provides a secure and private connection between your network or device and the AWS network. It allows you to establish secure communication channels for remote access or to connect your on-premises network to your AWS infrastructure.
`AWS Subnets`
* Answer
	* A subnet is a range of IP addresses in your VPC. Subnets allow you to segment your VPC's IP address range into smaller groups, which can be used to isolate and control access to resources for better security and operational efficiency.
`AWS Dedicated Hosts`
* Answer
	* Physical servers with EC2 instance capacity fully dedicated for your use. Dedicated Hosts can help you address compliance requirements and reduce costs by allowing you to use your existing server-bound software licenses.
`Amazon VPC`
* Answer
	* A service that lets you launch AWS resources in a logically isolated virtual network that you define. It gives you complete control over your virtual networking environment, including resource placement, connectivity, and security.

#### Others
`ElastiCache`
* Answer
	* A fully managed in-memory caching service that improves the performance of web applications by retrieving information from fast, managed, in-memory caches, instead of relying solely on slower disk-based databases. ElastiCache supports popular open-source in-memory engines such as Redis and Memcached, making it easy to set up, manage, and scale distributed in-memory data stores or cache environments in the cloud.
`Amazon Cognito`
* Answer
	* Service that provides authentication, authorization, and user management for web and mobile applications
`Amazon EMR`
* Answer
	* Cloud big data platform for processing massive amounts of data using open-source tools
`Amazon MQ`
* Answer
	* Managed message broker service for Apache ActiveMQ and RabbitMQ that makes it easy to set up and operate message brokers in the cloud
`EBS Snapshot`
* Answer
	* Point-in-time backup for your amazon EBS volume, which can be used to create a new EBS volume or restore a previous state
`AMI`
* Answer
	* An image of a server in the amazon Cloud that contains all the information necessary to boot instances of your software
`AWS WAF`
* Answer
	* Web application firewall service that helps protect web applications and API's against common web exploits and bots that may affect availability
`AWS X-ray`
* Answer
	* Provides insights into application performance and interactions with AWS and external services.
	- Helps analyze and debug distributed applications, including those built with microservices.
	- Offers an end-to-end view of requests through your application.
	- Shows a map of application components to identify performance issues and errors.
	- Useful for understanding application behavior and pinpointing the root cause of issues.
`aaS (Infrastructure as a Service)`
* Answer
	* This cloud computing model provides virtualized computing resources over the internet. IaaS allows users to rent virtual servers and storage, and to run and manage virtual data centers. Amazon EC2 is a classic example of IaaS, providing scalable compute capacity.
    
`SaaS (Software as a Service)`
* Answer
	* This model delivers software applications over the internet, on a subscription basis. Users access software through their web browser without managing underlying infrastructure. Examples include Google Workspace, Salesforce, and Microsoft Office 365.
    
`PaaS (Platform as a Service)`
* Answer
	* PaaS provides a platform allowing customers to develop, run, and manage applications without dealing with the complexities of building and maintaining the infrastructure typically associated with developing and launching an app. Examples include Heroku, Google App Engine, and AWS Elastic Beanstalk.
`AWS Elastic Beanstalk`
* Answer
	* A PaaS that automates the deployment and scaling of applications. You upload your code, and it handles provisioning, load balancing, and monitoring, while still allowing you to control the underlying resources.