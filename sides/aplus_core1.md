- Peripherals: user-touching interfaces
- Asymmetric connector design is called "keying"
- USB controllers typically only have 3 or 4 ports; MOBO has several USB controllers (bandwidth)
- USB 3 is now 3.2 Gen 1 (5Gbps), 3.2 Gen 2x1 (10Gbps), 3.2 Gen 2x2 (2x10Gbps)
    * Type A, B, C as normal; but Micro B is that dumb dual-plug port used on old phones
- Type B USB is for large devices and printers
- "Lowspeed" cables are 3 meters, "Highspeed" are 5 meters
- Most USB do 4.5W of power

# Questions from the Practice Test
- Fiber Optic Cables - Connector Types (SC, LC, ST, F)
- Touch Screen Technology - Clicking a desktop works, touching the screen does not
- Motherboard Ports - PCI vs PCIe (PCIe x1, x4, ...)
- Network Activity Lights - What **problems** do they indicate?
- Screen Types - OLED flexible/thin or IPS flexible/thin?
- TV Troubleshooting - Plasma TV burn-in symptoms
- Zigbee and Z-Wave - Bands, operation, use, etc
- Email Protocols - Use cases (traveling, switching devices frequently, etc)
- Printers - Hardware in printer, problem symptoms (ghost images)
- Printers - Laser printer AC->DC conversion (Volts over DC [VDC])
- Color depth, color depth, color depth.... why
- Digital subscriber line, optical network cable, cable modem... hybrid fiber-coaxial connection
SNMP 161
- Ports - Service Location Protocol (427, 445, 443, 389)
- Cloud Service Providers - Data breach causes
- Cables - 40-pin ribbon cable (eSATA? SATA? IDE? AGP?), wireless NIC
    * eSATA vs SATA
- Cables - SCSI connector type / pins
- Hard Disk Drives - Speeds (home users, ...)
- Cellular Technology - HSPA+ and EV-DO (wtf)

## T2
- Apple's printer software/service
- AGP?
### Results
- INTEL uses VT for virtualization
- CPU OVERHEATING CAUSES SHUTDOWNS
- PRINT SHARE FROM LOCALHOST OUTWARDS IS POSSIBLE
- 3D PRINTERS USE FILAMENT
- BOOTMGR MISSING IS `bootrec /fixmbr`
- BAD VGA IS EITHER WRONG COLORS OR NO OUTPUT
- 802.11af: PoE -- 802.11at: PoE+ -- 802.11s -- MESH
- IDENTIFY PROBLEM -- CREATE THEORY -- TEST THEORY -- PLAN FIX -- FIX -- DOCUMENT
- DC JACK IS SOLDERED
- BLUETOOTH CARD READERS EXIST
- OS NOT FOUND / NTLDR NOT FOUND = CAN FIND DISK, CAN'T FIND BOOT
- POWER AND VOLUME BUTTONS ON IPHONE TO POWER OFF
- DHCP CONFIG ON PORT 67
- VM LOCALHOST CANT DO NETWORKING; INTERNAL IS NEXT UP FROM THAT
- SFTP AND SSH ON PORT 22

In the IaaS Cloud Service Model: (Examples of an IaaS solution include Rackspace and DigitalOcean)
- The consumer maintains:
    * applications to be run
    * data
    * Operating System (OS)
    * middleware
    * runtime
- The **CSP** maintains hardware:
    * servers
    * storage
    * networking
    * any virtualization

With the PaaS model: (Examples of this include Microsoft Azure and AWS Elastic Beanstalk)
- The consumer is responsible for:
    * applications
    * data
- CSP is responsible for everything else

With the SaaS model: (such as Google Apps, Dropbox, or Salesforce)
- The consumer uses the CSP’s applications
- The CSP maintains responsibility for all aspects of the cloud solution stack

## SUM-MISSED and CURIOUS
- Problems caused by FAULTY RAM
- CABLE SPECIFICATIONS / FIBER OPTIC CABLE TYPES (SCSI/SATA/eSATA/AGP/IDE)
- Causes of OS NOT FOUND
- Use of DIGITIZER
- SMTP, SNMP, POP3, IMAP and their ports and their use cases
- MODEM, DSL, ONT
- PRINTER HARDWARE
- CELLULAR TECH
- OLED v IPS
- ZigBee/Z-Wave
- CLOUD SERVICE PROVIDERS


# LL from Practice Test
- Faulty RAM can cause continuous reboots
- Fiber Optic Cabling: 
    * ST (straight tip, spearlike)
    * SC (subscriber connector, two-square design)
    * LC (Lucent connector, only one line for both tx/rx)
- OS Not Found:
    * BIOS doesn't detect the hard disk
    * Hard disk is damaged
    * Sector 0 of the physical hard disk drive has an incorrect or malformed master boot record (MBR)
    * An incompatible partition is marked as Active
    * A partition that contains the MBR is no longer active
- SMTP is to SEND ("S" in SMTP), PORT 25. POP3/IMAP are used for RECEIVE.
    * SNMP is port 161
    * NetBIOS is 137/139
- INVERTER is for LCD OPERATION
- Cable modem: HFC, RFoG, Coaxial
- DSL: twisted-pair (telephone)
- ONT: all-fiber
- ::1 is LOOPBACK
- 15k RPM HDD is fast, 5400rpm HDD is low-end
- The DCPS (DC Power Supply/Source) of a laser printer is used to convert high voltage AC into lower voltage DC for the printer. The DCPS converts 115VAC or 220VAC power into +5 VDC and -5 VDC for use by the printer's logic board, and +24 VDC to power the motors that feed the paper through the printing path in the last printer.
- If your computer won't boot, but fans spin continuously, it indicates a problem with the power supply, the motherboard, or overheating could be occurring. 
- When the power supply to your computer fails, it won't start or power up, but the fans spin (as described in this question). One of the reasons your computer won't boot but the fans spin could be a bad processor or memory chip. To isolate this as a reason, you should remove the processor and memory and then attempt to boot up the computer and listen for a POST beep code. In this case, we could eliminate the motherboard, processor, and memory as the issue's source since no POST beep codes were heard. Based on the symptoms and actions performed, it appears that the power supply is not providing enough wattage to all the components of the computer, which is why the fans are spinning (they use low wattage) while the rest of the system fails to boot.
- 3G cellular technology is made up of two different technologies: HSPA+ and EV-DO. HSPA+ (Evolved High-Speed Packet Access) is a 3G standard used for GSM cellular networks and can support up to a theoretical download speed of 168 Mbps and a theoretical upload speed of 34 Mbps. In the real world, though, HSPA+ normally reaches speeds around 20 Mbps. EV-DO (Evolution-Data Optimized) is a 3G standard used for CDMA cellular networks and can support up to 3.1 Mbps downloads. 4G cellular technology is made up of LTE and LTA-A. Long Term Evolution (LTE) is a packet data communications specification providing an upgrade path for both GSM and CDMA2000 cellular networks. LTE has a theoretical speed of 150 Mbps and a real-world speed of around 20 Mbps. LTE Advanced (LTE-A) has a theoretical speed of 300 Mbps and a real-world speed of around 40 Mbps. 5G cellular technology is made up of three different types: low-band, mid-band, and high-band mmWave technology. Low-band 5G reaches an average speed of 55 Mbps with a theoretical speed of 150 Mbps. Mid-band 5G reaches an average speed of 150 Mbps with a theoretical speed of 1.5 Gbps. High-band 5G reaches an average speed of 3 Gbps with a theoretical speed of up to 70 Gbps.
- LOGICAL CORES is HYPERTHREADING
- PHYSICAL CORES is MULTITHREADING


- Mouses/keyboards (old ones) used: Mini-DIN port (or, PS/2 port)
- I/O Shield is for MOBO connection spots on back of tower ("System Unit" lol)
- https://pcpartpicker.com
    * Focus on motherboard / chipset!! Needs NVMe too for M.2/SSDs...
- CPU-Z allows you to see a lot about your computer HARDWARE

# Startup
1. Power button pressed
1. Electricity flows to "power good wire" on back of the CPU
1. CPU receives enough electricity and wakes up
1. CPU reaches out to BIOS chip for POST
1. POST broadcasts to all hardware components asking for their status
1. Required hardware reaches back to BIOS chip sounding off
1. POST sounds its beep indicating that POST has completed successfully
## Errors in Startup
- "Beep codes" indicate what hardware is unavailable
- "Display codes" show what's wrong when at least your graphics are working
- Some MOBOs have "POST card" (two-digit HEXADECIMAL light); can also get external ones
    * MOBO book will explain what the "POST error codes" mean

# BIOS
- Basic Input/Output System
- Contains programming for speaking to hardware, power-on self test (POST), and system setup (CMOS)
    * CMOS / system setup is just the BIOS interface thing, most are UEFI now
- CMOS is on an actual chip btw, and requires constant power (MOBOs have a CR2032 battery)
    * Funky errors may just need a battery replacement

# Motherboards
- Form Factors: ATX (12in x 9.6in, most common), MicroATX (9.6in x 9.6in, common), Mini-ITX (smaller, common)
    * Also, ITX (larger, extremely rare)
- Hardware (cases, power supplies, etc) are all standardized and interchangeable into the form factors
- Chipsets: conglomeration of many chips (floppy drive, sound, mouse); typically Northbridge, Southbridge
    * Northbridge: traditionally interface to CPU, ex: memory controller, expansion buses (fast stuff)
    * Southbridge: slower stuff (USB, etc)
    * Modern CPUs take on northbridge duties, still have a southbridge
- Chipsets define: max # of RAM sticks / video cards / USB ports / hard drives, fastest RAM/USB/etc speed
    * VERY IMPORTANT for buying decisions!
- Riser card: expansion of one MOBO slot into more slots

# Power Supply
- Transforms AC power to DC ("step-down transformer"), typically has a fan to expel air from the computer case
    * Volts of AC Power (VAC): Europe: 230VAC, America: 120VAC
    * Actually doesn't deliver the max-advertised; check its "80 Plus" rating to know what is realistic
- Modern power supplies are modular (choose your cables); old ones have cables soldered on
- ATX (mobo) power supply cabling had 20 pins, now has extra 4-pin offshoot
    * Individual cables: yellow (12v), red (5v), orange (3.3v); ATX extension is 
    * 4-pin offshoot: "ATX12V extension", extra power... governed by ATX12V standards
- Molex: 4-pin (in a line, horizontal)
- Mini connector: small version of 4-pin connector (in a line, horizontal)
- SATA: straight line with small hook on end, used for hard/disc drives
- PCIe connector: video cards

# CPU
- CPU, ARM (mobile/Apple), APU (integrated graphics)
- x86, x86-64, x64, IA-32 are "Instruction Set Architectures" (ISAs)
- The CPU has an internal code book that identifies each instruction pattern. 
- A register is a memory location inside a CPU. 
- The external data bus is the set of wires that carry data and instructions between the CPU and RAM. 
- PGA/LGA: Pin Grid Array or Land Grid Array for CPU connection types (PGA=AMD, LGA=Intel)
- ZIF: Zero Insertion Force for inserting CPUs

# RAM
- "Dual-channel memory" means 2 RAM sticks required on MOBO
    * "Running in single channel mode" means system only detects one stick
    * Might not boot if only one stick for two-channel MOBO!
- RAM typically has 8 chips, one for each bit of a byte
    * Parity/ECC RAM (rare, expensive) has a 9th chip, parity protects 1 chip failure, ECC protects 2 chip failure
    * SO-DIMMs (laptop/small computer RAM sticks) have 4... still have full DDR capability tho
        * DDR4: 260pin; DDR3: 204pin; DDR/DDR2 aren't standardized
    * Extra chip called Serial Presence Detect (SPD) chip, this reports RAM capacity/speed/brand/model/etc
- SDRAM (168 pin, TWO notches): uses clock speed of CPU basically (sync'd to it), synchronous dynamic RAM
- DDR (184 pin, one notch): double data rate memory, double clock speed (2 bits per 1 cycle), 8x the double-clock-speed for CPU score
    * 250mhz -> DDR-500 -> PC-4000
- DDR2 (240 pin, one notch): double speed of DDR, still 8x on CPU (DDR-500 -> DDR2-1000 -> PC2-8000), has a "2" in the CPU score, same thing
- DDR3 (240 pin like DDR2): same doubling against DDR2 but with "3"
- DDR4 (288 pin): same doubling against DDR3 (now 8x clock speed), uses MT/s now

# Storage
- Logical Block Addressing: allocating data to blocks/sectors/tracks (basically a driver)
    * Language: Advanced Technology Attachment (ATA)
    * Interface: Serial ATA (SATA); old version is parallel ATA (PATA) / integrated drive electronics (IDE) and is no longer in use
- SCSI (Small Computers System Interface) competed with PATA; used to both be parallel feeds, both are now serialized
    * SCSI is only ever used on servers nowadays
    * Serial Attached SCSI (serial version for mass storage), uses SATA connector with SCSI language
    * Internet SCSI (SCSI over Internet)
- SATA controller comes default on all MOBOs, can get more SATA connections
    * eSATA (external SATA) also exists, uses different cable; modern is USB-C though
- NVME is used for SSDs (especially M.2s) because it's faster than SATA
    * NVMe has one notch, SATA has two
- If storage drive appears in BIOS, physical setup succeeded
- Reason for OS saying storage is smaller than advertised: OS is kibi/mebi/gibi/etc (binary), storage is kilo/mega/giga/etc (decimal)
- 5.25in is optical media, 3.5in (main form for HDD), 2.5in (laptop/mobile), 1.8in (SSDs [old]), M.2 (SSDs)
## RAID
- Just a Bunch of Disks - JBOD - Spillover - Fill a disk until full, then move on to next
- Striping - RAID 0 - Speed Over All - Files split over drives with no safety
- Mirroring - RAID 1 - Safety Over All - Files fully copied between drives with slow speed
- Striping with Parity - RAID 5 - 2/3 Parity - Can lose *ONE* drive (minimum three drives)
- Striping with Parity - RAID 6 - 2/4 Parity - Can lose *TWO* drives (minimum four drives)
- Striping Mirrors - RAID 10 - Striping *over* pairs (a stripe is mirrored) - Can lose one of each pair (minimum four drives)
- Mirroring Stripes - RAID 0+1 - Striping *within* pairs, pairs mirrored - Can lose a full pair (minimum four drives)
- Proprietary RAIDs - ex Microsoft Storage Spaces - more RAID methodologies, often patented
- Hardware RAID (with controller chip or a RAID card) vs software RAID (CPU/OS RAID)
    * Hardware RAID: Not-CPU-intensive, is enabled in BIOS, configure settings with CTRL+R (RAID type, selected disks, etc); appears as single drive to OS
    * Software RAID: CPU-intensive, is enabled in Disk Management, can only do RAID 1 and RAID 0 unless you have fancier Windows versions

# USB
- 1.0: 1.5 Mbps --- 1.1: 12 Mbps --- 2.0: 480 Mbps --- 3.0: 5 Gbps --- 3.1 gen1: 5 Gbps --- 3.1 gen2: 10 Mbps
- Thunderbolt: 10 Gbps (mini display port), 20 Gbps (mini display port), 40 Gbps (USB-C)
- Lightning: Apple-proprietary

# Monitor
- Pixel: "Picture Element"; Nit: measure of brightness; refresh time / response time: amount of time to go from black to white to black
- One pixel with liquid crystal displays (LCDs) is RGB filter over a backlight (can be LED)
    * LCD requires digital input; VGA (analog) must be converted to digital by the monitor
    * Each filter is charged to become transparent (brighter color) or lower-charged to become dimmer / gray out
- Before LED it was CCFL; modern LCD can be TN (cheap, decent speed), IPS (wide color range)
    * CCFL is fluorescent light, these use inverters to go from DC power inside monitor to AC
- Organic LED is same as LCD/LED but it's merged into one light-up RGB
- DLP is used in projectors; DLP vs LED, throw distance, pincushion (curvy waist) vs keystone (trapezoid) vs skew (parallel sides, leaning)
## Connectors
- VGA: 15 pins, analog (monitor converts to digital for LCD)
- DVI: next step past VGA, DVI has a cross+4dots which can do analog for compatibility
    * DVI-I does both, DVI-D does digital only (no cross)
    * Single link: two blocks of digital connection; dual link: single big block of digital connection
- HDMI: next past DVI, does sound and DRM
- DisplayPort: competitor to HDMI, no sound, very good quality
    * Yes, this is larger Mini Displayport!!
## Resolutions
- VGA: 640w x 480l (4x3)
- SVGA: (Windows default during problems) 800w x 600l (4x3)
- SXGA: 1290w x 1024l (4x3)
- UXGA: 1600w x 1200l (4x3)
- WSXGA: 1440w x 900l (16x10), laptops!
- WUXGA: 1920w x 1200l (16x10)
- 720p: 1280w x 720l (1366 x 768)
- QHD/WQHD: 2560w x 1440l (popular for gaming)
- 1080p: 1920w x 1080l
- 4k: 3840w x 2160l
- 5k: 5120w x 2880l

# Networking
- One run: Switch -> Patch cable -> Patch panel -> horizontal run -> outlet -> patch cable -> computer
    * Switch, patch panel are in a rack / Main Distribution Frame
    * Patch cable is < 10m and "stranded" (flexible), horizontal run is < 90m and "solid core" (durable)
    * 110 punchdown tool gets horizontal run punched into patch panel
    * Test continuity (lightspeed/TDR), wiremap/tones (homeless cables), and loopback (port functionality)
- Main Distribution Frame (MDF): closet where the equipment is
- Patch panel: linking horizontal runs (cable to wall) with server
- LAN Ethernet frame: DstMAC - SrcMAC - Data - FCS
    * Data is in discrete chunks of 1500 bytes; files are broken up into these chunks, technology re-assembles these chunks
    * MAC addresses identify unique computers on a LAN; IP address information is stripped and MAC addressing is used (switch)
- Cross-LAN Ethernet frame: DstMAC - SrcMAC - DstIP - SrcIP - DstPort - SrcPort - Data - FCS
    * Protocol Data Units: Ethernet Frame, IP Packet, TCP segment / UDP datagram
    * Ethernet Frame: Entire thing (MACs, IPs, Ports, Data, FCS)
    * IP Packet: IPs, Ports, Data
    * "TCP Segment" / "UDP Datagram": Ports, Data
- Well known ports: 0-1023; Registered ports: 1024-49151; Ephemeral ports: 49152-65535
    * 20/21 FTP; 22 SSH; 23 Telnet; 25 SMTP; 53 DNS; 67/68 DHCP; 80 HTTP; 110 POP3; 137/139 NetBIOS; 143 IMAP; 161/162 SNMP
    * 389 LDAP; 443 HTTPS; 445 SMB/CIFS; 3389 RDP
    * Cross-LAN is detected when the subnet mask doesn't match up; 255.255.255.0 only varies last digit on LAN
- Uses MAC addresses; 48bit addressing with 12 hexadecimal characters; each network card has a unique one
    * First 6 characters are issued; rest are chosen by company
- Hub is a repeater; repeats ethernet frames to EVERYONE in the LAN
- Switch keeps track of which MAC is in which port, then when ethernet frame comes in, it only sends it to the correct port
    * Max theoretical is 1024 computers on a single switch; max realistic is 30-40
- Router does more than a hub/switch; it can connect multiple LANs (hub/switch only live inside one LAN)
    * Uses logical addressing instead of hardware (MAC) addressing
- CAT5: 100Mbps; CAT5e: 1Gbps; CAT6: 1Gbps over 100m, 10Gbps over 55m; CAT6a: 10Gbps over 100m
    * Fiber: multimode (LED) vs single mode??? (lasers???)
- PVC (non-plenum) cable: burnable, don't put into ceiling/floor; Plenum can go into ceiling/floor; Riser "rises" between floors; Direct burial cable (buried)
- UTP/STP cables and connectors: two standards (T568A/T568B), straight through (A-A) and crossover (A-B), crossover allows direct computer connection/comms
    * A: Brown-whbrn-Orange-whblu-Blue-whora-Green-whgrn; B: Brown-whbrn-Green-whblu-Blue-whgrn-Orange-whora
- IPv6: 8 groups, 7 colons; can drop leading zeroes in a group; can combine three consecutive 0 groups into double-colon
    * fe80:0000:0000:1234:0000:0000:0000:1234 -> fe80:0:0:1234:0:0:0:1234 -> fe80:0:0:1234::1234
    * Link-local: always starts with fe80:0:0:0, second half is generated by the system itself (on boot)
    * Global Unicast Address (internet address): router assigns first half, computer generates second half

# 802.11
- Based on the unlicensed ISM bands (2.4GHz, 5GHz)
- 802.11a: 54 Mbps on 5GHz
- 802.11b: 11 Mbps on 2.4GHz
- 802.11g: 54Mbps on 2.4GHz
- 802.11n: 150Mbps on both (WiFi 4)
    * MIMO: WAP hones its signal direction at the device
- 802.11ac: FAST on 5Ghz (WiFi 5)
    * MU-MIMO: multiple MIMO
- 802.11ax: FASTFAST on 6GHz (WiFi 6)
- Omnidirectional: "fuzzy bubble", large area
- Dipole: "squashed donut", large area
- Patch: "half of fuzzy bubble", one direction
- Highly directional (Yagi): "football"

# Special Protocols
- SMTP - port 25 - universal client-to-server
- POP3 - port 110 - requires clientside setup of folders (simplistic)
- IMAP - port 143 - copies serverside folders down to client (convenient)
- VPNs: PPTP, L2TP, IPsec