# **What is a Router?**

A router is a networking device that connects multiple networks together and directs data packets between them. Operating primarily at the **Network Layer (Layer 3)** of the OSI model, routers determine the best path for data to travel from the source to the destination across interconnected networks, such as the internet.

![](img/router.png)
### **How Does a Router Work?**

Routers use **IP (Internet Protocol) addresses** to route data between different networks. When data is sent from one device to another across networks, the router reads the destination IP address in the data packet, determines the best route, and forwards the packet to its next destination.

#### **Key Functions of a Router:**

1. **Routing**: Routers determine the optimal path for data packets to travel between networks.
2. **Packet Forwarding**: Once the route is determined, routers forward data packets from one network to another.
3. **Network Address Translation (NAT)**: Allows multiple devices on a local network to share a single public IP address.
4. **Firewall**: Many routers include basic firewall features to filter incoming and outgoing traffic based on security rules.
5. **Quality of Service (QoS)**: Routers can prioritize certain types of traffic, ensuring that critical applications receive sufficient bandwidth.


### **ARP**

ARP (Address Resolution Protocol) is like a phone directory for computers on a network. Imagine you know your friend's name but not their phone number you check a directory to find it.

Similarly, when a computer wants to communicate with another device on the same network, it knows the **IP address** (like a name) but not the **MAC address** (like a phone number). ARP helps by asking, **"Who has this IP address? Tell me your MAC address!"** The device with that IP responds with its MAC address, and then communication happens.

ARP works at **Layer 2 (Data Link Layer)** but interacts with **Layer 3 (Network Layer)** since it resolves IP addresses to MAC addresses.

![](img/how_arp_works.jpg)