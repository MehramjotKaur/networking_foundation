# IPv6 Configuration and Testing Lab Report

## Introduction  
This lab focused on configuring IPv6 addresses on two PCs using Cisco Packet Tracer and testing network connectivity through IPv6 ping commands. The exercise aimed to familiarize with IPv6 concepts, manual address assignment, and basic troubleshooting in a controlled simulated environment.

## Objectives  
- Configure IPv6 on two PCs with unique global unicast addresses.  
- Assign appropriate default gateways.  
- Verify end-to-end IPv6 connectivity using ping tests.

## Equipment and Software Used  
- Cisco Packet Tracer simulation tool.  
- Two PC end devices and one IPv6-enabled switch.  
- Command Prompt for ping testing.

## Procedure  
1. Created a simple topology connecting two PCs to a router via a switch.  
2. Assigned IPv6 global unicast addresses to each PC:  
   - PC0: `2001:db8:1::1`  
   - PC1: `2001:db8:1::2`  
3. Set default gateway (`2001:db8:1::ff`).  
4. From PC0, tested connectivity to PC1 using the IPv6 ping command:
'ping 2001:db8:1::2' 

## Observations  
- Successful configuration of unique IPv6 global unicast addresses on both PCs.   
- Ping tests between PCs were successful with no packet loss, verifying proper configuration and connectivity.  

## Results  
| Device  | IPv6 Address     | Default Gateway      | Ping Test Result          |
|---------|------------------|----------------------|--------------------------|
| PC0     | 2001:db8:1::1    | 2001:db8:1::ff       | Ping to PC1 - Successful |
| PC1     | 2001:db8:1::2    | 2001:db8:1::ff       | Ping to PC0 - Successful |


## Conclusion  
The lab exercise demonstrated a successful manual configuration of IPv6 addresses in a network simulation environment with functional connectivity between devices. The ability to ping IPv6 addresses confirms a proper understanding and implementation of IPv6 addressing. This foundational knowledge is essential for transitioning networks from IPv4 to IPv6.
