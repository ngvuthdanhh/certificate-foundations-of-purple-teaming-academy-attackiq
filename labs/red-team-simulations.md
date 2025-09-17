# Red Team Simulations

## Simulation 1 – Credential Dumping
- **Technique**: T1003 (OS Credential Dumping).  
- **Execution**: Use Mimikatz in controlled lab.  
- **Expected Detection**: LSASS access alerts.  

## Simulation 2 – Lateral Movement
- **Technique**: T1021 (Remote Services).  
- **Execution**: Pass-the-Hash into remote machine.  
- **Expected Detection**: Suspicious SMB session from unusual host.  

## Simulation 3 – Data Exfiltration
- **Technique**: T1041 (Exfiltration over Command & Control Channel).  
- **Execution**: Compress and send file via HTTPS to attacker server.  
- **Expected Detection**: Abnormal outbound connection volume.  
