***
#### AWS Cloud Adoption Framework
###### Six core perspectives of the Cloud Adoption Framework
* AWS CAF organizes guidance into six areas of focus, called `Perspectives`

`Business Perspective`
* Ensures that IT aligns with business needs and that IT investments link to key business results

`People Perspective`
* Supports development of an organization-wide change management strategy for successful cloud adoption

`Governance Perspective`
* Focuses on the skills and processes to align IT strategy with business strategy
* Ensures that you maximize the business value and minimize risks

`Platform Perspective`
* Includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud

`Security Perspective`
* Ensures that the organization meets security objectives for visibility, audibility, control, and agility

`Operations Perspective`
* Helps you to enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders

***
#### Migration Strategies
###### 6 Strategies for Migration
`Rehosting`
* Involves moving applications without changes

`Refactoring`
* Involves reimagining how an application is architected and developed by using cloud-native features

`Repurchasing`
* Involves moving from a traditional license to a software-as-a-service model

`Retaining`
* Consists of keeping applications that are critical for the business in the source environment

***
#### AWS Snow Family
`AWS Snow Family`
* A collection of physical devices that help to physically transport up to exabytes of data into and out of AWS
* Composed of Snowcone, Snowball, and Snowmobile

`AWS Snowcone`
* Small, rugged, and secure edge computing and data transfer device
* Features 2 CPUs, 4 GB of memory, and up to 14 TB of usable storage

`AWS Snowball`
* `Snowball Edge Storage Optimized`
	* Well suited for large-scale data migrations and recurring transfer workflows, in addition to local computing with higher capacity needs
	* Storage: 80 TB of HDD capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA SSD for block volumes
	* Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe 1 instances
* `Snowball Edge Compute Optimized`
	* Provides a powerful computing resource for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks
	* Storage: 80-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 28 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes
	* Compute: 104 vCPUs, 416 GiB of memory, and an optional NVDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances

`AWS Snowmobile`
* An exabyte-scale data transfer service used to move large amounts of data to AWS
* Can transfer up to 100 petabytes of data per Snowmobile, a 45 foot long ruggedized shipping container, pulled by a semi trailer truck

***
#### Innovation with AWS
###### Innovate with AWS Services
`Serverless applications`
* Refers to applications that don't require you to provision, maintain, or administer servers
* You don't need to worry about fault tolerance or availability

`Artifical Intelligence`
* Convert speech to text with Amazon Transcribe
* Discover patterns in text with Amazon Comprehend
* Identify potentially fraudulent online activities with Amazon Fraud Detector
* Build voice and text chatbots with Amazon Lex

`Machine Learning`
* Amazon SageMaker to remove the difficult work from the process and empower you to build, train, and deploy ML models quickly
