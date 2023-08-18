# 1.1 What Is the Internet?

## 1.1.1 A Nuts-and-Bolts Description
End systems are connected together by a network of *communication links* and 
*packet switches*.
- *Transmission rate* of a link is measured in bits/second (bps).
- A *packet switch* takes a packet arriving on one of its incoming communication 
links and forwards that packet on one of its outgoing communication links.
- Two most prominent types of packet switches are *routers* and *link-layer switches*.

The sequence 
of communication links and packet switches traversed by a packet from the sending end system to the receiving end system is known as a *route* or *path* through 
the network.

End hosts access the Internet through *Internet Service Providers (ISPs)*, including corporate ISPs, cellular data ISPs, etc. Each ISP is in itself a network of packet switches and communication links.
- lower-tier ISPs are interconnected through national and international upper-tier ISPs, upper-tier ISPs are connected directly to each other. 
- An upper-tier ISP consists of high-speed routers interconnected with high-speed links.
- Each ISP network is managed independently.
  
End systems, packet switches, and other pieces of the Internet run *protocols* that control the sending and receiving of information within the Internet. *Transmission 
Control Protocol (TCP)* and the *Internet Protocol (IP)* are the two of the most important. The Internet’s principal protocols are collectively known as *TCP/IP*.

*Internet standards* are developed by the Internet Engineering Task Force (IETF) [IETF 2020]. The IETF standards documents are called *requests for comments (RFCs)*.

## 1.1.2 A Services Description
Applications that run on end systems and involve multiple end systems that exchange data with each other are said to be *distributed applications*.

Internet *socket interface* is a set of rules that the sending program must follow so 
that the Internet can deliver the data to the destination program.

## 1.1.3 What Is a Protocol?
A **protocol** defines the format and the order of messages exchanged between two 
or more communicating entities, as well as the actions taken on the transmission 
and/or receipt of a message or other event.

## 1.2 The Network Edge
Edge of the network are the end systems. End systems are also called *hosts*, since they host (run) applications. Two categories of hosts: *clients* and *servers*.

### 1.2.1 Access Networks
Access network - the network that physically connects an end 
system to the first router (also known as the "edge router") on a path from the end 
system to any other distant end system. 

#### Home Access: DSL, Cable, FTTH, and 5G Fixed Wireless
Today, the two most prevalent types of broadband residential access are 
**digital subscriber line (DSL)** and **cable**. 

A residence typically obtains DSL Internet access from a local telephone company (telco).

The residential telephone line carries both data and traditional telephone signals simultaneously, which are encoded at different frequencies:
- A high-speed downstream channel, in the 50 kHz to 1 MHz band
- A medium-speed upstream channel, in the 4 kHz to 50 kHz band
- An ordinary two-way telephone channel, in the 0 to 4 kHz band

Cable Internet access makes use of the cable television company’s existing cable 
television infrastructure. A residence obtains cable Internet access from the same 
company that provides its cable television.

An up-and-coming technology that provides 
even higher speeds is **fiber to the home (FTTH)**. FTTH provides an optical fiber path from the CO (central office) directly to the home.

#### Access in the Enterprise (and the Home): Ethernet and WiFi
On corporate and university campuses, and increasingly in home settings, a *local 
area network (LAN)* is used to connect an end system to the edge router. *Ethernet* is by far the most prevalent LAN access technology.

### 1.2.2 Physical Media
Physical media of signals fall into two categories: *guided media* and *unguided media*. With guided media, the waves are guided along a solid medium, such as 
a fiber-optic cable, a twisted-pair copper wire, or a coaxial cable. With unguided media, the waves propagate in the atmosphere and in outer space, such as in a wireless LAN or a digital satellite channel.

Physical media: twisted-pair copper wire, coaxial cable, fiber optics, terrestrial radio channels, satellite radio channels, etc.

## 1.3 The Network Core
The network core is the mesh of packet switches and links that interconnects the Internet’s end systems.

### 1.3.1 Packet Switching
A **packet** is a chunk of data among many into which a complete message is broken.

Between source and destination, each packet travels through communication 
links and **packet switches**.

#### Store-and-Forward Transmission
Most packet switches use **store-and-forward transmission** at the inputs to the links. Store-and-forward transmission means that the packet switch must receive the entire packet before it can begin to transmit the first bit of the packet onto the outbound link.

#### Queuing Delays and Packet Loss
For each link attached to a packet switch, the packet switch has an **output buffer (also called an output queue)**, which stores packets that the router is about to send into that link. Congestion in a link may lead to *queuing delays*, or even **packet loss**, in the case the output buffer is full and cannot receive new incoming packets.

#### Forwarding Tables and Routing Protocols
Every end system has an address called an IP address.

Each router has a **forwarding table** that maps destination addresses (or portions of the destination addresses) to that router’s outbound links.

The end-to-end routing process is analogous to a car driver who does not 
use maps but instead prefers to ask for directions.

The Internet has a number of special *routing protocols* that are used to automatically set the forwarding tables.

#### Circuit Switching
There are two fundamental approaches to moving data through a network of links 
and switches: *circuit switching* and *packet switching*.

In circuit-switched networks, the resources needed along a path (buffers, link 
transmission rate) to provide for communication between the end systems are 
reserved for the duration of the communication session between the end systems. 
In packet-switched networks, these resources are not reserved; a session’s messages 
use the resources on demand and, as a consequence, may have to wait (that is, queue) 
for access to a communication link.

Traditional telephone networks are examples of circuit-switched networks. 

Before the sender can send the information, 
the network must establish a connection between the sender and the receiver. This connection is called a *circuit* in telephony.

#### Multiplexing in Circuit-Switched Networks
A circuit in a link is implemented with either **frequency-division multiplexing 
(FDM)** or **time-division multiplexing (TDM)**.
 
With FDM, the frequency spectrum 
of a link is divided up among the connections established across the link.

For a TDM link, time is divided into frames of fixed duration, and each frame is 
divided into a fixed number of time slots.

#### Packet Switching Versus Circuit Switching
Packet switch
- offers better sharing of transmission capacity than circuit switching
- simpler, more efficient, and less costly to implement than circuit switching
- not suitable for real-time services because of its variable and unpredictable end-to-end delays

The trend has been in the direction of packet switching.

### 1.3.3 A Network of Networks
ISPs are interconnected by creating a *network of networks*.

A *regional ISP* connects access ISPs in the region. Each regional ISP then connects to *tier-1 ISPs*. Tier-1 ISPs have larger coverage and are interconnected. Each ISP pays the upper-tier ISP to which it connects for connectivity to the Internet.

In addition to the hierarchical structure, there are points of presence (PoPs), multi-homing, peering, and Internet exchange points 
(IXPs). 
- A **PoP** is simply a group of one or 
more routers (at the same location) in the provider’s network where customer ISPs can connect into the provider ISP.
- Any non tier-1 ISP may choose to **multi-home**, that is, to connect to two or more provider ISPs. When an ISP multi-homes, it can continue to 
send and receive packets into the Internet even if one of its providers has a failure.
- A pair of nearby ISPs at the same level of the hierarchy can **peer**,  that is, they can directly 
connect their networks together so that all the traffic between them passes over the direct connection rather than through upstream intermediaries. This helps reduce traffic cost to upper-tier ISP.
- A third-party company can create an **Internet Exchange Point (IXP)**, 
which is a meeting point where multiple ISPs can peer together.

Large content-providing companies, like Google, create their own private networks to reduce payments to upper-tier ISPs and obtain greater control of service delivery.

## 1.4 Delay, Loss, and Throughput in Packet-Switched Network

### 1.4.1 Overview of Delay in Packet-Switched Network
As a packet travels from one 
node (host or router) to the subsequent node (host or router) along this path, the packet suffers from several types of delays at each node along the path. The most important of these delays are the *nodal processing delay* $d_{proc}$, *queuing delay* $d_{queue}$, *transmission delay* $d_{trans}$, and *propagation delay* $d_{prop}$; together, these delays accumulate to give a total *nodal delay*.

#### Types of Delay

The time required to examine the packet’s header and determine where to direct 
the packet is part of the **processing delay**. The processing can also include other factors such as checking for bit-level errors in the packet 
that occurred in transmission. Typically on order of microseconds. After this nodal processing, the router directs the packet to the queue that precedes the link to its neighbor router. 

At the queue, the packet experiences a **queuing delay** as it waits to be transmitted onto the link. Length depends on traffic of the link, can be on the order of microseconds to milliseconds.

A packet can be transmitted only after all the packets that have arrived before it have been transmitted. Let $L$ be the length of the packet, $R$ bits/sec be the transmission rate of the link. The transmission delay is $L/R$. This is the amount of time required to push (that is, transmit) all of the packet’s 
bits into the link. Typically on the order of microseconds to 
milliseconds.

The time required to propagate from the beginning of the link to a neighbor router is the *propagation delay*. Depends on the physical medium of the link. In wide-area networks, propagation delays are on the order of milliseconds.

### 1.4.2 Queuing Delay and Packet Loss
The most complicated and interesting component of nodal delay is the queuing delay, $d_{queue}$.

Let $L$ be the packet length, $R$ be the transmission rate in bits/sec at which bits are pushed out of the queue, $a$ be the average rate at which packets arrive at the queue in packets/sec. The average rate at which bits arrive at the queue is then $La$ bits/sec. $La/R$ is called the **traffic intensity**. If $La/R>1$, then the average rate at which bits arrive at 
the queue exceeds the rate at which the bits can be transmitted from the queue.
Golden rule in traffic engineering (TE): design the system so that the traffic intensity is no greater than 1.

In the case $La/R\leq1$, the nature of the arriving traffic impacts the queuing delay. E.g. periodic arrival of packets implies no delay, yet there can be a significant average queuing delay if packets arrive in bursts. Typically, the arrival process to a queue is random, i.e., it does not follow any pattern.

As the traffic intensity approaches 1, the average queuing delay increases drastically.

A packet loss occurs when a packet arrives to find a full queue. The fraction of lost packets increases as the traffic intensity increases. 
Therefore, performance at a node is often measured not only in terms of delay, but 
also in terms of the probability of packet loss. A lost packet may be retransmitted to ensure all data are eventually transferred from source to destination.

### 1.4.3 End-to-End Delay
Assuming $N-1$ routers between source host and destination host, and that the network is uncongested (no queuing delays), then the nodal delays accumulate and give an end-to-end delay,
$$d_{end-end}=N(d_{proc}+d_{trans}+d_{prop}).$$

**Traceroute** is a simple program that, suppose there are $N-1$ routers between the source and the destination, sends $N$ packets to each router and the destination to construct the route. RFC 1393 describes Traceroute in detail. Examples of traceroute: tracert on Windows, PingPlotter.

#### End System, Application, and Other Delay
Delay in transmitting a packet into a shared medium, packetization of data, etc.

### 1.4.4 Throughput in Computer Network
The **instantaneous 
throughput** at any instant of time is the rate (in bits/sec) at which the destination receives stream of data from source, e.g. download speed. The throughput of a route is determined by the bottleneck link along the route.

## 1.5 Protocol Layers and Their Service Models
### 1.5.1 Layered Architecture
To 
provide structure to the design of network protocols, network designers organize 
protocols—and the network hardware and software that implement the protocols—
in **layers**. We are interested in 
the services that a layer offers to the layer above—the so-called **service model** of a layer. Each layer provides its service by (1) performing certain actions within that layer and by (2) using the services of the layer directly below it.

A protocol layer can be implemented in software, in hardware, or in a combination of the two. When taken together, the protocols of the various layers are called the **protocol 
stack**. The Internet protocol stack consists of five layers: the physical, link, network, transport, and application layers.

Top down approach:

#### Application Layer
The application layer is where network applications and their application-layer protocols reside. Protocols including **HTTP** (for Web document request and transfer), **SMTP** (email message transfer), **FTP** (file transfer between two end systems). The **domain name system (DNS)**, is also an application-layer protocol.

An application-layer protocol is distributed over multiple end systems, with the 
application in one end system using the protocol to exchange packets of information 
with the application in another end system. We’ll refer to this packet of information 
at the application layer as a **message**.

#### Transport Layer
The Internet’s transport layer transports application-layer messages between application 
endpoints.  In the Internet, there are two transport protocols, **TCP** and **UDP**, either of 
which can transport application-layer messages.

TCP provides a connection-oriented service to its applications. This service includes guaranteed delivery of application-layer messages to the destination and flow control (that is, sender/receiver speed matching). TCP also breaks long messages into shorter segments and provides a congestion-control mechanism, so that a source throttles its transmission rate when the network is congested.

The UDP protocol provides a connectionless service to its applications. This is a no-frills service that provides no reliability, no flow control, and no congestion control.

We’ll refer to a transport-layer packet as a **segment**.

#### Network Layer
The Internet’s network layer is responsible for moving network-layer packets known 
as **datagrams** from one host to another.

The network layer provides the service of delivering transport-layer segments to the transport layer in the destination host.

The network layer includes the **IP** protocol, which defines the fields in the datagram as well as how the end systems and routers act on these fields. There is only one IP protocol, and all Internet components that have a network layer must run the IP protocol.

The Internet has many routing protocols, and the network administrator can run any routing protocol desired.

#### Link Layer
At each node, the network layer passes the datagram down to the link 
layer, which delivers the datagram to the next node along the route.

The services provided by the link layer depend on the specific link-layer protocol 
that is employed over the link. A datagram may be handled by different link-layer protocols at different links along its 
route.

Examples of link-layer protocols include Ethernet, WiFi, and the cable access network's DOCSIS protocol.

We'll refer to the link-layer packets as **frames**.

#### Physical Layer
The job of the physical layer is to move the *individual 
bits* within the frame from one node to the next. The protocols in this layer are again link dependent and further depend on the actual transmission medium of the link.

### 1.5.2 Encapsulation
Each layer adds its layer specific header to the packet of the layer above when sending, and strips of the header added by the layer below when receiving.

