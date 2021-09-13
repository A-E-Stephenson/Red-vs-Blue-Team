# Blue Team: Summary of Operations

## Table of Contents
- Network Topology



- Description of Targets
- Monitoring the Targets
- Patterns of Traffic & Behavior
- Suggestions for Going Further

### Network Topology

The following machines were identified on the network:

- Capstone
  - Operating System: Ubuntu 18.04.1 
  - Purpose: Capstone 
  - IP Address: 192.168.1.105 

- ELK
  - Operating System:  
  - Purpose: Monitoring System
  - IP Address: 192.168.1.100

- Kali
  - Operating System: Kali GNU/Linux Rolling version: 2020.1
  - Purpose: Attack Machine
  - IP Address: 192.168.1.90

- Target 1
  - Operating System: Debian GNU/Linux version 8
  - Purpose: Target 1
  - IP Address: 192.168.1.110

- Target 2
  - Operating System: Debian GNU/Linux 8 (jessie) 
  Purpose: Target 2
  IP Address: 192.168.1.115/24

### Description of Targets

The target of this attack was: `Target 1`: (192.168.1.110).

Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

### Monitoring the Targets

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:


Excessive HTTP Errors is implemented as follows:
  - Metric: Over 5
  - Threshold: Above 400 for 5 minutes
  - Vulnerability Mitigated: Brute Force Exploit
  - Reliability: Based on the traffic on this website, this would be a high reliability in showing Brute Force Exploit incidents. 

HTTP Request Size Monitor is implemented as follows:
  - Metric: HTTP request bytes over all documents
  - Threshold: 3500 for last 1 minute
  - Vulnerability Mitigated: DOS or Enumeration Exploits 
  - Reliability**: Based on the traffic on this website, this would be a medium reliability in showing DOS or Enumeration Exploit        incidents. 

CPU Usage Monitor is implemented as follows:
  - Metric: Total system process CPU packets are above 0.5
  - Threshold: Above 0.5 for last 1 minute 
  - Vulnerability Mitigated: Rogue Program(s) or Backdoor Exploit
  - Reliability: Based on the system configuration, this would have a low reliabilty in showing Rogue Program(s) or Backdoor Exploit because there may be false positives, however it would alert to potential malicious activity/program(s) running. 

### Suggestions for Going Further (Optional)
- Each alert above pertains to a specific vulnerability/exploit. Recall that alerts only detect malicious behavior, but do not stop it. For each vulnerability/exploit identified by the alerts above, suggest a patch. E.g., implementing a blocklist is an effective tactic against brute-force attacks. It is not necessary to explain _how_ to implement each patch.

The logs and alerts generated during the assessment suggest that this network is susceptible to several active threats, identified by the alerts above. In addition to watching for occurrences of such threats, the network should be hardened against them. The Blue Team suggests that IT implement the fixes below to protect the network:
- Vulnerability 1
  - Patch: PATCH Method for HTTP with OpenFlow implementation.
  - Why It Works: A software network can upload an AI program that intelligently detects and mitigates threats before reaching the vulberable system.
- Vulnerability 2
  - Patch: Method to Block DOS/Enumeration Exploit(s)
  - Why It Works: Microsoft Palo Alto is currently helping to prevent these exploits, however there are other patches available for further mitigation. 
- Vulnerability 3
  - Patch: Advanced Antivirus Software 
  - Why It Works: Advanced antivirus software detects, prevents and mitigates a range of exploits. These antiviruses can then detect backdoor viruses and eliminate them before they infect your system. 
