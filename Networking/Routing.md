# Routing #

VPC Context
- Route Tables
- Border Gateway Protocol

Route 53 COntext 
- Routing Policies

ELB Context 
- Request Routing

## Routing Tables ##
- VPCs have an implicit router and main routing table
- You can modify the main routing table, or create new tables
- Each route table contains a local route of the CIDR block
- Most specific route for an address wins

## Border Gateway Protocol ##
- Popular routing protocol for the internet
- "Propogates" information about the network to allow for dynamic routing
- Required for Direct Connect and optional for VPN
- Alternative of not using BGP with AWS VPC is static routes
- AWS supports BGP community tagging as a way to control traffic scope and route preference
- Required TCP port 179+ ephemeral ports
- Autonomous System Number (ASN) = Unique endpoint identifier
- Weighting is local to the router and higher weight is preferred path for outbound traffic

