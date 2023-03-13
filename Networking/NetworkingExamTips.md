# Networking Exam Tips #

## VPC  ##
- Know the pros and cons of each on prem to AWS connection mode
- Know the functions of the different VPC components (customer gateway, virtual private gateway)
- Know that Direct Connect is not inherently redundant, so know how to architect a network that is (VPN, secondary direct connect)
- Multicast and Broadcast arent supported in VPCs
- Know what is meant by stateless, stateful, connectionless and connection based in terms of IP protocols
- Know what ephemeral ports are and why they might need to be in NACLs or SGs

## Routing ##
- Understand BGP and how to use weighting to shift network traffic.
- Know how routes in a route table are prioritized (most specific first)
- What other routing protocols does AWS support (none.. only BGP)

## VPC Peering ##
- CIDR ranges cannot overlap
- After VPC owner accepts a peering request, routes must be added to respective route tables
- Transitive peering is not supported, but mesh or hub and spoke architectures are with proper NACLs and Routes
- A transit VPC is supported

## Internet Gateways ##
- Difference between a NAT instance and a NAT gateway. (Timeout behavior. NAT gateway returns an RST packet to any resources behind the NAT gateway that attempt to continue the connection.  NAT instance sends a FIN packet to resources behind the NAT instance to close the connection.)(FIN: a message that triggers a graceful connection termination between a client and a server. RST: a message that aborts the connection (forceful termination) between a client and a server)
- Internet Gateway is horizontally scaled, redundant, with no bandwidth constraints
- NATs do have bandwidth constraints
- VPCs can have multiple NATs across AZs and subnets for scale - so long as routes are defined properly
- Use Egress-Only Gateway for IPv6

## Route 53 ##
- Understand different types of routing policies and use cases
- Know the weighted routing formula
- Route 53 is a global service

## CloudFront ##
- Understand what must happen to use a custom domain with CloudFront
- Understand what SNI enables and the necessary alternative

## Elastic Load Balancer ##
- Know the three different types of load balancers and at which layer they work
- Understand which major features each deliver
- Know what sticky sessions are and when they come into play

## Additional Reading ##
[Amazon Virtual Private Cloud Connectivity Options January 2018](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://d0.awsstatic.com/whitepapers/aws-amazon-vpc-connectivity-options.pdf)
[Integrating AWS with Multiprotocol Label Switching](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://d1.awsstatic.com/whitepapers/Networking/integrating-aws-with-multiprotocol-label-switching.pdf)
[Security in Amazon Virtual Private Cloud](https://docs.aws.amazon.com/vpc/latest/userguide/security.html)

