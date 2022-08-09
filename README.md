# GovTech_GIG

## Assumptions made:

1. "The infrastructure must be provisioned on AWS automatically without manual intervention" ; I presume that I am required to use AWS Cloudformation to provisioned the infrastructure.
2. "The design should be based on best practices with security in mind"; I presume that I will need to have multi-tiered subnet (Public & Private Subnet), with Application EC2 instance and Database instance to be provisioned in private subnet.
3. "Candidate can propose any type of web application"; I presume that the web application may not need to be a working one. 


## Architecture Diagram

![image](https://user-images.githubusercontent.com/90443576/183464977-b97afbdd-9eb5-4940-81e6-ff508c3b6b26.png)


### Explanation on each component 

1. Internet Gateway - to allow internet traffic into the VPC
2. Application load balancer - to load balance across the Two Avaliability Zones (AZ-1 , AZ-2)
3. NAT Gateway - to allow traffic to flow from the public subnet into the private subnet (App Subnet and DB Subnet) 
4. Auto-Scaling Group - enable the application to scale in when the traffic flow is low, and enable the application to scale out when the traffic flow is high
5. Elasticache / Memcached - to decrease data access latency, increase throughput, and ease the load off the backend systems
6. Elastic File System - For cost-optimize file storage in AWS
7. Aurora Database - For database
