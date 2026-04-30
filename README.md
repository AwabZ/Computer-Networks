# Small Business Network Infrastructure Design:
This project involves the design, implementation, and verification of a small-scale network infrastructure using Cisco Packet Tracer. The primary focus was creating an efficient environment by utilizing subnetting to minimize address waste and ensuring full end-to-end connectivity across multiple network segments.

## Objectives
Topology Design: Build a network consisting of 4 routers, 4 switches, and 12 PCs connected via Serial and Ethernet interfaces.  

IP Addressing: Implement an efficient IPv4 subnetting scheme to allocate the minimum number of addresses required for each segment.  

Routing Configuration: Configure static IP routing between all routers to facilitate inter-network communication.  

Verification: Use IOS commands and connectivity tests (ping/traceroute) to validate the configuration.

## Network Topology:
The architecture consists of four distinct segments connected through a chain of routers (R1 through R4). Each router serves a local area network (LAN) containing a switch and three PCs.  

## Addressing Strategy:
To ensure efficiency, Variable Length Subnet Masking (VLSM) concepts were applied:

LAN Segments: Each LAN uses a /29 mask (255.255.255.248), providing exactly 6 usable host addresses per segment (3 for PCs, 1 for the Router interface, and 1 for the Switch management VLAN).  

Point-to-Point Serial Links: Connections between routers use a /30 mask (255.255.255.252), which provides the absolute minimum of 2 usable addresses required for a direct link.

## Configuration Highlights:

Static Routes: Each router is configured with static routes to reach non-adjacent networks. For example, R1 is configured to forward traffic for the 192.168.1.8, .16, and .24 networks to its next-hop neighbor, R2 (192.168.1.34).  

Clock Rates: DCE interfaces on the serial links were configured with a clock rate of 64000 to synchronize data transmission.  

Management: Switches were assigned IP addresses on Vlan1 and configured with a default gateway to allow for remote management within their respective segments.
