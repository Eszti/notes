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
- EC2
	- resizable compute capacity
	- use cases
		- web application hosting
		- batch processing
		- web services endpoint
		- desktop
	- concepts
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
