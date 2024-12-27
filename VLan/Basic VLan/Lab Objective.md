The goal of this lab is to create and configure VLANs on a Cisco switch to demonstrate traffic segmentation and isolation within a network. Two VLANs will be created:

1. **VLAN 10**, named "Sales," will represent one logical group in the network. It will have two PCs assigned, connected to the switch through ports `FastEthernet 0/1` and `FastEthernet 0/2`. These PCs will communicate within the VLAN using IP addresses `10.100.100.50` and `10.100.100.51`, both with a subnet mask of `255.0.0.0`.
    
2. **VLAN 20**, named "Development," will represent another logical group. Similarly, two PCs will be assigned to this VLAN, connected to `FastEthernet 0/3` and `FastEthernet 0/4`. These PCs will use IP addresses `10.100.100.52` and `10.100.100.53`, both with the same subnet mask as VLAN 10.
    

Additionally, a laptop will be connected to the switch on port `FastEthernet 0/5`. It will remain in the **default VLAN (VLAN 1)** and will use the IP address `10.100.100.54` with the same subnet mask. The default VLAN will not have direct communication with VLAN 10 or VLAN 20 due to VLAN isolation.