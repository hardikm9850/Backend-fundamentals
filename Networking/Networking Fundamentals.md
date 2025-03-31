# Networking Basics for Backend Development

## 1️⃣ Network Layers (OSI & TCP/IP Models)
Understanding how data flows through different layers helps you debug, optimize, and secure communication.

###   OSI Model (7 Layers)
1. **Physical** – Cables, Wi-Fi, signals  
2. **Data Link** – MAC addresses, switches  
3. **Network** – IP addressing, routers  
4. **Transport** – TCP/UDP, ports  
5. **Session** – Maintaining sessions  
6. **Presentation** – Encryption, compression  
7. **Application** – HTTP, FTP, DNS  

###   TCP/IP Model (Simplified OSI)
1. **Network Interface (Physical + Data Link)**
2. **Internet (Network)**
3. **Transport (Transport)**
4. **Application (Session + Presentation + Application)**

## 2️⃣ TCP vs UDP
###   TCP (Transmission Control Protocol)
- Reliable, connection-oriented (Three-way handshake)
- Ensures packet order and retransmits lost data
- Used in **HTTP, HTTPS, FTP, SSH**

###   UDP (User Datagram Protocol)
- Faster, connectionless (No handshake)
- No guarantee of order or delivery
- Used in **DNS, VoIP, gaming, streaming**

## 3️⃣ How Packets Travel (Encapsulation & Routing)
###   Encapsulation (Adding Headers)
- **Application Layer** → Adds HTTP headers  
- **Transport Layer** → Adds TCP/UDP headers  
- **Network Layer** → Adds IP headers  
- **Data Link Layer** → Adds MAC headers  

###   Routing (How Packets Move)
1. **Your device sends data** → Goes to the router  
2. **Router forwards packet** → Chooses best path via **BGP (Border Gateway Protocol)**  
3. **ISP handles traffic** → Routes packet globally  
4. **Destination server receives it**  
5. **Response travels back the same way**

## 4️⃣ Important Network Protocols
###   Application Layer Protocols
- **HTTP/HTTPS** – Web communication  
- **FTP/SFTP** – File transfers  
- **SMTP/IMAP/POP3** – Email  
- **DNS** – Resolves domain names  

###   Transport Layer Protocols
- **TCP** – Reliable communication  
- **UDP** – Faster, but no guarantee  

###   Network Layer Protocols
- **IP (IPv4 & IPv6)** – Addressing  
- **ICMP** – Ping, traceroute  

###   Data Link Layer Protocols
- **Ethernet (Wired) / Wi-Fi (Wireless)**  
- **ARP (Address Resolution Protocol)** – Maps IP to MAC  

## 5️⃣ Security Considerations
###   Encryption & Authentication
- **SSL/TLS (HTTPS)** – Encrypts HTTP  
- **SSH** – Secure remote access  
- **OAuth, JWT** – Secure API authentication  

###   Firewalls & NAT
- **Firewalls** filter incoming/outgoing traffic  
- **NAT (Network Address Translation)** allows multiple devices to share one public IP  

###   Attack Prevention
- **DDoS Protection** – Mitigating traffic floods  
- **MITM (Man-in-the-Middle) Attacks** – Prevented with HTTPS  
- **SQL Injection, XSS** – Secure web applications  

## 6️⃣ Debugging & Tools
###   Network Monitoring Tools
- `ping` – Check server reachability  
- `traceroute` / `mtr` – Trace packet paths  
- `netstat` / `ss` – Check open ports  
- `nslookup` / `dig` – Query DNS  
- `Wireshark` – Inspect packets  
- `tcpdump` – Capture network traffic  

## 7️⃣ Cloud & Load Balancing
###   Load Balancers
- **Round-robin, Least connections** – Distribute traffic  
- **Reverse Proxy (Nginx, HAProxy)** – Secures & manages requests  

###   Caching
- **CDNs (Cloudflare, Akamai)** – Cache static content  
- **Redis, Memcached** – Cache database queries  

## 🎯 Summary
✅ **Networking Basics** – OSI Model, TCP/IP, Ports  
✅ **Protocols** – TCP, UDP, HTTP, DNS, SSL  
✅ **Encapsulation & Packet Routing** – How data moves  
✅ **Security** – SSL/TLS, firewalls, attacks prevention  
✅ **Debugging** – Ping, Traceroute, Wireshark, DNS tools  
✅ **Cloud & Scalability** – Load balancers, caching  

