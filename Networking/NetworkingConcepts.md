# Networking Concepts #

You should already know:
- Physical layout of AZs and Regions
- VPC concept and how to create
- Create private and public subnets
- What a NAT is and "Disable Source/Destination Checks" means
- Route table and routing terminology (default routes, local routes)
- IPv4 Addressing and Subnet Mask Notation (/16, /24, etc)
- Intermediate Networking Terminology (MAC address, port, gateway vs. router)

## OSI Model ##

Layer | Name | Example | Mnemonic
- 7, Application, Web Browser, Away
- 6, Presentation, TLS SSL/Compression, Pizza
- 5, Session, Setup/Negotiation/Teardown, Sausage
- 4, Transport, TCP, Throw
- 3, Network, IP/ARP, Not
- 2, Data Link, MAC, Do
- 1, Physical, CAT5/Fiber Optic/5GHz carrier frequency, Please

- AWS is responsible for layers 1 and 2, Customer is resposible for remaining layers
- Multicast is not supported on AWS

## Protocols ##

Protocol | Characteristics | Plain Speak | Uses
- TCP (layer 4) | Connection-based, stateful, acknoledges receipt | After everything I say, I want you to confirm that you received it. | Web, Email, File Transfer
- UDP (layer 4) | Connectionless, stateless, simple, no retransmission delays | I am going to start talking and its ok if you miss some words | Streaming media, DNS
- ICMP (layer 3) | Used by network devices to exchange info | We routers can keep in touch about the health of the network using our own language | traceroute, ping

## Ephemeral Ports ##
- Short lived transport protocol ports used in IP communications
- Above the "well known" IP ports (about 1024)
- "Dynamic Ports"
- Suggested range is 49152 to 65535, however Linux kernals use 32568 to 61000, and Windows default from 1025
- NACL and Security Group implications

## Reserved IP Addresses ##
- 10.0.0.0: Network Address
- 10.0.0.1: Reserved by AWS for the VPC Router
- 10.0.0.2: Reserved by AWS for Amazon DNS
- 10.0.0.3: Reserved by AWS for future use
- 10.0.0.255: VPCs don't support broadcast so AWS reserves this address


## Video on Subnets and CIDR ##
[Subnets and CIDR](https://learn.acloud.guru/series/acg-fundamentals/view/62f923ef-8f30-2f51-8681-5ab5de29b45d)

