### **What is Routing?**

Routing is the **process of forwarding packets** from one network to another. Routers use a **routing table** to determine the best path for data to travel across networks.

### **Types of Routing in Cisco Devices**

## **1. Static Routing**

- Manually configured routes.
- Best for **small or simple networks** with fixed paths.
- Requires manual updates if the network changes.

### **Commands to Configure Static Routing:**
```
Router(config)# ip route <destination_network> <subnet_mask> <next_hop_IP>
```

**Advantages:**

- Simple and predictable.
- No additional CPU/memory usage.

**Disadvantages:**

- Doesn't adapt to network changes.
- Not scalable for large networks.

## **2. Dynamic Routing**

- Routers **automatically learn** routes and adjust based on network changes.
- Uses **routing protocols** to share and update routing information.
- Best for **large, complex, or frequently changing networks**.

### **Types of Dynamic Routing Protocols:**

### 🔹 **Distance Vector Protocols**

- Uses **hop count** (number of routers a packet must pass through) to determine the best path.
- **Example Protocols:**
    - **RIP (Routing Information Protocol)** → Max 15 hops.
    - **EIGRP (Enhanced Interior Gateway Routing Protocol)** → Cisco proprietary, faster than RIP.

### 🔹 **Link-State Protocols**

- Routers **share full network topology** instead of just hop counts.
- More efficient and scalable than distance vector.
- **Example Protocols:**
    - **OSPF (Open Shortest Path First)** → Uses **cost (bandwidth-based metric)** to find the best route.
    - **IS-IS (Intermediate System to Intermediate System)** → Similar to OSPF but used in larger ISP networks.

### 🔹 **Path-Vector Protocols**

- Used for interconnecting **multiple networks (Autonomous Systems)** like the Internet.
- **Example Protocol:**
    - **BGP (Border Gateway Protocol)** → Used by ISPs and large enterprises for global routing.

**Advantages of Dynamic Routing:**

- **Self-adjusting** (adapts to network changes).
- Scalable for large networks.

**Disadvantages:**

- Uses **more CPU/memory** than static routing.
- Slight delay in updating routes.

## **3. Default Routing**

- Used when a router doesn’t have a specific route for a destination.
- All unknown traffic is sent to a **default gateway**.
- Best for **small networks** or **edge routers** connecting to the internet

```
Router(config)# ip route 0.0.0.0 0.0.0.0 <next_hop_IP>
```