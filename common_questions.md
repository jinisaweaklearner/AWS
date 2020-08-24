
## S3 pre-signed URL 
A Solutions Architect is designing a new social media application. The application must provide a secure method for uploading profile photos. Each user should be able to upload a profile photo into a shared storage location for one week after their profile is created.
Which approach will meet all of these requirements?

- Use Amazon S3 with the default private access policy and generate pre-signed URLs each time a new site profile is created.

Use pre-signed URL (basically an API) that you can define and set an expiration on and many other parameters for users or entities that don't have AWS credentials to access objects in Amazon S3

## EFS
Amazon EFS file systems are distributed across an unconstrained number of storage servers. This distributed data storage design enables file systems to grow elastically to petabyte scale and enables massively parallel access from Amazon EC2 instances to your data. The distributed design of Amazon EFS avoids the bottlenecks and constraints inherent to traditional file servers.

https://docs.aws.amazon.com/efs/latest/ug/performance.html

