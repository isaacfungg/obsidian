***
#### Instance Stores and Amazon Elastic Block Store
###### Instance Stores
* Provides temporary block-level storage for an EC2 instance
	* Has the same lifespan as the instance (when the instance is terminated the data is gone)
* Block-level storage volumes behave like physical hard drives

`Amazon Elastic Block Store`
* Provides block-level storage volumes that you can use with Ec2 instances
* If you terminate the instance, the data attached to the EBS remains available
* To define an EBS volume, you define the configuration (such as volume, size, and type)
* Best for data that requires retention

###### EBS Snapshots
`EBS Snapshot`
* An incremental backup
* The first backup taken of a volume copies all the data
* For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved

***

#### Amazon Simple Storage Service
###### Object Storage
