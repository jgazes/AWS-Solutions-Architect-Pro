# Route 53 #
- Register domain names
- Check health of your domain resources
- Route internet traffic for your domain

What you should already know:
- What is a DNS?
DNS is Domain Name System, or phonebook of the internet.  Humans access information through domain names (aws.com) which route to ip addresses
- DNS Record Types
A record, address
CNAME or anonical name is a dns record that points a domain name to another domain, not an IP address
MX is a mail exchange record, which makes it possible to hand off emails to a dedicated email server
TXT lets the owner store text values in the DNS, which allow services to verify ownership of a domain
- Route 53 concepts
Alias- A type of record that you can create with Amazon Route 53 to route traffic to AWS resources such as Amazon CloudFront distributions and Amazon S3 buckets.
Hosted Zone- A container for records, which include information about how you want to route traffic for a domain (such as example.com) and all of its subdomains (such as www.example.com, retail.example.com, and seattle.accounting.example.com). A hosted zone has the same name as the corresponding domain.
- Why is it called Route 53?
DNS servers respond to queries on port 53

## Route 53 Routing Policies ##

Policy | Route 53 is thinking
Simple | Simple, heres the destination for that name
Failover | Normally I would route you here, but it appears down based on my health checks so Ill failover to here
Geolocation | Looks like youre in Eu, so Im going to route you to a resource closer to you in that region
Geoproximity | Youre closer to US East 1 than US WEST 2 so ill route you to US East
Latency | Which resources has lower latency from you then ill direct you that way
Multivalue Answer | I will return several IP addresses as a sort of basic load balancer
Weighted | You can setup multiple resources and route according to the percentage of the weight you assign each

