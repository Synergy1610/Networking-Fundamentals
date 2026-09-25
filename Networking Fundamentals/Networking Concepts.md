---
aliases:
  - Host
  - IP Address
  - Network
  - MAC Address
---
#networking 

Reference: [Practical Networking](https://www.youtube.com/watch?v=bj-Yfakjllc&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=1)

### Host
Any device that can send and receive information (data) is called a host.
They fall into two categories:
- Clients
- Servers

A *Client* is basically the device that sends the request and the *Server* is the device that responds to that request.
This relationship is not fixed, rather depends on the context of the communication, therefore a device can be a client at one instance and a server at another instance.

**Note:** The general term server just means a computer that has software installed that makes it respond to certain requests.

### IP Address
It is the identity of the host. Every host needs an IP address to communicate.
During any communication between a client and a server along with the data packets the *source and destination IP addresses are mentioned*.

An IP address consists of *32 bits* which is split into 4 octets, where each octet can have a *decimal from 0 to 255*.
Ex: 192.168.0.1 is an IP Address

More details: [[Networking Basics]]
There are also two different types of IP Addresses: [[Public and Private IP's]]

IP Addresses are hierarchically by a process known as [[Subnetting]].
For example if the ACME corporation owns every ip address with 10.x.x.x
![[IP Address Heirarchy.png]]

### MAC Address
Stands for Media Access Control. It is a unique serial number etched onto every NIC (Network Interface Card).
*No two devices can have the same MAC Address*. Therefore it is used to identify a device withing a network. 
It consists of 48 bits, that is 12 Hex digits.
Example: 24-B2-B9-70-A9-31 (This is the MAC Address for Soorya-Ideapad)

### Network
A network is what transports traffic between hosts.
It is basically a *logical grouping of devices*, for example we have home networks and school networks.

A network can also contain other networks inside them, these are knows as *sub-networks or subnets*. For example every classroom in a school has their own network which is connected to a central school network. The above example about the ACME corporation is also valid here.

A network can also connect to other networks. And instead of connecting to each and every other 
network out in the world, every network is connected to some intermediary networks (Like *ISP*), which themselves are interconnected. This vast web of interconnected networks is what's called as the *Internet*. 


