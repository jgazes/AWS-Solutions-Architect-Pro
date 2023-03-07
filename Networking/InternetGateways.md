# Internet Gateways #

Access to VPCs
- Internet Gateway
- Egress-Only Internet Gateway
- NAT Instance
- NAT Gateway

## Internet Gateway  ##
- Horizontally scaled, redundant and highly available component that allows communication between your VPC and the internet
- No availability risk or bandwidth constraints
- If your subnet is associated with a route to the internet, then it is a public subnet
- Supports IPv4 and IPv6

Purpose 1: Provide route table target for internet-bound traffic
Purpose 2: Perform NAT for instances with public IP addresses

Does not perform NAT for instances with private IP's only

## Egress-Only Internet Gateway ##
- IPv6 addresses are globally unique and are therefore public by default.
- Provides outbound internet access for IPv6 addressed instances
- Prevents inbound access to those IPv6 instances
- Stateful - forwards traffic from instance to internet and then sends back the response
- Must create a custom route for ::/0 to the Egress-Only internet gateway
- Use Egress-Only internet gateway instead of NAT for IPv6

## NAT Instance ##
- EC2 instance with a special AWS-provided AMI
- Translate traffic from many private IP instances to a single public IP and back
- Doesn't allow public internet initiated connections into private instances
- Not supported for IPv6 (use Egress-Only Gateway)
- NAT instance must live on a public subnet with a route to internet gateway
- Private instances in private subnet must have route to the NAT instance, usually the default route destination of 0.0.0.0/0

## NAT Gateway ##
- Fully managed NAT service that replaces need for NAT instance on EC2
- Must be created in a public subnet
- Uses elastic IP for public IP for the life of the Gateway
- Private instances in private subnet must have route to the NAT gateway, usually default route 0.0.0.0/0
- For multi-AZ redundancy, create NAT gateways in each AZ with routes for private subnets to use local gateway
- Up to 5Gbps bandwidth that can scale up to 45 Gbps
- Can't use a NAT Gateway to access VPC peering, VPN or Direct Connect, so be sure to include specific routes to those in your route table. (remember: most specific route is selected first)

## NAT Gateway vs NAT Instance ##

NAT Gateway//Nat Instance
- Availability: Highly available within AZ//On your own
- Bandwidth: Up to 45 Gbps//Depends on bandwidth of instance type
- Maintenance: Managed by AWS//On your own
- Performance: Optimized for NAT//Amazon Linux AMI configured to perform NAT
- Public IP: Elastic IP that can not be detatched//Elastic IP that can be detatched
- Security Groups: Cannot be associated with NAT gateway//Can use Security Groups
- Bastion Server: Not supported//Can be used as a bastion

