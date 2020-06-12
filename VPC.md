# VPC

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