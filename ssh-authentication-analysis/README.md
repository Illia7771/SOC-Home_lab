# SSH Authentication Analysis
## Objective

Analyze SSH authentication events on an Ubuntu Server and identify failed, successful, and invalid-user login attempts.
## Lab Environment

Ubuntu Server VM: 192.168.64.2  
Client: iMac  
Source IP: 192.168.64.1  
Service: SSH  
Port: TCP 22

## Log Collection

SSH authentication logs were reviewed using:

sudo journalctl -u ssh --since "5 minutes ago" --no-pager

## Event 1 - Failed SSH Login

Source IP: 192.168.64.1  
Destination IP: 192.168.64.2  
Destination Port: TCP 22  
Username: Illia  
Authentication Result: Failed  
Evidence: Failed password for Illia from 192.168.64.1 port 56160 ssh2  
Conclusion: One failed SSH login attempt was observed. No repeated attempts or other suspicious activity were identified at this time.

## Event 2 - Successful SSH Login

Source IP: 192.168.64.1  
Source Port: 56161  
Destination IP: 192.168.64.2  
Destination Port: TCP 22  
Username: Illia  
Authentication Result: Successful  
Evidence: Accepted password for Illia from 192.168.64.1 port 56161 ssh2  
Conclusion: One successful SSH login was observed from the same source IP after a failed login attempt. No additional suspicious activity was identified.

## Overall Analyst Conclusion

A failed SSH login attempt was followed by a successful SSH login from the same source IP and against the same user account. The activity should be reviewed in context, but no additional suspicious behavior was identified.