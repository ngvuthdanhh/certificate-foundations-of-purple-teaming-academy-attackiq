# Playbook: Compromised Credentials

**Objective:** Detect, revoke, and remediate stolen credentials.

**Trigger:**
- Impossible travel / anomalous logins.  
- IOC: credential dump activity flagged by EDR.  

**Inputs:**
- Account name, IPs, login timestamps, device IDs.  

**Priority:** High  

**Automated Actions:**
1. Enrich auth events (GeoIP, device reputation).  
2. Revoke sessions (SSO, VPN, OAuth).  
3. Force password reset and MFA re-enrollment.  
4. Search SIEM for related suspicious logins.  

**Manual Actions:**
- Analyst approves account disablement if needed.  

**Remediation:**
- Reset credentials for service accounts.  
- Investigate root cause (phishing, malware, external breach).  

**Rollback:**
- Re-enable account only after remediation.  

**Testing:**
- Simulate anomalous logins (geo anomalies).  

**KPIs:**
- Session revocation time.  
- % compromised accounts detected automatically.  
