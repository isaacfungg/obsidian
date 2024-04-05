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
