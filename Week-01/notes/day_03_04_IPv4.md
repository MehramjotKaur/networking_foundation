# Day 3–4: IPv4 Basics

## IP / Logical Addressing

**Definition:**  
A logical address is a unique, software-configured address assigned to a device on a network. It operates at the **Network Layer (Layer 3)** of the OSI model.

**Purpose:**  
- Identifies devices globally across networks.
- Enables end-to-end communication.

**Contrast with Physical (MAC) Address:**

| Feature           | Physical (MAC)                 | Logical (IP)                        |
|------------------|-------------------------------|------------------------------------|
| Layer             | Data Link Layer (Layer 2)     | Network Layer (Layer 3)            |
| Configuration     | Hard-coded by manufacturer    | Configurable by software           |
| Scope             | Local network segment only    | Global across networks             |
| Format            | 48-bit hexadecimal           | 32-bit binary (IPv4)               |

## IPv4 Structure

- **Size:** 32 bits (4 octets)  
- **Representation:** 4 decimal numbers separated by dots (Dotted-Decimal)  
- **Example:** `11000000.10101000.00000001.00000001` → `192.168.1.1`  
- **Total Addresses:** 2³² ≈ 4.3 billion  

**Notations:**  
- Dotted-Decimal: `192.168.1.1`  
- Binary: `11000000.10101000.00000001.00000001`  
- Hexadecimal: `C0 A8 01 01`  

**Reserved Addresses:**  
- **Network Address:** First address of subnet (e.g., `192.168.1.0`)  
- **Broadcast Address:** Last address of subnet (e.g., `192.168.1.255`)  
- **Loopback:** `127.0.0.1`  
- **APIPA:** `169.254.0.0/16` (auto-assigned if DHCP fails)

## Dynamic vs Static IP Addressing

| Feature       | Static IP                               | Dynamic IP (DHCP)                   |
|---------------|----------------------------------------|------------------------------------|
| Configuration | Manual                                  | Automatic                          |
| Pros          | Permanent, reliable for servers        | Easy management, plug-and-play     |
| Cons          | Administrative overhead                | IP can change, not suitable for servers |

## IP Address Types

- **Public IP:** Globally unique, routable on the Internet. Assigned by ISP.  
- **Private IP:** Local network only, not routable on Internet.  
  - Class A: `10.0.0.0 – 10.255.255.255`  
  - Class B: `172.16.0.0 – 172.31.255.255`  
  - Class C: `192.168.0.0 – 192.168.255.255`  
- **Reserved IP:** Loopback, APIPA, Network, Broadcast

## Unicast, Broadcast, and Multicast

- **Unicast:** One-to-One communication (e.g., PC → Web Server)  
- **Broadcast:** One-to-All communication in subnet (e.g., ARP request)  
- **Multicast:** One-to-Many (group) communication, IP range `224.0.0.0 – 239.255.255.255` (e.g., video conferencing)

## Classful Addressing & IP Classes

**Note:** Obsolete, replaced by CIDR.  

| Class | First Bits | First Octet Range | Default Mask    | Use Case                     |
|-------|-----------|-----------------|----------------|------------------------------|
| A     | 0         | 1 – 126         | 255.0.0.0      | Few massive networks         |
| B     | 10        | 128 – 191       | 255.255.0.0    | Medium-sized organizations   |
| C     | 110       | 192 – 223       | 255.255.255.0  | Small networks (LANs)        |
| D     | 1110      | 224 – 239       | N/A            | Multicast                    |
| E     | 1111      | 240 – 255       | N/A            | Reserved/Experimental        |

## Subnetting & Subnet Mask

- **Subnet Mask:** 32-bit number, 1 = network, 0 = host.  
- **Example:** IP `192.168.1.10` with Mask `255.255.255.0` (`/24`)  
  - Network: `192.168.1.0`  
  - Host: `10`  

**Subnetting Benefits:**  
- Reduces broadcast domains  
- Improves security & performance  
- Efficient IP usage  

**VLSM (Variable Length Subnet Mask):** Flexible subnetting for different sizes  

**P2P Connection Example:**  
- `/30` subnet → 2 usable hosts for router-to-router links  

**Subnet Calculations Example:**  
- Subnet `192.168.1.128/25`  
  - Block Size = 2^(32-25) = 128  
  - Usable Hosts = 128 – 2 = 126  
  - Network = `192.168.1.128`, Broadcast = `192.168.1.255`  
  - Usable IP Range = `192.168.1.129 – 192.168.1.254`

