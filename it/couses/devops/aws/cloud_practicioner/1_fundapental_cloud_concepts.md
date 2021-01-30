# Fundamental Cloud Concepts for AWS

## Understanding cloud computing

- traditional data center
  - building out a network
    - webserver
    - file server
    - database
  - takes an initial investment
  - forecasting demand is difficult
  - slow to deploy
  - maintenance is expensive
  - security and compliance burden

- benefits of cloud computing
  - capital expense for variable expense
  - stop guessing capacity
  - increase speed and agility
  - stop spending money for maintenance
  - go global in minutes

- concepts
  - elasticity
  - reliability
  - agility

- cloud computing
  - on-demand delivery of compute power, database, spplications and other IT resources
  - through a cloud service platform
  - with pay-as-you-go pricing

- types
  - IaaS: maximum control
  - PaaS: middle (e.g. wordpress host)
  - SaaS: minimum maintenance

- cloud deployments
  - public cloud (e.g. AWS)
  - on-premises (in private data center)
  - hybrid

## AWS global infrastructure

- infrastructures
  - regiions
    - is located in a specific geographic location
    - each geographic location has a cluster of data centers
    - ~22
    - us-east-2
  - AZ
    - smaller units a region operates with
    - each region has min 2 AZs
    - min one data center / AZs
    - located in the region
    - no SPOF...
    - to guarantee high availability: deploy to multiple AZs
    - us-east-2a
  - edge locations
    - global content delivery network (CDN)
    - supports only
      - CloudFront
      - Amazon Route 53
      - over 200 locations

## Understanding cloud economics

- capitalized expenditure (building, servers, equipment)
- operating expenditure (maintenance costs)
- problem
  - under & over capacity
- cloud: OpEx is in relation with capacity - pay as you go
- AWS Cost Explorer
  - by service
  - by cost tags
  - predictions
  - recommendations
  - API
- AWS Budget
- planning tools
  - AWS TCO calculator (total cost of ownership)
    - what it would cost to move the infrastructure to the cloud
  - AWS Simple Monthly Calculator
    - calculate monthly costs of a running workload
- Resource Tags
  - department, project...
- AWS Organizations
  - manage multiple accounts under a single master account
  - centralize logging & security standards
- AWS Cost Managemnet
  - Cost Explorer to monitor ongoing costs

## Supporting AWS Infrastructure

- AWS Support
  - plan tiers
    - Basic, Developer, Business, Enterprise
  - support categories
    - general guidance, system impaired, production system impaired, production system down, business-critical system down
- AWS Trusted Advisor
  - cost optimization, performance, security, fault tolerance, service limits
  - recommended actions
- AWS Personal Health Dashboard
  - event log, can be visualized in a dashboard

## Prepare for the Exam

- items
  - cloud vs traditional
  - global elements of AWS
  - funding cloud infrastructure
  - forecast & manage AWS Costs
  - AWS Support Plans
  - Additional Support Tools
