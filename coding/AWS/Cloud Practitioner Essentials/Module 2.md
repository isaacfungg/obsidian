***
#### EC2 Instance Types
`General purpose instances`
* Provides a balance of compute, memory and networking resources
* Good when you do not require optimization in any single resource area

`Compute ooptimized isntances`
* Ideal for compute-bound applications that benefit from high-performance processors

`Memory optimized instances`
* Deliver fast performance for workloads that process large datasets in memory

`Accelerated computing instances`
* Performs some functions more efficiently than is possible in software running on CPUs
* For ML, AI, 3d rendering

#### EC2 Pricing
`On-Demand`
* Ideal for short-term, irregular workloads that cannot be interrupted
* No upfront costs or minimum contracts apply

`Reserved Instances`
* Billing discount applied to the use of **On-Demand** instances in your account
* `Standard Reserved Instances`
	* If you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them
* `Convertible Reserved Instances`
	* If you need to run your EC2 instances in different Availability Zones or different instance types

`EC2 Instance Savings Plan`
* Reduces your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term.

`Spot Instances`
* Ideal for workloads with flexible start and end times, or that can withstand interruptions

`Dedicated Hosts`
* Physical servers with Amazon EC2 instance capacity that is fully dedicated to your use.

#### Directing Traffic with Elastic Load Balancing
`Elastic Load balancing`: AWS service that automatically distributes incoming application traffic across multiple resources

**Example**
`Low-Demand period`
* If only a few registers are open, this matches the demand of customers who need service. The coffee shop is less likely to have open registers with no customers. 

`High-Demand period`
* A coffee shop employee directs customers to the most appropriate register so that the number of requests can evenly distribute across the open registers.

#### Messaging and Queuing
`Monolithic Application`: An application with tightly coupled components
* Solution: Design your application through `microservices` approach
	* Application components are loosely coupled. In this case, if a single component fails, the other components continue to work because they are communicating with each other. The loose coupling prevents the entire application from failing.

`Amazon Simple Notification Sercie (SNS)`
* It enables the sending of messages or notifications from an application to multiple subscribers or other applications, including push notifications to mobile devices, email, SMS, and messaging to SQS queues or any HTTP endpoint.

`Amazon Simple QUeue Service (SQS)`
* Can send, store, and receive messages between software components, without losing messages or requiring other services to be available
