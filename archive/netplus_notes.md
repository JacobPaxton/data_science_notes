# Hot notes
- `ssh account@ip_address`
- Look into: Wavelength Division Multiplexing (WDM), Coarse WDM (CWDM), Dense WDM (DWDM), BiDi
    * WDM: a means of using a strand to transmit or receive more than one channel at a time.
    * CWDM supports up to 16 wavelengths and typically deploys four or eight bidirectional channels over a single fiber strand.
    * DWDM provisions a greater number of channels (20, 40, 80, or 160)
        * This means that there is much less spacing between each channel and requires more precise and expensive lasers.
    * BiDi: uses WDM to transmit the transmit (Tx) and receive (Rx) signals over slightly shifted wavelengths.
- CSMA/CD: Data, check network, transmit data, collision, wait, retransmit
- #10, #42, UC, 
- **OSPF v VRRP v RIPv1 v HSRP**
- 0: emergency, 1: alert (condition), 2: critical (failure), 3: error, 4: warning (of incoming error), 5: notice (of unusual activity), 6: info, 7: debug
- LACP v BPDU v STP
- Add DNS record:
    * New-NetIPAddress -InterfaceAlias 'Ethernet' -IPAddress 10.1.24.200 -PrefixLength 24
    * ipconfig /registerdns
- Commands
## Red-Hot Notes
- Protocol: Encapsulation (how things are bundled) and Addressing (different node types and rules)
- Trunking
- Differentiated Services (DiffServ)
- Generic Routing Encapsulation (GRE) and Multipoint GRE (mGRE)
    * Supports point-to-multipoint links, such as the hub and spoke dynamic multipoint VPN.
- Multiprotocol label switching (MPLS)
    * Overlay network to configure point-to-point or point-to-multipoint links between nodes regardless of the underlying physical and data link topologies.
- Network function virtualization (NFV)
    * Provisions virtual network appliances, such as switches, routers, and firewalls, via VMs and containers.
- E-line: point2point, E-LAN: mesh

# Troubleshooting
- APIPA address and intermittent IP address allocation: exhausted DHCP scope, check DHCP range *or* DHCP lease time
    * APIPA and no connectivity: DHCP server is down
- DNS: try ip address, if works, check `ipconfig /all` and network connections properties (DNS server settings)
    * DNS cache: `ipconfig /displaydns`, `ipconfig /flushdns` (re-query DNS records)
    * Check DNS awake: `nslookup` (start tool) -> `server 8.8.8.8`
    * Query DNS server: `dig`

# OSI Model
## 1. Physical
- 1s and 0s on the cable; cable specifications
- NIC assembles 1s and 0s into ethernet frame when sending data
    * Reads, destroys ethernet frame when receiving data
- Handles the `PREAMBLE` of an ethernet frame
    * Preamble warns the NIC that an ethernet frame is coming
- Uses the `FCS` of an ethernet frame to verify transmit integrity
## 2. Data link
- All about MAC addresses
- Makes sure self is "address-ed" in such a way that it can be contacted
- Checks `DESTINATION MAC` of an ethernet frame to see if it matches its own
    * If not matched, the ethernet frame is dropped
- If matched, this layer stores the `SOURCE MAC` and `DESTINATION MAC` for comms
- After "stripping off" MAC information, the frame is now an "IP Packet"
## 3. Network
- All about logical addresses (IP addresses)
- Makes sure self is "address-ed" in such a way that it can be contacted
- Checks `DESTINATION IP` of an IP packet to see if it matches its own
    * If not matched, the IP packet is dropped
- If matched, this layer stores the `SOURCE IP` and `DESTINATION IP` for comms
## 4. Transport
- All about splitting/joining the `DATA` being transmitted
- Splits the data because max `DATA` in ethernet frame is 1500 bytes
    * Splits are sequenced in a way that makes sense for transport-layer devices
- Joins the data because of the 1500 byte limitation
## 5. Session
- All about ports
- This is where host actually connects to remote host (computer to website, etc)
    * Ports connect applications
- Stores/uses `SOURCE PORT` and `DESTINATION PORT`
## 6. Presentation
- All about converting data for destination application compatibility
- Less important nowadays
## 7. Application
- Where network data interacts with applications directly

# With Dad
- Broadcast: always from host device, DST MAC is all F (in hex)
- Router has routing table; this is essentially "where to send given traffic"
    * Home routers: Two routes specified in routing table, local and public
    * Enterprise: Hub router may have 10 routes (spoke routers) or h/e many
    * 0.0.0.0 is for all IPs not on routing table; "send to router that knows!"
        * This is the "default route"
    * 0.0.0.0 can be tied to multiple upstream routers (multiple ISPs for SOHO)
        * Choices are weighed with "metric", lower number is better priority
- Router has ARP table; this maps IPs to MACs for a router's LAN

# Broadcasts
- Sent on "broadcast domain" with MAC address: FF:FF:FF:FF:FF:FF
    * This broadcast domain is typically just some sort of hub
- Sent because destination MAC is unknown
    * Payload has identifying info, ex: destination computer's name is known
- Goal is to get traffic back with clarifying information

# Routing
- Layer 2 network: SRC MAC (host), DST MAC (host), Payload, CRC
- Layer 3 network: SRC MAC (host), DST MAC (router), SRC IP (host), DST IP (host), Payload, CRC
    * "IP header" (IP information) + Payload is called the "IP Packet"
    * IP Packet is unchanged through all ethernet frame changes
- Windows CMD: `route print` or `netstat -r`
- Routers are either Link State (pings + continuous requests) or distance vector (interval, full routing table sends)
- External Gateway Protocol (EGP): between 2+ entities' routers
    * EGP is one whole-internet protocol: Border Gateway Protocol (BGP)
- Internal Gateway Protocol (IGP): between your own routers
    * Between routers in an autonomous system (AS), use AS numbers (ASN)
    * IGP option: Routing Information Protocol (RIP), uses distance vector to share route information
        * Cares about hop count (max 15 hops); once router learns how to get somewhere, sharing also shares that access route
    * IGP option: Open Shortest Path First (OSPF), uses link state, designated router + backup, and Area ID
        * Link state advertisement ("I'm connected to network A"), this is FAST, "convergence" happens quickly
- Quality of Service (QoS) can be set for more things than VOIP, including gaming (using protocol priorities)

# Wires
## Coaxial
- Highly resistant to EMI and physical damage; inflexible and pricy
- 4 parts: inner conductor/core/center wire, insulator, outer conductor, PVC sheath/jacket
    * Inner conductor: carries the signal
    * Outer conductor: a mesh
    * Insulator separates inner/outer conductors
- Main connector is the F-type (pin with spin jacket, think TV cable)
    * Older type: BNC (twist-lock)
- Type is determined by radio grade (RG); this is thickness / conductor info
    * Also characterized by resistance (Ohms)
- Main type is RG-6 (with 75 Ohm resistance)
- Newer than Coaxial: "Twinax" (twinaxial), two inner conductors and one outer
## Twisted (UTP/STP)
- UTP: sheath with solid-core wires in twisted pairs
- STP: copper-sheathed with solid-core wires in twisted pairs
- Cat 5:  100m 100Mbps
- Cat 5e: 100m 1Gbps  (EMI protection)
- Cat 6:  55m  10Gbps
- Cat 6a: 100m 10Gbps (EMI/crosstalk protection)
- Cat 7:  100m 10+Gbps
- Cat 8:  100m 25Gbps / 30m 40Gbps
## Fiber
- Fiber optic (core, carries light) surrounded by cladding (reflective) surrounded by sheath
- ST (long core), SC (square snub), FC (short core), LC (long bender), MT-RJ (tiny)
- Multimode: propagate light, always has two connectors, uses LED
    * Almost always orange
- Singlemode: propagate lasers, thinner/tighter, always has one connector, uses lasers
    * Almost always yellow
    * lasers can be different colors; allows bidirectional (bidi) comms
- PC contact (flat with rounded edges), UPC contact (rounded), APC (angled flat)
## Fire Ratings
- Plenum: good (wires in drop ceiling need to be not really burnable)
    * More expensive, but fire codes require it sometimes
- Riser: medium (you have other fire resistance vertically through the building)
- PVC/non-plenum: BAD (very burnable)

# Ethernet
- min 64 bytes (smaller is padded), max 1522 bytes (larger is sent over multiple)
    * Jumbo frame: up to 9000 bytes (high-speed networks)
    * Max byte count is called MTU (max transmission unit)
- Switches for fiber have multi source agreement (MSA) to allow intercompatibility between fiber connectors
    * Use transcievers (port conversions), ex: gigabit interface converter (GBIC) with SC connectors
    * Another ex: small form factor pluggable (SFP), SFP+
    * Another ex: quad SFP (meant for 40Gb ethernet, quad is just 4x speed)
## 100
- 100BaseT4: cat3, 100m, HUBS, all four pairs in twisted-pair
- 100BaseTX: cat5e, 100m, HUBS, two pairs, FULL DUPLEX
- 100BaseFX: multimode, 2,000m
## 1,000
- 1000BaseCX: twinax, 25m
- 1000BaseSX: multimode, 500m
- 1000BaseLX: singlemode, 5,000m
- 1000BaseT: cat6 UTP, 100m
## 10,000
- 10GBaseT: cat6/55m or cat6a/100m
- 10GBaseSR: multimode, 26-400m || SW works on SONET (different from ethernet)
- 10GBaseLR (long range): singlemode, 1310nm, 10,000m || LW works on SONET
- 10GBaseER: singlemode, 1550nm, 40,000m || EW works on SONET

# Switches & Hubs
- Hubs are limited to 10Mbps!!! Need compatible cards, cables, etc
- Hub: all connected computers are on the same Collision Domain
- Carrier Sense Multiple Access / Collision Detection (CSMA/CD)
    * NICs detect collision, roll a dice, then wait that # of milliseconds to xmit again
- Both: "uplink" port does crossover cable conversion at the port itself usually
    * This conversion is "medium dependent interface crossover" (MDI-X)
    * Modern boxes see that a crossover cable is needed and convert on the fly
- Connecting switches: "bridge protocol data units" (BDPUs), frames that choose in-charge box
    * Prevents switching loop
- Spanning Tree Protocol (STP): stop bridging loops with root switch assignment
    * Root switch shuts off the offending port; connection is still maintained at the other switch though
    * STP switches can detect other floods too and turn off ports
- Trunking: connecting multiple VLANs together, typically uses a trunk port (designated by you)
    * Uses crossover cables
    * Port bonding: Link Aggregation Control Protocol (LACP) to duplicate trunk connections (increase bandwidth) via active/active
- Root Guard protects the original root switch in STP from being overtaken by a rogue root-attempting switch
- BPDU (bridge protocol data unit) Guard protects against swapping a computer's connection to a switch with another switch
- DHCP snooping: detect rogue DHCP
- Port mirroring: big use is for passive monitoring

# ARP
- IP->lookup->MAC table; records are only preserved for a few minutes
- `arp -a` to see local cache

# IP Addressing
- IANA passes IP ranges to RIRs (large regions)
- RIRs pass IP addresses to ISPs
- ISPs pass IP addresses to companies/people
## Class Licenses
- Class A: 0-126 and /8; millions of computers
- Class B: 128-191 and /16; 65535 computers
- Class C: 192-223 and /24; 255 computers
## CIDR
- "Classless inter-domain routing"
- More granular version of IP classes / subnetting
- /24 is class C; 255 computers
- /25 is 126 computers (first bit of last octet is masked)
    * Two subnets within /24
- /26 is 62 computers (first two bits of last octet are masked)
    * Four subnets within /24
- /27: 30... /28: 14.... /29: 6... /30: 2... /31 not possible
    * /27 is eight subnets... /28 is 16 subnets... and so on
## Private IP addresses
- 10, 172.16, 192.168 (NAT'd devices, private IP addresses)
    * Router tracks private IP<->public IP connections
    * PAT (normal translation), SNAT (assign computer a static route), DNAT (router has choices to assign as needed)
- 127 is loopback, so is ::1 (ipv6)
## APIPA
- 169.254 is APIPA, aka can't find DHCP server

# DHCP
- One DHCP server per broadcast domain, for obvious reasons
- Host: DHCP Discover -> DHCP: DHCP Offer -> Host: DHCP Request -> DHCP: DHCP Acknowledge

# TCP/IP and UDP
- TCP/UDP are layer 4
- Ethernet frame: SRC/DST MAC + FCS with everything else
- IP Packet: drop SRC/DST MAC and FCS
- TCP Segment / UDP Datagram: drop IP address
- TCP 3-way handshake: client SYN -> server SYN/ACK -> client ACK -> session established
    * `netstat` allows you to see these active sessions
- ICMP is layer 3 (no port numbers), has many types (one of which is ping)
- IGMP is layer 3 (no port numbers), mainly for multicast (IP starting with 224)
## TCP/IP Model
- ICMP is layer 2

# Tools
- `netstat`: active connections and ports
    * `-a` will show listening ports (determine if server is running, inb p80)
- `net`: `view` systems in workgroup, `user` whoami, `view \\computernamehere` shared files/folders, `use`: map drives
    * `net use r: \\computernamehere\sharefolderhere` (mapping to R:), then try `r:` and then `dir` to see contents
    * `net share sharefolderhere=C:\Users\user\desktop\projects`
    * `net accounts` show accounts config for all accounts on machine (force logoff, min password length, etc)
    * `net start` all network-based services -- `net stop servicehere` to stop that service

# Mail
- SMTP: Sending (25) -> 465 (TLS)
- POP3: Receiving specific emails (110) -> 995 (TLS)
- IMAP: Folder sync (143) -> 993 (TLS)
- TLS allowed unencrypted first, then switched to: 465 (SMTP), 995 (POP3), 993 (IMAP)
- STARTTLS innovated on TLS, always-encrypted. Uses 587 (sometimes 465)

# NTP/SNTP
- Clock sync, different stratum (stratum 0: near-perfect -> 1,2,3,4,5,... -> stratum 15: not sync'd)
- NTP/SNTP both on port 123, both use UDP, choice seems arbitrary

# DNS
- www.google.com -> host.secondary.tld (FQDN)
- Root hints (root servers), represented by "."
    * `www.google.com.`, the trailing "." is root
- DNS server -> root hint "." -> root hint ".com" -> "google.com" -> "www.google.com"
    * DNS server itself has domain name on local area network, ex: "dns.local" (this is called "interior dns server")
- Your DNS server is authoritative for your computers, ex: "nerd.local" would point to computer1.nerd.com
    * Still is `nerd.local.`
- `A` ipv4, `AAAA` ipv6, `CNAME` alias for FQDN, `MX` mail server, `SRV` specific service like VOIP, `TXT` documentation or `DKIM`/`SPF` spam filtering
    * SPF is IP whitelisting, DKIM is key-based allow (passwords, etc); mail servers use these almost always nowadays
- Reverse lookup zone: IP -> FQDN (opposite of normal)
    * Uses `PTR` pointer record
- Name resolution: domains use domain controller, local uses netBIOS (137/138) or LLMNR (UDP 5355)
    * `nbtstat`: `-n` registered names, `-c` see cache, `-a computer1` access computer1's registered names, `-R` clear cache, `-RR` refresh/rebroadcast
- DNS server can do load balancing!!!!! (round-robin)
- DNS server can do delegation!!!!! (reverse-lookup to determine closest server to client)

# RADIUS
- RADIUS does AAA
- RADIUS server: system running RADIUS authentication software, ex: Microsoft IAS, Steel Belt and RADIUS, Open RADIUS
    * Can house the database, or a domain controller can house the database
- RADIUS client: handle auth requests from RADIUS supplicants (intermediary between server and supplicant)
    * Like a WAP
- RADIUS supplicant: laptop/smartphone that sends a RADIUS request (via RADIUS client) to RADIUS server
- RADIUS: UDP 1812-1813 or UDP 1645-1646

# TACACS+
- AAA, proprietary from CISCO; main use is for large network situations (large number of routers/switches)
    * Rarely used in wireless network
- TACACS+ server: computer keeping track of TACACS+ clients
- TACACS+ client: router
- TACACS+ user: a person trying to log in
- TACACS+: TCP 49

# Kerberos/EAP
- Kerberos: auth for LANs, proprietary from Microsoft
- Kerberos key distribution center: Windows Server domain controller + Authentication Service (AS) + Ticket Granting Service (TGS)
    * TGS Sends ticket granting ticket (TGT) to client (authentication), client timestamps it and sends to TGS
    * TGS sends token to client, token is time-sensitive (typically 8 hours) and basically SSO
- Kerberos client: Windows desktop
- Computers must all have sync'd time, timestamps are huge in Kerberos, can fail if time not sync'd
- Enterprise Authentication Protocol (EAP): flexibility in authentication
    * EAP PSK, PEAP (username/password), EAP MD5, EAP TLS (certificate from server), EAP TTLS (certs on both client and server)
    * Used almost exclusively for connecting to wireless networks; competes with Kerberos

# SSO
- LAN: Windows Active Directory (drives/folders)
- SAML: Identity Provider grants token, Service Provider are the endpoints (SCADA/websites)

# Certificates
- Website registers with Certificate Authority to prove validity of website's digital certificate
    * Public Key Infrastructure (PKI): Root cert authority stores, intermediate cert authority assists with checks
- Digital certificate contains public key with a hash that was encrypted via private key
- Client decrypts encrypted hash using website's public key
- Client verifies with Certificate Authority that website is trustworthy
    * Self-signed certs have no certification path
- Client uses website's public key to encrypt their own comms + send to server
- Certificate validity: OCSP servers and CRL

# Cisco
- VLAN Trunking Protocol (VTP) allows updating multiple VLAN switches
- Cisco language: `enable` does admin, `show config`, `show interface` (ports), `copy run start` + enter to save changes, `exit` to exit
- `show route` displays routing table (layer 3 switches)

# Proxy servers
- Application-specific
- Forward and reverse version
- Forward: hide client
    * client -> proxy -> firewall -> internet
    * Dedicated box for caching, content filtering, firewall, and more
    * Transparent: don't need config, but must be the sole entrance/exit to a LAN
    * VPN to proxy server is common (basically all commercial VPNs do this)
- Reverse: hide server
    * Protect server from bad actors, handle DoS, do load balancing / caching, encryption acceleration, more

# Load balancing
- DNS version versus server version

# Device placement
- DMZ: "loose" firewall/router allowing access to web servers, then connect that network via "strict" firewall/router to internal network
    * Jump box (inside a DMZ) allows a strict connection through an internal firewall to do free actions inside a DMZ (jump box is free)

# IPv6
- Running IPv4 and IPv6 is called "dual stack"
- IPv6 kills NAT, no point, all IP addresses are public
- 128-bit addressing, fast thanks to aggregation and Neighbor Discovery Protocol (NDP)
- Ignore leading zeroes, drop a section of three zeroes (0000:0000:0000 -> ::)
- IPv6 Address (in ipconfig) is internet address; these are not directly the MAC address, they're randomized (privacy reasons)
- Link-local address: always `fe80::` for first-half, MAC address converted to hex is second half, %14 on end is Microsoft being dumb
    * Self-generated IP addressing, allows neighbor solicitation and neighbor advertisement; uses ICMP v6, multicast (not "broadcast")
- Router advertisements are IPv6 messages to routers, replaces DHCP basically

# WAN technologies
- Fiber: wavelength division multiplexing (WDM), bidirectional WDM (BWDM), dense WDM (DWDM), coarse WDM (CWDM)
    * DWDM: each signal has different color (different wavelength), 150 different signals -> 7.6Gbps
    * CWDM: 60km, simpler than DWDM, lower cost
- Private WANs: faraway network connections privately; expensive; Multiprotocol Labeling System (MPLS), Software-defined WAN (SDWAN), Metro Ethernet/Optical
    * MPLS header (just like layer2 and layer3 headers); Labeling data to guide its movement/prioritization; expensive
    * SDWAN: uses MPLS, but is speedy AND secure
    * Metro Ethernet/Optical is what's used for a MAN; not connected to internet, so no security needed / is cheaper

# DSL
- Symmetric DSL vs Asymmetric DSL
- Filtering DSL (phone activity filtered from internet activity)... helps

# Cable
- Faster than DSL
- Doesn't require point-to-point protocol over ethernet (PPPoE)

# Satellite
- Asynchronous, 12Mbps download, 3Mbps upload
- Uses RG-6 and satellite modem

# Cellular
- Generations (2G, 3G, etc)
- Global System for Mobile Communications (GSM), uses Time-Divisiom Multiple Access (TDMA) so that more than one user can use same channel (2G)
- Code-Division Multiple Access (CDMA); uses spread-spectrum (different freq for each user); CDMA lacks SIM cards
    * Long-Term Evolution (LTE) - 300Mbps down 75Mbps up, uses nano-SIM, can just use LTE NIC to add CDMA to a device
- 5G (2019), 3 bands (low, medium, high), each uses different freq (faster speed at shorter range)

# Remote Desktop
- Citrix ICA, TightVNC (5900), RDP (3389)

# VPN
- PPTP (microsoft), L2TP/IPSec (cisco), SSTP (common), IKEv2
    * PPTP has fast speed but weak encryption, whereas, L2TP has a strong encryption but having slow speed
    * SSTP is much more secure than L2TP, but the downside is, it Mostly works for Windows
- VPN concentrator/heading (same thing)

# Wireless
- WAP (infrastructure mode), client, SSID, one of two ISM bands (2.4/5.0), and a transmission tech
- CSMA/CA (collision avoidance): wireless client won't send anything until coast is clear (backoff time)
    * CSMA/CD (collision detection): ethernet
- Transmission: 
    * Direct-sequence spread spectrum (DSSS): old, uses subfreqs in a channel, spread out over these and hope things work out
    * Orthogonal frequency-driven multiplexing (OFDM): current, wide channels allow better spread
- Gain: increase/decrease size of radiation, measured in dBi
    * Dipole/patch use 3-5 dBi
    * Directional use 15-30 dBi
## 802.11 Extensions
- 802.11a: 54Mbps, 5.0GHz, OFDM, 5.0 doesn't really use channels
- 802.11b: 11Mbps, 2.4GHz, DSSS, 11 channels (mainly 1, 6, 11)
- 802.11g: 54Mbps, 2.4GHz, OFDM, 11 channels (mainly 1, 6, 11)
- 802.11n: 300Mbps, both, OFDM, MIMO (two conversations at once instead of wait)
- 802.11ac: 1Gbps, 5.0 (but both), MU-MIMO (many conversations at once instead of wait)
## PoE
- 802.11af: PoE, 15.4W
- 802.11at: PoE+, 30W
## Security
- WEP: 64/128bit keys, crackable
- WPA: TKIP
- WPA2: AES/CCMP

# Virtual Networking
- Network Function Virtualization (NFV): make virtual implementations of physical network hardware (switch, bridge, etc)
- Software-Defined Networking (SDN): management plane (GUI/CMD management), control plane (protocol/tables/settings), data plane (packet movement)
    * SDN network controller allows ex: programming/controlling many WAPs (propagate changes)
- Modern datacenters use spine/leaf architecture (instead of three-tier architecture)
    * Core -> Spine, Agg/Endpoint -> Leaf; Spine connects to **all** Leafs, creating a mesh network with tons of flexibility
- First-Hop Redundancy Protocols (FHRP): redundant paths for internet connection between client and datacenter
    * VRRP/HSRP are the actual protocols for FHRP; uses active-passive (passive are dormant until needed)

# NAS and SAN
- NAS: file-based sharing protocol, NAS box usually has an OS and can be RAID'd, runs over standard network, shows up as normal network shares
    * Set up partitions, do formatting, set up NAS (Samba, Apple, etc)
- SAN: block-level file sharing, Fiber Channel/iSCSI connection out from SAN controller, multipathing (multiple NICs); expensive!
    * Appears as a drive in Disk Management!!!
    * FCoE (over Ethernet): the actual connection
    * iSCSI: target and initiator; initiator looks for targets, then makes the target one of its hard drives

# Unified Communications
- Combines VoIP, video, fax, chat, more into a single system
- Uses UC device, UC gateway, UC server
- Protocols:
    * RTP (realtime transport protocol): 5004/5005
    * SIP (session initiation protocol): 5060/5061
    * H.323 (telecom protocol for audio/video xmit): 1720
    * MGCP (media gateway / medianets): 2427/2727

# ICS/SCADA
- ICS: Interface -> ICS server -> actuators/sensors
    * Interface: Human-Machine Interface (HMI), unique to the ICS they monitor
    * ICS server is typically a PLC ("headless" computer)
- DCS: Interface -> distribution server -> multiple ICS servers
- SCADA: ICS with automation due to long-distance/remote aspect of systems
    * Uses a Remote Terminal Unit (PLC but autonomous/data-hungry), RTU can have HMI

# Operations
- Policy is goal, procedure is... procedure
- NDA, Licensing restrictions (usage, # of users, transfer, renewal), export controls / data restrictions (mil/nuke/license keys???)
## Forensics
- First responder: first in reaction to an incident; preserve data, screenshots, documentation, etc
    * Secure the area (lock people out)
    * Document the scene (what the forensics team needs to look for, can be stuff on table too)
    * Collect the evidence (typically the forensics team takes over for this)
    * Document chain of custody
- Forensics report
    * Legal hold
    * eDiscovery (requesting the evidence)
## Documentation
- SLA: service -> client
- MOU: between orgs, agreed duties, time frame, rest is varying
- MSA: multi-source agreement, kinda a standard between companies in an industry
- SOW: statement of work, LEGAL, work to be done / time to do it / more
## Security Policies
- Acceptable Use Policy: signature, websites, access time
- Remote Access Policy: VPN access, authentication/authorization method
- Password Policy: requirements
- IT Safety Policy: equipment lifting, safety equipment, spill handling
## Change Management
- Change Management Team: business analysts, marketing, operations, management, more
- Change Management only really applies to **infrastructure change** (not strategic change)
    * Strategic change (massive, ex: all computers changing, moving country)
    * Infrastructure change (Art team changes to new version of Adobe Premier)
- Change request to initiate the process
    * Type of change (software, hardware, backups, etc what is changing)
    * Configuration procedures (requirements for making the change)
    * Rollback process
    * Potential impact (save time, save money, efficiency improvement, etc)
    * Notification (how to let people know)
- Change request is submitted to change management team and considered
    * Cost? Management Approval? Time required? and more
- Change is approved: changes happen, Change Management Team estimates time/resource requirements
- Documentation of changes (network diagram changes, floor plan changes, software changes, more)
## Backup Plan
- RPO: how much data lost if backup is used
- RTO: time needed to restore to normal operations
- Backup config data
- Backup state data (router data, active directory user data, etc)
- MTTR: repair time estimate
- MTTF: uptime estimate
- MTBF: combo of MTTR and MTTF (estimate of full cycle of failure + uptime)
### Backup types
- You know these
## Business Continuity Plan
- Disaster recovery (ex: flood recovery) and business continuity (how to keep going in case of recovery)
- Cold site: weeks of recovery; warm site: days of recovery; hot site: hours of recovery; cloud site: fastfastfast
- Offsite considerations: distance from disaster, housing for employees, internet access, country data requirements, more
- Order of Restoration: Power -> Wired LAN -> ISP link -> Active Directory/DNS/DHCP -> servers -> workstations -> wireless -> peripherals
- After-Action Report
## Defense In Depth
- Perimeter -> Network -> Host -> Application -> Data
- Perimeter (vuln testing/honeypots)
- Network (DMZ, network segmentation, access control/VLANs)
- Host (antivirus/firmware)
- Application (testing)
- Data (separation of duties / least-privilege)

# SNMP
- OID: identify variable that can be read/set by SNMP
- MIB: translation file describing the structure of the management data; uses hierarchical namespace containing OIDs
- Trap: asynchronous notification from agent to manager, notifies management of real-time event (alarms, etc)
    * Granular: OID number and OID value
    * Verbose: All information about the alert + payload