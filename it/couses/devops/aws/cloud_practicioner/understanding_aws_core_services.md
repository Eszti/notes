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
	- purchase options
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

