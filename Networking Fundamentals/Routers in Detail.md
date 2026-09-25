---
aliases:
  - Routing Table
  - Router Hierarchies
---

#networking 

Reference video: [Practical Networking](https://www.youtube.com/watch?v=AzXys5kxpAM&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=9)

Routing is the *process of moving data between networks.* And a router is a device that performs this process.

Now a router also has MAC Addresses and IP Addresses, but what makes it different from a host is that, When a host receives a data packet with a wrong destination IP, it deletes the packet.
 Where as a router tries to find the correct device and forwards it to that device.

**Note:** Each network is connected to an interface on the router. And the router assigns each interface an IP address within that network and also a mac address. 

---
#### Routing Table
A router maintains a map to all the networks connected to it, this is called a **Routing Table.**
A routing table contains **Routes**, which are instructions telling the router how it can reach a particular network.

A routing table can be populated in 3 ways:
- *Direct Connection*: These are routes for the networks connected directly to the router
![[Direct Connection.png]]

**NOTE:** Here LEFT and RIGHT are referring to the two interfaces on the router, in reality the naming is different.

- *Static Routes*: When there are multiple routers connected. **Static Routes** are set by the administrator manually on a router , giving it instruction on how to communicate with a host connected to another router.
![[Static Routes.png]]
 So here if a data packet needs to be sent from Device C to Device A, the R2 knows that it needs to forward the packet to the IP of R1 for the packet to reach its destination network.

- *Dynamic Routes*: This also deals with the scenario where there are multiple routers connected. But instead of manual entries, the **Routing Table** is populated by the routers automatically communicating within themselves.
![[Dynamic Routing.png]]

**Note:** The exact methods used by routers to share information with each other depends on **Dynamic Routing Protocols**. Of which there are many.

**NOTE:** A routing table must be filled before communication, cuz if the router doesn't know where to send the packet, it will just drop it.

**NOTE:** A default route means that all the data on that will be sent to the same place. Can be represented by 0.0.0.0/0

---
#### ARP Table
Now we know that every device with an IP Address also has an ARP Table, and therefore even routers have ARP Tables. But *unlike routing tables that need to filled before the communication even begins, ARP tables start out empty and get filled dynamically whenever communication takes place through ARP protocol.*

To see how ARP Tables are populated, watch this [video](https://www.youtube.com/watch?v=Ep-x_6kggKA&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=10)

![[Routing + ARP Tables.png]]

So here each router:
- Looks up the destination IP Address in its routing table to find the next hop IP address.
- Then adds the mac address for the hop IP address, but if the router doesn't know the mac address then its does ARP .

*Now these steps will take place in the give scenario of two routers and also will take place when there are any number of routers and also when the two devices are on two sides of the internet.*

---
#### Router Hierarchies

Reference Video: [Practical Networking](https://www.youtube.com/watch?v=zmxLg4jV0ts&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=11)

![[Router Hierarchies.png]]

Routers in a corporation like this are always connected in a hierarchy, because:
- **It is easier to scale:** If we wanted to add a new router in the Tokyo branch, we can just directly connect that to R5 instead of connecting to all the others.
- **Route Summarization:** Reducing the number of routes we need to store in a routing table by grouping necessary ones. To learn more refer the [video.](https://www.youtube.com/watch?v=zmxLg4jV0ts&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=11)

**Note:** If a destination IP Address overlaps with multiple routes on the the routing table of a router then it is sent to the most specific route listed.
