# Neat Stuff
- Complete list of Windows shortcuts: https://support.microsoft.com/en-us/windows/keyboard-shortcuts-in-windows-dcc61a57-8ff0-cffe-9796-cb9706c75eec
- Ctrl+X for management shortcuts (can also right-click Start menu button)
- Ctrl+V to see clipboard history
- Windows+Space to change keyboard language
- Individual Settings app pages can be accessed from the Run dialog using uniform resource indicators such as ms-settings:system
    * Control Panel applets can be opened using commands in the form control ncpa.cpl
- Server administration tasks: Restarting, Remapping, Installing, Updating, Backups, Gathering

<br>

# Course Tasks
## You Should Be Able To...
- You should be able to use the Settings and Control Panel interfaces to configure Windows for different business-, home-, and user-requirements scenarios.
- You should be able to use management consoles and command-line utilities to manage Windows users, devices, apps, and performance.
- You should be able to explain differences between OS types, versions, and editions to identify a suitable choice of OS for a given scenario.
- You should be able to support diverse operating system and application software deployments by applying appropriate considerations and troubleshooting processes.
- You should be able to manage and troubleshoot Windows network settings, configure users and share permissions in workgroup environments, and summarize Active Directory/domain concepts.
- You should be able to identify features of Linux and macOS to help support diverse OS environments.
- You should be able to explain common social-engineering attacks, threats, and vulnerabilities; configure appropriate wireless security protocol/authentication and firewall settings on a SOHO network; and summarize physical security measures.
- You should be able to configure workstation and Windows OS settings to meet best practices for security; install and configure secure browsers; and detect, remove, and prevent malware using the appropriate tools and best practice procedures.
- You should be able to explain common methods for securing mobile and embedded devices and troubleshoot common and security-related mobile OS and app issues.
## Guidelines for Configuring Windows
- Document standard procedures and work instructions to make best use of Windows Settings and Control Panel for different tasks:
- Verify OS configuration options, version information, and security via System and Update & Security settings.
- Configure sign-in and desktop options via Accounts/User Accounts, Ease of Access, Time and Language, Personalization, and Privacy.
- Set up hardware via System, Devices, Sound, Devices and Printers, Device Manager, and Power Options.
- Configure file browsing and search via File Explorer Options and Indexing Options.
- Set up apps and Windows features via Apps, Mail, Gaming, and Programs and Features.
- Configure networking via Network and Internet, Network and Sharing Center, Windows Defender Firewall, and Internet Options.
- Use Administrative Tools to access advanced configuration consoles.
## Guidelines for Managing Windows
- Document standard procedures and work instructions to make best use of Windows management consoles and command-line utilities for different tasks:
- Use Device Manager, Disk Management, Disk Defragmenter, Disk Cleanup, chkdsk, diskpart, and format to ensure hardware availability, reliability, and performance.
- Use Local Users and Groups and Certificate Manager to manage users, personal digital certificates, and trusted root certificates.
- Use Group Policy Editor and Registry Editor for fine-grained settings configuration.
- Use System Information, Event Viewer, and winver to audit software and hardware inventory and monitor logs.
- Use Task Manager, Resource Monitor, Performance Monitor, System Configuration, shutdown, and sfc to optimize process, service, and startup performance.
- Use cd, dir, md, rmdir, x:, copy, xcopy, and robocopy to manage the file system from the command prompt.
## Guidelines for Supporting Operating Systems
- Follow these guidelines to support use of multiple operating system types in a home or business environment:
- Establish requirements for workstation (Windows, Linux, macOS, Chrome OS) and cell phone/tablet (iOS, iPadOS, Android) operating systems given devices used in the environment.
- Ensure that an appropriate edition is selected when deploying Windows:
    * 32-bit versus 64-bit support.
    * RAM and CPU limits between Home, Pro, Pro for Workstations, and Enterprise editions.
    * Features supported by Pro that are not available in Home (RDP server, BitLocker, gpedit.msc) and features supported by Enterprise editions that are not available in Pro.
    * OEM, retail, and/or volume-licensing availability.
- Monitor vendor life-cycle policies (update limitations and EOL announcements) to plan OS and device upgrade and replacement cycles.
- Plan for compatibility concerns between operating systems, including filesystem formats (NTFS, FAT32, ext3/ext4, APFS, exFAT), software, networking, and user training/education on different desktop styles.
## Guidelines for Supporting Windows
- Develop a checklist and work instructions to govern deployment of clean install of new operating systems:
    * Boot methods for attended (USB external drive versus optical media) and unattended (USB/disk versus remote network installation).
    * Partitioning (MBR versus GPT) and file system requirements for drive formatting or image-based installation.
- Develop a checklist and work instructions to govern deployment of in-place upgrades:
    * Availability and product life cycle, including feature updates.
    * Considerations (backup files and user preferences, app and driver support/backward compatibility, and hardware compatibility).
- Prepare for recovery scenarios by creating boot media/internal partitions, backup images, and backup user files/preferences.
- Develop a checklist and work instructions to govern deployment of new applications:
    * Establish system requirements for applications (CPU, 32-bit vs. 64-bit, RAM, dedicated graphics card vs. integrated, VRAM, storage, and external hardware tokens).
    * Establish application to OS compatibility.
    * Identify available distribution method (physical media vs. downloadable or ISO mountable) and ensure trustworthy sources.
    * Assess impacts to business, operation, network, and device.
- Develop a knowledge base to document steps to resolve Windows OS issues:
    * Symptoms including BSoD, sluggish performance, boot problems, frequent shutdowns, services not starting, applications crashing, low memory warnings, USB controller resource warnings, system instability, no OS found, slow profile load, and time drift.
    * Tools and techniques including reboot, restart services, uninstall/reinstall/update applications, add resources, verify requirements, sfc, repair Windows, restore, reimage, roll back updates, and rebuild Windows profiles.
## Guidelines for Managing Windows Networking
- Document the Internet Protocol (IP) addressing scheme to identify appropriate subnet mask, gateway, and DNS settings. Identify hosts that would benefit from static addressing, but plan to use dynamic configuration for most hosts.
- Document wired and wireless connection support and any special considerations, such as proxy settings for Internet access, metered connection configuration for WWAN, and VPN type and server address.
- Use setup and monitoring checklists and tools to ensure proper configuration of local OS firewall settings, including public versus private network types and application restrictions and exceptions.
- Use the principle of least privilege to configure user accounts within security groups with the minimum required permissions. Ensure that UAC is enabled to mitigate risks from misuse of administrator privileges.
- Consider replacing password-based local login and SSO authentication with MFA and/or passwordless authentication and sign-in verification, using email, hard token, soft token, SMS, voice call, and authenticator applications.
- Design ACL permissions on folders to support policy goals, taking account of share versus NTFS permissions and inheritance.
- Make training and education resources available to users to help them use File Explorer navigation and select appropriate network paths for accessing file shares, printers, mapped drives, and home folders.
- Develop a knowledge base to document use of command-line tools to resolve common issues (ipconfig, ping, hostname, netstat, nslookup, tracert, pathping, net user, net use, gpupdate, and gpresult).
- Consider that a large or growing network might be better supported by implementing an Active Directory domain with support for network-wide security groups, OUs, group policy, login scripts, and roaming profiles/folder redirection.
## Guidelines for Supporting Linux and macOS
- Create knowledge base support documentation to assist users and technicians with command-line management of the following Linux features:
    * Shell/terminal concepts and man help system.
    * Directory navigation and file management (nano, cat, pwd, ls, mv, cp, rm, df, grep, find, and backups/cron).
    * User and permissions management (su/sudo, chmod, chown, and Samba file sharing).
    * Package and process management (apt-get, yum, ps, top, and antivirus/integrity checking for updates/patches).
    * Network management (ip and dig).
- Create knowledge base support documentation to assist users and technicians with use of the following macOS features:
    * User interface features (Dock, Finder, Spotlight Search, and Terminal).
    * User System Preference settings and configuration (Apple ID and corporate restrictions, privacy, accessibility, Keychain, Gestures, and Multiple Desktops/Mission Control).
    * Package and process management (installation and uninstallation of applications and .DMG, .PKG, .APP file types, antivirus/integrity checking, updates/patches, and force quit).
    * Disk and file management (iCloud, Time Machine backups, Remote Disc, Disk Utility, and FileVault).
    * Network and devices settings (Displays, Networks, Printers, and Scanners).
## Guidelines for Configuring SOHO Network Security
- Develop a knowledge base to support technicians, developers, and end-users with information about common attacks, threats, and vulnerabilities:
    * Vulnerabilities such as non-compliant systems, unpatched systems, unprotected systems (missing antivirus/missing firewall), EOL OSs, and BYOD.
    * Threats and attacks such as insider threat, DoS, DDoS, zero-day, spoofing, on-path, brute-force, and dictionary, SQL injection, and XSS.
    * Social engineering attacks such as impersonation, evil twin, phishing, vishing, whaling, shoulder surfing, tailgating, and dumpster diving.
- Create a home-router deployment checklist to ensure secure and reliable configuration such as physical placement, change default passwords, static WAN IP, firmware update, changing SSID, disabling SSID broadcast, changing channels, encryption mode (WPA2 and TKIP or AES versus WPA3), and disabling guest access.
- Create a home-router firewall configuration checklist that includes disabling unused ports, IP filtering, content filtering, port forwarding/mapping, DHCP reservations, UPnP, and screened subnet.
- Consider the requirements for upgrading wireless authentication to use enterprise methods such as multifactor and RADIUS/TACACS+/Kerberos.
- Document building and campus physical security methods to guide selection of appropriate controls:
    * Bollards, fences, access control vestibules, magnetometers, and guards.
    * Alarm systems, motion sensors, video surveillance, lighting.
    * Door and equipment locks (badge reader, key fobs, smart cards, keys, and retina/fingerprint/palmprint biometric scanners.
## Guidelines for Managing Security Settings
- Create checklists for deploying workstations in hardened configurations and monitoring continued compliance:
    * Password best practices (length and character complexity requirements, expiration requirements, and BIOS/UEFI passwords).
    * Account management policies (restrict user permissions, restrict login times, disable guest account, use failed attempts lockout, use timeout/screen lock, and disable AutoRun/AutoPlay).
    * Antivirus and firewall settings and updates, using built-in Windows Defender or third-party products.
    * File and/or disk encryption, using built-in EFS/BitLocker or third-party products.
    * Secure browser and extension/plug-in installation via trusted sources and configuration of security settings (pop-up blocker, clearing browsing data, clearing cache, private-browsing mode, sign-in/browser data synchronization, and ad blockers).
- Develop training and awareness programs to support end-user best practices (use screensaver locks, log off when not in use, secure/protect critical hardware, and secure PII/passwords), threat awareness, and secure connection/certificates identification.
- Develop a knowledge base to classify malware types (Trojans, rootkits, viruses, spyware, ransomware, keyloggers, boot sector viruses, and cryptominers).
- Develop a knowledge base to document tools (recovery mode, antivirus/anti-malware, software firewalls, and OS reinstallation) and steps to resolve common security symptoms (unable to access the network, desktop alerts, false alerts regarding antivirus protection, altered system or personal files, missing/renamed files, unwanted notifications within the OS, OS update failures, random/frequent pop-ups, certificate warnings, and redirection).
- Apply the CompTIA best practice model for malware removal: 1. Investigate and verify malware symptoms, 2. Quarantine infected systems, 3. Disable System Restore in Windows, 4. Remediate infected systems (a. Update anti-malware software and b. Scanning and removal techniques [safe mode/preinstallation environment]), 5. Schedule scans and run updates, 6. Enable System Restore and create a restore point Windows, and 7. Educate the end user.
## Guidelines for Supporting Mobile Software
- Establish policies and procedures to support a BYOD or corporate-owned provisioning model and profile security requirements, such as locator apps, remote wipe, device encryption, remote backup, antivirus, and firewalls.
- Configure a screen lock with an appropriate authenticated unlock method (PIN, fingerprint, or facial recognition) and failed-attempts restrictions.
- Establish policies and procedures to support secure use of Internet of Things (IoT) devices.
- Develop a knowledge base to document steps for resolving general mobile OS and app issues (app fails to launch, app fails to close, app crashes, app fails to update, slow to respond, OS fails to update, battery-life issues, randomly reboots, connectivity issues with Bluetooth/Wi-Fi/NFC/AirDrop, and screen does not autorotate).
- Develop a knowledge base to document security concerns (APK, developer mode, root access/jailbreak, and bootleg/malicious application spoofing) and steps for resolving mobile-security issues (high network traffic, sluggish response time, data-usage limit notification, limited/no Internet connectivity, high number of ads, fake security warnings, unexpected application behavior, and leaked personal files/data).

<br>

# Troubleshooting
## General Approach
- System information: Windows Settings -> About
- Issue with Windows native apps: `sfc /scannow` in Admin cmd
    * This is an excellent place to start for native Windows things
    * Should take ~10 minutes; will repair system things like task manager
    * Check CBS logs to see the results of the scan/repairs: C:\Windows\Logs\CBS\CBS.log
    * If this doesn't work, and OS is corrupted, hopefully you have a system restore point... or you may need clean reinstall.
- Windows unable to boot: System Restore
- Printer Issues: Search -> Printers | Services -> Queue | Print Spooler
- Device Issues: Search -> Device Manager -> Check/Fix Drivers
## Printer Issues
- Printer issue: Open document, click on Print, observe; if no printers available:
    * Search "printers" for the windows setting window, check available printers
    * Open Wordpad and try to Print; if no printer here as well, then it's system-wide
    * Try "open queue" on an available printer; if failed, need to start print spooler
    * Search "services" for the running Services, go to Print Spooler, turn on
    * Open queue should now work
## Updating/Troubleshooting Devices
- Device not working: check device driver in Device Manager
- Driver not found: Device Manager -> Right-click the device/"unknown"/"generic"/yellow-exclamation -> Properties -> General -> Update Driver
- Device never worked: ensure device is compatible with the OS, download drivers from manufacturer website; 64bit Windows **requires** 64bit drivers (not 32bit)
- Driver recently updated: Device Manager -> Right-click the device -> Properties -> Roll Back Driver
- Driver fine: maybe problem with USB controller; use Windows Update or vendor site to obtain latest chipset/system driver; uninstall USB controllers, reboot them
    * If this doesn't work, disable "USB selective suspend" power management for a specific port/device or system-wide
    * If *this* doesn't work, try a USB 2 port with low-bandwidth devices and retain USB 3 for only the high-bandwidth ones (or, use less devices!)
- USB controller resource warning: Too many USBs connected (USB hub with >5 devices)
## Boot Issues / System Corruption
- If a system keeps booting in Safe Mode or to CMD, check Boot tab of msconfig.exe to see if these options were made permanent
- "No boot device found"/"Invalid boot disk": often firmware is set to USB priority boot (change it), sometimes HDD/SSD disconnected (reconnect cable)
    * If this occurs intermittently, disk might be failing; if the system is older and this occurs intermittently, firmware might be having trouble finding drive
- "No OS found": boot device found but OS loader not found (might be faulty disk); run diagnostics/`chkdsk`
    * If still finding boot device but not OS loader, enter system setup + try modifying settings or reset to defaults;
    * If *still* finding boot device but not OS loader, use recovery CMD and run `bootrec /fixmbr` (BIOS/MBR) or `bootrec`+`fixboot` (UEFI/GPT)
        * `bootrec /rebuildbcd` will try to add missing Windows installations to the boot configuration database (BCD)
    * Might be an "active" partition issue; use `diskpart` to ensure system partition is marked as active and inactivate non-system partitions
- OS still won't launch: use options/recovery tools to access an environment in which to run tests/attempt fixes (ex: Safe Mode + `chkdsk`/System Restore/antivirus)
    * Advanced Boot Options: select startup mode; auto-displayed if boot fails, or press F8 before OS loads (BIOS), or reboot system (SHIFT+restart) (UEFI)
    * Recovery media/partition (when BIOS/UEFI fail) and WinRE (installs CMD to recovery partition -> `diskpart`, `sfc`, `chkdsk`, `bootrec`, `bcdedit`, `regedit`)
        * Recovery partition (hit F11 or ctrl+F11 on start for BIOS/UEFI) and use wizard (ex: **System Restore**) to repair install; **this uses existing backups**
        * System Restore (rstrui.exe) allows system config rollback, ex: registry / program installation/updates; doesn't restore/delete user files
            * Can also uninstall Windows updates using this, or you can: "Programs and Features" -> View installed updates -> select update -> uninstall
        * Restore Points (for System Restore) are created automatically (every 7 days), manually, or scheduled via Task Scheduler
        * Restoring doesn't reset passwords unless it's ran from product disk
        * Antivirus (boot issues could be due to malware)
    * System Restore / Startup Repair fail and cannot boot to a logon: use a system repair tool or reinstall/restore from data backup (tool depends on version)
    * Use Recovery Image: image system config/files; create one using Backup and Restore; best compression ratio is 2:1; choose in AdvancedBoot/SystemImageRecovery
    * Reinstall Windows: "Reset this PC" in recovery environment, "Keep my files"/"Remove everything", restarts/asks for admin account creds, reinstall
- Windows boots but GUI doesn't load / black screen: boot configuration maybe changed in msconfig
    * If msconfig wasn't changed, likely corruption of drivers/system files; try booting to Safe Mode and replacing graphics adapter driver
    * If no GUI even in Safe Mode, likely need to repair/recover Windows installation from backup
- Windows intermittently flashes black screen: might be fine (update is installing), indicated by continued disk activity and spinning dots (loading)
    * If black screen doesn't disappear, try Windows+Ctrl+Shift+B to see if system is responsive (should hear a beep / display might come back)
    * If the system does not recover from a black screen, then try searching for any currently known issues on support and troubleshooting sites. 
    * Frequent flashes: use `chkdsk` and `sfc /scannow`, or update/rollback graphics adapter driver
- Windows randomly freezes/shuts down/reboots with no error: usually one of these: overheating, power problem, CPU/chipset/RAM issue, corrupt kernel
    * Windows Memory Diagnostics: test RAM for errors; run from Administrative Tools / recovery environment, computer will restart/run test (F1 for options)
    * If error(s) found, make sure RAM is seated, retest -> remove RAM, add one back at a time, retest each -> if known-good RAM is "faulty", then MOBO issues
    * After above checks, use `sfc C: /f` to attempt repairs
- Windows boots *slowly*: identify what's causing the delay (driver/service load); try checking "Display highly detailed status messages" in registry and reboot
- Windows loads desktop after sign-in *slowly*: maybe corrupt user profile; create new user, copy all files into it except NTUSER.DAT, NTUSER.DAT.LOG, NTUSER.INI
- Above is working but other issues / OS is slow: might be malware, quarantine!
    * Missing/renamed files, new official-looking executables (ex: scvhost.exe, ta5kmgr.exe), altered system/personal files (timestamps indicate), changed perms
    * Browser: Redirection (DNS/HOSTS file corruption, search engine bad), Bad certss (indicates potential risk; untrusted CA, FQDN v cert mismatch, revoked cert)
- Windows works: can "refresh" (recopy system files, revert settings, can preserve personalization/data/Windows Store apps) or "reset" (delete everything incl OS
## Blue Screen of Death (BSoD)
- BSoD: Microsoft status screen that indicates an error from which the system cannot recover (also called a stop error). 
    * Blue screens are usually caused by bad driver software or hardware faults (memory or disk); Windows halts and displays BSoD
    * Other operating systems use similar crash indicators, such as Apple's pinwheel and Linux's kernel panic message.
- System Restore, Roll Back Driver, Update rollback -> Remove recent hardware / uninstall recent-add programs -> Run hardware diagnostics/`chkdsk`, scan for malware
- Check component cables/seating -> Check fans and chassis vents for dust and clean if necessary.
- Make note of Stop error code (Stop: 0x0...), look up code on support.microsoft.com/search for fixes/troubleshooting ("newsgroups" can help)
- If the system auto restarts after a blue screen (you can't read the error), open the Advanced Options menu, and select the Disable automatic restarts option.
    * This option can also be set from Advanced System Properties > Startup and Recovery Settings.
## App/Service Issues
- Service not starting: check Event Viewer / Services snap-in to investigate; manually start/restart service.. startup might've glitched/"stuck" it (delay service?)
    * If you disabled a service, it may break other services; a service may also have perms issues- services use user/service account perms- account password issue?
    * If service is a core service, check system files / scan disk for errors/malware; if it's for an application, try reinstalling the application
    * Can use regsvr32 to re-register the DLL that a service relies on
    * If antivirus, firewall, OS updates, virus definition updates, etc not working, might be malware; run antivirus scan
    * Finally, are you down a rabbit hole? Faulty uninstalls might leave "orphan" registry entries/startup shortcuts; use msconfig/regedit to find orphaned items
- Authentication failing: maybe time sync issues (some auth can't handle 30s/60s discrepancies); MOBO has real-time clock (RTC) chip, but it's unreliable/can drift
    * Server located away from client? Servers and clients can use Internet time sources, but clients may be set to use different sources than the servers!
    * Ideally, network services should be in a domain and use GPS-synced time services or Internet time; client sampling can help identify/resolve drifts
- Application crash: try to preserve the data before remediation (ex: MSOffice autosaves) -> try to give the process time to wake back up -> kill in taskmgr
    * After crash, check event logs to investigate; maybe the crash happens when trying to process a certain file, maybe not
    * If unable to determine the issue, maybe an update is available that resolves the crashing; or, uninstall/reinstall/repair application
        * Windows installer may fail to remove every file/registry setting; follow manual uninstall instructions to complete uninstall
    * If (popular) software/app isn't running properly, might be malware; run antivirus scan
## Network Issues
- Connection unplug/discon (duh).. Limited connectivity: adapter looks for DHCP, none found (APIPA 169.254.x.y).. No Internet access: can't leave local (DNS/router)
- Connectivity issues: restart app service -> restart computer/server (be mindful of downtime effect) -> reset device's network stack (Network & Internet -> Status)
    * Might be malware (slow/not-connectable internet); run antivirus scan
- `ipconfig`: Is adapter set to static, and if yes, is IP/mask/gateway/DNS correct? Is adapter set by DHCP, and if yes, is lease valid / can connect (DHCP issue)?
    * DNS issue: `ipconfig /displaydns` (see maps) -> `ipconfig /flushdns` (clear the DNS resolver cache, which may be out-of-date and cause problems)
    * DHCP lease missing/incorrect: `ipconfig /release AdapterName`->`ipconfig /renew AdapterName` (get fresh lease)
- `hostname`: Get name of local machine (name of server is required for client machines to access shared folders/printers)
- Local network issues: `ping 127.0.0.1` -> `ping your-workstation` -> `ping default-gateway` -> `ping remote-host`; success will show latency
    * Can ping IP addresses, DNS names (comptia.org), or FQDNs (sales.comptia.org); latter-two won't work if DNS server is unavailable
    * Try various hosts on local network (see if it's single-client or multiple); multiple hosts failing means application server/print device/net infrastructure
    * Reply from SenderIP Destination unreachable: got no ARP response (destination disconnected or configured as non-discoverable? maybe dupe IPaddress/bad mask?)
    * Reply from GatewayIP Destination unreachable: gateway has no forwarding info for that IP (router misconfig or destination network misconfig)
    * No reply (Request timed out): gateway sent, but no response (destination is down or configured not to respond)
- `tracert`: Routing performance (single-run latency), ex: `tracert 8.8.8.8`; `pathping`: Routing performance (average latency/packet loss), ex: `pathping 8.8.8.8`
    * Routing issue: `tracert`/`pathping` time out; ensure local router is connected to Internet -> restart router -> call ISP to see if there's network/DNS issues
- Above cleared: check firewall (blocking? bad proxy?), check DNS service (connect by IP but not name), check app/OS (no 127.0.0.1? service crash?)
    * DNS issue: `nslookup -Option Host Server` (host: host name/FQDN/IP, Server: DNS server (default used if this argument omitted); compare w/ other DNS server
- Port test: `netstat`; `-a` include UDP, `-b` process that opened port (`-o` for PID), `-n` numeric ports/addresses, `-e` and `-s` for Ethernet and protocol stats
## Performance Issues
- Check utilization -> check for updates -> defrag/trim disks -> disable startup items (msconfig/taskmgr) -> scan for virus -> check power/heat-saving CPU throttle
1. Check Task Manager; look for 90–100% utilization, find process causing issue; if svchost is the issue, it's Windows or security software
    * svchost: Windows Update/Installer, SuperFetch/Prefetch caching engine, Windows Telemetry data collection, Windows Search/Indexing, Windows Defender
2. Wait for high-utilization processes to complete; a mix of CPU/memory/disk activity is normal, a non-stop 0% or 100% disk activity may indicate process stalled
3. If the process or system continues to be unresponsive, restart the service or kill the task process
4. If restart/kill process and still issue, reboot computer or full-shutdown (power down, disconnect from power for 30s, power on; this clears caches/memory)
5. If after restart/shutdown still issue, disable process (if possible) and check with the software vendor for any known problems
6. If Windows displays Low memory error, maybe too many programs; isolate programs to see if one is causing the issue (might have memory leak)
7. If Windows displays Low disk space error, might need more storage; use Disk Clean-up to delete unnecessary files, watch for excessive logging/tempfiles
## Malware Removal
1. Investigate and verify malware symptoms.
2. Quarantine infected systems.
    * Admins should not log in
    * System should be physically/logically segregated or sandboxed; this includes removable media (USB)
3. Disable System Restore in Windows.
    * This includes any automated backup system; backup might be infected, too
4. Remediate infected systems:
    * Update anti-malware software.
    * Scanning and removal techniques (e.g., safe mode, preinstallation environment).
    * Taskmgr to kill suspicious processes; run terminal commands; regedit; msconfig Safe Mode boot; boot to recovery media / WinPE; remove disk, externally scan
    * Maybe completely reinstall the OS (clean/format disk)
5. Schedule scans and run updates.
    * On-access scanning (scan file when accessed), schedule scans
6. Enable System Restore and create a restore point in Windows.
    * Validate any other security-critical services and settings that might have been compromised by the malware; Verify DNS config, re-enable/reset firewalls
    * Create a fresh restore point or system image and a clean data backup.
    * Re-run antivirus
7. Educate the end user.
    * Passwords/account management, PC/mobile security features, social engineering threats, software threats, specific anti-phishing training
    * Spoofed comms indicators: Unexpected comm, inconsistent sender/reply-to, disguised links/attachments, copied text/images, exaggerated urgency/risk claims
    * Education about common social engineering and malware threats, including phishing, website exploits, and spam plus alerting methods for new threats.
    * Secure use of software such as browsers and email clients plus appropriate use of Internet access, including social networking sites.
    * Specific anti-phishing training to identify 
## Mobile Devices
- If rebooting the device does not fix an issue, use the following steps to troubleshoot specific problems. If these do not work, try a factory reset.
- OS Fails to Update: Use the vendor site to verify update is compatible with device; connect to power/wifi; restart device; try update; check free space
- Random reboots: Overheating, low battery, faulty battery (check battery health), check free space, check faulty apps
- Device slow to respond: high temp/low battery, inadequate compute/storage resources, bad apps (overutilizing memory, try reboot), recent apps, updates
- Screen doesn't autorotate: autorotate disabled? user touching screen? apps running that lock rotation? hardware fault? 
- App issues: force stop, clear app cache, reboot phone, check app compatibility, uninstall/reinstall; MDM might be preventing app
- Signal connectivity: signal strength (low battery!), config (airplane mode/disabled radio/etc, wifi/bluetooth creds), 802.11 support (WAP compatibility mode)
- Security: rooting/jailbreaking, app spoofing, apk/enterprise apps not from app store ("sideloading"), bootleg apps (copy/imitate real ones)
- Malware symptoms: ads, fake warnings, slow response time, limited/no internet (bot), unexpected app behavior (request odd perms); set up 2-step auth (data leak)
## Remote Access (RDP/VNC, SSH)
- To allow remote access to host: perms should be granted to accounts selectively, use encrypted connection, identity confirm (evil twin), server not vulnerable
- Remote Desktop Protocol (RDP): Settings > Remote Desktop > Select Users || Advanced Settings (choose RDP client); RDP runs on 3389
- Open Remote Desktop Connection (mstsc.exe), enter server IP or FQDN, choose whether to trust/inspect any cert presented (NLA authenticates *before* connection)
    * Also set username of remote host; locally, use .\username or host\username; for domains, use format domain\username
- Microsoft Remote Assistance (MSRA) allows use of RDP with minimal user work (passcodes); chooses port between 49152 to 65535
    * Quick Assist (ctrl+start+Q) does something similar to MSRA over port 443; requires Microsoft account though
    * Neither MSRA nor QA allow remote host to bypass local UAC; need to disable/disarm UAC
- SSH: port 22, encrypted channel for auth, public/private keys, key storage (need to clear unused keys!!)
- Remote Monitoring and Management (RMM): Tool for distinguishing between information streams (used by MSP)
- Unified Endpoint Management (UEM) / Mobile Device Management (MDM): Governing access control and authorization
    * Agent: report status, log, and inventory information to a management server (EDR); provide integration with support ticket/help desk systems; broker RDP
        * Agents need running OS to comm w/ mgmt server. Mgmt suite can use hardware controller (Intel vPro / AMD PRO) for out-of-band (OOB) mgmt, remote power-on
    * UEM/MDM allows remote network boot capability (wake on LAN (WOL)) plus ability to enter system firmware setup and deploy firmware updates and OS installs
    * UEM/MDM access control (prevent hosts w/ incorred OS version/update / health policies from connecting), allow live chat

<br>

# Operating Systems
- OS: kernel files / device drivers to interface with hardware, programs to provide a user interface / configuration tools
    * Kernel: the low-level code that mediates access to system resources (CPU, RAM, and input/output devices) for other processes installed under the OS
    * Shell: runs on the kernel to provide the user interface (interchangeable)
    * Compatibility: Device hardware, software, host-to-host data exchange (network), user training requirements, host hardware (ex: Win11 and TPM)
    * Vendor lifecycle: public beta (user feedback, ex: Windows Insider), supported (patches/features), extended support (no longer commercial), EOL
- Windows: 3.1 (16bit, crap) -> NT 4 (32 bit, secure network) -> 95, 98, Me (bad) -> 2000 , XP (flexible, secure, AD) -> Vista, 7, 8, 8.1 (Aero) -> 10, 11 (touch)
- Mac: only on iMac, Mac workstation, Macbooks, built on UNIX, no touchscreens; 10.15 (Catalina) -> 11 (Big Sur) -> 12 (Monterey)
- Linux distributions (kernel/shell): SUSE and Red Hat (subscription), Ubuntu (premium features), Fedora, Debian, Mint, and Arch (community supported)
    * Linux uses two release models: Standard (distinguishable versions, can be long-term support (LTS)) and Rolling (update once stable, no versioning)
- Chrome OS: Chromium offshoot, requires an internet connection, very lightweight/cheap, chromebooks/chromeboxes, hosts web apps and can run Android
## Installation
- OS install copies files from installation media to a partition on the target computer's fixed disk; hardware must be compatible/sufficient (CPU, chipset, RAM)
    * Windows' "Logo'd Product List (LPL)" / Hardware Compatibility List (HCL) shows OS-compatible hardware (your hardware *should* be on the LPL/HCL)
        * If hardware isn't on the LPL/HCL, try the included Hardware Advisor or check the hardware vendor's website to see if a driver is available
    * Typical hardware that might need drivers: RAID setup, Ethernet/Wifi adapter
- Attended installation: installer asks for choices; Unattended installation: answer file (this is configured via Windows System Image Manager) and often images
    * Answer file: product key, disk partitions, computer name, language and network settings (including whether to join a domain or workgroup), etc
    * Image: consistent, can contain the base OS and configuration settings, service packs and updates, applications software, and whatever else is required
- Clean install: target disk is repartitioned/formatted, need to backup data/settings before,
- In-place upgrade: doesn't repartition/format, need to uninstall incompatible apps / contingent backup data, Feature Update is similar process
## Boot
- Optical media (need priority boot, fast-obsolete), USB (need priority boot), Network/PXE (non-internet, DHCP manages), Internet (norm connect / DHCP manages DNS)
    * Windows' Media Creation Tool can create install media (external HDD/USB) from scratch
    * Preboot eXecution Environment (PXE) requires some space (download files) and some boot capability
    * Internet boot is often used for virtual machines
    * HDD/SSD (mass storage devices) require partitioning/formatting before use; 
- After install, internal hard drive (generally) used for default boot device (priority boot), other boot methods disabled (security measure)
- On startup, firmware runs Power-On Self Test (POST) to verify system components are functioning/exist, then finds boot device and passes control to boot loader
    * BIOS: firmware -> boot device -> MBR -> "active" partition boot sector -> BOOTMGR.EXE -> BCD (available OSs) -> system root -> WINLOAD.EXE (boot loader) -> ..
    * EFI: firmware -> boot device -> GUID partition table (GPT) -> EFI System Partition -> EFI boot manager (BOOTMGFW.EFI) / BCD -> WINLOAD.EFI (boot loader) -> ..
    * EFI/BIOS -> .. NTOSKRNL.EXE (kernel load) / HAL.DLL (hardware abstraction layer) / boot device drivers -> kernel -> init required processes -> WINLOGON
## Partitioning and Formatting
- OS must be installed to a partition formatted with a compatible file system; Windows has NTFS, Mac has APFS, Linux has ext3/ext4
    * Linux's default is Partition 1 holding the EFI System Partitioner (ESP) bootloader, other partition holds root file system and is formatted as ext4
- Partition information is stored on the disk in Master boot record (MBR, old) or GUID partition table (GPT, current)
    * Partitions can be discrete areas for user data file storage, storing log files, or hosting databases
- Master boot record (MBR): **BIOS**, partition table in the first 512-byte sector on HDD/SSD, holds information about partitions / OS boot loader
    * With MBR, HDD/SSD contains max 4 primary partitions (one -> infinite logical unbootables); each can be different OS/filesystem; any can be "active" (bootable)
    * Each partition starts with partition boot record (PBR); "active"/"system partition"/"system reserved"; logical partitions can't boot, can contain boot files
        * PBR: a record put into the active partition's boot sector that points to the OS boot loader
- GUID partition table (GPT): **UEFI**, modern, allows 128 partitions and >2tb partition sizes, includes MBR for backward compatibility
## File Systems
- File system: Structure for file data indexing/storage; created by formatting a partition on mass storage device, ex: HDD, SSD, thumb drive
- NTFS: Microsoft design for Windows; file-by-file compression, RAID support, advanced file attribute management tools, encryption, disk quotas
    * 64-bit addressing scheme (allows large volumes/file sizes), max 16 exabytes (usually 137gb-256tb)
    * Journaling (checks/logs/bad sector marking/recovery for data write) and Snapshots (Volume Shadow Copy Service)
    * Security (file perms/owner, file access audit trails, quota management, encrypting file system (EFS))
    * POSIX Compliance (UNIX/Linux compatibility via case-sensitive naming, hard links, etc)
    * Indexing (catalog of file/folder locations/properties) and Dynamic Disks (combining multiple disks' free space into a volume)
- FAT32: FileAllocationTable32bit (links between allocation units), for system partition/removable media, max vol 2tb, max file 4gb, no NTFS security/reliability
- exFAT: 64bit version of FAT, for removable hard drives / flash media, large volumes (128 petabytes) and file sizes (16 exabytes), access perms but no encryption
- ext3/ext4: Linux, 64bit, journaling, ext4 is best, network file system (NFS) for mounting remote storage devices
- APFS: Apple, journaling, snapshots, permissions/ownership, encryption
## Applications
- Applications generally require installation; can be installed from CD/DVD/USB/ISO (setup files stored there), downloaded from the Internet
    * Verify authenticity/integrity of internet-based apps (Windows: check digital signatures; Linux: compare published hash to self-calculated), scan for malware
    * Research "security advisories" associated with the software, ensure devs have a way to identify/resolve security issues
- Setup files pack the app executable(s), config files, media files; during setup, these are extracted/copied to the app directory (ex: Program Files)
    * Windows setup files: .msi or .exe; Mac setup files: .dmg or .pkg; Linux setup files: DEB+APT or RPM+YUM (or can be compiled from source code)
- Apps can affect system security/bandwidth; IT department should know all installed apps (unknown = "Shadow IT"); licensing, support, training reqs, ops impact
    * Orgs often use network-based install (clients/service accounts run setup file in shared folder); can use group policy objects (GPOs) to auto-run installs
    * Service accounts can have perms to do installs (while user can't), but user needs read/execute perms of app directory to run apps
- Any files or custom settings/preferences created for a specific user should be saved to the user's home folder/profile (not app directory)

<br>

# Windows
- 3.1 -> NT 4 -> 9x -> 2000 / XP -> Vista/7/8 -> 10 -> 11 -- Windows Server 2019 / 2022 are NOSs
- Based around the desktop, Start menu, taskbar, notification area
- 32bit/64bit: Processing modes referring to the size of each instruction processed by the CPU; 64 can 32, 32 can't 64; 32bit only allows 4gb RAM, 64bit allows more
    * 32bit 90's-onward, most now 64bit tho; Win10-2004+ and Win11 are 64bit; main 64bit: AMD64, EM64T (Intel); software is compiled in 32 or 64;
    * 64bit Windows requires 64-bit hardware device drivers authorized ("signed") by Microsoft; if vendor doesn't have 64bit driver, hardware device is unusable
- Workgroup/Domain: Workgroup PCs/laptops can share data and communicate, but each machine/its users db is managed separately; Domain Controller does all (gpedit)
- Bitlocker: user can encrypt all the information on disk drive (not on Home edition); only NTFS, encryption key can be stored on TPM chip or USB
- Remote Desktop Protocol (RDP): user can connect to the machine and operate it over a network; Home has RDP client (not server); port 3389
    * RDP: Application protocol for operating remote connections to a host using a graphical interface. The protocol sends screen data from the remote host to the client and transfers mouse and keyboard input from the client to the remote host. It uses TCP port 3389.
- Home: consumer/small office home office [SOHO] w/ workgroups; no domains; usually OEM (vendor deliver); multicore/hyperthreading w/o multi-CPU; max 128gb RAM
- Pro: small/medium businesses, OEM/retail/volume licensing, network admin has more control, domains/group policy, bitlocker, 128core, 2-way; also Education flavors
    * Pro for Workstations: more advanced hardware accepted, ex: more maximum RAM, persistent system RAM, 6tb RAM
- Enterprise: volume license, domains/gp, bitlocker, DirectAccess VPN, AppLocker software execution control, Microsoft Desktop Optimization Pack, 256core 4-way, 6tb
## Windows Notes (things I didn't already know)
- In 64-bit Windows, 32-bit applications run within a special application environment called WOW64 (Windows on Windows 64-bit). 
    * WOW64 replicates the 32-bit environment and translates its requests into ones that can be processed by the 64-bit CPU, memory, and file subsystems
- Windows' 64-bit shared system files (DLLs and EXEs) are stored in %SystemRoot%\system32 ; that is, the same system folder as 32-bit versions of Windows
- Files for the 32-bit versions are stored in %SystemRoot%\syswow64
## Windows 11 Desktop
- Windows 11 refreshes the desktop style
    * Center-aligned taskbar
    * Better spacing for touch control
    * Rounded corners. 
- It also makes the multiple desktops feature more accessible
    * Multiple desktops allow the user to set up different workspaces, 
    * Can have one desktop for business apps and one for personal apps
- The Settings app has no “home” page
    * Use the Menu icon to navigate between the headings groups
- In Windows 11, Privacy & security settings are collected under the same heading and Windows Update is a separate heading
- In Windows 11, Ease of Access settings are found under the Accessibility heading.
- Windows 11 is adding support for Android app stores as well
- In Windows 11, links to Windows Terminal (via Windows + X) replace the PowerShell shortcuts.
- In Windows 11, the command interface is redesigned as the Windows Terminal.

<br>

# Windows Configuration
- **Administering an OS means: configuring options, setting up user accounts, adding and removing devices and software**
- All system configuration is in Registry; Windows Settings and Control Panel edit the Registry
## Registry
- Database of Windows configuration settings (keys); five root databases: HKEY_CLASSES_ROOT, HKEY_CURRENT_USER, HKEY_LOCAL_MACHINE, HKEY_USERS, HKEY_CURRENT_CONFIG
- HKEY_LOCAL_MACHINE (HKLM) is system-wide settings, HKEY_USERS is individual user profiles/personalization, HKEY_CURRENT_USER is current user
- Registry db is stored in binary files (hives); A hive is a no-extension file, a .LOG file (transaction logs), a .SAV file (original key), and a .ALT backup file
    * Most of these files are stored in the C:\Windows\System32\Config folder, but the NTUSER.DAT hive file is stored in each user's profile
- Each root database contains subkeys (basically folders) and data items called value entries (basically files); can search for them with regedit's Find tool
    * A value entry has three parts: the name of the value, the data type of the value (such as string or binary value), and the value itself.
- Can export a registry with File > Export Registry File; it can be merged into another computer's registry by double-clicking the file or by calling it from script
## Windows Settings
### System Settings
- Configuring input/output devices, power, remote desktop, notifications, and clipboard (data copying)
    * Power: Control Panel has advanced settings
- **About page**: system information, nav to Device Manager, Remote Desktop, Advanced System Settings via righthand panel
    * **Advanced System Settings**: Performance, User Profiles, Startup/Recovery, Environment Variables
### Update & Security
- Update, Firewall, Antivirus, Backup, Troubleshoot, Recovery, Encryption
- Windows Update: Feature updates, critical patches, driver updates, etc
    * Feature updates are released periodically and introduces changes to OS features and tools
    * You can also perform an in-place upgrade from Windows 10 to Windows 11 if the hardware platform is compatible
    * Updates are recorded in Windows Event Viewer: Applications and Service Logs > Microsoft\Windows > WindowsUpdateClient > Operational log file
        * For failed updates, check this log (look up the error code in Microsoft Knowledge Base)
- Windows Security: shortcuts to Windows Defender virus/threat protection/firewall products
- Activation: Microsoft Product Activation is an antipiracy technology that verifies that software products are legitimately purchased
    * You must activate Windows within certain # of days after installation; after grace period, disables certain feature until the system is activated
    * Activation is over the Internet using a valid product key or digital license; Activation page shows current status / allows diff product key
### Accounts
- Editing current user (your info / sign-in options), adding user accounts (family & other users), joining domain (Access work or school)
    * Local accounts vs Microsoft Accounts (Sync settings, which enables SSO, cloud backup, syncs)
- Email & Accounts: It can be used to add email accounts/profiles and manage the .OST and .PST data files used to cache and archive messages
- Each user account has specific permissions and is associated with a profile; profile has documents/pictures/videos/music folders and configuration
    * The first user of the computer is configured as the default administrator account
- Control Panel also allows changing account names, switching account between Administrator and standard user, and adjusting UAC settings
### Privacy
- Diagnostics, Activity/Telemetry, Permissions
### Devices
- Bluetooth, USB, Printers, Touchpad, Keyboard
    * Note: Smartphone connection to Windows is specifically through Phone (not Devices)
- Plug and Play (most Windows-compatible devices): Windows automatically detects new device, locates its drivers, and installs/configures it with minimal user input
    * Sometimes might need to install the hardware vendor's driver before connecting the device; the vendor usually provides a setup program to accomplish this
    * More typically, device drivers are supplied via Windows Update
- Display/Sound (output) are in "System"; Input devices are in "Devices"; Advanced input/output device management is in Device Manager
### Gaming
- Game mode suspends Windows Update and dedicates resources to supporting the 3-D performance and frame rate of the active game app rather than other software or background services
- There are also options for managing captures, in-game chat/broadcast features, and networking with an Xbox games console
### Network & Internet
- A Windows host can be configured with 1+ network adapters (Eth, Wifi, Cellular, VPN); each adapter must have IP address and trust profile (public/private/domain)
    * Trust profile determines firewall settings (public is more restrictive than private/domain)
- Multiple Network & Internet interfaces; use Windows Settings one (also Network Connections applet, Network and Sharing Center)
    * Advanced sharing settings is a Control Panel applet that configures network discovery of other hosts on network, enable/disable file sharing
- Windows Defender Firewall: host-based filtering of specified processes/protocols/hosts; set firewall rules in "Windows Defender Firewall with Advanced Security"
### Obvious
- Phone, Network & Internet, Personalization, Apps, Time & Language, Ease of Access, Search
## Control Panel
- All of these can now be configured in Settings app
### Power
- Power management allows Windows to automatically/selectively/conditionally reduce or turn off the power supplied to hardware components. 
    * Examples: No user input for certain amount of time; lid close action; etc
- The Advanced Configuration and Power Interface (ACPI) specification is designed to ensure software and hardware compatibility for different power-saving modes
    * S0: Powered On
    * S1: Standby (Sleep); power to all components cut except RAM ("Modern Standby" also keeps network connectivity)
    * S3: Suspend to RAM (Sleep); power to all components cut except RAM
    * S4: Suspend to Disk (Hibernate); hiberfil.sys created, RAM contents and open+unsaved files added, file stored in root of boot volume, full shutdown
        * Windows Desktops create hiberfil.sys on Sleep too, and will switch to Hibernation after a defined period of time
        * Fast Startup, when in use, saves an image of RAM contents to hiberfil.sys and upon startup loads the image
    * S5: Soft Power Off (Shutdown)
    * G3: Mechanically Powered Off (Cut power)
- You can also set sleep timers for individual components, EX: display or hard drive (they enter power-saving time after defined period)
- Control Panel Power Options allows advanced configuration of power options / power plan templates
    * Examples: CPU states, search and indexing behavior, display brightness, USB selective suspend
### Apps and Features
- Windows Features: WSL, Hyper-V, Internet Printing, Print to PDF, More
    * WSL allows install of Linux distribution and apps
- Windows Store apps run in sandbox, bypass UAC, can be transferred with Microsoft accounts, more
- Third-party apps are installed with installer or MSI (requires admin / UAC)
- Can set startup/default apps, uninstall apps (should disable antivirus / watch uninstall logs for file remnants)
### Applets
- Good ones: Device Manager, Devices & Printers, Storage Spaces, Credential Manager, Programs and Features, User Accounts, Indexing Options, Recovery, Sound, Windows Defender Firewall, Default Programs, File Explorer Options, Windows Mobility Center
- Useless: File History, Keyboard/Mouse, RemoteApp and Desktop Connections, Troubleshooting, Work Folders, Autoplay, Fonts, Network and Sharing Center, System, Bitlocker, Internet Options, Phone and Modem, Date and Time, Region, Speech Recognition, Taskbar and Navigation

<br>

# Administrative Tools
- Shortcut in Control Panel to several advanced configuration consoles; the Microsoft Management Console can hold these snap-ins
## Custom Microsoft Management Console
- A Microsoft Management Console (MMC) is a container for one or more snap-ins; it can be saved back into the Administrative Tools folder as a MSC file
- Most MMC snap-ins can be used to manage either the local computer or a remote computer (a computer elsewhere on the network)
## Computer Management (compmgmt.msc)
- The default management console with multiple snap-ins to schedule tasks and configure local users and groups, disks, services, devices, and so on
## Defragment and Optimize Drives (dfrgui.exe)
- Maintain disk performance by optimizing file storage patterns; runs various operations to speed up the performance of HDDs and SSDs
- HDDs: defragmenting rewrites file data so that it occupies contiguous clusters, reducing required time for controller to seek over the disk to read files
- SSDs: instructs drive controller to run TRIM operation (controller finds OS-designated deletable data, then tags the blocks as writeable)
    * Defrag *can* happen on SSDs if the SSD holds the OS and the system protection feature Volume Shadow Copy service is enabled
- Windows automatically schedules the disk optimizer to run using Task Scheduler. You should check for any issues, such as it not running successfully.
## Disk Cleanup (cleanmgr.exe)
- Regain disk capacity by deleting unwanted files
- The Disk Clean-up (cleanmgr.exe) tool tracks files that can be safely erased to reclaim disk space. 
    * cleanmgr.exe: Windows utility for removing temporary files to reclaim disk space.
- These files include ones deleted but still available in the Recycle Bin and various temporary files and caches. 
- The tool can be run in administrator mode using the Clean up system files option to reclaim data from caches such as Windows Update and Defender.
## Event Viewer (eventvwr.msc)
- Review or export system, security, and application logs
- Default page shows summary of system status with recent errors / warning events collected for viewing
    * Left-hand pane groups log files into different categories; With a log file selected, the three-part middle pane shows details of the selected event 
    * The third pane contains useful tools for opening log files, filtering, creating a task from an event, and so on.
## Local Security Policy (secpol.msc)
- View and edit the security settings; password and account policies (not available on Home)
## Resource Monitor (resmon.exe) and Performance Monitoring (perfmon.msc)
- View and log performance statistics
## Registry Editor (regedit.exe)
- Make manual edits/additions to the database of Windows OS, device, and software configurations (keys) in the registry
    * Can backup the entire registry with regedit, too
## Services Console (services.msc)
- Start, stop, and pause processes running in the background
## Task Scheduler (taskschd.msc)
- Run software and scripts automatically/regularly according to calendar or event triggers; many of Windows's processes come with predefined schedules
    * Requires sufficient permissions for the selected account; otherwise the task won't run
- A task can be a simple application process (including switches, if necessary) or a batch file or script; can have multiple actions
- A trigger can be an event rather than a calendar date/time, ex: when the user signs in, when the machine wakes from sleep or hibernation
- All activity is logged so that you can investigate failed tasks

<br>

# Management Tools
- These are not snap-ins, so they won't be found in Administrative Tools
## Device Manager (devmgmt.msc)
- Device Manager allows you to view and edit the properties/configuration of installed hardware, update drivers, or remove/disable devices
    * Disabling drivers can improve system security or disable broken drivers temporarily in pursuit of a replacement
- Drivers stay after devices are disconnected; to remove the driver, before physically unplugging the device, right-click it and select Uninstall device
## Disk Management Console (diskmgmt.msc)
- Disk Management displays summary of fixed/removable HDDs, SSDs, and optical drives; allows initializing, partitioning, and formatting these drives
- Initializing disks: If you add an unformatted HDD, SSD, or thumb drive, you will be prompted to initialize it. 
    * You can choose whether to use the master boot record (MBR) or Globally Unique ID (GUID) Partition Table (GPT) partition style for the new disk. 
- Partitioning: Each disk must be configured with at least one partition. 
    * You can create a new partition by right-clicking on an area of unpartitioned space; you'll be prompted for allocation size and file system choice
- Formatting: A new partition must be written with a file system—typically NTFS—to allow Windows to write and read files; can choose volume label/size
    * The simpler FAT32 file system might be used for small, removable drives. 
- Repartitioning: Existing partitions can be expanded into unallocated space or shrunk/removed to gain unallocated space
- Configuring dynamic disks: If there is more than one disk available, a new dynamic volume can be configured (**software** RAID redundancy, ex: mirroring)
## Local Users and Groups Console (lusrmgr.msc)
- Provides an advanced interface for creating, modifying, disabling, and deleting user accounts + password resets (within auth/perm scope of local system)
- Security groups (ex: Administrators, Users, and Guests) enforces standardized permissions, such as the right to edit files in a shared folder
## Certificate Manager (certmgr.msc)
- Digital certificate: proves the identity of a subject, such as a user, computer, or service; guaranteed by the issuing certification authority (CA)
- Certificate Manager shows which certificates have been installed (user certs, root certs) and provides a mechanism for requesting and importing new certificates
- Personal folder: User certificates, used for authentication to a network access server, encrypting data, and adding a digital signature to documents/messages
- Trusted Root CAs: contains a superset of the certificates of all trusted issuers, ex: Microsoft’s own CA root, local enterprise CAs, third-party CAs
    * Most of these certificates are managed via Windows Update; Third-party Root CAs contains trusted issuers from non-Microsoft non-local-enterprise providers
- certmgr.msc manages certificates for the current user. There is also a computer certificate store, which can be managed via certlm.msc.
- Trusting an unsafe CA raises critical security vulnerabilities; in some cases, you may need to use Certificate Manager to remove compromised certificates
    * EX: a rogue CA cert may allow masquerading as legitimate bank/service and trick users into submitting a password (browser trusts the web server's cert)
- Third-party browser applications usually maintain a separate store of personal certificates and trusted root CAs.
## Group Policy Editor (gpedit.msc)
- Provides a more robust/thorough/efficient means of configuring many of registry's settings (including those not editable by regedit) via policies
    * Vendors can write administrative templates to make third-party software configurable via policies.
- Can push registry configuration to many machines; some policies are configured by input, but most use an enabled/disabled/not defined toggle
- The Local Security Policy editor (secpol.msc) can be used to modify security settings specifically.
## System Information (msinfo32.exe)
- Produces a comprehensive report about the system’s hardware and software components and their configuration
    * Specifically: an inventory of system resources, firmware and OS versions, driver file locations, environment variables, network status, and so on.
## System Configuration Utility (msconfig.exe)
- Modify Windows startup settings/files; mainly used for testing configs/diagnosing problems (not permanent) then permanent changes made elsewhere (ex: Services)
    * General tab for normal/diagnosting/selective startup; Boot tab for Boot Configuration Data (BCD) settings (default OS, Safe Mode, boot option display timeout)
    * Services tab for startup services selection, date for when services were disabled; Tools tab for admin utils ex: System Information, RegEdit, PerfMon, more

<br>

# Command Prompt
- Basic shell interpreter; some commands require Administrative command prompt (new window); uses "switches" (flags), ex: `/s`, `/o:e`, `/scannow`, interactive
- `ctrl+C` to exit / quit, `cls`, `help`, `help command`, `command /?`, `winver` (Windows version [21H2], build [19044.2251] [version+feature.patch])
- `shutdown`: `/l` logoff, `/h` hibernate, `/s` shutdown, `/t nn` shutdown with delay (`shutdown/a` aborts this), `/r` restart
- `dir`: files in a given directory; can search for specific files: `dir *.exe`, `dir ????????.exe` or search a directory: `dir C:\Users`, `dir C:\Users\user\.*`
    * `/o` is used to order by something; `/o:n` (by name), `/o:s` (by size), `/o:e` (by extension), `/o:d` (by date)
    * `/t` is used to order by specific dates; `/t:c` (creation date), `/t:a` (access date), `/t:w` (modify date)
    * `/a` is used to see files with certain access rights; `/a:r` (read only), `/a:h` (hidden), `/a:s` (system), `/a:a` (archive)
- `cd`: change directory, ex: `cd \`, `cd C:\Users\user`, `cd \Users\user`, `cd subfolder_here`, `cd ..`, `cd E:`
- `move source destination`, `copy source destination`, `xcopy source destination switches`, `robocopy source destination switches` (robocopy can `/mov` for move)
- `md/mkdir Data`, `rd/rmdir /s Data` (/q for quiet), `mkdir E:\data`; keep in mind that folder/file names cannot contain the reserved characters: \ / : * ? " < > |
## Disk Management Commands
- The Disk Management snap-in is easy to use, but there are some circumstances where you may need to manage volumes at a command prompt.
### Disk Management: diskpart
- Disk Management is pretty good for most disk operations, but not comprehensive like the command line tool diskpart (foundation of Disk Management)
    * diskpart is powerful and *will* destroy system/boot volumes if used improperly
- There are too many options in diskpart to cover here, but the basic process of inspecting disks and partitions is as follows:
1. Run the `diskpart` utility, and then enter `select disk 0` at the prompt (or the number of the disk you want to check).
2. Enter `detail disk` to display configuration information for the disk. 
    * The utility should report that the partitions (or volumes) are healthy. 
    * If diskpart reports that the hard disk has no partitions, the partition table may have become corrupted.
3. Enter either `select partition 0` or `select volume 0` at the prompt (or the number of the partition or volume you want to check).
4. Enter either `detail partition` or `detail volume` to view information about the object. 
5. You can now use commands such as `assign` (change the drive letter), `delete` (destroy the volume), or `extend`.
6. Enter `exit` to quit diskpart.
### Disk Management: format
- The `format` command writes a new file system to a drive. This process "deletes" any data existing on the drive.
- The basic command is `format X: /fs:SYS`, where X is a drive letter and SYS is the file system, such as NTFS, FAT32, or EXFAT.
- It scans for bad sectors by default (can suppress using `/q`; then removes references to existing files in volume boot record (doesn't scrub/zero sectors)
    * Old files will simply be overwritten over time (can be recovered easily); will need a separate format utility to actually scrub sectors
### Disk Management: chkdsk
- chkdsk verifies filesystem integrity; it scans the filesystem and/or disk sectors for faults and can attempt to repair problems; if fault on boot, autochk is run
- Three run modes: `chkdsk X:` (read-only mode, no repairs), `chkdsk X: /f` (attempt fs fixes), `chkdsk X: /r` (attempt fs fixes and bad-sector recovery)
    * With fixes, you are prompted to save any recoverable data (data is stored in root directory as "filennnn.chk" files)
    * chkdsk /f and chkdsk /r can take a long time to run. Canceling a scan is not recommended. Run a read-only scan first.
    * Check Disk cannot fix open files, so you may be prompted to schedule the scan for the next system restart.
### Disk Management: sfc
- The Windows Resource Protection mechanism prevents damage to or malicious use of system files and registry keys and files. 
- System File Checker (sfc) verifies system/driver files' integrity / restores them from cache if they are found to be corrupt/damaged
    * System files (and shared program files) are maintained, and version-controlled in the WINSxS system folder (this folder can be very large)
- Requires Administrative CMD; `sfc /scannow` (immediate scan/fix), `sfc /scanonce` (next reboot scan/fix), `sfc /scanboot` (*each* reboot scan/fix)
### Bash
- Every shell script (.sh) must have execute permissions, ran by `./coolscript.sh`; a shell script always starts with "shebang" line, in Bash this is: `#!/bin/bash`
- Variables are usually declared, defined as a data type (ex: text string, number), and given an initial value *at the start of the routine*
    * In Bash, the values `$1`, `$2`, and so on are used to refer to arguments by position (the order in which they are entered when executing the script).
- Comparison operators: `==`or`-eq`, `!=`or`-ne`, `<`or`-lt`, `>`or`-gt`, `<=`or`-le`, `>=`or`-ge`, `&&`or`AND`, `||`or`OR`
- `shutdown -r` works in Bash script; `apt-get` or `apt` or `yum` for installing packages (`-y` to suppress confirmation messages); 
#### Bash Examples
```
#!/bin/bash
# Demonstrate If syntax ("branch" statement) in Bash; -z checks if a variable is unset/empty
# Note use of double-quotes to allow variable insertion and single-quote for raw string
$varname = 'VM'
if [ -z "$varname" ]
then
echo 'Hello World'
else
echo "Hello $varname"
fi
```
```
#!/bin/bash
# Demonstrate For syntax ("loop" statement) in Bash
for i in {1..254}
do
ping -c1 “192.168.1.$i”
done
```
```
#!/bin/bash
# Demonstrate Until syntax ("while" statement) in Bash
# &>/dev/null stops the usual ping output from being written to the terminal; the output gets redirected to a null device instead.
until ping -c1 "$1" &>/dev/null
do
echo “192.168.1.$1 not up”
done
echo "192.168.1.$1 up"
```
```
printf "Processes run by $1 on $(date +%F) at $(date +%T) \n" >> "ps-$1.log"
ps -ef | grep "$1" | cut "$((${#1}+9))-" >> "ps-$1.log"
```
### Powershell
- Powershell: .ps1, cmdlets in Verb-Noun format; EX: `Write-Host` output to cmd, `Read-Host` get input; Windows PowerShell Integrated Scripting Environment (ISE)
- `Restart-Computer -Force`
- `Start-Process`
- `PSWindowsUpdate` (many cmdlets in this for managing updates)
- `Get-NetAdapter` returns network adapters properties; `Get-WinEvent` return log data; (pipe these to `Where-Object` and `Select-Object` for filtering)
```
If (Test-Path L:) {
Get-PSdrive L | Remove-PSDrive
}
New-PSDrive -Name "L" -Persist -PSProvider FileSystem -Root "\\MS10\LABFILES"
```
### Batch
- Batch: .bat, meant for CMD; `net use` (drive mapping); 
- `C:\David\Downloads\setup.exe /S /desktopicon=yes` run executable
- `msiexec C:\David\Downloads\install.msi /qn` run installer
### VBScript
- VBScript: (LEGACY) .vbs, uses wscript.exe interpreter

<br>

# Task Manager
- The Task Manager is used to monitor/manage/prioritize: processes (software running in RAM), resources, user sessions, startup settings, and services
- Expand each app/background process to see subprocesses and their resource use; can see info in Details (or look up process info) and end processes/tasks
- Performance: more info about CPU, memory, disk, network, GPU; App History shows usage of Windows Store apps
    * CPU: # of cores/logical processors (HyperThreading), system is/isn't multisocket, virtualization is/isn't on, utilization, uptime, process/thread/handle count
        * Each process can run operations in multiple threads and can open handles to files, registry keys, network pipes, and so on.
    * Memory: which slots have RAM, RAM speed, utilization (In use), use vs available (Committed), cache, kernel/driver usage (Paged [pagefile] / Non-Paged pool)
        * High pagefile utilization may indicate a problem, high RAM usage is fine
    * Disk: disk type, capacity, statistics (average utilization; two disks may be 100% and 0%, the average is 50%), response time, read/write speed
        * Slow computers commonly due to slow HDD technology, excessive paging activity, file/cache corruption, or a faulty device with bad sectors/blocks
    * Network: send/receive throughput numbers for the active network adapter, IP/MAC addresses, WiFi SSID, WiFi type (802.11 standard), signal strength
    * GPU: only shows if system has GPU, shows graphics memory usage/availability
- Users: logged-on users, can send them a message / sign them out, can see what processes/resources they are using
- Startup: enable/disable (shortcuts|registry entries|task schedule triggers) for startup/login, see impact on boot time
- Services: monitor/start/stop background processes ("services"); service doesn't require user interaction, provides OS functions (logon, network, indexing, etc)
    * If something isn't working, FIRST check if services are running; Disabling services can improve performance/security; "Manual" toggle can prevent startup run
- Resource Monitor: live monitoring of CPU/GPU/memory/disk/network utilization with graphs/statistics (ex: threads started by process, hard page faults/second)
- Performance Monitor: logging/recording resource utilization via counter (stats) or trace (behavior [EVTX]) logs ("Data Collector Sets"), read logs into perfmon
    * Processor Counters: `Processor - % Processor Time` (< 85%) || `Processor - % Privileged Time or % User Time` (< 85%, not too far apart)
    * Disk Counters: `Physical Disk - % Disk Time` (< 85%) || `Physical Disk - Average Disk Queue Length` (not increasing, and while % disk time is low)
    * Memory Counters: `Memory - Available Bytes` (> 90% available) || `Memory - Pages/sec` (< 50) || `Paging File - % Usage` (< 50%)
    * Keep in mind that one problem might make another thing seem like a problem

<br>

# File Explorer
- The File Explorer, otherwise just known as Explorer (explorer.exe), you know it well
- System Objects: Logical storage areas; the objects in left-hand pane in Explorer, ex: This PC, Network, Recycle Bin, User Account, OneDrive
    * This PC: fixed disks/removable storage, personal folders; Network: other computers, shared folders/printers
- Drives and Folders: Actual system directory and files (not logical storage)
    * A "drive" can be a single physical disk or a partition on a disk, a shared network folder mapped to a drive letter, or a removable disc
- Root Directory: Every drive contains a directory called the root directory; represented by ex: C:\ (contains system files) or E:\
- System files: those required for the operating system to function, ex: Windows, Program Files, Program Files (x86), Users
    * Users contains NTUSER.DAT (registry), hidden subfolders used to store application settings/customizations, favorite links, shortcuts, and temporary files
- File Explorer Options: Control Panel applet related to view and browsing settings for File Explorer
    * General tab: layout of Explorer windows, switch between the single-click and double-click styles of opening shortcuts
    * View tab: many settings including Hide extensions for known file types, Hidden files and folders, Hide protected operating system files
        * File/Resource Protection prevents users (even administrative users) from deleting protected operating system files
- Indexing Options: Control Panel applet related to search database maintenance, can configure search behavior and indexed locations, rebuild indices
    * A corrupted index is a common cause of search problems; indexed locations can even include email data stores
## Logs
- The Windows Logs folder contains the four main log files: System, Application, Security, Setup (but many more than four)
    * System log: contains events that affect the core OS, ex: service load failures, hardware conflicts, driver load failures, network issues, and so on.
    * Application log: contains non-core processes/utilities and some third-party apps, ex: aapp installers write events to the Application log.
    * The Security log holds the audit data for the system
    * The Setup log records events generated during installation.
- Logs have default max size (usually 20mb) but you can change it; can also change write properties (overwrite, do not overwrite, archive [close/start new])
- Log events are generated by source application and allocated ID/severity; severity levels are critical, error, warning, information, and audit success/failure
    * Critical is high priority (ex: process halt/unresponsive); Error is medium priority; warning indicates future problem (low disk space); info is noteworthy
    * Audit success/failure: whether a security operation was successful or not, ex: successful user authentication, incorrect password
- You can also log boot events. This boot log file is saved to %SystemRoot%\ntbtlog.txt. It is not shown in Event Viewer.
## Storage
- Sector: The smallest unit of storage on a fixed disk; each is traditionally 512 bytes
- File system: Storage logic, can group sectors into allocation units/clusters of 2, 4, or 8 sectors
    * Smaller clusters make more efficient use of the disk capacity
    * Larger clusters can improve file input/output (I/O) performance, especially when working with large files
    * As fixed disk sizes have increased, some disk models now use Advanced Format, with 4 kilobyte (4K) sector sizes. 
        * If possible, will run as if native; if not, the drive controller will usually present the disk in 512 emulated (512e) mode
- Disk: storage space
    * Disk 0 typically holds the OS; Disk 0 has at least three volumes: system (boot/EFI), boot (OS, C: drive), recovery (vendor recovery or WinRE)
    * SSD drive controller determines how blocks are used according to wear-leveling routines to minimize degradation of the solid-state cells
- Partition: an allocation of a section of a disk to some storage purpose
    * You cannot format/delete system orboot partitions; During setup, boot partition is formatted as NTFS, system partition is formatted as FAT32
- Volume: a logical storage unit comprised of one or more devices/partitions ("more" is typically RAID setup)
- Drive: a volume mapped to a drive letter (ex: C: drive)
- Storage Spaces: a method of configuring redundant disk configurations, creates a single storage resource from multiple devices (protected from RAID failures)
## Disk Maintenance
- Of all the computer's subsystems, disk drives and the file system probably require the most attention to keep in optimum working order. 
- File storage is subject to three main problems: Fragmentation (**Only applies to hard disks**), Reduced Capacity, Physical Damage
    * Fragmentation: large files fragment across non-contiguous clusters, reducing read performance
    * Reduced Capacity: More data created than deleted typically; When boot volume has under 20% free space, performance can drop. 
        * At 200 MB, a Low Disk Space warning is generated
    * HDD Damage: Hard disk operations are physically intensive, and the platters of the disk are easy to damage, especially if there is a power cut. 
        * If the disk does not recognize that a sector is damaged, files can become corrupted. 
    * SSD Damage: SSDs can suffer from degradation of the memory circuitry, resulting in bad blocks, and can be damaged by impacts, overheating, and electrical issues.
- These problems can be addressed by the systematic use of disk maintenance tools; run regularly, at least every month and before installing software applications

<br>

# Networking
- Computer has network interface card (NIC); NIC is an adapter card with 1+ ethernet ports to connect a host to a network for data exchange over a link
- Computer joins a local network by connecting its NIC to a switch or wireless access point (WAP); NIC settings should match the capabilities of the switch/WAP
- Almost all wired connections are based on Ethernet; most use copper wire with RJ45, some use fiber optic cabling/connector; link is established on cable plug-in
    * Network adapter media type must match switch's type, use same Ethernet settings (typically auto-negotiated); manual config: edit adapter in Device Manager
    * Each wired adapter has a name (Ethernet, Ethernet2, ...), can rename; can edit adapter in Network & Internet settings
- Connect Wireless using the button on taskbar; select the network/service set ID (SSID) and connect, or input WLAN settings in Network & Internet page
    * Network & Internet -> Manage known networks -> Add a new network; but, WiFi adapter properties are in Device Manager: roaming agressiveness, xmit power, etc
- Adapter properties in Device Manager adjust the low-level network link properties (Ethernet/Wifi)
- *Logical* adapter must have valid client network config: client software w/ allocated IP address/subnet mask (# of bits to mask network ID from host/interface ID)
    * IPv4: 32bit binary in dotted decimal notation; subnet mask 255.255.255.0 splits 192.168.1.1 into network (192.168.1.0) and host (.100)
    * IPv6: 128bit binary in hexadecimal; first 64 bits is logical network, last 64 bits is interface address
## Routing
- All hosts in local network use same range; each host must be configured with IP address of local router ("default gateway"); router is usually #1 in range
    * Range example: 192.168.1.0/24; Router is 192.168.1.1; Hosts in different ranges can only communicate via router packet forwarding
- Hosts are typically config'd w/ addresses of DNS servers; DNS servers map fully-qualified domain names (FQDNs) to IP addresses on Internet / most TCP/IP networks
    * Router does DNS routing; client PCs usually set gateway/primary DNS server to same value (the router); host itself might have FQDN (PC1.cool.lan)
- IP values can be static or dynamic; many-host networks are typically dynamic (less complex) via DHCP; DHCP handles IPs that weren't assigned manually
    * The IP properties default to Obtain an IP address automatically (uses DHCP). To configure a static address, double-click the IP properties item.
- Adapter IP config is done in Network & Internet settings / Network Connections applet; adapters have the following clients, protocols, and services installed:
    * Client for Microsoft Networks, File and Print Sharing for Microsoft Networks software, Internet Protocol (both IPv4, IPv6 installed; adapter auto-selects)
    * Link-layer Topology Discovery (network mapping/discovery functions for networks without DNS)
## Firewall
- New network: Network Location Awareness (NLA) service prompts for public/private (restrictive/loose) network choices (Firewall profiles, via Network & Internet)
    * Public: block all incoming, make host undiscoverable; Private: allow host discovery and folder/print sharing; Domain: (hidden) set firewall using group policy
    * Network discovery makes other computers/devices accessible in Explorer's Network object; uses universal naming convention (UNC) in this format: \\Host\Path
        * Host is the host name / FQDN / IP address of the server, Path is a shared folder or file path
- Windows Defender Security Center (Windows Defender Firewall applet) handles firewall actions; turn on/off firewall, access config applets, etc
    * Choose to allow/block incoming, allow/block programs, set exceptions ("Allow an app through the firewall"/"Allow another program), more
## VPN/WWAN/Proxies
- Virtual Private Network: connects components/resources of two private networks over another public (unsecured) network via secure tunnel between two endpoints
    * Special connection protocols/encryption keep connection secure/authenticated; after connection, remote computer basically becomes part of local network
- Wireless Wide Area Network (WWAN): use cellular adapter / LOS microwave transmission; can be USB or internal; GSM/4G/5G require subscriber identity module (SIM)
    * Cellular providers charge by data amount; can set connection as "metered" in Windows (specify hard data limit) and monitor data usage
- Proxy server: sits between client/another server; can filter/modify comms and provide caching (webpages/content) to improve performance
    * Intercepting/transparent proxy doesn't require clientside change, some proxies auto-configure; otherwise client must get IP/port of proxy (Network & Internet)
## Network Share
- WORKGROUP: p2p network, computers can share resources (this is managed individually); note that AD is not peer to peer, it's centralized (client-server)
- Computers auto-join WORKGROUP by default if "Private" net type (not "Public"), broadcast their hostname (change it in sysdm.cpl); can change WORKGROUP name (rare)
- Sharing options are configured in Advanced sharing settings applet; turn on network discovery AND file and printer sharing; passwords are painful (see below)
    * Password-protected sharing: block share unless log in local account on target system; turn off password-protected share if desired in Advanced sharing options
- File share is *allowed* in firewall (open file/print server ports); Allow folder: Right click folder -> "Give access to" -> select account -> set perms
    * Can customize perms/share name/limit connections via Share tab in folder's Properties (Windows desktop versions are limited to 20 inbounds)
- Public folder allows "Everyone" read/write; Advanced sharing settings > All networks > "Turn on sharing ... read and write files in the Public folders"
- Nearby sharing: PC to smartphone/other using Bluetooth in a Personal Area Network (PAN); simple, files are saved to user's Downloads folder
- Admin shares are automatically created (and hidden); root folder of local drives (C$) and system folder (ADMIN$); note the $ ending (makes a folder hidden)
    * These remain password protected even if you disable password protection
- Can map a shared folder to a drive! Right click it -> Map Network Drive -> Select drive letter -> Reconnect at sign-in; Remove: Right Click -> Disconnect
- View shared resources: `net view`, `net view \\SERVERNAME`, `net use M: \\MYSERVER\DATA /persistent:yes` (map it), `net use M: /delete`, `net use * /delete`
- Printers: Add Printer (Devices and Printers) -> IP address/hostname -> Printer Properties -> Sharing -> Name it -> Add drivers? -> Explorer -> Network -> Connect
- Perms are universal via NTFS ACL (see in a file/folder's Security tab), over-network-only via Share perms; each ACE assigns perms to a principal (user/group)
    * Read/list/execute: open/browse files, run .exe; Write: create files/subfolders, append data to files; Modify; write+edit existing; Full: all+edit perms/owner
    * Each permission can be allow or deny; implicit deny generally with some explicit deny as necessary (overrides all other perms); user gets best perms possible
- Roaming profile: uses network share to store profile data across multiple-computer logins; retrieve at login, copy back at logout; `\\SERVER\ROAMING$\%USERNAME%`
- Folder redirection: change target of personal folders (Documents, Pictures, Start Menu, etc) to network share (file share); configured via GPO

<br>

# Security
- Security controls: physical (fences, doors, locks), procedural (indicent response, management oversight, training), logical (cyber systems, software)
- Access Control System (logical): user authentication, antivirus, firewalls; think Authentication/Authorization/Accounting
    * Authentication: knowledge (password), possession (smart card/smartphone), inherence (fingerprint); hard token; authenticator app; multifactor vs 2-step auth
- Access Control List (ACL): collection of access control entries (ACEs); determines account (SID)/MAC/IP/port/etc allow/blocks and read/read-write/etc perms
    * Note that SID is the only identifier in ACEs; account delete/recreate has different SID, so perms need to be assigned to re-created account
- ACL security uses implicity deny (firewall whitelist, reads top-to-bottom) and least privilege (minimum-required rights/privs/info)
## Accounts
- Local account: stored in Security Account Manager (SAM) database; SAM and account SIDS are in HKEY_LOCAL_MACHINE registry
- Microsoft account: email address username, managed in account.microsoft.com, sets local account with sync'd profile, have OneDrive and Microsoft 365
- Security group: collection of accounts, set perms/rights for multiple accounts at once; defaults are Administrators, Users, Guests (old), Power Users (old)
    * First account on system is auto-added to Administrators; standard accounts can still shut down computer, run desktop apps, install/run store apps, use printer
- Manage accounts/groups using "Local Users and Groups" (shortcuts/properties) or `net user` commands, ex: `net user badguy /active:no` (good for account scripting)
    * `net user nerd Pa$$w0rd /add /fullname:"Nerd Dee" /logonpasswordchg:yes` || `net user nerd` (see properties) || `net localgroup Administrators nerd /add`
- User Account Control (UAC): protect from scripts/attacks against users in Administrators group (require explicit consent); "least privilege"; Administrator no UAC
## Logins
- Sign-in options: Local sign-in; Windows network sign-in; Remote sign-in
    * Local sign-in / interactive logon: Local Security Authority (LSA) compares submitted cred to matching one in SAM database
    * Windows network sign-in: LSA instead sends cred to network service; preferred system is Kerberos (time-sensitive ticketing) using single sign-on (SSO) on AD
        * SSO on Windows also authenticates with Windows domain's SQL Server / Exchange Server services
    * Remote sign-in: authentication over VPN or web portal
- Authentication options: Password... or Windows Hello: PIN [on TPM] as backup, Fingerprint, Facial Recognition, Security Key [USB/SmartCard], TPM encryption key
    * Windows Hello for Business: passwordless SSO (ex: fingerprint SSO), asymmetric encryption comms between TPM and network auth server for auth
- Username/password: created by user, can change via Ctrl+Alt+Delete or account settings, admin can change a user's password in Local Users and Groups

<br>

# Domains and Active Directory
- Domain: group of hosts in same namespace, admin'd by same authority; needs Windows Server computer config'd as Domain Controller (DC)
    * Domain: Domain accounts, DCs for auth, Member Servers for file/print/app services, Security Groups for perms, and Organizational Units for admin-rights zoning
- DC stores db of network info called Active Directory (AD); AD is a scalable network directory service for Windows domain networks, does user auth (Kerberos)
- Group policy: normal, from DC; `gpupdate` (use `/force` to re-apply all); `gpresult` and specify `/s` host, `/u` user, `/p` password, and `/r` desktop policies
    * Via group policy (or user profile), login scripts perform set of actions automatically after user account is authenticated; works for huge variety of things
# DOMAIN SETUP
- When a computer is joined to a domain rather than a workgroup, it is put under the control of the domain administrators. To communicate on a domain, the computer must have its own account in the domain. This is separate from any user accounts that are allowed to sign-in.
    * The Windows Home edition cannot join a domain.
- Windows does not support joining the computer to a domain during an attended installation. The computer can be joined during an unattended installation by using an answer file or script. Otherwise, you use either the Access work or school option in the Account settings app or the System Properties (sysdm.cpl) dialog to join a domain. The computer must be on the domain network and configured by DHCP with an appropriate IP address and DNS servers. Each domain is identified by a FQDN, such as ad.company.example, and the local computer must be able to resolve this name via DNS to join. The credentials of an account with domain admin privileges must be input to authorize the new computer account.
- The same interfaces can be used to detach the computer and revert to workgroup use. This requires a user account that is a member of the local Administrators group.
- To use services in the domain, the user must sign in to the PC using a domain account. The Other user option in the sign-in screen will provide a domain option if it is not the default. You can also enter a username in the format Domain\Username to specify a domain login.
- Conversely, when a machine is joined to a domain, .\Username or hostname\username will authenticate against a local user account.
# HOME FOLDERS
- On a domain, data storage and PC configuration should be as centralized as possible so that they can be more easily monitored and backed up. This means that user data should be stored on file servers rather than on local client computers. Various settings in Active Directory can be used to redirect user profile data to network storage.
- A home folder is a private drive mapped to a network share in which users can store personal files. 
    * home folder: Default local or network folder for users to save data files to.
- The home folder location is configured via the account properties on the Profile tab using the Connect to box. Enter the share in the form \\SERVER\HOME$\%USERNAME% , where \\SERVER\HOME$ is a shared folder created with the appropriate permissions to allow users to read and write their own subfolder only.
- When the user signs in, the home folder appears under This PC with the allocated drive letter

<br>

# Linux
- GNU (GNU is Not Linux (recursive!)): open-source license covering replacements for closed-source UNIX non-kernel software
- Linux distribution: Linux kernel plus package manager / software repository with customizable shells, utilities, and apps.
    * Distros also have either community-supported or commercial licensing + support options.
    * Shells: command env for OS/app ops; Bash, zsh, ksh; shells differ in history, autocomplete/correct, syntax highlighting
- Many Linux distros have no desktop (servers); boot to terminal (I/O tied to shell interpreter) tied to teletype (tty) device
    * stdin (0): user input to shell to tty; stdout (1): tty to shell to terminal; stderr (2): error information
    * Interactive use of shell: user inputs; Non-interactive use of shell: script inputs
- Linux distros w/graphical desktop (clients) use X Window Display ("Xorg"/"X") to launch desktop environments
    * X server sits in one of the tty consoles, typically tty1; tty consoles allow multiple users to use one host at same time
    * Example desktop environments: Gnome (GNU Object Model Environment), KDE (K Desktop Environment), Cinammon, Xfce
    * Within a desktop env, terminals are emulated- "pseudoterminals" (pty/pts)- and use either default or alt command shell
- Uses "unified file system": "everything is a file"; first fixed disk is /dev/sda, second storage (ex: USB port) is /dev/sdb
    * Boot -> system kernel+virtual file system loaded into RAM -> UFS locates persistent root partiton, loads file system
    * Linux doesn't use drive letters; unified file system starts at root `/`; everything hinges on root, ex: `/home`, `/etc`
        * Linux Filesystem Heirarchy Standard (FHS) specifies folders inside `/` and their contents
        * `/home`: user subdirectories (includes each user's `~`), `/etc`: configuration files
- Networks have persistent configuration (loaded at boot) and running configuration (changed during run)
    * Persistent config is in /etc/network/interfaces; Most distros use NetworkManager package for GUI edit or nmcli tools
        * Can use systemd-networkd config manager instead, or, just edit the files in that directory and use `ifup`/`ifdown`
    * Running config can be seen/changed with `ip`/`ifconfig` (ifconfig is deprecated)
- Software is either source code or pre-compiled apps; choice of package manager (for pre-compiled apps) marks distro types
    * Distros come with pre-compiled software; this software is available at vendor site, and package manager needs link to it
        * With link, pm can install/uninstall/update software; pm guided setup automatically configures repository choices
        * Package integrity tested via hash comparison (MD5, SHA-256, or GNU Privacy Guard (GPG) signing); pm auto-does this
    * Source code package needs appropriate compiler w/preferred options; Pre-compiled packages install via package manager
    * Distro package managers: Advanced Packaging Tool (APT) (Debian, .deb); Yellowdog Updater, Modified (YUM) (RedHat, .rpm)
- Antivirus: Clam AntiVirus (ClamAV), Snort Intrusion Prevention System (IPS); both OS/free via General Public License (GPL)
- Samba: Server Message Block (SMB)–compatible file sharing protocol, allows use of Windows print/sharing inside Linux env
## Commands
- Format: `command options arguments` (case-sensitive); pipe results to other commands `|`; do multiple statements with `;`
    * Escape characters: `\` (escape), `' '` ("strong escaping"/raw string), `" "` ("weak escaping"/allow substitution)
        * Need to always escape metacharacters; Linux is constantly eyeing metacharacters
- Output pagination: `ls --help | more`; use up/down to tab through commands; some terminals can scroll output
    * If possible, SHIFT+PAGEUP or SHIFT+PAGEDOWN / CTRL+SHIFT+UPARROW or CTRL+SHIFT+DOWNARROW to scroll through output
    * Instead of `ls --help` you can use `man ls`
- Substitution: `"$(pwd) * example one"` -> `/home/user * example one`
- Backups: mix cron job with file copy statement, ex: `§ 15 02 * * 5 /usr/bin/rsync –av --delete /home/sam/mount/rsync`
    * "Run the rsync backup program at 2:15 a.m. on a Friday (day 5), sync /home/sam directory with /mount/sync folder"
        * /mount/sync can be an external drive... for backup
    * `15` minute (0-59), `02` hour (0-23), `*` day (0-31), `*` month (0-12 or jan/feb/mar), `5` day of week (1-7 or mon,tue)
        * Wildcards for time: `*` any, `,` multiple values (21,22,23,24), `-` range of values (21-24), `/2` every other
    * `/usr/bin/rsync` command, `-av --delete` flags, `/home/sam/mount/rsync` argument
- Change account info: `useradd`/`usermod`/`userdel`/`passwd`; Group membership: `groupadd`/`groupmod`/`groupdel`/`newgrp`
- `pwd`, `cd`, `ls`, `rm`, `su`/`su -`/`su username` only switch user (stay inplace, etc), `sudo command`
- `chmod` change perms of file/directory (only owner can do this); `chown` change owner of file/directory (helps `chmod`)
    * Symbolic permission format: dir(d)/file(-) || owner(rwx) || owner'sgroup(rwx) || allotherusers(rwx)
    * Octal permission format: read=4 write=2 execute=1, so 7 (rwx), 5 (rx), 4 (r), 0(deny) -> 755, 540, ...
    * See perms of files in directory: `ls -l`; "drwxr-xr-x 2 bobby admins Desktop", "-rwx-r-x r-- 1 bobby admins scan.sh"
    * Note: `chown` can only be done by superuser; file owner can change group with `chgrp` instead
- `df` "disk free", see free space, file system, total size, space used, percentage value of space used, and mount point
- `du` "disk usage", how a device is used, including the size of directory trees and files within it
- `cp file.txt /home/user/old/file.old`, `cp file.txt file.old` copy to new file, `cp -v /etc/hosts /tmp` copy directory over
    * Move/rename (instead of copy): `mv file.txt /home/user/docs/file.old`, `mv file.txt file.old` rename file
- `find`: search; `find path exp` look in path for exp match; `-name`, `-size`, `-user` owner, `-perm` perms, `-type` (odd)
    * `-type`: files v directories v block devices (disks) v network sockets v symbolic links v named pipes (not filetypes)
- `cat`: show file content; `-n` line numbers, `| more`/`| less` pagination, `> file` overwrite file, `>> file` append to file
- `nano filepath` or `nano -l filepath` (show filenumbers) to edit plaintext; CTRL+O save to file, CTRL+X exit editor
- `vim filepath` to edit plaintext; `i` insert `a` append `A` append EOL `o` insert on newline; ESC to exit a mode
    * Meta commands: `:set number` (add line numbers), `:w` save file, `:wq` save and quit, `:q!` quit without saving
- `apt-get update` Check for updates; `apt-get upgrade` Update all packages; `apt-get install package` Install package
    * `yum check-update`, `yum update`, `yum install package` as the Red Hat alternatives
- `ps`: Currently-running processes; by itself looks at current shell's processes; PID, terminal/pty, CPU time, parent command
- `top`: Interactive version of `ps`; ENTER (refresh), SHIFT+N (sort by PID), M (by memory), P (by CPU), u (by user), q (quit)
- `ip`: Network config; `ip addr show dev eth0` (report eth0), `ip link` (interface status), `ip -s link` (net stats)
    * More: `ip link set eth0 up|down` (enable/disable eth0), `ip addr add|delete` (modify IP address configuration)
- `dig`: query DNS about a domain/resource; `dig domainname` (any available DNS), `dig @server domainname` (specific DNS)
### grep
- `grep`: search every file's contents for match ("Globally search a Regular Expression and Print"); excellent for many things
    * Nice grep tutorial: https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/
- `ls -l | grep cool` return files with "cool" in filename; this pipes `ls -l` (filenames) as grep's search context
- `cat ~/notes/coolfile.txt | grep -i "cool"` pipe coolfile.txt into grep and case-insensitive search for "cool"
- `grep -E "cool|uncool"` lines with either "cool" or "uncool"; `grep -v "^cool"` shows *all lines* that don't have "cool"
- `grep -R "cool"` recursively-search all files in current directory for "cool"; output shows file and the match in it
    * `grep -R -h "cool"` only returns matched rows (no filenames)
- `grep -B 5 "fubar"` show matching row and 5 previous lines; use `-A` for same thing but next lines

<br>

# MacOS
- "Menu bar" (top), "Apple menu" (topleft Apple logo), "Dock" (bottom apps), Mission Control (F3, apps/multi-desktop)
- System Preferences ("prefpane") Apple Keyboards, Apple Magic Mouse and Trackpad and Gesture Support, Displays, Accessibility
    * Apple Keyboards: Normal is Command(CTRL), Option(ALT), Control(...); but, can map non-Apple external keyboard keys here
    * Some prefpanes might require admin approval for changes (lock icon)
- Users: Admin/Guest on first boot; add new via System Preferences Users & Groups
    * Apple ID can be added to accounts for sync/iCloud/App Store/etc (sign in to Apple ID via System Preferences)
- Security & Privacy prefpane: configure analytics/telemetry/personalized info, perms for location/camera/contacts/calendar
- Internet Accounts/Keychain: email/cloud accounts, keychain manages passwords for them; can see passwords in Keychain too
- FileVault: disk encryption; users must have password to access the encrypted disk; a recovery method/key should be generated
- Networks managed via menu bar / System Preferences; use Advanced button to configure IP/proxy settings; can use Terminal too
- Disk Utility exists and can do defrag, but usually not needed; Remote Disc is used for CD/DVD, but it's not great...
- Time Machine does backups and drive formatting/partitioning; default is hourly backup/24 hours, daily/1mo, weekly/allmonths
    * Backups are snapshots; stored locally and on any available backup drive; if timeline tick is dimmed, no dice
    * Restore files: timeline on right side shows available backups; choose the folder in Finder and slide the timeline back
## Apps
- Finder/iCloud: Explorer/OneDrive but for Mac; iCloud caps at 5gb by default but you can upgrade; mail/contacts/calendar/more
- Install more apps via App Store or normal downloads; App Store requires Apple ID; normal download disabled by default LOL
    * DMG (disk image) for simple installs, just copy to Applications; PKG for more actions (run service, write files, ...)
    * Once app is installed (either DMG or PKG), an application with extension .app is added to the Applications folder
    * To uninstall an app, locate it in the Applications folder and drag it to the trash; might leave remnants LOL
- Updating: App Store checks daily, notifies you; third party apps follow their own system of course
- Antivirus: Avira/Avast/Sophos... only download trusted apps, only download trusted content, careful about Windows partitions
- Corporate restrictions still apply when Mac is used in business environment
    * Can use Business Manager portal as group-policy; see: support.apple.com/guide/deployment/welcome/1/web
## Troubleshooting
- App crashes: spinning wait cursor or unresponsive; use Force Quit or press Command+Option+ESC
- Recovery: on boot, hold Command+R; this boots into recovery mode; if startup drive is unavailable, Mac will boot to internet

<br>

# Cybersecurity
- Information security: CIA triad (includes paper/digital); Cybersecurity: Specifically protecting computer storage / processing systems
    * Both of these are assured by developing security policies and controls; making a system more secure is "hardening" it
- Security policies should cover every aspect of an org's use of computer/network technologies; procurement/change control, acceptable use, etc
    * To develop security policies, security teams must perform assessments to determine how secure a network is; vulnerabilities, threats, and risk
    * Vulnerability: weakness (accidentally/intentionally used); Threat: exploit potential (from someone/something); Risk: likelihood & impact of exploitation
## Vulnerabilities
- Non-compliant systems: system not following hardened configuration
- Unprotected system: lacking one or more security measures
- Software/zero-day vulnerabilities: software security circumvention, app crash; malware code infecting target host (often via software vulnerability) is exploit
    * Zero day is where a vulnerability has not been discovered yet by security researchers / developers
- Unpatched and EOL OSs: not receiving security updates
- BYOD vulnerabilities: untested devices
## Attacks
- Social Engineering: Impersonation, Dumpster Diving, Shoulder Surfing, Tailgating, Piggybacking, Phishing, Evil Twin
- Strategies: External threat vs Internal threat, Footprinting, Spoofing, On-path, Denial of Service, Distributed Denial of Service
- Password attack: brute force (trying many passwords) and dictionary (comparing hash to known hashes)
- Cross-Site Scripting (XSS): attacker exploits input validation on a site, makes visitor execute "trusted" code
- SQL Injection: attacker sends a query ended by `' or 1=1--#` which attempts to return entire tables/databases or destroy information
## Hashing and Encryption
- MD5 (old) and SHA (current) to one-way encode something; hashes are highly unique, a single character difference causes an entirely-new hash to be created
- Symmetric (ex: AES) encryption uses one encrypt/decrypt key; this is often sent initially via an Asymmetric (ex: RSA, ECC) encryption to establish secure comms
- Asymmetric: Sender encrypts the transmission using the recipient's public key; only the recipient can decrypt the transmission after this is done
    * Symmetric key exchange happens via this method; the symmetric key itself is sent via asymmetric encryption, and follow-on comms are symmetric encryption
- To ensure the sender is legitimate, the sender encrypts a message with their private key and the recipient decrypts it with the sender's public key
    * The message (before encryption) is hashed; this hash is sent with the encrypted message so that the recipient can compare hashes (determining legitimacy)
## Connection Security
- WEP (vulnerable, RC4) -> WPA (TKIP, RC4, vulnerable to replay) -> WPA2 (CCMP, AES, Pre-Shared Key (PSK)) -> WPA3 (current)
    * Simultaneous Authentication of Equals (SAE), Updated cryptographic protocols (GCMP), Protected management frames. Wi-Fi Enhanced Open (encrypted open)
- Enterprise Authentication Protocol (EAP): avoiding password exchange for enterprise comms; AAA server authenticates user, device, or both; device often uses TPM
    * AAA servers: RADIUS (usually wireless/VPN access point auth), TACACS+ (auth for admin router/switch/access point access), Kerberos (RADIUS/TACACS+ for domain)
- Screened subnet: a DMZ; a network isolated from the secure zone, it has different rules and can serve as a "jumpbox" with certain authentication
## Home Routers
- Consider placement; broadcast range while minimizing unauthorized physical access
- Setup: provider cable into WAN port (RJ45 fiber, RJ11 DSL, F coax, or modem: RJ45 WAN/LAN); power on; connect computer to RJ45 LAN (yellow); nav to site; config
    * Site can be http://192.168.0.1, http://www.routerlogin.com, etc; once there, change admin's default password (12+ characters, more config; then check status
    * If ISP is providing a static IP to the router and requires you to config your router in a specific way, follow their instructions!!
- Router should get firmware update if available; download update from vendor website (need correct patch for device make/model), then in router, "Firmware Upgrade"
- Set router SSID, enable encryption (WPA3 unless you need compatibility, then WPA2 AES/CCMP or WPA2 TKIP), disable SSID broadcast (if desired)
- Firewall: inbound filtering (default no inbounds), outbound filtering (content filtering aka website blocks and time shutdowns)
- Port fowarding (allowing inbounds to connect to specific devices inside firewall) works by mapping internal devices to router ports; disable unused ports!!
    * This is remedied by Universal Plug and Play (UPnP), where devices know what ports to open and how; just enable UPnP on the firewall, done!
    * UPnP is dangerous; disable client device UPnP that don't need it if the firewall allows UPnP... or else outsiders can access webcams/printers/etc!!