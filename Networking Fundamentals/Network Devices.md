---
aliases:
  - Repeaters
  - Hubs
  - Bridges
  - Switches
  - Routers
---
#networking 

Reference: [Practical Networking](https://www.youtube.com/watch?v=H7-NR3Q3BeI&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=2)

### Repeater
A simple network can be established by connecting two devices with a cable.
But as data travels through a cable it decays, now this is not a problem if the signal doesn't decay before reaching the destination. But for long connections we use a **repeater** whose sole purpose is to regenerate weak signals.

## Central Connections
When there are only a few devices they can all be connected to each other to form a network, *but this doesn't scale well*. Because it is impractical to connect every device with each other.

Rather we use a central device to which all other devices are connected, and it handles the network traffic between them. This scales well because to add a new device its just plugging it into the Central device.

### Hub
Is the first of such devices. *It receives data from the source device and then duplicates and sends it to every other device connected to it*.
Now the advantage is that every device is connected, but the disadvantage is that devices that are not involved in the communication will also receive a copy of the data.
    
![[Hub.png]]

### Bridge 
A bridge *sits between two Hub connected hosts*, and it also learns which hosts are on which side of the bridge.

Now the bridge has the ability to block data going from one side to another. It only lets the data go if the data has to go to the devices on the other side.

![[Bridge.png]]

So it is a type of device that *helps contain packets to its relative side*.

### Switch
Now a switch is a device that *facilitates communication within a network.*
A switch contains multiple ports and it also learns which device is connected to which port using their [[Networking Concepts#MAC Address|MAC Address]]. (Here we are referring to physical ports.)

And when two devices want to communicate, the switch makes sure that only those two ports are open for the packets to flow through. It can also accommodate multiple such communications at the same time. Without data being leaked to other devices.

Now all the devices connected to a switch form a [[Networking Concepts#Network|Network ]].
Hosts on a network share the same [[Networking Concepts#IP Address|IP Address]] space, Only the last octet would have a different value which makes it so that each host can be uniquely identified.

![[Switch.png]]

For more information: [[Switches in Detail]]

### Routers
Now switches facilitate communications within a network, whereas routers facilitate communications *between networks.* 
It is the device that connects multiple networks. It also learns which networks are connected to it.
Now each network is connected to an interface on the router and the router has an [[Networking Concepts#IP Address|IP Address]] for each interface where each interface belongs to a different network.

Now this IP address given to the router by a network is called the **Gateway**. Which is the exit point out of the local network.

If two hosts from different networks want to communicate, the data packet from one device is sent to its gateway on the router which then routes it to the other gateway of the other network and sends it forward.

All the information of which networks are where and the hosts connected are called **routes**, and all this stored in tables called **routing tables.**

![[Routers-1.png]]

Now since Routers are connecting many such networks, many security and other such policies are set up in such routers as all traffic flowing between networks flow through it. *Acts as a traffic control point*.

**NOTE:** There is something called [[Public and Private IP's]] which are related to routers.

**NOTE:** Home Wi-Fi routers are actually a combo device that has a router, a switch and a wireless access point all within.

# Note
**Routing:** The process of moving data between networks.
    A Router is a device whose primary purpose is routing.

**Switching:** The process of moving data withing a network.
    A Switch is a device whose primary purpose is switching.