***
#### Key Concepts
Cloud computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing
* Common resources are for compute, storage, database, networking

#### Shared Responsibility Model
Examples of what AWS is responsible for:
* Hardware/Global infrastructure
* Software for Compute, Storage, Database, Networking services

Examples of what the customer is responsible for:
* Securing data via client/server-side encryption
* Configuration of Virtual Infrastructure and systems
* Configuration of managed services or 3rd party software

#### Benefits of using the cloud
**Agility** - Increase agility of business
**Pay as you go pricing** - Trade capital expenses for operating expenses
**Economy of scale** - Benefit from massive economies of scale
**Global reach** - Go global in minutes
**Security** - Shared Responsibility model
**Reliability** -Performs how you need it
**Availability** - Accessible when needed
**Scalability** Grows with demand
**Elasticity** - Quickly add or remove resources

#### Six advantages to using AWS
1. Trade capital expense for variable expense
* There are no upfront costs to using resources, and you only pay for what you use
2. Benefit from massive economies of scale
* You share costs of the resources AWS provided with millions of other customers
3. Stop guessing capacity
4. Increase speed and agility
7. Stop spending money on data centers
8. Go global in minutes

#### AWS Global Infrastructure
`Regions` - A geographical location comprised of data center clusters
`Availability zones` - One or more physical data centers within a region that have their own power networking, and connectivity to each other within a region
`Edge locations` - A site used to cache copies of data for faster delivery to end users. Mostly used for the CloudFront service

#### AWS Well-Architected Framework
**Operational Excellence** - Run and monitor systems
**Security** - Protect data and systems, mitigate risk
**Reliability** - Mitigate and recover from disruptions
**Performance Efficiency** - Use resources effectively
**Cost optimization** - Get the lowest prices

#### Managing AWS resources
`Management console` - User friendly web based interface
* The most user-friendly way to interact with and manage AWS Resources
`Software Development Kits (SDKs)` - Make your code compatible to run and manage AWS resources
* Set of tools used to build software
`Command Line Interface (CLI)` - Used to programmatically make changes to your AWS resources
* Tool you can use to create and run scripts to automate processes in AWS

#### Access Keys
2 components to access keys:
* Access Key ID
* Secret access key

#### EC2
The flagship AWS compute service that allows you to launch Virtual Machines, called instances
* A VM is an emulation of a physical computer using osftware
* Multiple VM's can run on the same physical server, allowing you to share costs

You can configure components such as:
* Amount of memory
* Amount of CPU's (processor cores)
* Amount of network bandwidth
* OS 

#### EC2 instance types
`General purpose` - Balance of compute, memory, and networking resources
`Compute Optimized` - Ideal when high processing power needed
`Memory Optimized` - Used for workloads processing large data sets in memory
`Accelerated Optimized` - Primarily used for Machine Learning
`Storage Optimized` - High read/write access to large data sets on local storage

#### EC2 Tenancy Types
Tenancy is what allows for cost savings between customers
`Shared (default)` - Multiple AWS accounts are using the same physical hardware
`Dedicated instance` - Instance runs on single-tenant hardware (not an entire host)
`Dedicated host` = Instance runs on its own physical server that you can control and configure

#### EC2 Pricing Models
`On-Demand`
* Pay as you go
* Pricing works based on hourly rates

`Reserved instances`
* Best for applications that have a steady, predictable usage
* Can commit to 1 or 3 years of usage
* Can pay upfront, partial upfront, or no upfront
* Can be shared between accounts, and if not being used you can sell your reserved instances

`Spot instances`
* Unused compute capacity you can buy from AWS with up to 90% savings when compared to on demand

#### Auto scaling groups and Load balancers
These two services together are what allows you to achieve high elasticity and scalability for compute workloads

`Auto scaling groups` - Can automatically add or remove instances to meet your performance requirements
`Elastic Load Balances (ELB)` - Distribute traffic between instances to achieve best possible latency
* `Application Load balancer` - Used for distributing traffic from the web to targets in your network
* `Network Load Balancer` - Used to handle millions of requests per second (TCP traffic)

#### VM's and Containers
VM utilizes software to replicate using an actual server
* `Amazon Lightsail` - managed VM service (user friendly EC2)

Containers have everything an application needs to run on a server
* `Elastic Container Service (ECS)` - supports Docker containers
* `ECS Fargate` - More hands-off container management service
* `Elastic Kubernetes Service (EKS)` - More hands-on container management service that utilizes Kubernetes

#### Serverless
Serverless doesn't mean there are no servers, rather it refers to an absence of physical dedicated servers. In other words, your programs and workloads aren't tied to a specific server

`AWS Lambda` is the primary serverless compute tool. Used to run code without provisioning servers
`AWS Elastic Beanstalk` is fully managed service to allow you to deploy serverless web applications. You tell AWS what kind of resources your app needs to run and AWS will deploy and manage them for you, allowing you to focus on your app and not infrastructure

#### Types of storage services
`Elastic Block Storage (EBS`
* Block storage 
* Most compatible with EC2 instances
* Can be attached to multiple instances, but only one at a time

`Elastic File System (EFS)`
* File storage
* Useful when multiple users need access to the same drive
* Automatically grows or shrinks based on usage

`Simple Storage Service (S3)`
* Object storage
* Offers virtually unlimited amounts of storage 
* Most widely used AWS storage service

`AWS Snow Family`
* Used to migrate data in or out of AWS cloud

#### S3
Object based storage service with unlimited storage capacity
Consists of objects and buckets
* `Object` - What actually contains your data, similar to a file. Consists primarily of key/value pairs
* `Bucket` - What holds your objects, can contain folders. Name must be globally unique

#### S3 Storage Classes
`S3 Standard (default)`
* Most expensive, 99.99% availability, 11 9's durability, replicated across at least 3 AZ's. Very fast data retrieval

`S3 Intelligent tiering`
* Uses ML to move objects to most appropriate storage class

`S3 Standard-IA`
* Best if objects are accessed less than once a month
* Cheaper than standard, still fast data retrieval

`S3 One Zone IA`
* Same as standard IA but data only lives in one AZ, so it is cheaper

`S3 Glacier`
* Long term storage ideal for archives. Very cheap but data retrieval takes minutes to hours

`S3 Glacier Deep Archive`
* Same as Glacier but cheaper and slower

#### AWS Snow Family
Physical devices used to move data in and out of the AWS cloud

`AWS Snowcone`
* Supports 8TB of storage for HDD, 14TB for SSD

`AWS Snowball`
* Snowball Edge storage optimized - 80 TB HDD
* Snowball Edge Compute optimized - 28TB SSD

`AWS Snowmobile`
* 100 PB or more

#### AWS Relational DB Services
`Relational Database Service (RDS)`
* Support for most common SQL based databases such as MySQL, PostgreSQL, Oracle, and Microsoft SQL

`Amazon Aurora`
* Fully managed RDBS service for MySQL or PostgreSQL
* Highly available, durable, scalable, and secure
* Can be serverless as well

#### AWS non-relational DB services
`DynamoDB`
* Primary NoSQL database from AWS, designed to be extremely fast, available, and scalable
* Can scale to billions of records with guaranteed consistent data return in seconds

`DocumentDB`
* NoSQL document database, primarily used for MongoDB