# Week 1: OSI & TCP/IP Models

## OSI Model (7 Layers)
1. *Physical* – Hardware like cables, switches. Responsible for sending raw data.  
2. *Data Link* – MAC addresses, frames, and connecting devices in the same network.  
3. *Network* – IP addresses, routing between networks.  
4. *Transport* – TCP/UDP, ensures data is delivered correctly.  
5. *Session* – Manages sessions between apps (e.g., login sessions).  
6. *Presentation* – Encrypts/decrypts and formats data.  
7. *Application* – Apps we use like WhatsApp, YouTube, Browsers.

## TCP/IP Model (4 Layers)
1. *Network Interface* – Physical + Data Link  
2. *Internet* – Network layer (IP addressing & routing)  
3. *Transport* – TCP/UDP  
4. *Application* – Apps like WhatsApp, YouTube, Browsers

*Mapping real-world examples:*
  - WhatsApp → Application Layer
  - YouTube → Application Layer
  - Browsers → Application Layer
  - Ethernet cables → Physical Layer
  - Routers → Network Layer

## Hands-On
1. *List apps and map to OSI layers* (see above).
2. *TryHackMe:* Completed module of “Pre-Security → Networking Fundamentals”.
3. *Packet Tracer:*
   1. Dragged 2 PCs and a Switch.
   2. Connected them using a straight-through cable.
   3. Assigned IP addresses:
       - PC0: 192.168.1.2 /24
       - PC1: 192.168.1.3 /24
   4. Tested connectivity using ping:
       - PC0 → PC1: Success ✅
       - PC1 → PC0: Success ✅

## Key Takeaways
- Data travels through layers from Application → Physical.  
- Each layer has a specific role in networking.  
- IP addresses act like “house addresses” for devices.  
- Hands-on practice helped me understand networking concepts better.

