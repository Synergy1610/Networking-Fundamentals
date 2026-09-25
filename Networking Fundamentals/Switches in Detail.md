---
aliases:
  - VLAN
  - Unicast
  - Broadcast
---

#networking 

Now we know that switching is the *process of moving data within a network*. 
And switches are the devices that perform this process.

Now any switch can only perform 3 functions:
- Learn
- Flood 
- Forward

The information a Switch learns about which devices are connected to which of its ports is saved in a table called the **MAC Address Table**.

Now to learn about these three functions, watch this [video](https://www.youtube.com/watch?v=AhOU2eOpmX0&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=7)

**Note:** A switch can also have its own MAC Address and IP Address, but these are not used on the normal basis when data is sent *through the switch.* It is only used when data needs to be sent *to the switch*, in which case it acts like a regular host.

---
Reference to this section:  [Practical Networking](https://www.youtube.com/watch?v=G7GyWjJtjNs&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=8)

#### Unicast vs Broadcast Frames

**A Unicast frame has a destination MAC Address**, and if that destination MAC Address is saved in the MAC Address Table of the switch, then it performs the *forward* function.
If it is not saved then it performs the *flood* function and sends a duplicate to every device.

**A Broadcast frame has the destination MAC Address as all f's (ff:ff:ff:ff:ff:ff:ff:ff)**, In this case the switch doesn't even look at the mac address table, and just floods this to all the devices.

Therefore, a unicast frame is *flooded only sometimes*, where as the broadcast frame is *always flooded*.

---

#### VLAN's 
This stands for Virtual LAN's.

Here we take a switch and *separate some ports in to their own isolated LAN's.*
Basically separating a large switch into smaller switches.
Now each of this smaller switches will perform their own learning, flooding and forwarding. And will also have their own Mac Address Tables.

![[VLAN's.png]]

---

#### Switching involving Multiple Switches
For learning for the three functions work when there are multiple switches. Watch this [video](https://www.youtube.com/watch?v=G7GyWjJtjNs&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=8) 
Time stamp is "5:14".