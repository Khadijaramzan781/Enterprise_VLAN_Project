
🌐 Next-Gen Enterprise Network Architecture: VLAN Segmentation & Secure Wireless Bridging
🎯 Executive Summary
Traditional flat networks are prone to security risks and broadcast storms. This project implements a Robust Multi-VLAN Infrastructure designed to optimize traffic flow and enhance departmental security within a corporate environment. By leveraging Layer 2 Switching and Router-on-a-Stick topology, the design ensures high availability and modular scalability.
🏗️ Technical Architecture
The network is engineered using a hierarchical approach, focusing on three core pillars:
1. Logical Segmentation (VLANs)
 * VLAN 10 [Admin]: Dedicated management lane for sensitive administrative operations.
 * VLAN 20 [Finance]: Isolated broadcast domain to protect financial data integrity.
 * VLAN 30 [Customer Service]: High-traffic zone featuring both wired and integrated wireless nodes.
2. Advanced Wireless Integration (The "Bridge" Strategy)
 * Mode: Transparent Layer 2 Bridging.
 * Strategy: Bypassed the standard Wireless Router NAT/DHCP layer to integrate mobile clients directly into the Enterprise Subnet.
 * Advantage: Allows central management of IP addresses and seamless Inter-VLAN communication without firewall overhead.
3. Inter-VLAN Routing
 * Utilized 802.1Q Encapsulation on a Cisco Router to facilitate seamless communication across different subnets while maintaining strict broadcast isolation.
🛠️ The Engineering Challenge (Troubleshooting Case)
> Problem: Initial deployment of "Laptop1" resulted in Destination Host Unreachable because the Wireless Router was acting as a separate Layer 3 gateway (Subnet 192.168.10.0/24).
> Solution: Re-engineered the device as a Wireless Access Point (WAP) by disabling the internal DHCP server and utilizing LAN-to-Switch trunking.
> Outcome: Successfully converged the wireless node into the main network with a 0% packet loss ratio.
> 
📈 Performance Verification
Connectivity was validated through rigorous ICMP testing across all VLAN boundaries.
| Source Node| Destination Node | IP Address  | Status | Packet Loss |
|-------|----|------------------|------------ |--------|-------------|
| Admin  PC  | Wireless Laptop  |192.168.1.134| SUCCESS|     0%      |
🖼️ Network Topology Visual
Network visual showing active link status and departmental segmentation.
🧰 Tools & Technologies
 * Simulator: Cisco Packet Tracer
 * Protocols: IPv4, ICMP, 802.1Q (Trunking), DHCP (External), IEEE 802.11 (Wireless).
 * Hardware: Cisco 2911 Router, 2960 Switches, WRT300N Wireless Router.
