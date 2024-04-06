***
#### Connectivity to AWS
`Amazon Virtual Private Cloud (VPC)`:  A networking service that you can use to establish boundaries around your AWS resources
`Internet Gateway`: Allows public traffic from the internet to access your VPC

`Virtual Private Gateway`
* Allows you to access private resources in a VPC
* Generally easier and cheaper to set up
* Uses the public internet for connectivity
`AWS Direct Connect`
* Allows you to establish a dedicated private connection between your data center and a VPC
* Requires physical setup and may have a higher cost
* Uses a private, dedicated network line

#### Subnets and Network Access Control Lists
`Subnet`: A section of a VPC that can contain resources such as Amazon EC2 instances
* `Public Subnets`
	* Contains resources that need to be accessible by the public
* `Private Subnets`
	* Contains resources that should be accessible only through your private network

###### Network Traffic in a VPC
When a customer requests data from an application hosted in the AWS Cloud, this request is sent as a `packet`.
`Packet`: A unit of data sent over the internet or a network

###### Network ACLs
`Network Access Control List`: A virtual firewall that controls inbound and outbound traffic at the subnet level
* By default, a network ACL allows all inbound and outbound traffic
* Network ACLs perform `stateless` packet filtering. They remember nothing and check packets that cross the subnet border each way inbound and outbound.

###### Security Groups
`Security Group`: Virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance
* By default, a security group denies all inbound traffic and allows all outbound traffic
* Security groups perform `stateful` packet filtering. They remember previous decisions made for incoming packets.

#### Global Networking
