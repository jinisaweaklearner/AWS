
## General Knowledge
- Data is phisically stored in multiple different availability zones
- AWS is rigion scoped except IAM and S3 which are global services


## IAM
- users
- groups (users can join groups)
- roles for different applications

## EC2
Main capability of EC2:
- Rent virtual machine (EC2)
- Store data on virtual drive (EBC)
- Distributing load across machines
- Scaling the services using an auto-scaling group

two ways to connect EC2
- ssh -i "airflow_ec2.pem" ubuntu@192.168.152.223 (-i for identity_file)
- EC2 Instance Connect (browser-based SSH connection) (need to have a ssh inbound rule)

## inbound network
from other to the instance (blocked by default)
## outbound network
from the instance to other (authorised by default )

## about port
In computer networking, a port is a communication endpoint. At the software level, within an operating system, a port is a logical construct that identifies a specific process or a type of network service.
https://en.wikipedia.org/wiki/Port_(computer_networking)

## public and private IP
• Networking has two sorts of IPs. IPv4 and IPv6:
• IPv4:1.160.10.240
• IPv6: 3ffe: 1900:4545:3:200:f8ff:fe21:67cf
• In this course, we will only be using IPv4.
• IPv4 is still the most common format used online.
• IPv6 is newer and solves problems for the Internet of Things (IoT).
• IPv4 allows for 3.7 billion different addresses in the public space • IPv4: [0-255].[0-255].[0-255].[0-255].

## Public IP
• Public IP means the machine can be identified on the internet (WWW)
• Must be unique across the whole web (not two machines can have the same public IP). • Can be geo-located easily
## Private IP
• Private IP means the machine can only be identified on a private network only • The IP must be unique across the private network
• BUT two different private networks (two companies) can have the same IPs.
• Machines connect to WWW using an internet gateway (a proxy)
• Only a specified range of IPs can be used as private IP

## Elastic IPs
• When you stop and then start an EC2 instance, it can change its public IP.
• If you need to have a fixed public IP for your instance, you need an Elastic IP
• An Elastic IP is a public IPv4 IP you own as long as you don’t delete it
• You can attach it to one instance at a time



## EC2 auto scaling

- Dynamic scaling

Changing based on some metrics. For example, let's say that you have a web application that currently runs on two instances, and you want the CPU utilization of the Auto Scaling group to stay at around 50 percent when the load on the application changes. This gives you extra capacity to handle traffic spikes without maintaining an excessive number of idle resources. https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html

- Scheduled scaling

Scheduled scaling allows you to set your own scaling schedule. For example, let's say that every week the traffic to your web application starts to increase on Wednesday, remains high on Thursday, and starts to decrease on Friday. 
https://docs.aws.amazon.com/autoscaling/ec2/userguide/schedule_time.html

- Manual scaling



## EC2 User Data

• It is possible to bootstrap our instances using an EC2 User data script

## what is DNS
https://aws.amazon.com/route53/what-is-dns/

## Auto Scaling groups
An Auto Scaling group contains a collection of Amazon EC2 instances that are treated as a logical grouping for the purposes of automatic scaling and management. An Auto Scaling group starts by launching enough instances to meet its desired capacity. It maintains this number of instances by performing periodic health checks on the instances in the group.

https://docs.aws.amazon.com/autoscaling/ec2/userguide/AutoScalingGroup.html

## Auto Scaling Termination Policy
Amazon EC2 Auto Scaling first identifies which of the two types (Spot or On-Demand) should be terminated. It then applies the termination policy in each Availability Zone individually, and identifies which instance (within the identified purchase option) in which Availability Zone to terminate that will result in the Availability Zones being most balanced. The same principles apply to Auto Scaling groups that use a mixed instances configuration with weights defined for the instance types.

https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html


## 5 types of EC2 instance
https://aws.amazon.com/ec2/pricing/
- On-demand 
  - pay for compute capacity by the hour or the second
  - short-term
  - Applications being developed or tested on Amazon EC2 for the first time
- Spot instances
  - request spare Amazon EC2 computing capacity for up to 90% off the On-Demand price.
  - Applications that have flexible start and end times
  - Applications that are only feasible at very low compute prices
  - Users with urgent computing needs for large amounts of additional capacity
- Savings Plans
  - Applications with steady state usage
  - Customers that can commit to using EC2 over a 1 or 3 year term to reduce their total computing costs
- Reserved Instances
  - Applications with steady state usage
  - Applications that may require reserved capacity
  - a significant discount (up to 75%) compared to On-Demand instance pricing
- Dedicated Hosts
  - a physical EC2 server
  - Can be purchased On-Demand (hourly)
  - Can be purchased as a Reservation for up to 70% off the On-Demand price
  - Dedicated Hosts allow you to use your existing per-socket, per-core, or per-VM software licenses, including Windows Server, SQL Server, SUSE Linux Enterprise Server, Red Hat Enterprise Linux, or other software licenses that are bound to VMs, sockets, or physical cores, subject to your license terms. 

  ## EC2 Auto Scaling
  Amazon EC2 Auto Scaling is a fully managed service designed to launch or terminate Amazon EC2 instances automatically to help ensure you have the correct number of Amazon EC2 instances available to handle the load for your application. 

  ## Amazon EC2 Auto Scaling vs. AWS Auto Scaling
  AWS Auto Scaling to manage scaling for multiple resources across multiple services. AWS Auto Scaling lets you define dynamic scaling policies for multiple EC2 Auto Scaling groups or other resources using predefined scaling strategies. 