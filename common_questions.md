

## EFS

Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances, enabling your applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.


Amazon EFS file systems are distributed across an unconstrained number of storage servers. This distributed data storage design enables file systems to grow elastically to petabyte scale and enables massively parallel access from Amazon EC2 instances to your data. The distributed design of Amazon EFS avoids the bottlenecks and constraints inherent to traditional file servers.

https://docs.aws.amazon.com/efs/latest/ug/performance.html

Amazon EFS provides elastic, shared file storage that is POSIX-compliant. The file system you create supports concurrent read and write access from multiple Amazon EC2 instances and is accessible from all of the Availability Zones in the AWS Region where it is created.

File lock, concurrent access, auto scale = EFS

## AWS Elastic Beanstalk
- AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.
- No need to manage services
- the service automatically handles all the details such as resource provisioning, load balancing, auto-scaling, and monitoring

## ELB Elastic Load Balancing
Elastic Load Balancing automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, IP addresses, and Lambda functions. It can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones. Elastic Load Balancing offers three types of load balancers that all feature the high availability, automatic scaling, and robust security necessary to make your applications fault tolerant.

- Application Load Balancer
  - Elastic Load Balancing provides access logs that capture detailed information about requests sent to your load balancer. 
  - for micro services;path-based routing
- Network Load Balancer
- Classic Load Balancer

Internet-Facing LB needs public subnet for each AZ (2 x 1 public subnet). Web and DB servers need to be on separate pvt subnets in 2 AZs for HA

## Elastic Block Store (EBS)
Amazon Elastic Block Store (Amazon EBS) provides block level storage volumes for use with EC2 instances. EBS volumes behave like raw, unformatted block devices. You can mount these volumes as devices on your instances. EBS volumes that are attached to an instance are exposed as storage volumes that `persist independently from the life of the instance`. You can create a file system on top of these volumes, or use them in any way you would use a block device (such as a hard drive). You can dynamically change the configuration of a volume attached to an instance.

- RAID 0
- RAID 1

Amazon Elastic Block Store (EBS) is an easy to use, high performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale.

Block storage that can be encrypted=EBS

https://aws.amazon.com/blogs/aws/protect-your-data-with-new-ebs-encryption/


## Copying an Amazon EBS snapshot
With Amazon EBS, you can create point-in-time snapshots of volumes, which we store for you in Amazon S3. After you create a snapshot and it has finished copying to Amazon S3 (when the snapshot status is completed), you can copy it from one AWS Region to another, or within the same Region.
# EC2 auto scaling

## Dynamic scaling
https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-scale-based-on-demand.html

## Scheduled scaling
Scheduled scaling allows you to set your own scaling schedule. For example, let's say that every week the traffic to your web application starts to increase on Wednesday, remains high on Thursday, and starts to decrease on Friday. You can plan your scaling actions based on the predictable traffic patterns of your web application. Scaling actions are performed automatically as a function of time and date.
https://docs.aws.amazon.com/autoscaling/ec2/userguide/schedule_time.html


## Automated Cross-Region Snapshot Copy for Amazon Redshift
You simply select the second region and the desired retention period; Redshift will take care of the rest:
https://aws.amazon.com/blogs/aws/automated-cross-region-snapshot-copy-for-amazon-redshift/

## cost-optimized and can handle the expected traffic
To handle traffic = Autoscaling + ELB
To cost optimize = Cloudfront

## CloudFront
Amazon CloudFront is an easy to use, high performance, and cost efficient content delivery service. With over 50 worldwide edge locations, CloudFront is able to deliver your content to your customers with low latency in any part of the world.

Amazon CloudFront is a web service that speeds up distribution of your `static` and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the user is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.
https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html

Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment. CloudFront is integrated with AWS – both physical locations that are directly connected to the AWS global infrastructure, as well as other AWS services. 

## CloudFront and Origin Access Identity
To restrict access to content that you serve from Amazon S3 buckets, follow these steps:

Create a special CloudFront user called an origin access identity (OAI) and associate it with your distribution.

Configure your S3 bucket permissions so that CloudFront can use the OAI to access the files in your bucket and serve them to your users. Make sure that users can’t use a direct URL to the S3 bucket to access a file there.

## How is Amazon SQS different from Amazon SNS?
Amazon SNS allows applications to send time-critical messages to multiple subscribers through a “push” mechanism, eliminating the need to periodically check or “poll” for updates. Amazon SQS is a message queue service used by distributed applications to exchange messages through a polling model, and can be used to decouple sending and receiving components. 





## VPC and S3
I would like to tell you about a new AWS feature that will allow you to make even better use of Amazon Virtual Private Cloud and Amazon Simple Storage Service (S3). As you probably know, S3 provides you with secure, durable, and highly scalable object storage. You can use the Virtual Private Cloud to create a logically isolated section of the AWS Cloud, with full control over a virtual network that you define.

When you create a VPC, you use security groups and access control lists (ACLs) to control inbound and outbound traffic. Until now, if you wanted your EC2 instances to be able to access public resources, you had to use an Internet Gateway, and potentially manage some NAT instances.

## new VPC endpoint
Today we are simplifying access to S3 resources from within a VPC by introducing the concept of a VPC Endpoint. These endpoints are easy to configure, highly reliable, and provide a secure connection to S3 that does not require a gateway or NAT instances.

EC2 instances running in private subnets of a VPC can now have controlled access to S3 buckets, objects, and API functions that are in the same region as the VPC. You can use an S3 bucket policy to indicate which VPCs and which VPC Endpoints have access to your S3 buckets.

- Pvt connectivity to AWS resource w/o internet use + same account - VPC Endpoint
- Pvt connectivity to AWS resource w/o internet use + different account - VPC Peering

## Amazon EBS volume types
- General Purpose SSD (gp2)	
- Provisioned IOPS SSD (io1)	
- Throughput Optimized HDD (st1); HDD has `sequential` workloads	
- Cold HDD (sc1)

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html


## S3 Performance Tips (prefix)
https://aws.amazon.com/blogs/aws/amazon-s3-performance-tips-tricks-seattle-hiring-event/

## CloudTrail across all regions
AWS CloudTrail is a web service that records activity made on your account and delivers log files to your Amazon S3 bucket.https://aws.amazon.com/about-aws/whats-new/2015/12/turn-on-cloudtrail-across-all-regions-and-support-for-multiple-trails/

## EBS vs EFS
Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources.
Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances, enabling your applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.

## Customer master keys (CMKs)
All activity using a key in a custom key store is also logged to AWS CloudTrail in the same way.
https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html

## Lambda@edge
Lambda@Edge is a feature of Amazon CloudFront that lets you run code closer to users of your application, which improves performance and reduces latency. 

https://aws.amazon.com/lambda/edge/

## Route 53
Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. It is designed to give developers and businesses an extremely reliable and cost effective way to route end users to Internet applications by translating names like www.example.com into the numeric IP addresses like 192.0.2.1 that computers use to connect to each other. Amazon Route 53 is fully compliant with IPv6 as well.
https://aws.amazon.com/route53/

- Active-active failover (when you want all of your resources to be available the majority of the time.)
- Active-passive failover (when you want a primary resource or group of resources to be available the majority of the time and you want a secondary resource or group of resources to be on standby in case all the primary resources become unavailable)
- Latency routing policy – Use when you have resources in multiple AWS Regions and you want to route traffic to the region that provides the best latency.

## Multivalue answer routing
Multivalue answer routing lets you configure Amazon Route 53 to return multiple values, such as IP addresses for your web servers, in response to DNS queries. For example, use multivalue answer routing when you need to return multiple values for a DNS query and route traffic to multiple IP addresses.

## Kinesis Data Firehose
Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics services. It can capture, transform, and deliver streaming data to Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, generic HTTP endpoints, and service providers like Datadog, New Relic, MongoDB, and Splunk. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. 

##  VPC peering
A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering connection).

## VPC Flow Logs
VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC. Flow log data can be published to Amazon CloudWatch Logs or Amazon S3. After you've created a flow log, you can retrieve and view its data in the chosen destination.

https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html


## NAT gateway vs NAT instance
Highly available. NAT gateways in each Availability Zone are implemented with redundancy. Create a NAT gateway in each Availability Zone to ensure zone-independent architecture.
- NAT Gateway and NAT instance only support IPV4 traffic. For IPV6, you need to use egress only Internet Gateway.

https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-comparison.html

## NAT
You can use a network address translation (NAT) gateway to enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.

## S3 prefix
https://docs.aws.amazon.com/AmazonS3/latest/dev/optimizing-performance.html

## Glacier
Glacier = lowest cost but pay extra for expedited retrieval


## Securing environment variables in lambda
Lambda encrypts environment variables with a key that it creates in your account (an AWS managed customer master key (CMK)). Use of this key is free. You can also choose to provide your own key for Lambda to use instead of the default key.

## Fargate
AWS Fargate is Amazon’s solution to run docker containers without managing any servers for container orchestration. Where things get confusing with Fargate is that Fargate is actually just one way of running containers in Amazon ECS. 

## RDS
For your MySQL, MariaDB, PostgreSQL, Oracle, and SQL Server database (DB) instances, you can use Amazon RDS Multi-AZ deployments. When you provision a Multi-AZ DB instance, Amazon RDS automatically creates a primary DB instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ).

High Availability (Multi-AZ) for Amazon RDS
https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html

## Compare 4 Storage Classes
https://aws.amazon.com/s3/storage-classes/

## Athena
Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL. Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.

## Config
AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. Config continuously monitors and records your AWS resource configurations and allows you to automate the evaluation of recorded configurations against desired configurations. 
