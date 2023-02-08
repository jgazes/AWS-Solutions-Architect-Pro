# Network to VPC Connectivity #
[AWS re:Invent 2016: Amazon Global Network Overview with James Hamilton](https://www.youtube.com/watch?v=uj7Ting6Ckk&ab_channel=AmazonWebServices)

## AWS managed VPN ##
- What.  AWS Managed IPsec VPN connection over your existing internet.
- When. Quick and usually simple way to establish a secure tunneled connection to a VPC; Redundant link for Direct Connect or other VPC VPN.
- Pros.  Supports static routes or BGP peering and routing
- Cons.  Dependent on your internet connection
- How. 
1. Designate an appiance to act as your customer gateway (usually your on prem router)
2. Create the VPN connection in AWS and download the config file for you customer gateway
3. Configure your customer gateway using the information from the config file. (typically IPSEC for encryption protocol)
4. Generate traffic from your side of the VPN connection to bring up the VPN tunnel.
5. Configure BGP routing if needed
## AWS Direct Connect ##
- What. Dedicated network connection over private lines straight into AWS backbone
- When. Require a big pipe into AWS.  Lots of resources and services being provided on AWS to your corporate users.
- Pros. More predictable network performance, potential bandwidth cost reduction; up to 10Gbps provisioned connections; Supports BGP peering and routing
- Cons. May require additional telecom and hosting provider relationships and/or new network circuits.
- How. Work with your existing Data Networking provider; Create Virtual Interfaces (VIF) to connect ot VPCs  (private VIF) or other AWS service like s3 or Glacier (public VIF) 
## AWS Direct Connect + VPN ##
- What. IPsec VPN connection over private lines
- When. Want added security of encrypted tunnel over Direct Connect
- Pros. More secure than direct connect alone
- Cons. More complexity introduced by VPN layer
- How. Work with your existing Data Networking Provider.
## AWS VPN CloudHub ##
- What. Connect locations in a Hub and Spoke manner using AWS's Virtual Private Gateway
- When.  Link remote offices for backup or primary WAN access to AWS resources and each other
- Pros. Reuses existing internet connection; Supports BGP routes to direct traffic (for example, use MPLS first then CloudHub VPN as backup)
- Cons. Dependant on internet connection; No inherent redundancy
- How. Assign multiple customer gateways to a virtual private gateway, each with their own BGP ASN and unique IP ranges.
## Software VPN ##
- What. You provide your own VPN endpoint and software
- When. You must manage both ends of the VPN connection for compliance reasons or you want to use a VPN option not supported by AWS
- Pros. Ultimate flexibility and manageability
- Cons. You must design for any needed redundancy across the whole chain.
- How. Install VPN software via Marketplace appliance or on an EC2 instance
## Transit VPC ##
- What. Common strategy for connecting geographically disperse VPCs and locations in order to create a global network transit center.
- When.  Locations and VPC-deployed assets across multiple regions that need to communicate with one another.
- Pros. Ultimate flexibility and manageability but also AWS-managed VPN hub-and-spoke between VPCs
- Cons. You must design for any needed redundancy across the whole chain
- How. Providers like Ciso, Juniper Networks and Riverbed have offerings  which work with their equipment and AWS VPC
