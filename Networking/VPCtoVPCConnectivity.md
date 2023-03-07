# VPC to VPC Connectivity #

- VPC Peering *
- Software VPN
- Software to AWS Managed VPN
- AWS Managed VPN
- AWS Direct Connect
- AWS PrivateLink *

## VPC Peering  ##

- What. AWS-Provided network connectivity between two VPCs
- When. Multiple VPCs need to communicate or access each others resources
- Pros. Uses AWS backbone without touching the internet
- Cons. If A is connected to B and B is connected to C, A cannot talk to C via B. (transitive peering not supported)
- VPC Peering request is made; Accepter accepts request (either within Account or across Accounts)

## AWS PrivateLink ##

- What. AWS-provided network connectivity between VPCs and/or AWS services using interface endpoints
- When. Keep private subnets truly private by using the AWS backbone to reach other services rather than the public internet
- Pros. Redundant: uses AWS backbone
- Cons. VPC endpoins can only be accessed over inter-region VPC peering
- How. Create endpoint for needed AWS or Marketplace service in all needed subnets; access via the provided DNS hostname

## VPC Enpoints  ##

Interface Endpoint
- ENI with a private IP
- Uses DNS entries to redirect traffic
- API Gateway, CloudFormation, Cloudwatch etc.
- Secured through security groups

Gateway Endpoint
- A gateway that is a target for a specific route
- Uses prefix lists in the route table to redirect traffic
- S3, DynamoDB
- Secured through VPC endpoint policies

