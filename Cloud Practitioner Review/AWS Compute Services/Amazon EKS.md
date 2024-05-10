* A managed service that allows you to run Kubernetes on AWS without installing, operating, or maintaining your own Kubernetes control plane or nodes
* Integration with various AWS services to provide scalability and security for your applications:
	* `Amazon ECR` for container images
	* `Elastic Load Balancing` for load distribution
	* `IAM` for authentication
	* `Amazon VPC` for isolation

#### Components
**Clusters**
* An EKS cluster is made up of two main components:
	* EKS control plane
		* Made up of nodes than run the Kubernetes software
	* EKS nodes
		* Connects to the cluster's control plane via the API server endpoint
* EKS Supports two autoscaling products
	* `Cluster Autoscaler`
	* `Karpenter`
	* 