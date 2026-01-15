# Day 1 - Networking Fundamentals

**Date:** 15th January 2026  
**Topic:** Introduction to Networking & TCP/IP Model  


---



### Basic Network Devices

**Client vs Server**
- **Client**: A device that accesses a service made available by a server
- **Server**: A device that provides services to clients
- Example: Your laptop (client) accessing a website (server)

**Switches**
- Have MANY network interfaces (usually 24+) for end hosts to connect
- Provide connectivity to hosts WITHIN the same LAN
- DO NOT provide connectivity over the internet
- Think of them as: "Connecting devices in the SAME neighborhood"

**Routers**
- Have FEWER network interfaces than switches
- Provide connectivity BETWEEN LANs
- Send data over the internet
- Think of them as: "Connecting different neighborhoods together"

**Firewalls**
- Control network traffic entering and exiting your network
- Can be placed outside your router to protect endpoints
- **Next-gen firewalls**: Include modern and advanced filtering capabilities
- **Host-based firewall**: Software that filters traffic on the end device itself

---

## 📊 Data Transmission Basics

### Bits and Bytes
- **Bit**: The smallest unit - represented by 0 or 1
- **Byte**: 8 bits = 1 byte
- **Important**: Network speed is measured in BITS per second (not bytes!)
- Information is received ONE BIT at a time, not a full byte

### Network Speeds
- 1 Kilobit (Kb) = 1,000 bits
- 1 Megabit (Mb) = 1,000,000 bits
- 1 Gigabit (Gb) = 1,000,000,000 bits

---

## 🔌 Network Cables: UTP vs Fiber Optic

| Feature | UTP (Copper) | Fiber Optic |
|---------|--------------|-------------|
| **Cost** | Cheaper | More expensive |
| **Distance** | Shorter maximum | Longer maximum |
| **EMI** | Vulnerable to interference | No vulnerability |
| **Security** | Leaks faint signal | Does not leak data |

**My takeaway**: Fiber is better but expensive. UTP is good for most office networks.

---

## 🌐 TCP/IP Model - The Foundation

### History (Cool Facts!)
- Started in the 1960s with ARPANET (US Department of Defense project)
- Vint Cerf and Bob Kahn created TCP in 1974
- TCP later split into TCP and IP
- Became the official standard on **January 1, 1983**
- Won over other competing protocols because it was OPEN and could run on different types of networks

### Standards Organizations
- **IEEE** (Institute of Electrical and Electronics Engineers)
  - Develops local network technologies
  - Examples: Ethernet (802.3), Wi-Fi (802.11)
  
- **IETF** (Internet Engineering Task Force)
  - Defines internet protocols
  - Examples: TCP, IP, UDP, HTTP, DNS
  - Publishes standards in RFCs (Requests for Comments)

---

## 📚 The 5 Layers of TCP/IP Model

![TCP/IP 5 Layers](day-01/images/tcp-ip model.png)

**Layer 5 - Application**
- Protocols for communication between application processes
- Creates and interprets the data
- Examples: HTTP, FTP, DNS

**Layer 4 - Transport**
- Provides end-to-end communication between application processes
- Uses **PORT NUMBERS** to identify applications
- Examples: TCP, UDP

**Layer 3 - Internet**
- Provides end-to-end communication between hosts across networks
- Uses **IP ADDRESSES** and routers
- Example: IP protocol

**Layer 2 - Local Network (Data Link)**
- Provides hop-to-hop delivery within a local network
- Uses **MAC ADDRESSES** and switches
- Example: Ethernet

**Layer 1 - Physical**
- Sends bits as electrical, optical, or radio signals over physical medium
- Example: Cables, fiber optics, radio waves

---

## 🔄 How Data Moves: Encapsulation & Decapsulation

**[SUGGEST IMAGE HERE: Encapsulation/Decapsulation diagram from PDF page 4-5]**

### Encapsulation (Sending Data)
When PC1 sends data to SRV1:

1. **Application layer**: Creates the data
2. **Transport layer**: Adds Layer 4 header → Creates a **SEGMENT** (TCP) or **DATAGRAM** (UDP)
3. **Internet layer**: Adds Layer 3 header → Creates a **PACKET**
4. **Local Network layer**: Adds Layer 2 header and trailer → Creates a **FRAME**
5. **Physical layer**: Transmits bits over the wire

### Decapsulation (Receiving Data)
When SRV1 receives data:

1. **Physical layer**: Receives bits
2. **Local Network layer**: Removes L2 header/trailer
3. **Internet layer**: Removes L3 header
4. **Transport layer**: Removes L4 header
5. **Application layer**: Delivers data to the application

### PDU Names (Protocol Data Units)
- **Layer 4**: Segment (TCP) or Datagram (UDP)
- **Layer 3**: Packet
- **Layer 2**: Frame
- **Layer 1**: Bits

**My aha moment**: Each layer adds its own "envelope" to the data, like wrapping a present multiple times!

---

## 🔗 How Layers Interact

**Adjacent-Layer Interaction**
- Each layer provides a SERVICE to the layer above it
- Layer 4 serves Layer 5 by delivering data to correct application (using port numbers)
- Layer 3 serves Layer 4 by delivering to correct destination host (using IP addresses)
- Layer 2 serves Layer 3 by delivering to next hop (using MAC addresses)
- Layer 1 serves Layer 2 by sending frames as signals

**Same-Layer Interaction**
- Each layer communicates with the SAME layer on other devices
- Application on PC1 talks to Application on SRV1
- TCP on PC1 talks to TCP on SRV1
- IP on PC1 talks to IP on Router talks to IP on SRV1

**[SUGGEST IMAGE HERE: Layer interaction diagrams from PDF page 6-7]**

---

## 📖 TCP/IP vs OSI Model

**Quick Comparison:**
- **TCP/IP**: 5 layers (what we actually use)
- **OSI**: 7 layers (theoretical reference model)
- OSI layers 5, 6, 7 = TCP/IP Application layer
- TCP/IP "won" because it was simpler and already deployed

TCP/IP Application layer is often called "Layer 7" (borrowing from OSI terminology)

---

## 💡 Key Takeaways

1. ✅ **Switches** connect devices in the SAME network (use MAC addresses)
2. ✅ **Routers** connect DIFFERENT networks (use IP addresses)
3. ✅ Data gets "wrapped" in headers at each layer (encapsulation)
4. ✅ The 5 layers work together - each serving the one above it
5. ✅ Network speed is measured in BITS per second, not bytes
6. ✅ TCP/IP model is what we actually use in real networks




