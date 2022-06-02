# AWS-Cloud-Solution-For-2-Websites-Using-A-Reverse-Proxy-Technology

## Set Up a Virtual Private Network (VPC)

Created a VPC

![](images/1.png)

Created 2 public subnets and 4 private subnets 

![](images/4.png)

![](images/5.png)

Created a route table and associated it with public subnets

![](images/6.png)

Create a route table and associate it with private subnets

![](images/7.png)


Create an Internet Gateway

![](images/2.png)

![](images/3.png)


Associated public route tables with internet gateway

![](images/10.png)

![](images/11.png)

Created a NAT gateway with an elastic IP and associated with private subnets

![](images/12.png)

![](images/13.png)

![](images/14.png)

created security groups for 

- Application load-balancers
- Bastion servers
- Nginx servers
- Webservers
- Data layer 

![](images/15.png)

![](images/16.png)

![](images/17.png)

![](images/18.png)

![](images/19.png)

![](images/20.png)

![](images/21.png)

## TLS Certificates From Amazon Certificate Manager (ACM)

Requested a public wildcard certificate for the domain name

Validated the domain name using DNS

![](images/22.png)

![](images/23.png)

![](images/24.png)


## Setting up EFS

Created an EFS filesystem

Created an EFS mount target per AZ in the VPC and associated it with both subnets dedicated for data layer

Associated the Security groups created earlier for data layer

![](images/25.png)

![](images/26.png)

![](images/27.png)

Create an EFS access point. 

![](images/28.png)

## Setting up RDS

Created a key for RDS with key management service 

![](images/29.png)

Created and configured RDS

![](images/30.png)

![](images/31.png)

## Setting up compute resources

Created 3 ec2 instances to set up compute resouces 

Installed the following 
- python
- ntp
- net-tools
- vim
- wget
- telnet
- epel-release
- htop

![](images/ami1.png)

![](images/ami2.png)

![](images/ami3.png)

![](images/ami4.png)

![](images/ami5.png)

![](images/ami6.png)

![](images/ami7.png)

![](images/ami8.png)

![](images/ami9.png)

![](images/ami10.png)

![](images/ami11.png)

![](images/ami12.png)

![](images/ami13.png)

![](images/ami14.png)

![](images/ami15.png)

Created AMIS for bastion, Nginx and webservers from the configured ec2 instances

![](images/32.png)



## CONFIGURE APPLICATION LOAD BALANCER (ALB)

Created target groups for Nginx, tooling site and wordpress site

![](images/33.png)

Created external application load balanacer

![](images/34.png)

Forward traffic to nginx target 

![](images/35.png)

Create internal load-balancer

![](images/37.png)

Forward to tooling target and wordpress target

![](images/38.png)

Created Launch templates

added below user data for nginx

![](images/ltnginx.png)

added below user data for wordpress

![](images/ltwordpress.png)

added below user data for tooling

![](images/lttooling.png)

![](images/lttooling2.png)


![](images/40.png)

Created auto-scaling groups

![](images/41.png)

## Databases 

Create database for tooling and wordpress 

ssh into bastion server

![](images/42.png)

![](images/43.png)

![](images/44.png)

## Route53

Creates records

![](images/47.png)

![](images/48.png)

Confirm target groups are healthy 

![](images/45.png)

![](images/49.png)

![](images/50.png)

Confirm Websites are fucntionioning 

![](images/51.png)

![](images/52.png)

![](images/53.png)









