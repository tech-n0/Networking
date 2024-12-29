
# What's that packet tracer file?

In this lab, What we are trying to achieve is a routing configuration between two vlan's. This concept is know as "Router-on-a-stick". Which can be achieved using a trunk mode in the switch interface.

### **Switch Configuration**
**Configure Trunk Port (to Router):** Assigning the trunk port to the router is `Fa0/05`.

```
Switch(config)# interface Fa0/05
Switch(config-if)# switchport mode trunk
Switch(config-if)# exit
```

### **Router Configuration**

1. **Create Subinterfaces for VLANs:** Configure the router's `GigabitEthernet0/0/0` interface with subinterfaces for each VLAN.

```
Router(config)# interface GigabitEthernet0/0/0.10
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 10.10.8.1 255.255.255.0
Router(config-subif)# exit

Router(config)# interface GigabitEthernet0/0/0.20
Router(config-subif)# encapsulation dot1Q 20
Router(config-subif)# ip address 10.10.16.1 255.255.255.0
Router(config-subif)# exit
```

2. **Enable the Physical Interface:**

```
Router(config)# interface GigabitEthernet0/0/0
Router(config-if)# no shutdown

```
### **PC Configuration**

For each PC in the VLANs, configure the IP addresses, subnet masks, and gateways:

- **VLAN 10 (Sales):**
    
    - PC 1: `IP: 10.10.8.50`, `Subnet Mask: 255.255.255.0`, `Gateway: 10.10.8.1`
    - PC 2: `IP: 10.10.8.51`, `Subnet Mask: 255.255.255.0`, `Gateway: 10.10.8.1`
- **VLAN 20 (Development):**
    
    - PC 1: `IP: 10.10.16.50`, `Subnet Mask: 255.255.255.0`, `Gateway: 10.10.16.1`
    - PC 2: `IP: 10.10.16.51`, `Subnet Mask: 255.255.255.0`, `Gateway: 10.10.16.1`