***
#### Global Infrastructure

`Selecting a Region`
* When determining the right Region for your services, data, and applications, consider the following four business factors
* `Compliance with data governance and legal requirements`
	* For example, if your company requires all of its data to reside within the boundaries of the UK, you would choose the London Region
* `Proximity to your customers`
	* Selecting a Region that is close to your customers will help you to get content to them faster
* `Available services within a Region`
	* Sometimes the closest Region might not have all the features that you want to offer to customers
* `Pricing`

`Availability Zone`: A single data center or group of data centers within a Region. 

`Edge Location`: A site that Amazon CLoudFront uses to store cached copies of your content closer to your customers for faster delivery

#### How to Provision AWS Resources

##### **Ways to interact with AWS Services**
`AWS Management Console`
* Web-based interface for accessing and managing AWS services
`AWS Command Line Interface (CLI)` 
* Allows you to control multiple AWS services directly from the command line within one tool
`Software Development Kits (SDKs)`
* Makes it easier to use AWS services through an API designed for your programming language or platform


`AWS Beanstalk`
* You provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:
	* Adjust capacity
	* Load balancing
	* Automatic scaling
	* Application health monitoring

`AWS CloudFormation`
* You can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources

``