## Communication methods
Data can be transmitted in **serial** or **parallel**. In serial communication, bits are sent sequentially one after another, whereas in parallel communication, multiple bits are sent at once. Considerations of both methods include:
- Parallel does not work well over long distances, as there can be interference (crosstalk) between wires.
- Serial can transmit at higher baud rate than parallel because parallel has issues with synchronisation (skew)

Data can be transmitted synchronously or asynchronously. In **synchronous** transmission, two devices are synced by a regular clock signal. In **asynchronous** transmission, there is no dedicated clock signal, instead synchronisation is achieved during transmission by using start and stop bits. A parity bit may also be sent.

## Communication definitions
**Baud rate** is the number of signal changes per second.
**Bit rate** is the number of bits transmitted per second, and is proportional to bandwidth. The bit rate can be higher than the baud rate if more than one bit is transmitted per signal change.
**Bandwidth** is the amount of data that can be transmitted over a medium in a fixed amount of time. Bandwidth differs from bit rate in that bandwidth is the maximum capacity of the communication channel.
**Latency** is the time delay when waiting for a response to an instruction, or the time between an action and its first effects.

A **protocol** is a set of rules that allows computers to communicate with peripherals or other computers. A protocol covers:
- The format data is transmitted in (packet / frame size)
- The speed of communication (baud rate / bit rate)
- Voltages used
- Format of error detection (e.g. parity bits, checksums)
- How devices are identified
- How data is encrypted

## Networks
#### Topologies
In a **star** topology, each device on the network is connected to a central switch. Star topology networks are fast and secure as messages are only forwarded to their intended recipients. A cable failing will only affect the device connected.

In a **bus** topology, each device on the network is connected to a shared backbone, which has terminators at either end. Bus topology networks are slower and less secure as any message sent will reach all connected devices, making collisions possible when two devices try to transmit at the same time.

A physical star topology can behave as a **logical bus network**, by using a bus protocol and switching. Switches direct traffic but can only transmit to one device at a time. Switches receive and buffer data from multiple nodes and transmit in turn.

#### Network types
In a **peer-to-peer** network, each computer has equal status. Every computer can share resources such as files or hardware. This is more suitable for smaller networks. In a **client-server network**, most computers are nominated as clients and one or more as servers. The clients request services from the servers, which provide these services, for example a file server or email server.

In a **local area network** (LAN), nodes are connected over a small geographical distance (e.g. a single building or site). The infrastructure is owned and operated by a single individual or organisation. In a **wide area network** (WAN), nodes are spread over a wide geographical area, typically including LANs in separate sites. WANs are operated by large organisations or consortiums.

#### Wireless networks
**Wi-Fi** is a protocol for wireless local area networks (WLANs) based on international standards, enabling devices to connect to a network wirelessly. Data is sent using radio waves. WLANs use protocols such as Wi-Fi, while wireless wide area networks (WWAN) use protocols such as 4G and 5G.

To operate a WLAN, wireless access points and wireless network adaptors are needed. A **wireless access point (WAP)** allows devices to connect wirelessly to a wired network, bridging between the two by translating Wi-Fi frames to Ethernet frames. Each device has a wireless NIC with a unique MAC address.

Each WAP has a **Basic Service Set ID (BSSID)**, which is like a MAC address. A **Service Set ID (SSID)** is a human-readable name for the network, which is shared across all WAPs on the network. The BSSID is used by wireless NICs to ensure data goes to the correct WAP.

Wireless networks are secured through several methods:
- **WPA (Wireless Protected Access)** or WPA2 - provide encryption for data transmitted over wireless network to prevent interception.
- **SSID (Service Set Identifier) broadcast disabling** - the WAP can avoid broadcasting the existence of the SSID
- **MAC (Media Access Control) allowlists** - only devices with MAC addresses on the allowlist are permitted to connect to the network

Carrier Sense Multiple Access with Collision Avoidance **(CSMA/CA)** is a protocol for avoiding collisions. **CSMA** means devices will check if other devices are transmitting before transmitting. **CA** means devices will not send if another device is transmitting and will wait for a random period of time before sending.

In the Request to Send / Clear to Send **(RTS/CTS)** protocol, a device sends a Request to Send. The WAP then responds with a Clear to Send, the data is sent, and the WAP sends an ACK (acknowledgement) that the data was received. If the device does not receive an ACK, it reattempts transmission.

## The Internet
The **Internet** is a global WAN, connecting between many LANs. The **World Wide Web** is a service provided on the Internet. Packet switching is the idea that Internet transmissions are split into packets, which each take an independent route through the network, and are reassembled at the destination.

Packets have:
- Source and destination port
- Source and destination IP address
- A sequence number
- Checksum / error detection
- Data

**Routers** are devices that forward packets through the network to reach their destination, using routing tables.
**Gateways** connect between WANs and LANs using different protocols.

A **URL (Uniform Resource Locator)** identifies a resource on the Internet.
- The **fully qualified domain name** (FQDN) identifies a specific host (a server), with a hostname (e.g. `www`), domain name (`google`) and top-level domain (`.com`), for example in `www.google.com`
- A **domain name** identifies an organisation on the Internet, for example `google.com`. ICANN manages top level domains such as `.com` and `.edu`, and gives various Internet registrars accreditations to issue domain names. Registries ensure domain names are unique.

#### IP addresses
An **IP address** identifies a host on the Internet. IPv4 addresses have 32 bits e.g. `192.168.1.1`, while IPv6 addresses have 128 bits. IPv6 was introduced because the limited number of IPv4 addresses (around 4 billion) meant they were exhausted.

Because IP addresses make little sense to humans, domain names are used instead. Each fully qualified domain name (FQDN) maps to an IP address. The **Domain Name System (DNS)** converts a FQDN to an IP address. A DNS resolver first queries a root nameserver to find the IP for the TLD nameserver, which it then queries to find the IP for the FQDN.

Routable addresses are public and globally unique, whereas non-routable addresses are used in private LANs. **Dynamic Host Configuration Protocol (DHCP)** assigns temporary IP addresses to devices on the LAN for a limited amount of time.

An IP address can be split into a network ID and host ID. Networks can be divided into **subnets**, and the network ID defines the subnet. **Subnet masking** is a technique to identify the subnet of an IP, for example, if 20 bits identify the network ID, the subnet mask is `192.168.240.0`. The subnet mask is then bitwise ANDed with the IP to get the network ID.

**Network address translation (NAT)** is where a router generates a temporary port number that maps to a socket in the LAN. The router replaces outgoing packets' source IP address to be its own public IP, and the source port to the new temporary port. The temporary ports are kept track of in a table. Incoming packets to ports in the table are forwarded to the correct LAN IP and port.

**Port forwarding** is where specific router ports are opened up, and traffic to these router ports are redirected to specific sockets within the LAN. The sockets within the LAN must have static IP addresses to ensure packets are forwarded to the receiving host.

#### Internet security
###### Firewalls
A firewall protects networks from unauthorised external access from outside the LAN, protecting against malware and harmful content. Firewalls can work by:
- **Packet filtering** (static filtering) - the simplest type of firewall where each packet is analysed for unauthorised data. IP addresses, protocols, and port numbers are checked according to a lookup table to identify if the packet should be passed on to the LAN.
- **Stateful inspection** (dynamic filtering) - the firewall keeps track of open communication channels, using a table of active connections. The firewall checks if a packet forms part of an existing series of packets.
- **Proxy server** - all traffic is routed through the proxy server. This hides the client IP address. Requests passed through the proxy are examined and filters can be used to allow or block certain websites.
###### Encryption
Encryption is the process of applying an algorithm (cipher) to a plaintext to transform it to a ciphertext, such that it cannot be understood by anyone without the key. **Asymmetric** (public / private key) encryption means the private key does not need to be exchanged. The sender encrypts their message with the recipient's public key, and the recipient then uses their private key to decrypt the message.
###### Digital signatures
A **digital signature** verifies the sender of a message and also verifies the message has not been tampered with. To create a digital signature:
- The message is hashed to create a digest
- The digest is encrypted with the sender's private key to make the digital signature.
- The digital signature is appended to the message.
- The message and signature are encrypted with the recipient's public key.
- The recipient decrypts the message with their private key.
- The recipient decrypts the encrypted digest (the digital signature) using the sender's public key.
- The recipient computes the digest on the received message and compares it against the decrypted digest.
###### Digital certificates
A **digital certificate** verifies the identity of a remote host. They are issued by a certificate authority and are important for asymmetric encryption for SSL or TLS. Certificates contain a serial number, the key owner, an expiry date, the public key, and the certificate authority's digital signature. Digital certificates prevent man-in-the-middle attacks.

###### Worms, viruses, and trojans
A **worm** is a piece of malware that can infect a computer without any explicit user interaction by exploiting vulnerabilities in software. Worms can self-replicate and spread across a network.

A **trojan** is a piece of malware that is disguised as legitimate software. Trojans cannot self-replicate; they rely on users downloading and running them.

A **virus** is a piece of malware that requires some form of user interaction to run and infect the user's computer.

Worms, trojans, and viruses can be addressed through **improved code quality** (to remove vulnerabilities which malware can exploit) and **monitoring and protection** (such as antivirus software).

#### Transmission Control Protocol / Internet Protocol (TCP / IP)
At the **application layer**, protocols such as HTTPS are used. Here, packets of informations are messages, for example a HTTPS GET message.

At the **transport layer**, TCP breaks long messages into TCP segments. TCP establishes a connection between two endpoints. The two endpoints are known as sockets, and a **socket** is uniquely defined by an IP address and a **port** number. The port number is usually associated with a protocol, as the port number is used to ensure the correct process on the host receives incoming data.

**Well-known ports** are in the range 0 - 1023, and are assigned to specific services, e.g. FTP uses port 21, HTTP uses port 80, and HTTPS uses port 443. **Client ports** are allocated temporarily when a client application creates a connection socket Well-known ports are assigned by IANA, whilst client ports are not.

TCP tries to ensure segments are delivered by:
- Monitoring the connection for errors and retransmitting segments
- Detecting when the connection is broken

At the **Internet layer**, IP moves datagrams through the network, through intermediate routers to their destination. IP does not guarantee delivery; the reliability of the connection is handled by the transport layer. Together, TCP and IP hide the differences in underlying networks as a packet passes from source to destination host.

At the **link layer**, data is physically moved through the network. The link layer handles the physical details of communicating over a network cable or wireless connection. Source and destination hardware addresses (e.g. MAC addresses) are added at the link layer.

MAC addresses are unique 48-bit addresses that identify a network adapter / NIC so the packet's destination hardware address can be matched to a particular host.

#### Application layer protocols
Application layer protocols include:
- **HTTP** (Hypertext Transfer Protocol) - a client sends a request, and the server replies with a response
- **HTTPS** (Hypertext Transfer Protocol Secure) - HTTPS, but with secure socket layer (SSL) that encrypts requests and responses
- **SMTP** (Simple Mail Transfer Protocol) - used by email clients to send emails to an email server
- **POP3** (Post Office Protocol v3) - used to download emails from remote servers
- **SSH** (Secure Shell) - used to make a TCP connection to a remote port that allows application layer protocol commands to be sent. SSH can be used to log in securely to a remote computer and execute operations.

## Client-server model
In the **client-server model**, a client sends a request to a server, which then replies with a response message to the client. The **websocket protocol** defines an API (application programming interface) that establishes a full duplex (bidirectional) connection between a web browser and server over TCP. This provides a persistent connection such that either party can send data at any time.

**CRUD** is an acronym for 'Create, Retrieve, Update, Delete'. **REST (representational state transfer)** enables CRUD operations to be mapped to SQL functions (POST: INSERT, GET: SELECT, PUT: UPDATE, DELETE: DELETE).

A browser connects to a database using REST, which relies on HTTP request methods (POST, GET, PUT, DELETE). REST allows JavaScript to talk to server through HTTP. A REST API (Application Programming Interface) created and run on server, browser Javascript calls API. 

**JSON** (JavaScript Object Notation) or **XML** can be used to transmit data between a server and web application. Javascript referenced by HTML file, eg index.html, is run in browser. Compared to XML, JSON is:
- Easier for humans to read
- More compact
- Easier to create
- Easier / quicker for humans to parse

##### Thin and thick clients
A **thin client** is a workstation with little RAM and a low-spec CPU, whereas a **thick client** has more RAM and CPU compute to run applications locally. Thin clients are used to connect to a central server, which stores all the files and runs all applications.

Benefits of thin clients include:
- Centralised management and security
- Reduced cost
- Reduced power consumption
