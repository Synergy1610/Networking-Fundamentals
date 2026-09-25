---
aliases:
  - OSI Model
  - Layer 1
  - Layer 2
  - Layer 3
  - Layer 4
  - Encapsulation
  - Deencapsulation
---
#networking 
Reference: [Practical Netwoking](https://www.youtube.com/watch?v=LkolbURrtTs&list=PLIFyRwBY_4bRLmKfP1KnZA6rZbRHtxmXi&index=3)

**What is the purpose of networking?**
Allows two hosts to transfer data among them without using portable media like USB.

The rules of networking are divided into *7 different layers*, this is known as the OSI Model.
Each layer has its own function and all of the them need to function properly in order for us to transfer data over the network.

![[OSI Model.png]]

**Mnemonic:** All Projects Seem To Need Data Processing

## Layer 1: Physical
All data consist of bits that are 1s and 0s.
Now this layer *depicts the technology that is used to transfer these bits from one host to another.*
Layer 1 technologies include wires (Ethernet, Fiber Optics), WIFI, [[Network Devices|Repeater]], [[Network Devices|Hub]].

**Note:** WIFI is also a layer 1 tech as it is used to transfer bits wirelessly. It is called still called physical layer cuz these terms were coined long before wireless tech was available.

## Layer 2: Data Link (Hop to Hop)
These are basically *the devices that put the bits into the physical layer*.
Such as NICs (Network Interface Cards) and WIFI Access Cards. 
The ethernet cables are connected to NICs, and WIFI cards work similarly but with radio waves.
This layer is also called the [[Networking Concepts|MAC Address]] Layer, because the devices in this layer use MAC Addresses to identify the other device the bits are being sent / received from.

**Note:** A [[Network Devices|Switch]] is also a Layer 2 Device as it uses MAC Addresses to identify connected hosts, and it facilitates the transfer of data within the network.

Now think of layer 2 as the layer that deals with the hopping of data, so if its between two hosts that's one hop. But for communications between hosts in different networks, multiple hops are required. 
So the data hops from the client and routers then finally reaches the server.

**Note:** Each router also has built in NICs with their own MAC Address. So if there are three interfaces on the router (three connected networks) that means the router will have *3 NIC's* therefore **3 IP's and MAC Address.**

`Question: Now when the data hops from the client to a router then to another router and so on, the mac address changes after every hop, So how does it know from where to where the data needs to go.`

This is where Layer 3 comes into play.

## Layer 3: Network (End to End)
The addressing scheme used in this layer is the [[Networking Concepts|IP Address]].
So when data needs to be sent from one host to another host, *along with the data a source and destination IP Address header is also added* which is removed once it reaches the destination.
Layer 3 also deals with finding the best route among multiple for the data to travel between.
Layer 3 devices include anything with an IP Address such as [[Networking Concepts|Host]], [[Network Devices|Router]] etc.

**General Idea**
Layer 3 = The 'where' (The final destination + deciding direction at each stop)
Layer 2 = The 'how' (Physically delivering to the next location once the direction is decided)

![[Layer 3.png]]

**Note:** Here it seems like Layer 2 and Layer 3 are two separate entities but there is actually a protocol called [[Protocols|ARP]] Resolution that links a L3 address to a L2 address.

## Layer 4: Transport (Service to Service)
`Now consider a device that has a web browser open and an online game open. They both send and receive there data through the same wire, then how does the device know which data is for which program.`

This is where Layer 4 comes into play, the addressing scheme used here is **Ports.** 
So whenever a service connects to a network it has a unique port. And all incoming data packets also have a Layer 4 header which informs the device as to which port this data packet is for.

For Example, if the web browser could be on port 443 and the online game on port 28.

*TCP and UDP* are the two main protocols that deal with separating the data packets into their respective services.
TCP = Favors Reliability whereas UDP = Favors Efficiency.
Both TCP and UDP can have ports from 0 to 65535.

**Note:** When a client sends a request to a server, the server is usually listening on a specific well known (destination) port and during the establishing of the connection the client chooses a random local (source) port. Now when the server responds it will respond to the same port the client chose randomly.
*This also allows for multiple connection to the same server, as each connection will have a unique source port.*

## Layers: 5, 6, 7
When the OSI Model was initially created each of these three layers had distinct  functionalities. But now the difference between them are very vague and they all usually come under one layer called the **Application Layer**.  This is called the **TCP/IP Model.**

![[New OSI model.png]]

# Encapsulation and De-encapsulation
Now lets talk about the flow of data between two hosts with regards to the OSI Model.

### Sender (Client): Encapsulation
The client's application generates some data. *This data now traverses down the network stack and gets assigned headers.*

1) Data + Layer 4 = Forms a **Segment**. This contains the data and a TCP/UDP header which contains the source and destination Ports for service to service delivery.
2) Segment + Layer 3 = Forms a **Packet**. This contains the segment and an IP Address header which contain source and destination IP Address for end to end delivery.
3) Packet + Layer 2 = Forms a **Frame**. This contains the Packet and a MAC Address header which contains source and destination MAC Address for hop to hop delivery.
4) Frame + Layer 1 = Frame gets converted into **bits** and is sent across the wire.

### Receiver (Server): De-encapsulation
When the server receives the information , it first check it one header at a time to make sure it is the right destination and makes sure it reaches its target application.

1) Bits received are converted into data and first the MAC Address is checked if it matches with the NIC.
2) Then the IP address is checked .
3) Then the port is checked.
4) And finally the data is sent to the application.

## Final Notes
The OSI Model is just a framework. It is not a defined set of rules that needs to be followed to implement networking.
[[Network Devices]] exist at specific layers.
[[Network Protocols]] exist at specific layers.
But exceptions do exist.

![[OSI Model final.png]]