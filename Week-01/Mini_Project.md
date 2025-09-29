# Packet Journey from Laptop to Google.com

This mini project documents how a data packet travels from a laptop to Google’s servers, showing the packet journey across OSI layers using **Wireshark**, **traceroute**, and **browser traffic**. Both **ICMPv6** (for traceroute) and **TCP/HTTPS** traffic are analyzed.

## Objective

- Capture and observe packets traveling to google.com.
- Understand how data moves through OSI layers.
- Document ICMPv6 traceroute and HTTPS browser traffic safely.

## Tools

- **Wireshark** – Network packet analyzer  
- **Command Prompt / Terminal** – To run tracert  
- **Browser** – To generate HTTPS traffic  

## Steps

1. Open Wireshark and select the active network interface.
2. Start packet capture.
3. Run traceroute in Command Prompt:
   ```cmd
   tracert google.com
4. Observe ICMPv6 Echo Request, Echo Reply, and Time Exceeded messages in Wireshark.
5. Open browser and visit [https://www.google.com](https://www.google.com).
6. Observe TCP/HTTPS packets in Wireshark (filter: `tcp.port == 443`).
7. Stop capture and analyze packet details.

## Observations

| Packet Type         | OSI Layer(s) | Source Address        | Destination Address   | Notes                                 |
|---------------------|--------------|----------------------|----------------------|----------------------------------------|
| Traceroute ICMPv6   | L2-L4        | fe80::1              | fe80::2, fe80::3 ... | Echo Request/Reply, TTL behavior       |
| HTTPS Browser       | L4-L7        | 192.168.1.x          | 172.217.x.x          | TCP handshake, TLS handshake, Port 443 |

## Packet Journey Diagram

Laptop → Router → ISP → Google Server

## Conclusion

- Packets are encapsulated as they move from the laptop through the network:  
Application Data → TCP/ICMPv6 Segment → IP/IPv6 Packet → Ethernet Frame → Bits.
- Wireshark shows the reverse process (decapsulation) as responses return.
- Traceroute reveals the hops (routers) packets pass through using ICMPv6 messages.
- HTTPS traffic demonstrates the TCP handshake and TLS setup for secure connections.
- This project helps visualize real network communication and OSI layer interaction safely.
