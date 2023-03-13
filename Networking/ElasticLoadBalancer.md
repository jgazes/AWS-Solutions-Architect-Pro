# Elastic Load Balancer #
- Distributes inbound connections to one or many backend endpoints
- Three different options: ALB, NLB, CLB
- Cam be used for public or private workloads
- Consume IP addresses within a VPC subnet

# ELB Similarities #
- Zonal Failover
- Platform VPC, CLB has EC2 Classic as well
- Health Checks
- Cross-Zone Load Balancing
- CloudWatch Metrics
- SSL Offloading
- Resource-based IAM Permissions

# ELB Differences #
- ALB supports HTTPS/HTTP 
- NLB supports TCP, UDP, TLS
- CLB supports TCP, SSL, HTTP, HTTPS

- ALB supports path or host-based routing, other two do not

- ALB and NLB support WebSockets, CLB doesnt

- ALB and NLB support Server Name Indication (SNI)

- All support Sticky Sessions

- ALB only supports Static IP and Elastic IP through AWS Global Accelerator, NLB supports, CLB does not

- ALB supports user authentication, other two do not.

## ELB Routing ##

Network Load Balancers
- Port Number
- TCP connections to backend are persisted for the duration

Application Load Balancers
- Host based 
- Path based
- HTTP header
- HTTP method
- Query string parameter
- Source IP CIDR


