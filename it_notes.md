## Overview
- OS is comprised of kernel files and device drivers; interfaces with hardware
    * Programs provide a user interface and configuration tools
    * Top level is the desktop (first thing seen on startup, do all from here)
- Registry (a database) contains all Windows configuration data
- Windows Settings is the main administrative interface; control panel is legacy
- Accounts settings: accounts, emails, sign-in, domain connection, family, sync
    * Legacy version is User Accounts in the control panel
- User accounts are associated with "profiles"
    * Profiles contain default folders and configuration
- File Explorer Options in control panel allows Explorer customization
- Indexing Options in control panel is also useful for search
- System Settings: I/O devices, power, remote desktop, notifications, clipboard

## OS Considerations
- Check hardware limitations
    * CPU, chipset, and RAM must be able to run the OS. (ex: 64bit CPU, 4gb RAM)
- Check application and driver support/backward compatibility
- Backup files and user preferences
- Obtain third-party drivers
    * The OS setup media might not contain drivers for certain hardware devices. 
    * This is typically only an issue where the computer uses a RAID controller.

## Boot Styles
## Master Boot Record (MBR)-Style Partitioning
- MBR stores a partition table in the first 512-byte sector on the disk
    * This keeps track of partitions
- A given physical disk can contain up to four primary partitions
    * Any one of the four can be marked as active, and therefore made bootable
- Each partition can host an OS, files, or more
    * A partition can be separated into infinite logical (non-boot) drives, too
- The start of primary partitions have boot sector / partition boot record (PBR)
- Active partition: its boot sector gets a record pointing to the OS boot loader
    * In Windows, the active partition is "system partition" / "system reserved"
- Boot partition: The drive containing the Windows operating system files
    * Usually just the active partition, but can be in an extended partition
- With MBR, the system firmware must be set to use the legacy BIOS boot method
    * If the boot method is set to UEFI, the disk will not be recognized as boot
## GPT-Style Bootboot
- Globally unique identifier (GUID) partition table (GPT) style 
- Provides a more up-to-date scheme to address some of the limitations of MBR
- Supports more than four primary partitions (Windows allows up to 128)
* GPT also supports larger partitions (2 TB+) + backup copies of primary ones
* A GPT-style disk includes a protective MBR for compatibility with old systems
- GPT requires UEFI setting; if set to BIOS, disk will not be recognized as boot



<!-- 
#     #                                   
#     # #####  #    # #    # ##### #    # 
#     # #    # #    # ##   #   #   #    # 
#     # #####  #    # # #  #   #   #    # 
#     # #    # #    # #  # #   #   #    # 
#     # #    # #    # #   ##   #   #    # 
 #####  #####   ####  #    #   #    ####   
 -->

# Ubuntu

## Ubuntu Installation
- Install using the UI
- Open terminal
- `sudo apt update`
- `sudo apt install -y openssh-server`



<!-- 
#     #                                      
#  #  # # #    # #####   ####  #    #  ####  
#  #  # # ##   # #    # #    # #    # #      
#  #  # # # #  # #    # #    # #    #  ####  
#  #  # # #  # # #    # #    # # ## #      # 
#  #  # # #   ## #    # #    # ##  ## #    # 
 ## ##  # #    # #####   ####  #    #  ####   
-->

# Windows

## System Objects
- Access to data files is typically mediated by system objects
- These are shown in the left-hand navigation pane in File Explorer
- These don't actually store files/folders; it's called "logical storage"
### User account
- Object contains the signed-in account profile's personal data folders
### OneDrive
- Shows the files and folders saved to your cloud storage service
    * Only if you're signed in to the service
### This PC
- Contains fixed disks / removable storage drives attached to the PC
    * This includes the user profile's folders
### Network
- Contains computers, shared folders, shared printers available over the network
### Recycle Bin
- Contains files/folders marked for deletion; allows recovery

## Drives and Folders
- Where the actual data resides
- C: drive is the main drive for files (A: is for floppy disks!)
- A drive's root directory is marked as a backslash: C:\
### Root Directory: Windows
- Contains drivers, logs, add-in apps, system/config files (System32), fonts...
### Root Directory: Program Files/Program Files (x86)
- Subdirectories for installed applications software
    * 64-bit Windows: a Program Files (x86) folder stores 32-bit applications.
### Root Directory: Users
- User profiles and data stored here; each has NTUSER.DAT (user's registry data)

## Network Settings
### Network & Internet
- Modern settings app used to view network status, change the IP address properties of each adapter, and access other tools
### Network Connections (ncpa.cpl)
- Control panel applet that shows status information
### Advanced sharing settings
- Control panel applet that configures network discovery (allows detection of other hosts on the network) and enables or disables file and printer sharing.
### Windows Defender Firewall
- Determines which processes, protocols, and hosts are allowed to communicate with the local computer over the network.
- Windows Security Settings app and the applet in Control Panel allow the firewall to be enabled or disabled.
- Complex firewall rules can be applied via the Windows Defender with Advanced Security management console.
### Internet Options
- The Internet Options control panel applet exposes the configuration settings for Microsoft's Internet Explorer (IE) browser.
- The Security tab is used to restrict what types of potentially risky active content are allowed to run.
- However, IE is end of life.
- You are only likely to have to use Internet Options and IE where there is an internal website that has not been upgraded to work with a modern browser.

## Device Manager
- Device Manager (devmgmt.msc)
- Allows view/edit of properties of installed hardware
- Can change hardware config settings, update drivers, or remove/disable devices
- Disk Management Consolde displays a summary of fixed/removable disks
    * HDDs, SSDs, optical drives
- HDDs and SSDs can be divided into "logical" partitions (partition = a volume)
- Disk 0 typically holds the operating system
    * Three volumes on this: boot files (EFI), OS files (C:), and recovery
- Initializing disks uses master boot record (MBR) or GUID Partition Table (GPT)
- Partitioning: disk has at least one partition, empty space can create more
- Formatting: truncates drives; NTFS (Windows), FAT32 (small removable drives)
- Repartitioning: up/downsizing existing partitions depending on space available
- Dynamic disks: basically RAID setups

## Disk Maintenance
- Disk Management console (diskmgmt.msc)
    * Init new drives, partitioning, formatting
- Fragmentation: files fragment across clusters
- Capacity: read performance drops at > 80% drive fill
- Damage: sector corruption, memory circuitry degredation, etc
- Once a month, and before installing software, run the following tools
### Disk Defragmenter
- Defragment and Optimize Drives tool (drfgui.exe)
- Makes it easy for the disk controller to read the disk (write simple values)
- Can be used to speed up the performance of HDDs

## Task Scheduler
- Task Scheduler (tasksch.msc)
- Name says it all... and activity is logged, so you can dig in to see issues

## Local Users and Groups
- Local Users and Groups console (lusrmgr.msc)
- Advanced interface for create/modify/disable/delete user accounts
- Can also reset account passwords

## Certificate Manager
- Certificate Manager console (certmgr.msc)
- Shows installed certificates, allows request/import of new certificates
- Personal folder has user account's certificates
- Trusted Root Certification Authorities has "trusted" certs (Windows Update)
- Third-party Root Certification Authorities has "trusted" certs (not MS/local)

## Registry Editor
- Registry Editor (regedit.exe)
- Registry: a set of five root keys, containing computer/user databases
- HKEY_LOCAL_MACHINE (HKLM) database is system-wide settings
- HKEY_USERS database is individual user settings ex: desktop personalization
- HKEY_CURRENT_USER is a subset of HKEY_USERS for just the logged-in account
- Registry database is stored in binary files ("hives")
    * Hive: a single file, a .LOG file (transactions), a .SAV file (key copy)
    * Usually at C:\Windows\System32\Config; NTUSER.DAT (hive file) is elsewhere
- Can export a portion of the registry via File > Export Registry File (regedit)
### Group Policy Editor
- Group Policy Editor (gpedit.msc)
- Updating the registry, especially via administrative templates
### Local Security Policy
- Local Security Policy editor (secpol.msc)
- Edit the registry

## Microsoft Management Console
- Microsoft Management Console (MMC)
- Container for one or more snap-ins (ex: devmgmt.msc, diskmgmt.msc, gpedit.msc)
- The MMC command allows you to create a console w/ personally-selected snap-ins

## System Information
- System Information tool (msinfo32.exe)
- Produces a comprehensive report of the system's hardware/software components
### Event Viewer
- Event Viewer console (eventvwr.msc)
- For viewing/managing logs on Windows
### Default System Logs
- Logs are max 20 MB (can change this in properties)
- System log: core OS logs, ex: service load fails, hardware conflicts, ...
- Application log: non-core processes/utilities, ex: app installers
- Security log: audit data
- Setup log: events during installation
- Many more
### Sources and Severity
- Critical: highest-priority for the source application (halts/freezes)
- Error: next after critical
- Warning: can potentially lead to error/critical if not remediated (disk space)
- Information: noteworthy but not requiring action
- Audit success/failure: success is good authentication, failure is bad password

## Task Manager
- Task Manager tool (taskmgr.exe)
- Monitoring computer resources; accessible by CTRL + SHIFT + ESC
- Can end tasks forcefully
- Can prioritize tasks at the CPU level
### Performance
- Performance tab: CPU, memory, disk, network, GPU subsystems
- CPU: number of cores / logical processors, multisocket, virtualization
    * Utilization, system uptime, count of processes/threads/handles
- Memory: slots in use, speed, usage statistics
    * In use (RAM), Committed (all), Cached (caching)
    * Paged / non-paged pool (pagefiles; usually OS, driver memory usage)
- Disk: type and capacity, statistics for active time, response time, read/write
- Network: send/receive throughput for the active network adapter (Wifi/Eth)
    * IP address, MAC address, SSID (wireless), type (802.11), signal strength
### App History
- App History tab: usage info for Microsoft Store apps
### Startup
- Startup tab: choose which programs will launch when the computer starts up
- Use `shell:startup` in the Run command box to access this (or use taskmanager)
### Users
- Users tab: see who is logged on, their resource utilization; can log them off
### Services
- Services tab: monitors state of all registered background processes
- Service: a Windows process that doesn't require user interaction (background)
- Can disable services to (sometimes) improve system performance
- Can troubleshoot programs by seeing if their service is down / not working

## Resource Monitor
- Resource Monitor (resmon.exe)
- Shows enhanced version of snapshot monitoring from task manager
- Graphs, resource performance, key statistics, # of faults, more
### Performance Monitor
- Performance Monitor (perfmon.msc)
- Real-time charts of system resources
- Great for seeing bottlenecks in a system (high-utilization, longer runs, etc)
- Can create log files / measurements using this; called "data collector sets"
    * Counter log: health of resources; Trace log: resource behavior/actions
- Objects: processor, physical disk, memory, paging file

## System Configuration Utility
- System Configuration Utility (msconfig.exe)
- Modify settings/files that affect boot/load of Windows
- Great for *testing* configurations for diagnostic purposes, rarely permanent
- Configure a startup mode in General: "normal", "diagnostic", "selective"
- Boot: choose default OS, boot options (safe mode), boot options screen timeout
- Services: choose services to run at startup (shows date of changes, too)
- Tools: shortcuts to admin utils (System Information, Regedit, Perfmon, etc)

## Command Prompt
- Command Prompt (cmd)
- Soon to be called Terminal in Windows 11
### CMD Commands
- Exit CMD: `exit`, `quit`, or CTRL+C
- Clear screen: `cls`
- Help: `help`
- Help for a command: `command_here /?`
- List files in a location: `dir`
    * Specify files to list using wildcards, ex: `dir *.exe` (add flags after)
    * Use `/o:n` to order files by name (`n`); `s` size; `e` extension; `d` date
    * Use `/t:c` to order files by create date; `a` last access; `w` modified
    * Use `/a:r` to show read-only files; `h` hidden; `s` system; `a` archive
- Move to a new directory: `cd`
    * Shortcuts: `cd Documents`, `cd ..`, `cd \`, `cd \Windows` (absolute)
- Change drive: `C:`, `D:`, etc just by itself
- File movements: `move src dst`, `copy src dst`, 
- Multi-directory move: `xcopy [src1, src2, ..] [dst1, dst2, ...]`
    * Microsoft recommends `robocopy` (robust copy) instead of xcopy
- Make new directory: `md`
- Remove directory: `rmdir` (use `/q` to suppress confirmation messages)
    * Force removal of directory: `/s` (just like `rm -rf`)
- Disk partition: `diskpart` -> `select disk 0` -> `detail disk`
    * Also can `select partiton 0`, `select volume 0` (and detail)
    * Also can `assign` (change drive letter), `delete`, `extend`
    * Use `exit` to quit disk partition
- Formatting: `format drive_letter:/X:SYS` (SYS is `NTFS`, `FAT32`, `EXFAT`)
- Check disk: `chkdsk X:` with optional flags `/f` (fix), `/r` (recover)
    * These take awhile; be careful!
- Shut down computer: `shutdown /s`, `/t 60` (60sec delay), `/r` (restart)
    * Shut down immediately: `shutdown /s /t 00`
- System file checker: `sfc` 
    * `/scannow`, `/scanonce` (after restart), `/scanboot` (after each boot)
- Check Windows version" `winver`
#### Windows Aliases
- `%userprofile%` goes to C:\Users\username_here

## Operating Systems
- Business client: OS in a centrally-managed business domain network
- Network Operating System (NOS): OS to run servers in business networks
- Home client: OS on a lone machine or a workgroup network (home / small office)
- Cell phone / Tablet: OS on prtable device (must be touch-operated)
- Microsoft Windows is used for all of the above
    * Win10, Win11 on clients and smartphone/tablet
    * Windows Server 2019, Windows Server 2022 for NOSs
- macOS: only Apple products (based on UNIX)
- UNIX: fundamentally-supports all of the above; is not itself a modern OS
- Linux: UNIX with completion factors to make it an OS
    * Standard release (versions) vs rolling release (no versions; "if stable")
- Chrome OS: derived from Linux, uses web applications primarily
- iOS: Apple smartphones, is closed source (also see iPadOS)
- Android: based on Linux, is open source
### Windows File System Types
#### NTFS
- NTFS: New Technology File System, proprietary by Microsoft, used for Windows
- 64 bit addressing (large volumes/file sizes; max volume is 16 Exabytes!)
- Journaling: write actions are re-read, verified, and logged
    * When problems occur, sectors are marked as "bad" and the data is relocated
- Snapshots: "Volume Shadow Copy Service" makes read-only copies (file versions)
- Security: file permissions/ownership, file access audit trails, more
- POSIX Compliance: (UNIX compatibility) case-sensitive naming, hard links, more
- Indexing: catalog of file and folder locations and properties
- Dynamic Disks: multiple physical disks can be combined into volume(s)
#### FAT32
- FAT32: File Allocation Table with 32-bit addressing (max volume is 2 TB)
- Mainly used for formatting; no reliability/security features of NTFS
#### exFAT
- 64-bit version of FAT32
- Mainly used for removable hard drives / flash media
- Supports large volumes and file sizes like NTFS (max volume is 128 petabytes)
- Supports access permissions but not encryption
### Linux/macOS File System Types
- Supports FAT32 and exFAT (Linux calls it VFAT), but not NTFS
- NFS (Network File System) allows mounting remote storage devices to local sys
#### ext3, ext4
- Used for formatting partitons on mass storage devices
- ext3: 64-bit file system with journaling
- ext4: ext3 but better
#### Apple File System
- Apple File System (APFS), proprietary for Apple Mac workstations/laptops
- Supports journaling, snapshots, permissions/ownership, encryption