Multi-Site OSPF Enterprise Network Lab (GNS3)

Overview
A comprehensive GNS3 simulation of a multi-site enterprise network featuring:
- OSPF dynamic routing across 3 routers
- Frame Relay & HDLC WAN encapsulation
- Inter-VLAN routing across 10 VLANs
- DHCP IP assignment for all end devices
- Full end-to-end connectivity verified via pings and Wireshark

Topology
| Device | Role | Connected To |
|--------|------|-------------|
| R1 | Core Router + DHCP Server | IOU1, IOU4, R2 (HDLC), R3 (Frame Relay) |
| R2 | Core Router + DHCP Server | IOU2, IOU3, R1 (HDLC), R3 (Serial) |
| R3 | WAN Hub Router | R1 (Frame Relay), R2 (Serial) |
| IOU1 | L3 Switch | VLANs 10, 20, 30 (192.168.1-3.0/24) |
| IOU2 | L3 Switch | VLANs 40, 50, 60 (192.168.4-6.0/24) |
| IOU3 | L3 Switch | VLANs 70, 80 (192.168.7-8.0/24) |
| IOU4 | L3 Switch | VLANs 90, 100 (192.168.9-10.0/24) |

Technologies Used
- Cisco IOS Routers (GNS3)
- Cisco IOU Layer-3 Switches
- OSPF (Open Shortest Path First) — Area 0
- Frame Relay encapsulation (DLCI-based)
- HDLC serial encapsulation
- DHCP (Dynamic Host Configuration Protocol)
- Inter-VLAN routing (Router-on-a-Stick / L3 Switch SVIs)
- Wireshark packet analysis

Verification
- `show ip route` on R2 confirms full OSPF convergence (14 remote routes)
- VPCS `ip dhcp` confirms DORA process across all VLANs
- Cross-site pings (PC8 → PC1–PC5) confirm end-to-end reachability
- Wireshark captures confirm HDLC + OSPF Hellos on R1↔R2 serial
- Wireshark confirms Frame Relay DLCI framing on R1↔R3 serial

## Skills Demonstrated
OSPF · Frame Relay · HDLC · DHCP · VLANs · Inter-VLAN Routing · 
Wireshark Analysis · GNS3 · Cisco IOS · Network Troubleshooting
