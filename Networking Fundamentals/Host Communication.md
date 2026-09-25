---
aliases:
  - intranetwork communication
  - internetwork communication
---
 #networking 

[This Video](https://www.youtube.com/watch?v=gYN2qN11-wE) explains how two hosts *who are in the same network* communicate with each other.
It also covers **[[Protocols|ARP]] Resolution**.

**Note:** During an ARP Broadcast with destination MAC Address as FF:FF:FF:FF:FF:FF:FF:FF the broadcast is sent to every device on the network. If there is a switch , then the switch also broadcasts it to every device connected to it except the one it came from.

Once one host finds the MAC Address of the other host through ARP, it stores this data in ARP Cache. Every device with an IP Address has ARP Cache. If the device does not use that cache anymore it will get auto deleted.

**NOTE:** Every device with an IP Address has an ARP Table.

---

[This Video](https://www.youtube.com/watch?v=JI9Zm2tbUoE) explains how two hosts *on different networks* communicate with each other with the help of  [[Network Devices|Routers]]. 

**NOTE:** ARP Cache is not permanently saved, its saved for few seconds to few hours depending on the system and other factors.