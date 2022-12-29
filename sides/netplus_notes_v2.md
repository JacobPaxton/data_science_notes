# My Questions
- IPsec, GRE, PPP, L2TP, ...
- Transport mode v tunnel mode
- Layer review

# Hard to Place
- ARP: Address Resolution Protocol, MAC<->IP information
    * ARP request is a *broadcast* asking for MAC of known IP address; destination MAC is `ff:ff:ff:ff:ff:ff`
    * ARP reply contains the requested MAC address
- Packet switching: sending a transmission's packets over various paths for speed reasons
    * This is opposite of leased lines; packet switching shares a network with others
- Circuit-switched connection: connection as-needed, like a phone call
- Cyclic Redundancy Check (CRC): basically hash matching
- RRAS: routing + remote access service, a Windows Server service for remote stuff
- PDU: Protocol Data Unit, name given to the data structure at different layers
    * Layer 1: bit... Layer 2: frame... Layer 3: packet... Layer 4: segment
- Link Aggregation: multiple physical connections bonded into one logical connection
- SNMP: monitor/manage network devices like routers, switches, servers
- Zeroconf: automagically creating a network from a connection
    * Assigns link-local IP addresses, resolves computer names to IP addresses, and locates network services
- TCP (connection), UDP (connectionless)
- Stateful Firewall: watches outgoing sessions and allows incoming traffic for those sessions; "watching" is called stateful inspection
- Elasticity is a real-time thing; Scalability is NOT real-time
- PaaS includes SQL database
- Transparent proxy (inline) and non-transparent proxy (IP address and port 8080)
# MOAR
The Common Address Redundancy Protocol (CARP) enables multiple hosts to share an IP address on the same network segment so that they can act as a default gateway.
The open standard protocol Virtual Router Redundancy Protocol (VRRP) allows the automatic assignment of IP routers to act as a default gateway on a single subnet.
The Hot Standby Router Protocol (HSRP) allows multiple physical routers to serve as a single default gateway for a subnet, but it is a proprietary protocol developed by Cisco.
The Link Aggregation Control Protocol (LACP) detects configuration errors and recovers from the failure of one of the physical links.

# Troubleshooting
- APIPA: 169.254.x.x/16
- Bit-error rate tester (BERT): use bit-pattern generator + error detector to detect BER (bit-error rate)
- Butt set: check for dial tone / call ability on EX: 66 block or 110 block
- Cable certifier: determine cable category / freq range (data throughput)
- Cable tester: check for opens/breaks in ethernet cable "conductors", OR check "pinouts" in RJ-45, comes in two pieces (each piece connects to one end of cable)

# Useful Commands
## Both
- `ping`
- `arp`: show ARP table
- `host`: resolve a host's FQDN to IP
- `netstat`: active connections
- `nmap`: port discovery (vulnerability scanning)
- `nslookup`: FQDN to IP
- `route`: view/change routes in routing table
## Windows
- `ipconfig`
- `nbtstat`: NetBIOS name resolution
- `tracert`: hop info for a destination
## Linux
- `dig`: resolve FQDN to IP
- `traceroute`: hop info for a destination
- `iptables`: edit the rules enforced by the Linux kernel firewall; change INPUT, OUTPUT and FORWARD chains (firewall rulesets)

- public key infrastructure (PKI):
    * A PKI system uses digital certificates and a certificate authority to allow secure communication across a public network.

- Network Address Translation (NAT):
    * Allows private IP addresses (as defined in RFC 1918) to be translated into Internet-routable IP addresses (public IP addresses).
- Static NAT (SNAT):
    * A variant of NAT in which an inside local IP address is statically mapped to an inside global IP address. SNAT is useful for servers inside a network that need to be accessible from an outside network.
- Port Address Translation (PAT):
    * A variant of NAT in which multiple inside local IP addresses share a single inside global IP address. PAT can distinguish between different flows based on port numbers.

# 802.11
- TDM (Time-Division Multiplexing): sessions take turns
- OFDM (Orthogonal Frequency-Division Multiplexing): slow modulation but 52 data streams (still fast), resistant to crosstalk
- DSSS (Direct-sequence spread spectrum): modulate data over freqs, uses "chips" (faster than bits), contains decoy info (chips decode), uses entire freq
- FHSS (Frequency-Hopping spread spectrum): freq hopping
- 802.11 standards:
    * 802.11a: 1999, 5.0GHz, 54Mbps, OFDM transmission method
    * 802.11b: 1999, 2.4GHz, 11Mbps, DSSS transmission method
    * 802.11g: 2003, 2.4GHz, 54Mbps, either OFDM or DSSS transmission method
    * 802.11n: 2009, both, 130-150Mbps (channel bonding: 300 Mbps), OFDM transmission method
    * 802.11ac: 5GHz range, with increased throughput
- BSS v ESS: BSS has one AP (SOHO), ESS has more than one AP (Enterprise)
    * Both are LAN technologies, both run in infrastructore mode (wireless connection to wired *infrastructure*)
    * ESS needs to be careful about channel overlap
- IBSS (Independent Basic Service Set): peer-to-peer WLAN

# AAA
- Authenticator: (802.1X) forwards supplicant's authentication request to authentication server
    * After supplicant is authenticated, the authenticator receives the key for the supplicant's secure session
- Authentication server: (802.1X) checks supplicant's credentials, notifies authenticator of approval and sends a key
- Personal mode: using a pre-shared key (PSK) instead of a centralized server
- Enterprise mode: using ex: RADIUS for centralized authentication (not PSKs)
## AAA Examples
- RADIUS: UDP-based protocol used to communicate with a AAA server. 
    * Unlike TACACS+, RADIUS does not encrypt an entire authentication packet, but only the password
    * However, RADIUS offers more robust accounting features than TACACS+
    * Also, RADIUS is a standards-based protocol, whereas TACACS+ is a Cisco proprietary protocol
- TACACS+: TCP-based protocol used to communicate with a AAA server. 
    * Unlike RADIUS, TACACS+ encrypts an entire authentication packet rather than just the password. 
    * TACACS + offers authentication features, but they are not as robust as the accounting features found in RADIUS. 
    * Also, unlike RADIUS, TACACS+ is a Cisco-proprietary protocol.
- PAP (Password Authentication Protocol): one-way authentication, USES CLEARTEXT
- Kerberos: Mutual authentication, Uses trusted third party (a key distribution center) that hands out tickets to be used (no username/pass)
- CHAP (Challenge Handshake Authentication Protocol): server-authenticates-client (one-way, like PAP) using challenge + response + acceptance (unlike PAP)
    * Microsoft CHAP (MS-CHAP): CHAP plus more features; includes two-way authentication and other features
    * A Microsoft-enhanced version of CHAP, offering a collection of additional features not present with PAP or CHAP, including two-way authentication. 
- CRAM-MD5 (Challenge-Response Authentication Mechanism Message Digest 5): server-authenticates-client (one-way, like CHAP), variant of HMAC for email



# OSI Model
## Layer 1: Physical
- Concerned with the transmission of bits on a network
- Devices: Hubs, Repeaters, Cables, Fibers, Wireless
    * 66 block v 110 block: 
        * 66 block is OLD and SLOW and CROSSTALK-Y and FOR PHONES, UP TO CAT3
        * 110 block is CURRENT and FAST
    * Coaxial cable: two conductors, one is inner insulated conductor, other surrounds inner and is made of a metallic foil or woven wire
        * Twinax: Extremely short (5-10 meters max), can do 10Gbps or 4-cable 40Gbps
    * Digital Subscriber Line (DSL): data over telephone wire; asymmetric DSL, symmetric DSL, very high bit rate DSL
    * SFP: 1Gbps; SX: 500m MM; LX: 10km SM; EX: 40km; ZX: 80km
    * SFP+: 10gbps (QSFP+ is 40Gbps, 4x cables); similar ranges but "SR", "LR", "ER", "ZR"
    * BASE-T -- Cat 5: 100Mbps - Cat 5e: 1Gbps - Cat 6: 10Gbps 55m - Cat 6a: 10Gbps 100m - Cat 7: 10Gbps 100m SHIELDED GG45/TERA - Cat 8: Data centers only
    * Tip and Ring: red and green wires in RJ-11 wall jacks
        * These carry voice, ringing voltage, and signaling information between an analog device (for example, a phone or a modem) and an RJ-11 wall jack
- Concepts: Baseband (single talker) vs Broadband (multiplexing)
    * Baseband Signaling: one talker at a time, one channel, bi-directional
    * Broadband Signaling: multiple talkers at a time and multiple channels (frequency-division multiplexing (FDM)), unidirectional (bi-directional with channels)
    * Current State Modulation: represent a binary 1 or 0 with voltage/light on or off
    * State Transition Modulation: represent a binary 1 or 0 with voltage/light *turning on* or *turning off*
    * SONET: Synchronous Optical Network: fiber optic, high data rates (up to 10Gbps) and long range (10+km), can transport Layer 2 encapsulation types like ATM
- Goal: direct point-to-point data connection
## Layer 2: Data Link
- Concerned with packaging of data into frames, xmit frames, detecting/correcting errors, device identification, and doing flow control
- Devices: Bridges, Modems, Network cards, 2-layer switches
    * Cable modem: send/receive data over coaxial cables (TV cables), uses predetermined freq ranges
    * Content switch: Managed switch with load balancing and higher-layer packet inspection
- Concepts: MAC addresses, CSMA/CD (Ethernet), CSMA/CA (Wireless), Frame Relay, STP, trunking, tagging
    * Multicast: one-to-many communications
        * IGMP: Internet Group Management Protocol, multicast protocol used between clients and routers (router knows which interface(s) have multicast going on)
        * PIM: Protocol Independent Multicast, multicast protocul used between routers to construct a "multicast distribution tree"
    * Collision: two devices transmitting at same time (Ethernet segments can't handle more than one frame at a time); frames are corrupted by this
    * CSMA/CA (Collision Avoidance): WLAN device listens for xmit on wireless channel, if activity, wait for a random backoff time
    * CSMA/CD (Collision Detection): (ONLY ON HALF-DUPLEX) Ethernet device listens on Ethernet segment for frame recover if a collision does occur
    * Bootstrap Protocol (BOOTP):
        * A legacy broadcast-based protocol used by networked devices to obtain IP address information.
    * Frame Relay: packet switching for LANs to connect across WAN
        * Either Permanent Virtual Circuit (PVC) or Switched (temp) Virtual Circuit (SVC)
        * CIR (Committed Information Rate): Minimum bandwidth requirement for a Frame Relay
        * Virtual circuits are used, data-link connection identifiers (DLCI) identify each virtual circuit
    * STP: Spanning Tree Protocol
        * 802.1D, a network can have redundant Layer 2 connections while preventing loops (preventing broadcast storms and MAC address table corruption)
        * Root Port: port closest to root bridge, one on every non-root bridge/switch
        * Designated Port: port closest to root bridge/switch
        * Nondesignated Port: ports that block traffic to prevent loops
    * L2TP: Layer 2 Tunneling Protocol, tunneling but lacks encryption
    * PPTP: Point-to-Point Tunneling Protocol, VPN tunnel, older
        * Generic Routing Encapsulation: Cisco, used with PPTP to create a tunnel over IP network
    * PPP: Point-to-Point Protocol, popular, can do multilink interface, looped link detection, error detection, and authentication.
        * L2F: Layer 2 Forwarding (Cisco), VPN, tunneling for PPP, INSECURE
        * PPPoE: PPP over Ethernet (encapsulates PPP frames in Ethernet frames), commonly used between DSL modem and a service provider
    * Trunking: a single physical or logical connection that simultaneously carries traffic for multiple VLANs
        * If a frame is headed for port on same VLAN and switch, no tag added
        * If a frame is going over trunk link, add the tag to identify the source VLAN then send
        * If a frame is received over *access port*, strip the tag then forward
        * A tagged port can transport traffic addressed to multiple VLANs
            * The tagged port is usually the trunk port
- ATM: Asynchronous Transfer Mode; *layer 2* WAN technology (packet *SWITCHING*), interconnects fixed sites using virtual paths
    * Virtual path (whole) contains many virtual circuits (segments); each virtual circuit is identified by VPI:VCI pair
    * Path vector uses the number of autonomous system hops that must be transited to reach a destination network (not individual hops)
- Goal: reliable data connection
## Layer 3: Network
- Concerned with forwarding data based on logical addresses
- Devices: Routers, Brouters, 3-layer switches
    * Black-hole router: for packets that exceed MTU size of an interface and can't be fragmented, this router drops them (without notifying the sender)
    * Administrative distance (AD): rankings assigned to *routes* based on the router protocol used to discover it
        * EX: Directly connected > Static route > Internal EIGRP > OSPF > RIP > External EIGRP
        * Smaller numbers are more trustworthy and preferred
    * ACL: Access Control List, rules on router interfaces (permit/deny)
        * Layer 2, 3, or 4
    * Anycast: a special unicast that is re-routed to a designated destination, usually the nearest (DNS), but sometimes a load-balancing measure (CDNs)
        * EX1: [123.45.67.89] from Cambodia routes to Cambodian datacenter
        * EX2: [123.45.67.89] from Australia routes to Australian datacenter
        * EX3: [123.45.67.89] from Zimbabwe routes to Zimbabwe datacenter
    * Default static route: where all unspecified traffic is routed (routing table)
    * Next Hop: next router's IP to which traffic should be forwarded
- Concepts: IP addresses, Transport/Tunnel Mode
    * Dual Stack: a router that does both IPv4 and IPv6
    * Auto-addressing: IPv4 uses DHCP, IPv6 uses SLAAC (stateless address autoconfiguration)
    * IPv6 EUI (extended unique identifier) is MAC address with `fffe` in middle and first bit flipped (00 -> 10 [as in, 02])
    * Link-local IP address: nonroutable IP address usable only on a local subnet
        * IPv4 link local is APIPA
        * IPv6 link local starts with `ff`
    * CARP (Common Address Redundancy Protocol): open version of HSRP, one IP address for multiple devices, if one device breaks another takes over
    * Transport mode: no encapsulation; headers are wide open to allow routing
    * Tunnel mode: entirety of packet is contained in another (including header)
    * GRE: Generic Routing Encapsulation, IP packet encapsulation with no authentication
- Goal: addressing, routing, delivery of datagrams between points on network
#### ROUTER METHODS
- Routing protocol: advertises route information between routers (describing how to reach specified destination networks)
- Autonomous System (AS): A network under a single administrative control
    * IGP exists within one AS, EGP connects multiple AS (and only uses BGP, a path-vector protocol [uses AS hops])
- Convergence: routers learning the paths and converging with other routers on agreed pathing
- Route Redistribution: different protocols sharing route information
- Hold-Down Timers: time delay after a change to a route entry; stability helps convergence
- TTL: Time To Live, a count of hop values inside a frame, decreases on each hop, when reaching 0 the frame is discarded
#### DISTANCE VECTOR
- Distance Vector: send full copy of routing table to directly-attached neighbors
    * Poison Reverse: set a route to "infinite" and return to sender as such
    * Split Horizon: prevent a learned route from being advertised back out
- EIGRP (Enhanced Interior Gateway Routing Protocol) (Cisco) is "advanced" distance vector ("hybrid"), uses combination of manually-set metrics
    * Relies on neighboring routers to report paths to remote networks
    * Combo metrics: reliability, bandwidth, delay and load
- RIP (Routing Information Protocol) is distance-vector, uses a metric of hop count (max is 15 hops, 16 is infinite)
    * RIP only considers the next hop router to reach a given network or subnet (vector)... one-hop memory
#### LINK STATE
- Link State: uses an algorithm to determine shortest path to destination network
- LSA (Link State Advertisement): router advertises its connections, other routers use this to create network map
- OSPF (Open Shortest Path First) is link state, uses metric of cost, which is based on the link speed between two routers
    * Ideal for hierarchical systems/networks, suitable for orgs with redundant paths between networks (router for each floor of building)
    * Popular because of its scalability, fast convergence, and vendor interoperability.
- IS-IS (Intermediate System-to-Intermediate System) is link state, similar to OSPF but less popular
## Layer 4: Transport
- Devices: Gateways, Firewalls
- Concepts: Encapsulation (splitting data), Decapsulation (unsplitting data)
- Channel bonding: wireless band addition (typically two adjacent 20MHz bands into 40MHz band)
- Goal: reliable delivery of datagrams between points on a network
## Layer 5: Session
- Responsible for setting up, maintaining, and tearing down sessions
- Devices: Gateways, Firewalls, PC’s
- Concepts: SSL/TLS
    * SSL: Allows secure web browsing over HTTPS (same with TLS); "Provides cryptography and reliability for upper layers (Layers 5– 7) of the OSI model"
- Goal: stability in interhost communication
## Layer 6: Presentation
- Responsible for data formatting/encryption/decryption
- Devices: Gateways, Firewalls, PC’s
- Concepts:
- Goal: encrypt/decrypt and also data type conversion
## Layer 7: Application
- Devices: Gateways, Firewalls, all end devices like PC’s, Phones, Servers
- TCP/IP model has "Application Layer" at layer 5,6,7 (don't get confused... or else!)
- Supports services used by end-user applications (not the actual applications themselves). 
- Advertising available services
- Goal: feed the application

# Organizations
- Asset management: tracking network components + managing the lifecycle of those components
- Availability: network uptime
- T1, T2, T3, E1, ...: Telecommunications/internet lines with standardized speeds; these can be leased
    * Slower than other common options, but uniquely, these can be entirely leased
    * T1: originally for voice, 1.5Mbps
    * T3: 44.7Mbps
- Central Office (CO): a building with a telecom's telephone-switching equipment
    * Five hierarchical classes: Class 1 (long-distance) > Class 2 (less) > Class 3 (less) > Class 4 (less w/ live operator) > Class 5 (connects to customer)
    * Local loop: connection between a customer premise and a local telephone company’s central office. 
- Channel Service Unit / Data Service Unit (CSU/DSU): digital modem between customer and provider
- Content Engine: content caching (lowering WAN usage)
- CPE: Customer Premise Equipment
- Differentiated Services (DiffServ): packets are marked for switch/router work, great for QoS
    * Marking alters bits within a frame/cell/packet; other tools reference markings and make decisions, ex: forward or drop
- Integrated Services (IntServ): "hard QoS", can set strict bandwidth reservations
    * RSVP (Resource Reservation Protocol): an example of an IntServ approach to QoS
- ESLR (Edge Label Switch Router): connects provider to one or more customers, uses labels
- Label switch router (LSR): provider's internal router, uses labels
- MPLS: Multiprotocol Label Switching, WAN tech for service providers, add labels to frames for switch purposes
- Optical carrier (OC): speed references for optical networks ("OC levels", ex: OC-1, OC-2 (which is OC-1 * 2), OC-3 (which is OC-1 * 3) and so on)

# IPSec
- IP Security (IPsec): Layer 3 encapsulation; a type of VPN that provides confidentiality, integrity, and authentication.
    * Used for securing IPv4 and/or IPv6 communications on local networks and as a remote access protocol
    * Each host required to use IPSec must be assigned a policy
- AH: Authentication Header, a protocol that provides authentication/integrity services (no encryption)
    * Hashes whole packet + IP header + shared secret key, adds this secret in its header as an Integrity check value (ICV)
- ESP: Encapsulating Security Payload, header/trailer/check, a protocol that provides authentication/integrity/encryption services
    * Encrypt the packet (not just calculating a hash)
- IKE: Internet Key Exchange, a protocol used to set up an IPsec session
- ISAKMP: Negotiates parameters for an IPsec session
    * SA: Security Association, an agreement between the two IPsec peers, agree on crypto params in ISAKMP session

# ISDN
- Integrated Services Digital Network, used mainly in DSL nowadays
- Two modes: BRI and PRI
    * BRI: Basic Rate Interface, two B channels and one D channel (two simultaneous conversations)
    * PRI: Primary Rate Interface, 23 B channels and one D channel (23 simultaneous conversations)
    * D channel is Q.921/Q.931 signaling protocols (D channel sets up, maintains, and tears down connections)
- Two circuits: T1 (North America/Japan) or E1 (Everywhere else)
    * T-carrier / E-carrier is a generic designator for any of several digitally multiplexed telecommunications carrier systems

# Topologies
- Physical (connections) vs Logical (flow)
- Bus topology: one-at-a-time, typically one cable that all devices tap into
- Hub-and-spoke topology: multiple segments connecting to centralized point, typically over WAN from main corporate location to several smaller locations
    * Star topology is the same thing
- Ring topology: One-direction send on a loop until reaching destination
- Partial-mesh topology: Hybrid of hub-and-spoke and full-mesh; mesh multiple main sites, spoke smaller locations to one of the main sites
- Full-mesh topology: Directly connects every site to every other site

# Broadcast Domains
- Classful subnet mask: Class A, Class B, Class C
    * Class A: 1-126, Class B: 128-191, Class C: 192-223, Class D: 224-239 (multicast)
    * Borrowed bits: bits added to a classful subnet mask
    * Classful mask: 255.0.0.0 for Class A, and so on
- Classless: VLSM or CIDR depending on situation
    * VLSM: Variable Length Subnet Mask, used by enterprises to assign IPs internally (subdivide/subnet), CREATES SUBNET
    * CIDR: Classless Inter-Domain Routing, used by service providers for block advertisement (combine/supernet), MASKS COMPLEXITY
- Block size: number of IPs in subnet; this includes subnet's address / subnet's directed broadcast address

# Attacks
- Buffer overflow:
    * This attack occurs when an attacker leverages a vulnerability in an application, causing
    * data to be written to a memory area (that is, a buffer) that’s being used by a different application.
- FTP bounce:
    * An FTP bounce attack uses the FTP PORT command to covertly open a connection with a remote system. 
    * Specifically, an attacker connects to an FTP server and uses the PORT command to 
        * cause the FTP server to open a communications channel with the intended victim, which might 
        * allow a connection from the FTP server, while a connection directly from the attacker might be denied.

# Defenses
- Pretty Good Privacy (PGP): widely deployed asymmetric encryption algorithm and is often used to encrypt e-mail traffic.
- GNU privacy guard (GPC): A free variant of pretty good privacy (PGP), which is an asymmetric encryption algorithm.
- Nessus: A network-vulnerability scanner available from Tenable Network Security.
- Syslog: syslog servers and clients; clients send log messages to servers

# As A Service
- NaaS: purchase data services, ex: email, LDAP, DNS

# Unified Communications
- RTP: Real-time Transport Protocol, Layer 4 protocol that carries voice (and interactive video)
- SIP: Session Initiation Protocol, VoIP signaling protocol used to set up, maintain, and tear down VoIP phone calls
- Integrating legacy voice and VoIP: use a VOICE GATEWAY to translate between legacy and VoIP
- VoIP PBX: the core switch that controls all functions found in a VoIP system
    * Provides digital switching
    * Must connect to a voice or VoIP gateway to connect back to the external voice provider, especially an analog service
    * PBX: Private Branch Exchange, provides switch services for analog voice (traditional telephone network)
    * Virtual PBX: VoIP solution between company telephones and service provider
- Shaping (store in buffer) and Policing (drop)
- Link Efficiency: make best use of bandwidth through ex: compression or fragmentation
- QoS: prioritizing data, uses MANAGEMENT PLANE, CONTROL PLANE, and DATA PLANE
    * Uses traffic/bandwidth shapers to do these things (shapers are protocols, appliances, or software)
    * Management plane monitors traffic conditions and instructs changes
    * Control plane makes decisions about how to prioritize traffic and where it should switch them
    * Data plane handles the actual switching of traffic; it actually forwards packets through the router to their destination

# LDAP
- Accessing/maintaining distributed directory information services over an Internet Protocol (IP) network.
    * Bind (auth w LDAP version), Search, Compare, Add/Delete/Modify entry, Modify Distinguished Name (index), Abandon (halt), Unbind (close connection)
        * Bind in LDAPS is through SASL, SASL negotiates the security mechanism to be used
    * Plaintext entries; "dn" contains relative distinguished name and dc is domain component (DNS-related)
1. A client starts an LDAP session by connecting to an LDAP server, called a Directory System Agent (DSA)
    * TCP/UDP port 389 or 636 (LDAPS)
2. The client then sends an operation request to the server, and a server sends responses in return. 
3. Client can send next request before receiving response; server can send responses in any order

# DNS
- Forward lookup zone: have DNS -> get IP (most records)
- Reverse lookup zone: have IP -> get DNS (PTR records)
- Internal DNS zone: domains in internal network
- External DNS zone: domains in external network
- Recursive lookup: originating DNS server -> root DNS server -> sub-root DNS server -> ... -> authoritative DNS server
- Zone transfers can fail if NTP stratum is inaccurate...
- SRV: DNS record identifying a network service/protocol (incl port/protocol)
- CNAME: alias
- TXT: freeform, includes SPF record (whitelisted email address senders), DKIM (whitelisted email address receivers)

# DHCP
- Leasing: DORA (Discover, Offer, Request, and Acknowledge)
    * T1 time: 50% of lease
    * T2 time: 87.5% of lease
- DHCP Relay: send traffic from one subnet to another

# SAN
- iSCSI: cheaper, uses ethernet
- Fibre Channel: expensive
    * "T11 ANSI standard", contains initiator, the target, and a director
- Fibre Channel over Ethernet: VERY expensive (?)

# Top-of-rack Switching
- Spine-leaf, main switch distributes to other switches

# Cisco Network Heirarchy
- The Core Layer: Handles and transports huge amounts of data quickly and reliably; connects multiple end networks together
- The Distribution Layer: Intermediary between the Core Layer and the Access Layer; 
    * Keeps local traffic confined to local networks; fault-tolerant; routing boundaries
    * Provides fault-tolerant interconnections between different access blocks
    * Used for implementing traffic policies, such as quality of service (QoS)
- The Access Layer: Provides access points for hosts to connect to the network.

# Software-Defined Networking
- Infrastructure Layer: Network devices; move packets based on SDN's rules
- Control Layer: SDN Controller; processes application layer's instructions/requirements, sends to network devices; does the reverse of this, too
- Application Layer: programs; they communicate their desired network behavior/requirements to the SDN Controller