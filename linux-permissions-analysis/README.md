# Linux Permissions & Least Privilege

## Objective

Practice Linux file and directory permissions and understand how incorrect permissions can create security risks.

## Lab Environment

Ubuntu Server VM  
User: Illia

## Permission Values

r = 4  
w = 2  
x = 1

Common permissions:

600 = rw-------  
644 = rw-r--r--  
700 = rwx------  
755 = rwxr-xr-x  
777 = rwxrwxrwx

## Security Scenario

I created files with different permissions and tested how access changes for the owner, group, and others.

A file with 777 permissions gives read, write, and execute access to everyone. This violates the principle of least privilege because users receive more permissions than they need.

I corrected insecure permissions by removing unnecessary write and execute access.

## Finding Risky Permissions

Examples:

Find objects where others have write permission:

find . -perm -002

Find files where group has write permission:

find . -type f -perm -020

Find objects where the owner has write permission:

find . -perm -200

## Conclusion

Linux permissions are an important part of host security.

The principle of least privilege means giving users only the permissions they need. Misconfigured permissions can allow unauthorized reading, modification, or execution of files.