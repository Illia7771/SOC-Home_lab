# TCP Three-Way Handshake Analysis
## Objective

Capture and analyze a TCP three-way handshake during an SSH connection.

## Lab Environment

Client: iMac  
Client IP: 192.168.64.1  
Server: Ubuntu Server VM  
Server IP: 192.168.64.2  
Protocol: TCP  
Service: SSH  
Destination Port: 22

## Packet Capture Command

sudo tcpdump -nn -i enp0s1 -c 3 tcp port 22

## Captured Handshake

1. SYN  
2. SYN-ACK  
3. ACK

## Analysis

The client IP 192.168.64.1 using source port 49512 sent a SYN packet to the server IP 192.168.64.2 on port 22.

The server responded with a SYN-ACK packet.

The client then sent an ACK packet, and the TCP connection was established.

## Conclusion

The TCP three-way handshake was successfully captured and analyzed during an SSH connection.