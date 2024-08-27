# Understanding-AWS-VPC

## SUMMARY


This project explores AWS Virtual Private Cloud (VPC), to understand the components of VPC infrastructure.
We will take a look at Virtual Private cloud,(VPC).

We will demonstrate how to create VPCs and all others components within a VPC namely, subnets, gateways and routing tables to have a better insight into managing these components. 

The idea is to showcase the tools needed to create an isolated and  secure network in the cloud and provide an extensive practical experience  on the fundamentals of cloud networking in deploying VPC infrastructure.


## STEP 1
### Setting up a VPC

We navigate to the search bar on AWS console,enter "VPC",upon locating the relevant result, proceed to click "create VPC" and enter the fields to create a VPC.

![alt text](<Images/Image 1.PNG>)

We created a VPC called "mytest vpc2 specifying its PV4 CIDR


## STEP 2
### Configuring Subnets within the VPC

We navigate to the subnets section on the left sidebar to click "create subnets"button.
These subnets will be within the VPC so we choose the vPC created above when configuring. We create a public subnet and a private subnet.

![alt text](<Images/Image 2.PNG>)


![alt text](<Images/Image 3.PNG>)

## STEP 3
### Creating Internet Gateway and attach to VPC

We navigate to "Internet Gatewy" section located on the left sidebar of the console  and proceed to click on the "create internet gateway" button.
We create an Internet gateway called and attach it to VPC

![alt text](<Images/Image 4.PNG>)

## STEP 4
### Setting up Route Tables

We will se up route tables to enable internet connectivity  with the internet gateway and secure outbound access.

![alt text](<Images/Image 5.PNG>)

We also edit subnet association for the route tables

![alt text](<Images/Image 6.PNG>)

Next, we edit the route table to configure it to route traffic to the internet gateway, allowing connectivity to the internet. Since only the subnet named "PublicsubnetA" is associated with this route table, only resources within that subnet can access the internet.


![alt text](<Images/Image 7.PNG>)


## STEP 5
### Enabling Outbound Internet Access through NAT Gateway

![alt text](<Images/Image 8.PNG>)

Here, we follow the previous steps used for the Internet gatewy to edit the route table for the private subnet by adding the NAT gateway  created, in the "Target field" as well as configure Private Subnet associatiation for the NAT Gateway. 
With this, the private subnet will be successfully attached to the route table.

## STEP 6
### Establishing VPC Peering Connections

1. We create two VPCs in the same region,the requester VPC and the Accepter VPC


![alt text](<Images/Image 9.PNG>)


![alt text](<Images/Image 10.PNG>)

2. We navigate to "Peering Connections" on the left sidebar to configure peering connection between the requester vpc and accepter vpc.
First we make a vpc peering request, upon acceptance the peering connection is then established

![alt text](<Images/Image 11.PNG>)

![alt text](<Images/Image 12.PNG>)


3. We go further to modify our route table to establish route peering between the requester vpc and accepter vpc.

This we achieve by editing the route table of the accepter vpc by pasting the IPV4 CIDR block of the requester vpc in the "Destination field" when adding a route.

We repeat this same process for the requester vpc to successfully create peering connection between the two vpcs.

# Understanding-AWS-VPC
