- Elastic Compute Cloud
- Provides virtual machines referred to as EC2 instances in the cloud
- Launch instances using AMIs
- On demand scalable computing capacity on the AWS cloud

### Launching an EC2 instance:
1) AMI (Amazon Machine Image)
	Types:
	1) Quick start - AWS prebuild AMIs
	2) My AMIs - AMIs you created
	3) AWS Marketplace - AWS catalogue of AMIs for specific use cases
	4) Community AMIs - AMIs created by ppl around the world

2) Select an instance type depending on use case
	eg: T3/C5/R5

### Instance Lifecycle:
1) Pending
2) Running
3) Stopping
4) Stopped
5) Shutting down
6) Terminated

![[Pasted image 20241126212914.png]]

### Purchase Options:
1) On demand
	- Pay per second
	- Full control over instance lifecycle

2) Reserved instances
	- Long term commitment 1/3 year plan
	- In exchange for discount (compared to on demand)

3) Spot instances
	- Request to use spare EC2 capacity
	- For quick temporary computations like batch jobs/background processing/optional tasks/etc.
	- High discount
	- No guarantee that it will not get used up by someone else

4) Dedicated hosts
	- Bare metal physical server fully dedicated to your org
	- BYOL (Bring Your Own License) support 
	- You control everything from setting up OS to hosting applications