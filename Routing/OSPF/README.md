
# What is OSPF

Open Shortest Path First (OSPF) is a link-state routing protocol that is used to find the best path between the source and the destination router using its own Shortest Path First). It is a network layer protocol which works on protocol number 89 and uses AD value 110. OSPF uses multicast address 224.0.0.5 for normal communication and 224.0.0.6 for update to designated router(DR)/Backup Designated Router (BDR).

**Dynamic Routing Protocol:**

OSPF dynamically adapts to network changes, such as link failures or network topology changes, by recalculating the best paths. 

- **Link-State Protocol:**
    
    OSPF routers exchange information about their directly connected links (link-state advertisements or LSAs) to build a complete picture of the network topology.

```
enable
configure terminal
router ospf <processID>
network <ip> <subnet in opposite> area 0
Eg: network 10.0.1.2 0.0.0.0 area 0
```
## OSPF Terms

1. **Router Id ** It is the highest active IP address present on the router. First, the highest loopback address is considered. If no loopback is configured then the highest active IP address on the interface of the router is considered.
```
show ip ospf
```
1. ****Router priority –**** It is an 8-bit value assigned to a router operating OSPF, used to elect DR and BDR in a broadcast network.
2. ****Designated Router (DR) –**** It is elected to minimize the number of adjacencies formed. DR distributes the LSAs to all the other routers. DR is elected in a broadcast network to which all the other routers share their DBD. In a broadcast network, the router requests for an update to DR, and DR will respond to that request with an update.
3. ****Backup Designated Router (BDR) –**** BDR is a backup to DR in a broadcast network. When DR goes down, BDR becomes DR and performs its functions.
4. ****DR and BDR election –**** DR and BDR election takes place in the broadcast network or multi-access network. Here are the criteria for the election:
    - The router having the highest router priority will be declared as DR.
    - If there is a tie in router priority then the highest router I’d be considered. First, the highest loopback address is considered. If no loopback is configured then the highest active IP address on the interface of the router is considered

```
show ip ospf interface brief
show ip ospf neighbour
```