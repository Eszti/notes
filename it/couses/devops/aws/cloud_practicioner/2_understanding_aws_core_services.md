# Understanding AWS Core Services

## Interacting with AWS

- methods
	- AWS Management Console
		- browser & mobile app
		- for testing out
		- quick access: root user, regions (Route53 - global)
	- AWS CLI
		- command line
		- for repeated tasks
		- access keys
		- configure: profile
	- AWS SDK
		- programming language
		- java, .NET, Node.js, pyhton, go, C++...
		- for repeated tasks, also for custom apps

## Compute Services

- cloud-based virtual machines for workload services
- compute services
	- EC2
	- Elastic Beanstalk
		- scaling & deployment
	- Lambda
		- compute without managing servers

### EC2

- resizable compute capacity
- use cases
	- web application hosting
	- batch processing
	- web services endpoint
	- desktop

#### concepts

- instance type
	- processor, memory, storage
	- cannot be changed without downtime
	- categories
		- general purpose
		- optimized (compute, memory, storage)
		- accelerated
- root device type
	- Instance Store
	- Elastic Block Store
- Amazon Machine Image (AMI)
- purchase options

#### purchase options

- on-demand
	- pay by the second
- reserved
	- discount for 1-3 years
		- cost models	
			- all upfront: maximum savings
			- partial upfront
			- no upfront: minimum savings but still cheaper than on-demand
- spot-instance
	- largest discount
	- up to 90% discount
	- Spot price: your bid must be higher
		- if bid prices go higher instance will be terminated
		- you can get a 2-minute prior to termination notification

#### AWS Elastic Beanstalk

- PaaS
- handles provisioning, load balancing, scaling and monitoring
- Java, .Net, PHP, Node.js, Python, Ruby, Go, Docker
- EB vs EC2
	- logs
	- health
	- alarms
	- monitoring
	- deployment
	- scaling
- use cases
	- reduce overall maintenance needed
	- few customizations

### AWS Lambda

- summary
	- run code without provisioning infrastucture
	- charged on execution time
	- configurable memory
	- integrates with many AWS services (e.g. s3)
	- enables event-driven workflows
	- primary service for serverless applications
- advantages
	- reduced maintenance
	- fault tolerance
	- scale on demand
	- pricing based on usage

## Content and Network Delivery Services

### VPC and Direct Content

- virtual private cloud
	- logically isolated network
	- support IPv4 and IPv6
	- can be configured
		- IP address range
		- subnets (private & public), NAT for private subnets
		- route tables
		- network gateways
		- connect to data center
		- connect to other VPC (peering connection or transit gateway)
		- private connection to many AWS services
- Direct Connect
	- establish dedicated connection (e.g. to data center)

### Amazon Route 53

- DNS service (to map domain names to IP addresses)
- global AWS service (not regional)
- highly available
- enables global resource routing
- DNS changes can take hours
- can have a failover (to redirect users)

### Elastic Load Balancing

- elasticity: to grow and contract based on usage
- distributes traffic across multiple targets
- integrates with EC2, ECS, Lambda
- one or more AZs
- 3 types
	- ALB (application)
	- NLB (network)
	- ELB (classic)
- scaling
	- vertical = scale up (get a larger instance type)
	- horizontal = scale out (add additional instances)

### CloudFront & API Gateway

- CloudFront
	- CDN: content delivery service
	- static & dynamic
	- users get from the closest server to them
	- utilize AWS edge locations
	- advance security 
- API Gateway
	- fully managed API mgm service
	- deploy your API with CloudFront
	- directly integrates with multiple AWS services
	- monitoring & metrics on API calls
	- supports VPC and on-premise
	
## File Storage and Data Transfer Services

### S3

- store files as objects in buckets
- defferent storage classes
	- standard
	- intelligent-tiering
		- move files based on access
		- between frequent & infrequent
	- standard-infrequent-access
	- One Zone-IA (only in one az)
- across multiple az
- URL access for files
- rules for lifecycle
	- transitions to move objects to a different stroage class based on time (not back and forth)
	- expiration based on age
	- can factor in versions of a specific object
- can serve as a static web host
	- allow public access
	- allow read access for everyone
	- static website hosting tab
- S3 Transfer Acceleration (AWS Edge, CloudFront)
- works with unique names across accounts

### Glacier

- archive in s3
- configurable retrieval time
- pay a retrieval fee
- two different storage classes
	- S3 Glacier
		- 90 day min duration
		- min - hour retrieval time
		- 5 times less expensive
	- S3 Glacier Deep Archive
		- 180 day min storage duration
		- retrieved in hours
		- 23 times less expensive
- data can only be uploaded programatically

### EBS (elastic block store)

- connects to a single EC2
- can scale up
- supports multiple volume types
	- general purpose SSD
	- provisioned IOPS SSD
		- more intense workload
	- throughput optimized HDD
		- frequently access
	- cold HDD
		- less frequent
- redundancy
- snapshots
- offers encryption

### EFS (elastic file system)

- fully managed NFS
- for linux
- multiple AZ
- storage access
	- standard
	- infrequent
- can be attached to multiple instances
- FSx: for windows

### Data transfer

- AWS Snowball
	- petabyte scale
	- physical device
	- device is returned by local carrier
- AWS Snowmobile
	- exabyte scale
	- shipping container delivered to your location

## Database Services and Utilities

- IaaS: Database on EC2
- PaaS: RDS
- SaaS: DynamoDB

### RDS

- PaaS
- handle core things
	- provisioning
	- patching
	- backup
	- recovery
- multiple AZ
- read replicas
- launches into a VPC
- platforms
	- MySQL
	- Postgre
	- MariaDB
	- Oracle DB
	- SQL Server
	- Aurora
		- was built for the cloud
- Database Migration Service (DMS)
	- to migrate existing databases

### DynamoDB

- NoSQL, SaaS
- key-value and document db
- low latency at virtually any scale
- automated scaling
- in-memory cache with DAX (DyanmoDB Accelerator)
- use cases
	- serverless
	- scale up
	- data models without BLOB
	- low latency

### Elasticach

- in memory datastore
- Memcached and Redis
- handles common use cases
	- database layer caching
	- session storage

### Redshift

- data warehouse service
- petabytes
- disks and columnar storage
- isolation with a VPC
- querying with Redshift Spectrum

## App Integraion Services

### Messaging Services

- decoupled applications
- SNS + SQS
	- user order -> SNS Topic (fan out) -> Queue A -> Service A
																			-> Queue B -> Service B
	- if service is not available, message won't be lost

#### SNS (Simple Notification Service)

- ~ smart phone notification
- organize information according to topics (SNS Topic)
- integrates with multiple AWS services
	- lambda
	- SQS
- also provides end user notifications
- if we are not listening, we won't get it
- subscribe & publich

#### SQS (Simple Queue Service)

- ~ mailbox
- fault-tolerant apps
- up to 256 KB
- can be stored up to 14 days 
- types
	- standard
	- FIFO

### AWS Step Functions

- enables orchestration of workflows
- supports serverless architecture
- charged per state transition
- workflows are defined by Amazon States Language (json)
- integrates
	- computing services
	- db services
	- messaging services...

## Management & Governance Services

### CloudTrail

- audit train
- monitor account activity
- all actions (console, SDK, command line tools ...)
- insert into S3 bucket or CloudWatch logs
- use cases
	- for compliance purposes
	- forensic analysis
	- operation analysis (who did)
	- troubleshooting (when what happened)
- best practice: to enable

### Managing Infrastructure

#### Cloudwatch

- metrics, logs, alarms, events
- 1st class citizen
- visualisation capabilities
- dashboards

#### AWS Config

- evaluate infrastructure against a set of rules
- config history of your infrastructure
- conformance packs for compliance
- remediation steps (how to fix standards)

#### AWS Systems Manager

- enable automation tasks
- store commonly used parameters securely

### CloudFormation

- managed service for provisioning infrastructure
- based on templates
- no additinal charge
- yaml or json
- infrastructure as a code
- manages dependencies between resources
- provides drift detection (notice if someone changes a setting)

### AWS Control Tower

- centralizes users
- integrates Guardrails (main account and child accounts)

## Exam Preparation

