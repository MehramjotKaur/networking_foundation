# Wireshark Ping Capture Notes

This file documents the process of capturing a ping using **Wireshark** and observing how a packet travels across OSI layers: Ethernet (L2), IP (L3), and ICMP (L4).

## Objective

Capture a ping to `8.8.8.8` using Wireshark to observe real network traffic and understand **encapsulation and decapsulation** in action.

## Tools

- **Wireshark** – Network packet analyzer  
- **Command Prompt / Terminal** – To send ping requests  

## Steps

1. Open **Wireshark** and select the network interface (Wi-Fi or Ethernet).  
2. Click **Start Capture**.  
3. Open Command Prompt / Terminal and run:  
   ```bash
   ping 8.8.8.8
4. In Wireshark, filter packets by ICMP:  
   ```text
   icmp
5. Observe the captured packets and note down details for Ethernet, IP, and ICMP layers.

## Observations

| Observation No. | OSI Layer        | Source Address / IP / Info     | Destination Address / IP / Info | Other Details / Notes               |
|-----------------|------------------|-------------------------------|---------------------------------|-------------------------------------|
| 1               | Ethernet (L2)    | AA:BB:CC:DD:EE:FF             | 11:22:33:44:55:66               | Type: IPv4 (0x0800)                 |
| 2               | IP (L3)          | 192.168.1.x                   | 8.8.8.8                         | Protocol: ICMP, TTL: 128            |
| 3               | ICMP (L4 Request)| 192.168.1.x                   | 8.8.8.8                         | Type: 8 (Echo Request), Code: 0, Sequence: 1, Checksum: 0x4d5a |
| 4               | ICMP (L4 Reply)  | 8.8.8.8                       | 192.168.1.x                     | Type: 0 (Echo Reply), Code: 0, Sequence: 1, Checksum: 0x555a   |

## Conclusion

- Each ping packet is encapsulated as Ethernet → IP → ICMP on the way out.
- Wireshark shows how data is decapsulated in reverse on the return.
- This hands-on exercise helps visualize data moving across OSI layers and understand real network packet structure.

