# Playbook: Suspected Ransomware / Malware Containment

**Objective:** Quickly isolate suspected ransomware hosts, preserve logs, and prevent spread.

**Trigger:**
- EDR alert: mass file encryption, ransom note creation.  
- SIEM correlation: multiple endpoints show suspicious file activity.  

**Inputs:**
- Hostname, IP, user, process name, process hash, file paths.  

**Priority:** Critical  

**Automated Actions:**
1. Isolate host via EDR/firewall.  
2. Capture forensic snapshot & memory dump.  
3. Kill suspicious process and collect process tree.  
4. Block process hash and C2 domains globally.  
5. Unmap SMB shares and pause backups to prevent corruption.  

**Manual Actions:**
- Forensics team reviews artifacts and decides rebuild vs cleaning.  

**Remediation:**
- Restore from clean backup.  
- Rotate service credentials.  
- Patch exploited vulnerabilities.  

**Rollback:**
- Reconnect host to network only after verification.  

**Testing:**
- Tabletop + controlled ransomware simulation.  

**KPIs:**
- Host isolation < 5 minutes.  
- % forensic captures successful.  
