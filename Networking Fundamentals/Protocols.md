---
aliases:
  - ARP
  - FTP
  - SMTP
  - HTTP
  - SSL
  - TLS
  - HTTPS
  - DNS
  - Protocol
---

#networking 

*A protocol is a set of rules/instruction that forms an internet standard*. Most of the protocols for communication are defined in the rfc, which is public so it can be implemented by any vendor. 

# Some Commonly Used Protocols

#### ARP
Stands for **Address Resolution Protocol**, helps hosts find the MAC Addresses of specific devices they want to communicate with as long as they have its IP Address.
So ARP basically links Layer 2 to Layer 3.
ARP is defined in RFC 826.
**Note:** The messages sent for ARP that is Arp Request and Arp Response are all standards set in the rfc.

#### FTP
Stands for **File Transfer Protocol**, helps hosts transfer files between themselves, or an FTP server.

#### SMTP
Stands for **Simple Mail Transfer Protocol**, helps establish connection between two hosts or a host and a server to send and receive e-mails.

#### HTTP
Stands for **Hyper Text Transfer Protocol**, helps establish connection between a host and server to display Webpages. These Webpages are written in HTML (Hyper Text Markup Language). 

#### SSL and TLS
SSL: **Secure Sockets Layer**
TLS: **Transport Layer Security**

#### HTTPS
This is basically HTTP secured with SSL and TLS, which basically establishes secure connections between the host and the server.

#### DNS
Stand for **Domain Name System**.
We cannot remember the IP address of all the websites we want to visit, rather it is easier to remember names, That where DNS servers come into play, when we provide it with a domain name it returns with IP Address which we can use to establish communication.

**Note:** This is also applicable for Email Addresses, to convert them into the actual mail server ip address.

#### DHCP
Stands for **Dynamic Host Configuration Protocol**. 
For more details refer: [[Requirements for Internet Connectivity]]
