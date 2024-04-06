***
#### Connectivity to AWS
`Amazon Virtual Private Cloud (VPC)`:  A networking service that you can use to establish boundaries around your AWS resources

`Subnet`: A section of a VPC that can contain resources such as Amazon EC2 instances
* `Public Subnets`
	* Contains resources that need to be accessible by the public
* `Private Subnets`
	* Contains resources that should be accessible only through your private network
	
`Internet Gateway`: Allows public traffic from the internet to access your VPC

`Virtual Private Gateway`
* Allows you to access private resources in a VPC
* Generally easier and cheaper to set up
* Uses the public internet for connectivity
`AWS Direct Connect`
* Allows you to establish a dedicated private connection between your data center and a VPC
* Requires physical setup and may have a higher cost
* Uses a private, dedicated network line

