# HTTP vs HTTPS Traffic Analysis

## Objective

Capture and compare HTTP and HTTPS traffic from an Ubuntu Server VM using tcpdump.

## Lab Environment

Client: Ubuntu Server VM  
Client IP: 192.168.64.2  
HTTP Port: 80  
HTTPS Port: 443  
Interface: enp0s1

## Packet Capture Commands

HTTP:

sudo tcpdump -nn -A -i enp0s1 -c 10 tcp port 80

HTTPS:

sudo tcpdump -nn -A -i enp0s1 -c 12 tcp port 443

## Traffic Generation

HTTP request:

curl http://example.com

HTTPS request:

curl https://example.com

## Conclusion

HTTP traffic is sent in plaintext, while HTTPS protects the content using encryption. However, network metadata such as IP addresses, ports, and traffic direction can still be observed.