# Three-Tier Web Application 

Created and deployed a three-tiered Web Application (WordPress) that is highly available and scalable. The application will be running on ec2 instance, a mock database using Aurora with Read and Write instance, and a file server. It will be deployed across two AZs and a load balancer is used to distribute the traffic flow. Auto scaling group have also been configured to scale in/out according to the user traffic flow. 

You will need to start your WAMP for this project

## Assumptions made:

1. "The infrastructure must be provisioned on AWS automatically without manual intervention" ; I presume that I am required to use AWS Cloudformation to provisioned the infrastructure.
2. "The design should be based on best practices with security in mind"; I presume that I will need to have multi-tiered subnet (Public & Private Subnet), with Application EC2 instance and Database instance to be provisioned in private subnet.
3. "Candidate can propose any type of web application"; I have deployed a wordpress website. 


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


### Video Deployment

[AWS_Cloudformation.webm](https://user-images.githubusercontent.com/90443576/183982759-2e460fe7-e942-4cc0-8d8f-bc195002b665.webm)
