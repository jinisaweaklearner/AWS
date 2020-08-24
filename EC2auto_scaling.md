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
Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the user is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.
https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/Introduction.html

## How is Amazon SQS different from Amazon SNS?
Amazon SNS allows applications to send time-critical messages to multiple subscribers through a “push” mechanism, eliminating the need to periodically check or “poll” for updates. Amazon SQS is a message queue service used by distributed applications to exchange messages through a polling model, and can be used to decouple sending and receiving components. 

## EBS
Amazon Elastic Block Store (EBS) is an easy to use, high performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale.

Block storage that can be encrypted=EBS

https://aws.amazon.com/blogs/aws/protect-your-data-with-new-ebs-encryption/


## Copying an Amazon EBS snapshot
With Amazon EBS, you can create point-in-time snapshots of volumes, which we store for you in Amazon S3. After you create a snapshot and it has finished copying to Amazon S3 (when the snapshot status is completed), you can copy it from one AWS Region to another, or within the same Region.

## Amazon CloudFront
Amazon CloudFront is a fast content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency, high transfer speeds, all within a developer-friendly environment. CloudFront is integrated with AWS – both physical locations that are directly connected to the AWS global infrastructure, as well as other AWS services. 

## VPC and S3
I would like to tell you about a new AWS feature that will allow you to make even better use of Amazon Virtual Private Cloud and Amazon Simple Storage Service (S3). As you probably know, S3 provides you with secure, durable, and highly scalable object storage. You can use the Virtual Private Cloud to create a logically isolated section of the AWS Cloud, with full control over a virtual network that you define.

When you create a VPC, you use security groups and access control lists (ACLs) to control inbound and outbound traffic. Until now, if you wanted your EC2 instances to be able to access public resources, you had to use an Internet Gateway, and potentially manage some NAT instances.

## new VPC endpoint
Today we are simplifying access to S3 resources from within a VPC by introducing the concept of a VPC Endpoint. These endpoints are easy to configure, highly reliable, and provide a secure connection to S3 that does not require a gateway or NAT instances.

EC2 instances running in private subnets of a VPC can now have controlled access to S3 buckets, objects, and API functions that are in the same region as the VPC. You can use an S3 bucket policy to indicate which VPCs and which VPC Endpoints have access to your S3 buckets.

## Amazon EBS volume types
- General Purpose SSD (gp2)	
- Provisioned IOPS SSD (io1)	
- Throughput Optimized HDD (st1)	
- Cold HDD (sc1)

- HDD has sequential workloads

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html


## S3 Performance Tips (prefix)
https://aws.amazon.com/blogs/aws/amazon-s3-performance-tips-tricks-seattle-hiring-event/

## CloudTrail across all regions
AWS CloudTrail is a web service that records activity made on your account and delivers log files to your Amazon S3 bucket.https://aws.amazon.com/about-aws/whats-new/2015/12/turn-on-cloudtrail-across-all-regions-and-support-for-multiple-trails/

## EBS vs EFS
Amazon Elastic File System (Amazon EFS) provides a simple, scalable, fully managed elastic NFS file system for use with AWS Cloud services and on-premises resources.
Amazon EFS is designed to provide massively parallel shared access to thousands of Amazon EC2 instances, enabling your applications to achieve high levels of aggregate throughput and IOPS with consistent low latencies.

## Customer master keys (CMKs)

https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html

## Lambda@edge
Lambda@Edge is a feature of Amazon CloudFront that lets you run code closer to users of your application, which improves performance and reduces latency. 

https://aws.amazon.com/lambda/edge/

## Route 53
Amazon Route 53 is a highly available and scalable cloud Domain Name System (DNS) web service. It is designed to give developers and businesses an extremely reliable and cost effective way to route end users to Internet applications by translating names like www.example.com into the numeric IP addresses like 192.0.2.1 that computers use to connect to each other. Amazon Route 53 is fully compliant with IPv6 as well.
https://aws.amazon.com/route53/

## Kinesis Data Firehose
Amazon Kinesis Data Firehose is the easiest way to reliably load streaming data into data lakes, data stores, and analytics services. It can capture, transform, and deliver streaming data to Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, generic HTTP endpoints, and service providers like Datadog, New Relic, MongoDB, and Splunk. It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. 

##  VPC peering
A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering connection).

