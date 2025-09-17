# Playbook: Lateral Movement Detection & Containment

**Objective:** Detect and contain lateral movement.

**Trigger:**
- EDR/SIEM detects Pass-the-Hash, RDP/SMB abuse, suspicious service creation.  

**Inputs:**
- Source host, destination host(s), user, auth method.  

**Priority:** Critical  

**Automated Actions:**
1. Correlate abnormal connections.  
2. Quarantine source host.  
3. Block SMB/RDP from source.  
4. Invoke credential theft playbook for impacted accounts.  
5. Collect artifacts from source/destination endpoints.  

**Manual Actions:**
- Incident handler decides rebuild if confirmed.  

**Remediation:**
- Reimage hosts.  
- Reset credentials.  
- Patch exploited services.  

**Testing:**
- Simulate Pass-the-Hash in lab.  

**KPIs:**
- Containment time.  
