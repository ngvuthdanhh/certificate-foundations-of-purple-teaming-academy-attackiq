# Playbook: Phishing Response (Email-based)

**Objective:** Automate triage of suspicious emails, quarantine attachments/mailboxes if required, and gather IOCs for hunting.

**Trigger:**
- SIEM/Email gateway alert: phishing URL/attachment.
- User-reported phishing via report button.

**Inputs:**
- Message-ID, sender, recipients, subject, attachment hashes, URLs.

**Priority:** High

**Automated Actions:**
1. Enrich sender & URLs via Threat Intel (VirusTotal, internal TI).  
2. If attachment exists: extract, compute SHA256, and submit to sandbox.  
3. Query mailbox activity (recent logins, rules creation).  
4. Quarantine attachment and block URL at proxy if reputation is malicious.  
5. If spoofed domain detected: create mail-flow rule to quarantine similar messages.  

**Manual Actions:**
- Analyst reviews sandbox results and decides containment level (disable account, force password reset).  
- Notify impacted users with remediation steps.  

**Remediation:**
- If compromise confirmed: enforce MFA reset, revoke sessions, and run EDR scans.  
- Update IOC lists (hashes, domains, URLs) and push to SIEM/EDR.  

**Rollback:**
- Restore quarantined emails if false positive.  
- Remove temporary mail rules.  

**Testing:**
- Simulate benign & malicious phishing.  
- Validate: sandbox submission, URL blocking, mailbox quarantine, session revocation.  

**KPIs:**
- Time to triage < 15 min.  
- Time to contain < 60 min.  
- False positive rate.  
