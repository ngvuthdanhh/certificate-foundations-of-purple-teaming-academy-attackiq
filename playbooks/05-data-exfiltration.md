# Playbook: Data Exfiltration Handling

**Objective:** Identify, block, and investigate exfiltration attempts.

**Trigger:**
- Unusual outbound traffic volumes.  
- Long-lived HTTPS sessions to unknown hosts.  

**Inputs:**
- Source host, destination, protocol, bytes transferred, filenames.  

**Priority:** High  

**Automated Actions:**
1. Enrich destination reputation.  
2. Block malicious IP/domain.  
3. Pause account if abnormal transfers.  
4. Collect network captures.  
5. Search for similar transfers.  

**Manual Actions:**
- Compliance/legal review.  

**Remediation:**
- Revoke access, rotate creds, remove exfil tools.  
- Notify stakeholders.  

**Rollback:**
- Unblock destination if false positive.  

**Testing:**
- Simulate exfil over cloud storage.  

**KPIs:**
- Time to detection.  
- % blocked transfers.  
