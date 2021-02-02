# VPC
Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined.
CIDR (Classless Inter-Domain Routing)

- We’ve seen WW.XX.YY.ZZ/32 == one IP  
- We’ve seen 0.0.0.0/0 == all IPs 
- But we can define for ex: 192.168.0.0/26: 192.168.0.0 – 192.168.0.63 (64 IP) 



Quick memo: 

- /32 – no IP number can change 

- /24 - last IP number can change 

- /16 – last IP two numbers can change 

- /8 – last IP three numbers can change 

- /0 – all IP numbers can change



CIDR CALCULATOR: https://www.ipaddressguide.com/cidr



DNS Resolution

- DNS (Domain Name Server) resolution is the process of translating IP addresses to domain names.

- We can use private hosted zones to create private DNS (e.g. google.com)



Network ACLs & Security Group Incoming Request

- A gateway VPC endpoint only supports S3 and DynamoDB
- Interface VPC endpoints

## Network ACLs
A network access control list (ACL) is an optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of one or more subnets. 
- [Comparison of security groups and network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html#VPC_Security_Comparison)


## Example
you can create a public-facing subnet for your web servers that have access to the internet. You can also place your backend systems, such as databases or application servers, in a private-facing subnet with no internet access.



### VPC endpoint and VPC Peering

- Pvt connectivity to AWS resource w/o internet use + same account - VPC Endpoint
- Pvt connectivity to AWS resource w/o internet use + different account - VPC Peering
