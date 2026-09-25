    #networking 

For a host to achieve internet connectivity, a *host needs 4 things* that need to be configured for the communication to take place.
Now these are:

1) [[Networking Concepts|IP Address]]: A host needs to have a configured IP Address.
2) [[Subnet Mask]]: It can either be in /24 format or 255.255.255.0 

**Note**: With only these two the host can communicate with other devices on the same network. But for Internet Communication it needs a:

3) Default Gateway: This is the IP Address of the router.
4) [[Protocols|DNS]] Server: So that the device can translate domain names to IP's.

*Now whenever any device wants to connect to the internet, it must be configured with these four initially.*  But doing this manually is complicated and not for everyone, therefore there is a [[Protocols|Protocol]] to make this easier.

### DHCP
This stands for Dynamic Host Configuration Protocol.
Now a DHCP server provides an IP, Subnet Mask, Default Gateway and DNS server to any client automatically.

In a home network, the DHCP server runs on the router itself, so when u connect a device to the wifi, your device sends a message requesting all  4 to the DHCP server, which it provides and then u can connect to the internet.

---

To see packets move through the internet and how the tables are filled and use 
refer this video: [Practical Networking](https://www.youtube.com/watch?v=YJGGYKAV4pA&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=13&pp=iAQB)


