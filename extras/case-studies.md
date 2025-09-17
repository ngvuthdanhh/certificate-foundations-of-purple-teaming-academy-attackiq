# Case Studies

## Case Study 1 – Ransomware Simulation
- **Scenario**: Adversary encrypts files on endpoints.  
- **Red Team Action**: Simulated ransomware execution using MITRE ATT&CK technique T1486.  
- **Blue Team Detection**: Monitored unusual file extensions and spikes in file writes.  
- **Purple Team Outcome**: Detection rule improved by adding correlation between process and file events.  

## Case Study 2 – Credential Dumping
- **Scenario**: Attacker attempts credential theft from LSASS.  
- **Red Team Action**: Used Mimikatz in controlled environment.  
- **Blue Team Detection**: EDR alert on LSASS memory access.  
- **Purple Team Outcome**: Validated SIEM correlation rule, improved hunt queries.  

## Case Study 3 – Phishing Campaign
- **Scenario**: Malicious email attachment delivered.  
- **Red Team Action**: Delivered simulated malicious doc with macro.  
- **Blue Team Detection**: Identified unusual process spawn (winword → powershell).  
- **Purple Team Outcome**: Playbook created to auto-contain user account on detection.  
