# Introduction to Security and Architecture

## Architecture Core Concepts

### Acceptable Use Policy

- sending too much emails
- harmful content
- penetration tests only for certain services (recently changed)

### Least Privilege Access

- give minimum access

### Shared Responsibility Model

- security and compliance
- AWS: security of the cloud
	- access & training of employees
	- global data centers
	- hw
	- config management
	- patching cloud infrastructor
- customer: security in the cloud
	- individual access and training
	- data security & encryption
	- OS, network and firewall configuration
	- code you deployed
	- patching custom applications

### Well-Architected Framwork

- best practices how to create systems that create business value
- five pillars
	- operational excellence
	- security
	- reliability
	- performace efficiency
	- cost optimization

### High-availability and Fault Tolerance

- Fault Tolerance
	- support failure of components (eg SQS)
	- must be architected
- High Availability
	- keep the entire solutiion running
	- most services provide out of the box
- best practices
	- SQS
	- use multiple AZs
	- Route 53 (redirect services)

### Compliance

- standards
	- PCI-DSS: for credit cards
	- HIPAA: healthcare data, privacy
	- SOC 1,2,3
	- FedRAMP
	- ISO...
- how to comply
	- AWS Config
		- infrastructure
	- AWS Artifact
		- self service access to AWS compliance report (e.g. for a bank)
	- AWS GuardDuty
		- threat detection

## Identites and User Management

### IAM

- controls access to AWS resources
- free
- both authentication (login) & authorization (what that user can do)
- supports identity federation (e.g AD)
- types
	- User
	- Group
		- you can have users in multiple groups
	- Role
		- either user or service
- policy
	- json
	- for an identity
	- defines both service and actions
	- custom managed or by AWS
		- managed e.g: readonly, full access to s3...
- best practice
	- MFA (multi-factor authentication)
		- virtual MFA device... (e.g. Google Authenticator)
	- least privilege access
- create user
	- programmatic or console access

### Cognito

- authentication for custom apps
- user directory
- UI components
- security capabilities
- enables controlled access to AWS (e.g. to s3 bucket)
- can work with social & enterprise identity providers (e.g. Google)

## Data Architecture

### Integrate on-premise data

#### AWS Storage Gatewy

- hybrid-cloud storage service
- cloud storage into your local network
- deployed as VM or HW
- S3 or EBS
- types
	- File Gateway
		- store files in S3 but keep certain file in the local cache
	- Tape Gateway
		- enables tape backup (on virtual tapes)
	- Volume Gateway
		- cloud based iSCSI volumens

#### AWS DataSync

- automated data transfer (but not like snowball)
- DataSync agent deployed as a VM on your network
- integration: s3, EFS, FSx
- AWS custom protocol

### Processing Data

#### AWS Glue

- ETL service (extract, transform, load)
- RDS, dynamo, Redshift, S3
- supports a serverless model

#### AWS EMR

- elastic MapReduce
- big-data processing
- open-source framework support
	- (Apache) Sprak, Flink, Hive, Hudi, HBase and Presto
- clustered environment

#### AWS Data Pipeline

- workflow orchestration
- also ~ managed ETL
- manages data workflow through AWS
- RDS, S3, EMR, Redshift, dynamo
- can integrate on-premise data stores

### Data Analysis

#### Athena

- fully-managed
- serverless
- query large-scale data in s3
- SQL support
- charge: based on scanned data

#### Quicksight

- BI service
- dashboards
- charge: per-user, per-session

#### CloudSearch

- fully managed search service
- support scaling
- charge: per hour and instance type
- enables custom application integration

### AI and ML

#### Rekognition

- image & video recognition
- object and action detection
- deep learning
- facial analysis
- custom labels for business object

#### Translate

- fully managed 
- translation
- 54 languages
- language identification
- batch and real time (stream)

#### Transcribe

- fully-managed
- speech recognition
- sub-service for medical use
- 31 languages
- batch and real-time

## Disaster Recovery

- how we prepare for a disaster (earthquake...)

### Architecture

#### Types

- Backup and Restore
	- back up production data in s3
	- launch a new environment
	- longest recovery time
- Pilot Light
	- key components are in cloud
- Warm Standby
	- scale down version of the full environment
	- critical systems run on less capable instance types
- Multi Site
	- full environment is running in the cloud at all times
	- near seamless recovery
	- instance types for production

#### Selection

- recovery time objective
	- time it takes to get back
- recovery point objective
	- data loss in terms of time

## Architecting Applications

### Scaling

- vertical scaling
	- scale up
- horizontal scaling
	- scale out
	- much more sustainable

#### Autoscaling Group

- launch template
- min, max & desired number of instances
- health check
- multiple AZ
- ELB (e.g. application load balancer) 
	- distributes traffic
	- checks if application is not healthy --> does not send treffic
	- checks if application has registered --> sends traffic

#### Secrets Manager

- secure way to store credentials
- auto-rotation
- native integration with RDS, DocumentDB, Redshift

### Access Control

#### Security Group

- ~ firewall for EC2 instances
- work at instance level
- control in- & outbound traffic
- EC2 can belong to multiple SGs (e.g. webserver...)
- VPCs' have a default SG
- not default must be explicitely associated
- by default all outbound traffic is allowed

#### Network ACL

- subnet level within a VPC
- enable both allow & deny traffic
- VPC default: allows in- & outbound traffic
- custom: by default denies

#### AWS VPN

- encrypted tunnel to your VPC
- types
	- site-to-site VPN
		- cutomer gateway + VPN Gateway
		- encrypted traffic between data center & AWS
		- ~ Direct Connect: does not go over the internet

### Infrastructure protecting

#### AWS Shield

- managed DDoS (distributed denial of service)
	- flooded with more traffic than they can handle
- on-going threat detection
- service-levels
	- standard
	- advanced

#### Amazon Macie

- ML to analyze data stored in S3
- detect personal info
- dashboards
- alerts
- anomaly detection

#### Amazon Inspector

- scan for vulnerabilities
- charged per assessment run
- type
	- network reachability assessment: what is available for the internet from our servers
	- host assessment: patched for critical vulns & no config errors have been made

### Pre-defined Solution

#### AWS Service Catalog

- IT services by Amazon
- wide variety
- to meet compliance
- lifecycle support

#### AWS Marketplace

- 3rd party softwares
- curated catalog
- e.g. AMI, CloudFormation stacks....
- different pricing
- sometime on top charges

### Developer Tools

#### CodeCommit

- code repo
- utilize git
- access with IAM
- alternative Github, Bitbucket, Gitlab

#### CodeBuild

- managed CI
- run build commands to build artifacts
- charge per minute to compute

#### CodeDeploy

- deployment to many different AWS services
- deploy to EC2, Fargate, Lambda, on-premise...
- dashboard

#### CodePipeline

- managed CD
- works together with CodeCommit, CodeBuild, CodeDeploy
- builds a pipeline
- to automate building, testing and deploying

#### CodeStar

- bootsrap the enire process
- workflow tool
- custom dashboards and configs
- only charged for the other services

## Exam

### Content

- 90 min proactored
- two types
	- multiple choice
	- multiple answers
	- a
- 100 - 1000, 700< passed
- areas
	- Cloud Concepts (~ 25%)
		- general info about cloud
		- difference between traditional & cloud platforms
		- AWS global infrastructure
		- scalability
		- CapEx & OpEx
	- Technology (~ 33%)
		- review each service
		- name, description
		- implement basic solution
		- architectural principles (fault tolerance & high availability)
		- scalability
	- Security & Compliance (~ 25%)
		- shared responsibility model
		- compliance reports
		- secure account & resource
		- securing traffic
		- review IAM
		- Least Privilege Access
	- Billing & Pricing (~ 15%)
		- tools
		- most cost-effective ways (instances, storage)
		- how cost differs from traditional data centers
		- ways organisations can manage & review costs
		- support level models

### Register

- can be taken at home (not all countries)
- online proactor

### Preparatiion

- learn
- sign up
- study
	- 
- test

