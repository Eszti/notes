# Architecting for reliability

## Defining realiability

### Reliability or Resiliency

- to avoid af an application to avoid and recover from failure

### Availability

- quentifying reliability
- poor performance implies low availability
- decide early

### Architecting

#### Traditional Application

- backend : database
- frontend: web interface & logic
- two-tier application
	- web tier
	- data tier
- ELB
- EFS: shared file system

#### SLA

- includes annual availability
- redundant instances: 
	- multiply failure rate, then substract
	- EC2: 90%
	- ELB: 99.99%
	- EFS: 99.99%
	- RDS: 99.95% (multi zone)

### Loose Coupling

- design principle
- e.g. url connects ELB not the app directly
- one component does not depend on a specific component
- one-to-many connection
- elastic resources are redundant
- redundancy -> loose coupling -> availability
- scale independently
- performance & availability are connected

### SQS

- decople services from each other

#### Monolithic Architecture

- apps run on the same instance

#### Microservices Architecture

- run separate apps on separate instances
- easier updates
- availability & scalability
- communication: messaging queue

### ECS

- decouple services from instances they run on

#### Containers

- like a VM
- isolated from the host
- multiple services can run on the same host

#### Docker

- image contains everything
- launch containers from an image
- ~ launching an EC2 from AMI

#### Benefits

- deployment and updates are easier
	- build image
	- deploy it to instances
	- launch containers from it
- can have multiple containers on a single instance

#### Services

- ECS clusters contain EC2 instances
- ECR stores images
- task definition: how to launch a container
	- image to use
	- cpu
	- memory
	- instance to container port mappings
	- storage mappings

### Cloud Native Applications

- depend on cloud services that can't be deployed on-premises (eg. sqs, s3, dynamoDb)
- services instead of servers

#### Example

- lambda
	- "serverless" compute service (makes you think about servers less)
	- many programming languages (C#, Java, Python...)
	- 99.95%
- s3
	- unlimited file storage
	- static web hosting
	- 99.9%
- DynamoDB
	- non-relational
	- replicate tables across multiple regions
	- 99.999%

#### Advantage

- scalability
- performance
- convenience

#### Disadvantage

- cloud vendor lock-in
- probably less availability
	- can be improved by deploying it to multiple regions

### Trusted Advisor

- service limits
	- you can't provision an unlimited number of AWS resources
- trusted advisor helps you find out your limits
- you can request a limit raise

## Setting up an AWS Environment

### Billing

- Billing preferences
	- Receive Free Tier Usage Alerts
	- Receive Billing Alerts
- Budget
	- Monthly budget threshold alerts
- setting up an aleart does not prevent high costs, just notifies

### IAM

- password policy
	- IAM, Account Settings
- MFA
	- account, My Security Credentials
- admin user
	- attach to group & attach policies to it
	- you can download the credentials

### CloutTrail

- can be searched for event sources
- `aws configure`

### TLS certificate

- transport layer security certificate
- to encrypt traffic (e.g. between load balancer and the client)
- SSL certificate (deprecated)
- first you need a domain name

#### Route 53

- register domain
- public hosted zone
	- where DNS records are stored

## Building a VPC

### VPC

- VPC has 1 or more subnets
- a subnet exist in 1 availability zone (AZ)
- an instance exists in a subnet
- achieve redundancy by having instances in multiple subnets in different AZs
- AZ
	- different data centers
	- different physical location
- VPC
	- exists in a single region
	- by default is isolated from anything else outside of it
- access VPC
	- Internet Gateway
	- Virtual Private Networt (VPN)
	- Direct Connect link
- connect to another VPC or data center
	- Transit Gateway

### Elastic IP Address (EIP)

- a public IP address
- bound to an ENI (Elastic Network Interface)
- ENI is attached to an instance
- you can move an EIP to a different ENI
- EIP replaces a public IP of an instance
- types
	- Amazon owned
		- tied to a region
		- AWS picks
	- Customer owned
		- bring your own
- if EIP is not associated to a running instance it costs

### Global Accelerator

- two anycast IPv4 addresses
- not tied to region
	- spread across POPs (points-of-presence)

### Creating a VPC

- public subnet
	- full access to internet
	- reach and be reachable
	- Internet Gateway
		- allows instances to get a public IP and access the internet
		- that makes a subnet public
- private subnet
	- completely isolated
	- cannot be reached from the internet and the internet cannot reach them
	- NAT gateway
		- provides outbound only internet access
		- costs per hour
		- sends traffic to Internet Gateway
		- has at least 2 interfaces (1 in public, 1 in private), to bridge the gap
- 0.0.0.0/0
	- encompasses all IP addresses of the internet

### Creating subnets

- you can use the same routing table
- default subnet is private

### Launching an instance

- AWS Shield Standard
	- protect infrastructure
	- free & automatic
- into a public subnet
	- associate an IP (a temporary or an EIP)
- into a private subnet
	- just launch
	- not reachable

### Access a VPC

#### Direct Connect

- dedicated link to AWS VPC
- more expensive
- bypasses the Internet
- types
	- dedicated
		- physical
		- terminates at a Direct Connect location (AWS has it, must be fortunate to have it)
	- hosted
		- can be bought from a partner (eg local Internet provider)

#### VPN Connection

- encrypted IPsec connection over the Internet
- unpredictable latency
- two ways to implement
	- Virtual Private Gateway
		- VPN tunnel with only one VPC
		- does not scale well
	- Transit Gateway
		- ~ virtual router
		- multiple VPN connections
		- transit gateway route tables
		- supports multicast

## Automated Deployment with CloudFormation

### Template

- text document (josn, yaml)
- infrastructure as code
- used to create a stack
- best practice: multiple templates, e.g.
	- app-stack
	- network-stack

### Stack

- created by a template
- collection of resources that you create, update and delete as a single unit

### Template Syntax

- nested stack - parent stack
	- nested stack must be created first
- Resources
- Outputs
	- key-value pair
	- available for other stacks and via describe-stacks

### ALB: Application Load Balancer

- tasks
	- balance HTTP(S) traffic on any TCP port
	- receives connection from a client and proxies to an instance in the target group
	- round-robin
	- monitor health
- schemes
	- internet-facing
		- reachable from the internet
		- public IP address
		- public DNS name
	- internal
		- not reachable from the internet
		- private IP
		- private DNS
- resources
	- load balancer
		- proxies requests
	- load balancer listener
		- where to listen
		- if secure refer TLS certificate
	- security group
		- controls traffic
	- target group
		- load balance connections
		- perform health check in every 10 sec

### Auto Scaling Group

- tasks
	- launch a certain number of instances into an Auto Scaling Group
	- add the instances to the ALB target group
	- terminate & recreate unhealthy instances
	- scale in or out based on average group CPU utilization
- resources
	- auto scaling group
		- launches a template
		- min & max number of instances
		- add instances to the target group
	- launch template
		- details about the instance
		- script to install out application (e.g. download docker, docker image, deploy it to a container)
			- cfn-signal: feedback that the auto scaling group is working
		- scaling policy
			- CPU utilization

### Deploying the Stack

- check template `aws cloudformation validate-template`
- deploy `aws cloudformation deploy`
- delete `aws cloudfromation delete-stack`
- describe `aws cloudformation describe-stacks`

### Takeaway

- ELB and Auto Scaling group work together
- ELB: provides health check
- Auto Scaling Group: adds instances to the ELB target group
