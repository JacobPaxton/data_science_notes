# Cyber Notes

<!-- 
#######                                                  #####                                                 
   #      ##   #####  #      ######     ####  ######    #     #  ####  #    # ##### ###### #    # #####  ####  
   #     #  #  #    # #      #         #    # #         #       #    # ##   #   #   #      ##   #   #   #      
   #    #    # #####  #      #####     #    # #####     #       #    # # #  #   #   #####  # #  #   #    ####  
   #    ###### #    # #      #         #    # #         #       #    # #  # #   #   #      #  # #   #        # 
   #    #    # #    # #      #         #    # #         #     # #    # #   ##   #   #      #   ##   #   #    # 
   #    #    # #####  ###### ######     ####  #          #####   ####  #    #   #   ###### #    #   #    ####  
-->

# Table of Contents

I.    [Activity Logging and Search      ](#logs-and-search)
1.    [System Logs                      ](#system-logs)
2.    [Log Aggregation                  ](#log-aggregation)

II.   [ELK Stack                        ](#elk-stack)
1.    [ELK Stack Basics                 ](#elk-stack-basics)
2.    [Elastic Search in Python         ](#elastic-search-in-python)

III.  [Splunk                           ](#splunkhttpswwwsplunkcom)
1.    [Splunk Overview                  ](#splunk-overview)
2.    [Splunk Examples                  ](#splunk-examples)

IV.   [Understanding the Attack         ](#understanding-the-attack)
1.    [Attack Goals                     ](#attack-goals)
2.    [General Aspects of Attacks       ](#general-aspects-of-attacks)

V.    [MITRE ATT&CK Framework           ](#mitre-attck-framework)
1.    [Reconnaissance                   ](#reconnaissance)
2.    [Resource Development             ](#resource-development)
3.    [Initial Access                   ](#initial-access)
4.    [Execution                        ](#execution)
5.    [Persistence                      ](#persistence)
6.    [Privilege Escalation             ](#privilege-escalation)
7.    [Defense Evasion                  ](#defense-evasion)
8.    [Credential Access                ](#credential-access)
9.    [Discovery                        ](#discovery)
10.   [Lateral Movement                 ](#lateral-movement)
11.   [Collection                       ](#collection)
12.   [Command and Control              ](#command-and-control)
13.   [Exfiltration                     ](#exfiltration)
14.   [Impact                           ](#impact)

VI.   [Alternative Frameworks           ](#alternative-frameworks)
1.    [Diamond Model                    ](#diamond-model)
2.    [Cyber Kill Chain                 ](#cyber-kill-chain)
3.    [NIST CSF                         ](#nist-csf)

VII.  [Detecting the Attack             ](#detecting-the-attack)
1.    [Attack Intelligence Sources      ](#attack-intelligence-sources)
2.    [Detection Overview               ](#detection-overview)
3.    [General Aspects of Detection     ](#general-aspects-of-detection)

VIII. [Signature-Based Detection        ](#signature-based-detection)
1.    [Sigma (Signature Creation)       ](#sigma-signature-creation)
2.    [Snap Attack (Signature Testing)  ](#snap-attack-signature-testing)

IX.   [Behavior-Based Detection         ](#behavior-based-detection)
1.    [Behavior Creation                ](#behavior-creation)
2.    [Behavior Implementation          ](#behavior-implementation)

X.    [Attack Detection Tools           ](#attack-detection-tools)

XI.   [Attackers and Strategies         ](#attackers-and-strategies)
1.    [APT28                            ](#apt28httpsattackmitreorggroupsg0007)
2.    [APT29                            ](#apt29httpsattackmitreorggroupsg0016)
3.    [Leviathan                        ](#leviathanhttpsattackmitreorggroupsg0065)
4.    [Sandworm Team                    ](#sandworm-teamhttpsattackmitreorggroupsg0034)

<br>

<br>







<!-- 
###################################################################################################

   #                                           #                                            
  # #    ####  ##### # #    # # ##### #   #    #        ####   ####   ####  # #    #  ####  
 #   #  #    #   #   # #    # #   #    # #     #       #    # #    # #    # # ##   # #    # 
#     # #        #   # #    # #   #     #      #       #    # #      #      # # #  # #      
####### #        #   # #    # #   #     #      #       #    # #  ### #  ### # #  # # #  ### 
#     # #    #   #   #  #  #  #   #     #      #       #    # #    # #    # # #   ## #    # 
#     #  ####    #   #   ##   #   #     #      #######  ####   ####   ####  # #    #  ####  
                                                                                            
                         #####                                     
  ##   #    # #####     #     # ######   ##   #####   ####  #    # 
 #  #  ##   # #    #    #       #       #  #  #    # #    # #    # 
#    # # #  # #    #     #####  #####  #    # #    # #      ###### 
###### #  # # #    #          # #      ###### #####  #      #    # 
#    # #   ## #    #    #     # #      #    # #   #  #    # #    # 
#    # #    # #####      #####  ###### #    # #    #  ####  #    # 

###################################################################################################
-->

<!-- Needs work -->
# Logs and Search

## System Logs
- Logging activity and data of all sorts of sources, proprietary, integrated, free, and more
### Sysmon (System Monitor) Logs
- Free tool, monitors and logs system activity to the Windows event log
- Process creation, network connection, file creation or modification, driver loads, raw disk access, remote threads, process memory access
- Doesn't hide from intruders; doesn't generate logs of the logs it has created
### Windows Security Logs
- Window-specific, monitors security-related activities
- Attempted and successful unauthorized activity, problem troubleshooting, login/logout
- Sysadmin can delete specific logs, separate rights, and even clear the log- priv escalation
### Windows System Logs
- Windows-specific, monitors application/system events including errors, warnings; uses event IDs
- Windows system components (drivers, built-in interfaces), installed programs
- Shows basic, non-harmful errors that can be misconstrued by scammers to be serious
### Netflow Logs (from Cisco)
- Monitors network traffic flow, network traffic volume, router/switch IP information
    - Netflow Collector and Analyzer is a GUI for this information
- Network admins can use these to identify which users/protocols/applications are high-volume
- No mentioned downsides
### PCAP (Packet Capture)
- API for collecting network traffic
- Saves packets and a lot of various metadata, very popular and widely used
- No mentioned downsides
### Firewall Logs
- Monitors how firewall handles traffic, identifies suspicious activity (real-time)
- Connection: Time and date, kind (TCP/UDP), receiving port, and dropped/accepted packets
### Proxy Logs
- Monitors users/applications that access the network and app/service requests
- HTTP version/request method, content type, user agent, client username/IP/source port, requested resource, and more
### Browser History Logs
- Browser activity
- Forensics the websites visited, timestamp, access numbers, if data entered, downloads
- Excellent at leaking data and providing vulnerabilities to illicit actors, esp through plugins
### DNS Logs
- Extremely detailed information about DNS data that is sent/received by DNS server
- Records requested, client IP, request flags, zone transfers, query logs, rate timing, and DNS signing
- No mentioned downsides- built to identify various DNS attacks (hijack, tunnel, DOS, C2, cache poisoning)

## Log Aggregation
- The effort to bring disparate log sources into one unified picture
- Many competing technologies with varying performance

[[Return to Top]](#table-of-contents)






<!-- 
####### #       #    #     #####                             
#       #       #   #     #     # #####   ##    ####  #    # 
#       #       #  #      #         #    #  #  #    # #   #  
#####   #       ###        #####    #   #    # #      ####   
#       #       #  #            #   #   ###### #      #  #   
#       #       #   #     #     #   #   #    # #    # #   #  
####### ####### #    #     #####    #   #    #  ####  #    # 
-->

# ELK Stack

<!-- Needs work -->
## ELK Stack Basics
- Aggregated log storage and querying with frontend and ingest capability
### [Elastic Search](https://www.elastic.co/elasticsearch/)
- RESTful (JSON-based) search and analytics engine for distributed sources
- "Index" is the word for database
- An index's data is distributed across "shards"
- Elastic Common Schema: standardized field names, values, and dtypes for Elasticsearch
    * https://www.elastic.co/guide/en/ecs/1.4/ecs-reference.html
    * https://www.elastic.co/guide/en/beats/winlogbeat/7.9/exported-fields-ecs.html
### [Kibana](https://www.elastic.co/kibana/)
- User interface for Elastic Search
### [Beats](https://www.elastic.co/beats/)
- Single-purpose movement of data from distributed sources to Elastic Search or Logstash
- Filebeat: logs and other data
- Packetbeat: network data
- Winlogbeat: Windows event logs
- Functionbeat: cloud data
- Others: Metricbeat (metrics), Auditbeat (audit data), Heartbeat (uptime monitoring)
### [Logstash](https://www.elastic.co/logstash/)
- Server-side system to ingest data from multiple sources, transform it, and send it to "favorite stash"

## Elastic Search in Python
- Walkthrough: http://blog.adnansiddiqi.me/getting-started-with-elasticsearch-7-in-python/
- `pip install elasticsearch` and `pip install elasticsearch-dsl`
- Create an index using PUT, access the index using the URL and /index-name-here
- Delete an index using a specific curl command
    - Example with "company" index in POSTMAN app: `curl -X DELETE \ http://localhost:9200/company/ \ -H 'cache-control: no-cache' \ -H 'content-type: application/json' \ -H 'postman-token: c67845af-5c96-a6ce-06dd-50ad3d8070b0'`
- Add data (a document) to the index using POST and JSON format, returns with index name, type, ID, and more
- Query for a document using its ID (IDs are random unless explicitly specified, don't typically specify it but DO store ID for queries)
- Return all documents using URL/index-name-here/doc/_search (essentially same as SQL `select * from table`)
- Schema of an index (called mapping): stored as `{ "mappings": { "properties": { "col1": {"type":"date"}, "col2": {"type":"text"}, ... } } }`

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                     
#     # #####  #      #    # #    # #    # 
#       #    # #      #    # ##   # #   #  
 #####  #    # #      #    # # #  # ####   
      # #####  #      #    # #  # # #  #   
#     # #      #      #    # #   ## #   #  
 #####  #      ######  ####  #    # #    #  
-->

# [Splunk](https://www.splunk.com/)

<!-- Needs work -->
## Splunk Overview
- Log search, security, etc in a unified tool
### [SPL](https://docs.splunk.com/Splexicon:SPL)
- SPL is the abbreviation for Search Processing Language. SPL is designed by Splunk for use with Splunk software.
    - SPL example: `(CommandLine="rundll32.exe %APPDATA%\*.dat",*" OR CommandLine="rundll32.exe %APPDATA%\*.dll",#1")`
- SPL encompasses all the search commands and their functions, arguments, and clauses. Its syntax was originally based on the Unix pipeline and SQL. The scope of SPL includes data searching, filtering, modification, manipulation, insertion, and deletion.

<!-- Needs work -->
## Splunk Examples
- 

[[Return to Top]](#table-of-contents)






<!-- 
###################################################################################################

#     # #     # ######  ####### ######   #####  #######    #    #     # ######  ### #     #  #####  
#     # ##    # #     # #       #     # #     #    #      # #   ##    # #     #  #  ##    # #     # 
#     # # #   # #     # #       #     # #          #     #   #  # #   # #     #  #  # #   # #       
#     # #  #  # #     # #####   ######   #####     #    #     # #  #  # #     #  #  #  #  # #  #### 
#     # #   # # #     # #       #   #         #    #    ####### #   # # #     #  #  #   # # #     # 
#     # #    ## #     # #       #    #  #     #    #    #     # #    ## #     #  #  #    ## #     # 
 #####  #     # ######  ####### #     #  #####     #    #     # #     # ######  ### #     #  #####  
                                                                                                    
####### #     # #######       #    ####### #######    #     #####  #    # 
   #    #     # #            # #      #       #      # #   #     # #   #  
   #    #     # #           #   #     #       #     #   #  #       #  #   
   #    ####### #####      #     #    #       #    #     # #       ###    
   #    #     # #          #######    #       #    ####### #       #  #   
   #    #     # #          #     #    #       #    #     # #     # #   #  
   #    #     # #######    #     #    #       #    #     #  #####  #    # 

###################################################################################################
-->

<!-- Needs work -->
# Understanding the Attack
## Attack Goals
## General Aspects of Attacks
- 

[[Return to Top]](#table-of-contents)






<!-- 
#     # ### ####### ######  #######       #    ####### #######   ##     #####  #    # 
##   ##  #     #    #     # #            # #      #       #     #  #   #     # #   #  
# # # #  #     #    #     # #           #   #     #       #      ##    #       #  #   
#  #  #  #     #    ######  #####      #     #    #       #     ###    #       ###    
#     #  #     #    #   #   #          #######    #       #    #   # # #       #  #   
#     #  #     #    #    #  #          #     #    #       #    #    #  #     # #   #  
#     # ###    #    #     # #######    #     #    #       #     ###  #  #####  #    #
-->

<!-- Needs work -->
# MITRE ATT&CK Framework
- Overview text

<!-- Needs work -->
## Reconnaissance

<!-- Needs work -->
## Resource Development

<!-- Needs work -->
## Initial Access
### Phishing - [T1566](https://attack.mitre.org/techniques/T1566/)
- Artifacts/traces of the specific attack type
- Manual detection of the specific attack type

<!-- Needs work -->
## Execution
### Command and Scripting Interpreter - [T1059](https://attack.mitre.org/techniques/T1059/)
- [T1059.003](https://attack.mitre.org/techniques/T1059/003/): Windows Command Shell, use of CMD to execute commands and scripts
    - Splunk SPL ([bogusecurity](https://bogusecurity.com/2019/12/26/sofacy-trojan-loader-activity/)): `(CommandLine="rundll32.exe %APPDATA%\*.dat",*" OR CommandLine="rundll32.exe %APPDATA%\*.dll",#1")`
    - Potential Trend Micro coverage: https://www.trendmicro.com/vinfo/us/threat-encyclopedia/malware/Trojan.Win32.DLOADR.AUSUSN/
- Artifacts/traces of the specific attack type
- Manual detection of the specific attack type

<!-- Needs work -->
## Persistence

<!-- Needs work -->
## Privilege Escalation

<!-- Needs work -->
## Defense Evasion

<!-- Needs work -->
## Credential Access

<!-- Needs work -->
## Discovery

<!-- Needs work -->
## Lateral Movement

<!-- Needs work -->
## Collection

<!-- Needs work -->
## Command and Control
### Application Layer Protocol - [T1071](https://attack.mitre.org/techniques/T1071/)
- Artifacts/traces of the specific attack type
- Manual detection of the specific attack type

<!-- Needs work -->
## Exfiltration
### Exfiltration Over Alternative Protocol - [T1048](https://attack.mitre.org/techniques/T1048/)
- Artifacts/traces of the specific attack type
- Manual detection of the specific attack type

<!-- Needs work -->
## Impact
- 

[[Return to Top]](#table-of-contents)






<!-- 
   #                    #######                                                                
  # #   #      #####    #       #####    ##   #    # ###### #    #  ####  #####  #    #  ####  
 #   #  #        #      #       #    #  #  #  ##  ## #      #    # #    # #    # #   #  #      
#     # #        #      #####   #    # #    # # ## # #####  #    # #    # #    # ####    ####  
####### #        #      #       #####  ###### #    # #      # ## # #    # #####  #  #        # 
#     # #        #      #       #   #  #    # #    # #      ##  ## #    # #   #  #   #  #    # 
#     # ######   #      #       #    # #    # #    # ###### #    #  ####  #    # #    #  ####  
-->

<!-- Needs work -->
# Alternative Frameworks

<!-- Needs work -->
## Diamond Model
- General -> Specific, bulleted explanation

<!-- Needs work -->
## Cyber Kill Chain
- General -> Specific, bulleted explanation

<!-- Needs work -->
## NIST CSF
- General -> Specific, bulleted explanation

[[Return to Top]](#table-of-contents)






<!-- 
###################################################################################################

######  ####### ####### #######  #####  ####### ### #     #  #####  
#     # #          #    #       #     #    #     #  ##    # #     # 
#     # #          #    #       #          #     #  # #   # #       
#     # #####      #    #####   #          #     #  #  #  # #  #### 
#     # #          #    #       #          #     #  #   # # #     # 
#     # #          #    #       #     #    #     #  #    ## #     # 
######  #######    #    #######  #####     #    ### #     #  #####  
                                                                    
####### #     # #######       #    ####### #######    #     #####  #    # 
   #    #     # #            # #      #       #      # #   #     # #   #  
   #    #     # #           #   #     #       #     #   #  #       #  #   
   #    ####### #####      #     #    #       #    #     # #       ###    
   #    #     # #          #######    #       #    ####### #       #  #   
   #    #     # #          #     #    #       #    #     # #     # #   #  
   #    #     # #######    #     #    #       #    #     #  #####  #    # 

###################################################################################################
-->

<!-- Needs work -->
# Detecting the Attack
## Attack Intelligence Sources
## Attack Goals
## General Aspects of Detection
- 

[[Return to Top]](#table-of-contents)






<!-- 
 #####                                                       ######                                                   
#     # #  ####  #    #   ##   ##### #    # #####  ######    #     # ###### ##### ######  ####  ##### #  ####  #    # 
#       # #    # ##   #  #  #    #   #    # #    # #         #     # #        #   #      #    #   #   # #    # ##   # 
 #####  # #      # #  # #    #   #   #    # #    # #####     #     # #####    #   #####  #        #   # #    # # #  # 
      # # #  ### #  # # ######   #   #    # #####  #         #     # #        #   #      #        #   # #    # #  # # 
#     # # #    # #   ## #    #   #   #    # #   #  #         #     # #        #   #      #    #   #   # #    # #   ## 
 #####  #  ####  #    # #    #   #    ####  #    # ######    ######  ######   #   ######  ####    #   #  ####  #    #
-->

# Signature-Based Detection

<!-- Needs work -->
## Sigma (Signature Creation)
- Signature format for SIEM systems and log events, uses rules and .yml files
- Widely used and very straightforward
- Look into pySigma and sigma-cli (which uses pySigma)
- Guide: https://isc.sans.edu/forums/diary/Sigma+rules+The+generic+signature+format+for+SIEM+systems/26258/
- Repository and readme: https://github.com/SigmaHQ/sigma
### Sigma Example
```
    title: Webshell Detection by Keyword
    description: Detects webshells that use GET requests by keyword searches in URL strings
    author: Florian Roth
    logsource:
        type: webserver
    detection:
        keywords:
            - '=whoami'
            - '=net%20user'
            - '=cmd%20/c%20'
        condition: selection and keywords
    falsepositives:
        - Web sites like wikis with articles on os commands and pages that include the os commands in the URLs
        - User searches in search boxes of the respective website
    level: high
```

<!-- Needs work -->
## Snap Attack (Signature Testing)
- Proprietary system for analytics validation, uses purple teaming methodology (red + blue)
    - Used to build/test analytics that can be exported to production environments
    - Blue team builds analytics, red team creates penetration tests to validate those analytics
    - Snap Attack brings blue+red work into a unified dashboard, can filter this dashboard
- Blue team's untested analytics are considered red team's backlog
- Red team's undetected threats are labeled attacks with no analytic yet tested against it
- Validated analytics are the merge point, where labeled threats and created analytics are tested
### Snap Attack Process
1. Red team studies a technique (how) and tactic (why)
2. Red team recreates the attack and records it
    - Choose the system, choose an optional attacker framework like Kali Linux (Metasploit), then perform attack
3. Red team labels certain moments in the recording for the techniques/subtechniques being performed at that moment
    - Existing analytics can be referenced in these labels
4. Blue team analyzes the recording and labeling
    - Log analysis through Splunk (button at top of interface)
    - Keystrokes in main body from button "Keystrokes"
5. Blue team creates an analytic based on the labeled technique/subtechnique's signatures using Sigma signature format
    - Creating the analytic from selecting an attack populates defaults for the analytic (easier than from scratch)
    - Interface makes it easy to build analytic logic (rules)
    - Further refinement of analytic logic can be done in Sigma signature format with click of a button on interface
6. Purple team validates the analytic
7. Validated analytic is exported using a format of choice (several options)

[[Return to Top]](#table-of-contents)






<!-- 
 ######                                                 ######                                                   
#     # ###### #    #   ##   #    # #  ####  #####     #     # ###### ##### ######  ####  ##### #  ####  #    # 
#     # #      #    #  #  #  #    # # #    # #    #    #     # #        #   #      #    #   #   # #    # ##   # 
######  #####  ###### #    # #    # # #    # #    #    #     # #####    #   #####  #        #   # #    # # #  # 
#     # #      #    # ###### #    # # #    # #####     #     # #        #   #      #        #   # #    # #  # # 
#     # #      #    # #    #  #  #  # #    # #   #     #     # #        #   #      #    #   #   # #    # #   ## 
######  ###### #    # #    #   ##   #  ####  #    #    ######  ######   #   ######  ####    #   #  ####  #    #  
-->

# Behavior-Based Detection

<!-- Needs work -->
## Behavior Creation

<!-- Needs work -->
## Behavior Implementation
- 

[[Return to Top]](#table-of-contents)






<!-- 
 ######                                                      #######                             
#     # ###### ##### ######  ####  ##### #  ####  #    #       #     ####   ####  #       ####  
#     # #        #   #      #    #   #   # #    # ##   #       #    #    # #    # #      #      
#     # #####    #   #####  #        #   # #    # # #  #       #    #    # #    # #       ####  
#     # #        #   #      #        #   # #    # #  # #       #    #    # #    # #           # 
#     # #        #   #      #    #   #   # #    # #   ##       #    #    # #    # #      #    # 
######  ######   #   ######  ####    #   #  ####  #    #       #     ####   ####  ######  ####   
-->

# Attack Detection Tools

<!-- Needs work -->
## Tool Here
- How tool implements signature-based detection
- How tool implements behavior-based detection

[[Return to Top]](#table-of-contents)






<!-- 
###################################################################################################

   #                                                          
  # #   ##### #####   ##    ####  #    # ###### #####   ####  
 #   #    #     #    #  #  #    # #   #  #      #    # #      
#     #   #     #   #    # #      ####   #####  #    #  ####  
#######   #     #   ###### #      #  #   #      #####       # 
#     #   #     #   #    # #    # #   #  #      #   #  #    # 
#     #   #     #   #    #  ####  #    # ###### #    #  ####  
                                                              
                         #####                                                          
  ##   #    # #####     #     # ##### #####    ##   ##### ######  ####  # ######  ####  
 #  #  ##   # #    #    #         #   #    #  #  #    #   #      #    # # #      #      
#    # # #  # #    #     #####    #   #    # #    #   #   #####  #      # #####   ####  
###### #  # # #    #          #   #   #####  ######   #   #      #  ### # #           # 
#    # #   ## #    #    #     #   #   #   #  #    #   #   #      #    # # #      #    # 
#    # #    # #####      #####    #   #    # #    #   #   ######  ####  # ######  ####  

###################################################################################################
-->

<!-- Needs work -->
# Attackers and Strategies

<!-- Needs work -->
## [APT28](https://attack.mitre.org/groups/G0007/)
- Background
- Hashes and Detection Strategies
### APT28 Strategy 1
- **Initial Access** - T1566.001/T1566.002: Spearphishing Attachment/Spearphishing Link
    - [T1566.001](https://attack.mitre.org/techniques/T1566/001/): APT28 sent spearphishing emails containing malicious Microsoft Office and RAR attachments.
    - [T1566.002](https://attack.mitre.org/techniques/T1566/002/): APT28 sent spearphishing emails which used a URL-shortener service to masquerade as a legitimate service and to redirect targets to credential harvesting sites.
- **Execution** - T1059.003: Windows Command Shell
    - [T1059.003](https://attack.mitre.org/techniques/T1059/003/): An APT28 loader Trojan uses a cmd.exe and batch script to run its payload. The group has also used macros to execute payloads.
- **C2** - T1071.001/T1071.003: Web Protocols/Mail Protocols
    - [T1071.001](https://attack.mitre.org/techniques/T1071/001/): Later implants used by APT28, such as CHOPSTICK, use a blend of HTTP, HTTPS, and other legitimate channels for C2, depending on module configuration.
    - [T1071.003](https://attack.mitre.org/techniques/T1071/003/): APT28 has used IMAP, POP3, and SMTP for a communication channel in various implants, including using self-registered Google Mail accounts and later compromised email servers of its victims.
- **Exfiltration** - T1048.002: Exfiltration Over Asymmetric Encrypted Non-C2 Protocol
    - [T1048.002](https://attack.mitre.org/techniques/T1048/002/): APT28 has exfiltrated archives of collected data previously staged on a target's OWA server via HTTPS.
### APT28 Extra Techniques
- 

<!-- Needs work -->
## [APT29](https://attack.mitre.org/groups/G0016/)
- Background
- Hashes and Detection Strategies
### APT29 Strategy 1
- **Initial Access** - T1195.002: Compromise Software Supply Chain
- **Execution** - T1059.001: Command and Scripting Interpreter: PowerShell
- **C2** - T1071.001: Web Protocols
- **Collection** - T1560.001: Archive via Utility
### APT29 Extra Techniques
- 

<!-- Needs work -->
## [Leviathan](https://attack.mitre.org/groups/G0065/)
- Background
- Hashes and Detection Strategies
### Leviathan Strategy 1
- **Initial Access** - T1133: External Remote Services
- **Execution** - T1059.001: PowerShell
- **Collection** - T1560: Archive Collected Data
- **C2** - T1572: Protocol Tunneling
### Leviathan Extra Techniques
- 

<!-- Needs work -->
## [Sandworm Team](https://attack.mitre.org/groups/G0034/)
- Background
- Hashes and Detection Strategies
### Sandworm Team Strategy 1
- **Initial Access** - T1195.002: Compromise Software Supply Chain
- **Persistence** - T1133: External Remote Services
- **C2** - T1105: Ingress Tool Transfer
- **Exfiltration** - T1041: Exfiltration over C2 Channel
### Sandworm Team Extra Techniques
- 

[[Return to Top]](#table-of-contents)