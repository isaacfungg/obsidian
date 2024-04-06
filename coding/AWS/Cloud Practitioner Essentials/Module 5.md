***
#### Instance Stores and Amazon Elastic Block Store
###### Instance Stores
* Provides temporary block-level storage for an EC2 instance
	* Has the same lifespan as the instance (when the instance is terminated the data is gone)
* Block-level storage volumes behave like physical hard drives

`Amazon Elastic Block Store`
* Provides block-level storage volumes that you can use with EC2 instances
* If you terminate the instance, the data attached to the EBS remains available
* To define an EBS volume, you define the configuration (such as volume, size, and type)
* Best for data that requires retention
* Stored in a single Availability Zone
* To attach an EC2 to an EBS volume, both EC2 and EBS have to be in the same Availability Zone

###### EBS Snapshots
`EBS Snapshot`
* An incremental backup
* The first backup taken of a volume copies all the data
* For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved

***

#### Amazon Simple Storage Service
###### Object Storage
* Each object consists of data, metadata, and a key
	* **Data**: Image, video, text document
	* **Metadata**:  Information about what the data is, how it is used, the object size
	* **Key**: Unique identifier

###### Amazon Simple Storage Service 
* Provides object-level storage in buckets
* You can set permissions to control visibility and access 
* Can also track changes to your objects over time

###### Amazon S3 storage classes
* Pay for what you use
* When selecting an S3 storage class, consider these two factors:
	* How often you plan to retrieve your data
	* How available you need your data to be
* `S3 Standard`
	* Designed for frequently accessed data
	* Stores data in a minimum of three Availability Zones
* `S3 Standard-Infrequent Access (Standard-IA)`
	* Ideal for infrequently accessed data
	* Similar to S3 standard but has a lower storage price and higher retrieval price
* `S3 One Zone-Infrequent Access`
	* Stores data in a single Availability Zone
	* Has a lower storage price than S3 Standard-IA
* `S3 Intelligent-Tiering`
	* Ideal for data with unknown or changing access patterns
	* Requires a small monthly monitoring and automation fee per object
* `S3 Glacier Instant Retrieval`
	* Works well for archived data that requires immediate access
	* Can retrieve objects within a few milliseconds
* `S3 Glacier Flexible Retrieval`
	* Low-cost storage designed for data archiving
	* Able to retrieve objects within a few minutes to hours
* `S3 Glacier Deep Archive`
	* Lowest-cost object storage class ideal for archiving
	* Able to retrieve objects within 12 hours
* `S3 Outposts`
	* Creates S3 buckets on Amazon S3 Outposts
	* Makes it easier to retrieve, store, and access data on AWS Outposts

***

#### Amazon Elastic File System (EFS)
###### File Storage
* Multiple clients (such as users, applications, servers) can access data that is stored in shared file folders.

`Amazon Elastic File System (EFS)`
* A scalable file system used with AWS and on-premises resources
* EFS grows and shrinks automatically
* Stores data across multiple Availability Zones

***
#### Amazon Relational Database Service (RDS)
###### Relational Database
* Data is stored in a way that relates it to another piece of data
* Uses **structured query language** (SQL) to store and query data

###### Relational Database Service (RDS)
* Automates tasks such as hardware provisioning, database setup, patching, and backups

###### RDS database engines
* Amazon RDS is available on six database engines, which optimize for memory, performance, or input/output
	* Amazon Aurora
	* PostgreSQL
	* MySQL
	* MariaDB
	* Oracle Database
	* Microsoft SQL Server

###### Amazon Aurora
* An enterprise-class relational database
* Compatible with MySQL and PostgreSQL relational databases
* Up to five times faster than standard MySQL databases and up to three times faster than standard PostgreSQL databases
* Helps reduce database costs by reducing unnecessary input/output operations


