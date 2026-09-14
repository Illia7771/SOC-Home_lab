# DNS Traffic Analysis

## Objective

Capture and analyze DNS traffic from an Ubuntu Server VM and identify A and AAAA DNS records.
## Lab Environment

Client / DNS Requester: Ubuntu Server VM  
Client IP: 192.168.64.2  
DNS Resolver / Gateway: 192.168.64.1  
DNS Port: 53  
Interface: enp0s1

## Packet Capture Command

sudo tcpdump -nn -i enp0s1 port 53

## DNS Queries

### A Record

Command:

nslookup -type=A google.com

Result:

google.com -> 142.250.73.110

### AAAA Record

Command:

nslookup -type=AAAA google.com

Result:

google.com -> 2607:f8b0:400a:80c::200e

## Analysis

I generated a DNS request from the Ubuntu VM. The VM sent the query to the DNS resolver at 192.168.64.1 and received responses for both A and AAAA records.

The difference is that an A record returns an IPv4 address, while an AAAA record returns an IPv6 address.
## Conclusion

DNS traffic was successfully captured and analyzed. The Ubuntu VM sent DNS queries to the resolver on port 53, and the differences between A and AAAA records were identified.