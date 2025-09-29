# OSI Model: Data Encapsulation & Decapsulation

This mini project demonstrates how *data moves down and up the OSI model layers* through the processes of *encapsulation* and *decapsulation*, ensuring reliable data transfer between devices in a network.


## 📌 Overview

- *Encapsulation:* The process of wrapping data with necessary protocol information as it moves *down* the OSI layers at the sender's side.
- *Decapsulation:* The process of unwrapping data as it moves *up* the OSI layers at the receiver's side to retrieve the original information.

*Protocol Data Units (PDUs):*

- *Application Data → Segment → Packet → Frame → Bits*


## 🛠 Encapsulation: Data Moving Down the OSI Layers

1. *Application Layer (Layer 7)*  
   - Creates the original data (e.g., HTTP request, FTP transfer).  
   - PDU: *Data*

2. *Presentation Layer (Layer 6)*  
   - Formats, compresses, or encrypts data.  
   - PDU: *Data*

3. *Session Layer (Layer 5)*  
   - Manages sessions and adds session control information.  
   - PDU: *Data*

4. *Transport Layer (Layer 4)*  
   - Breaks data into *segments*, adds headers with source/destination port, sequence numbers, and error checking.  
   - PDU: *Segment*

5. *Network Layer (Layer 3)*  
   - Adds *IP addresses* and routing information to form *packets*.  
   - PDU: *Packet*

6. *Data Link Layer (Layer 2)*  
   - Adds *MAC addresses* and error detection, forming *frames* with headers and trailers.  
   - PDU: *Frame*

7. *Physical Layer (Layer 1)*  
   - Converts frames into a *bitstream* for transmission over the physical medium (cable, Wi-Fi, etc.).  
   - PDU: *Bits*

> Each layer adds its own header (and sometimes trailer) during encapsulation, preparing data for delivery over the network.


## 🔄 Decapsulation: Data Moving Up the OSI Layers

1. *Physical Layer (Layer 1)*  
   - Receives bitstream and converts it into frames.  

2. *Data Link Layer (Layer 2)*  
   - Checks frame integrity, removes headers/trailers, passes payload upward.  

3. *Network Layer (Layer 3)*  
   - Reads packet information, removes network headers, forwards to transport layer.  

4. *Transport Layer (Layer 4)*  
   - Reassembles segments, verifies integrity, removes transport headers.  

5. *Session Layer (Layer 5), Presentation Layer (Layer 6), Application Layer (Layer 7)*  
   - Sequentially remove session/formatting/encryption headers.  
   - Finally, deliver the *original application data* to the intended application.

> This “unwrapping” restores the original data step by step.


## 📊 OSI Layer PDUs & Header/Trailer Information

| Layer          | PDU Name | What’s Added (Encapsulation)       | What’s Removed (Decapsulation)     |
|----------------|----------|-----------------------------------|-----------------------------------|
| Application    | Data     | App-specific info (HTTP, FTP…)    | App info                          |
| Presentation   | Data     | Formatting, encryption, compression | Decodes, decrypts                |
| Session        | Data     | Session headers                   | Session control                   |
| Transport      | Segment  | Ports, sequence, error checks     | Ports, sequence, error checks     |
| Network        | Packet   | IP addresses, routing info        | Network headers                   |
| Data Link      | Frame    | MAC addresses, error detection    | MAC headers, trailers             |
| Physical       | Bits     | Converts to bitstream             | Converts bits to usable data      |


## ✅ Conclusion

Encapsulation and decapsulation ensure that data is reliably sent and correctly interpreted at the receiving end. Each OSI layer only handles its own headers/trailers, making the process *modular, standardized, and error-resistant*.
