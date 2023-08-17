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

## 1.1.3 What Is a Protocal?
A *protocol* defines the format and the order of messages exchanged between two 
or more communicating entities, as well as the actions taken on the transmission 
and/or receipt of a message or other event.

## 1.2 The Network Edge
