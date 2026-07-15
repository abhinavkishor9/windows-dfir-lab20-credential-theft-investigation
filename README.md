# windows-dfir-lab20-credential-theft-investigation
## Overview

Credential theft is one of the most common objectives during post-compromise attacks. Before attempting to dump credentials, attackers typically perform reconnaissance to identify users, privileges, cached credentials, running processes, and system information.

This lab safely simulates suspicious reconnaissance activity using legitimate Windows commands and demonstrates how a SOC analyst can investigate the activity through Windows Security logs.

No credential dumping tools or malware were used.

---

## Objectives

- Simulate credential theft reconnaissance
- Generate Windows Process Creation events
- Investigate Event ID 4688
- Identify suspicious command execution
- Correlate process activity
- Build an investigation timeline
- Document findings

---

## Environment

- Windows 10 VM
- VMware Workstation Player
- Event Viewer
- PowerShell
- Command Prompt
- Windows Security Logs

---

## Skills Practiced

- Windows DFIR
- Credential Theft Investigation
- Process Analysis
- Windows Security Logging
- Event Correlation
- IOC Identification
- Incident Documentation

---

## Investigation Workflow

1. Enable Process Creation auditing
2. Create investigation workspace
3. Execute reconnaissance commands
4. Generate PowerShell activity
5. Review Security Event Logs
6. Analyze Event ID 4688
7. Build investigation timeline
8. Document findings

---

## Suspicious Commands Investigated

- whoami
- whoami /priv
- whoami /groups
- cmdkey /list
- net user
- net localgroup administrators
- tasklist
- systeminfo
- PowerShell execution

---

## Windows Events Reviewed

| Event ID | Description |
|----------|-------------|
| 4688 | Process Creation |
| 4624 | Successful Logon (optional) |
| 4672 | Special Privileges Assigned (optional) |

---

## Indicators Investigated

- Privilege enumeration
- User enumeration
- Local administrator enumeration
- Cached credential inspection
- Running process discovery
- System reconnaissance
- PowerShell execution

---

## MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1003 | OS Credential Dumping (Preparation Phase) |
| T1087 | Account Discovery |
| T1033 | System Owner/User Discovery |
| T1059.001 | PowerShell |
| T1057 | Process Discovery |
| T1082 | System Information Discovery |

---

## Evidence Collected

- Windows Security Logs
- Event ID 4688
- PowerShell Output
- Command Prompt Output
- Process Creation Timeline
- Screenshots

---



## Key Takeaways

- Credential theft often begins with reconnaissance.
- Legitimate Windows commands may indicate malicious intent when executed in sequence.
- Process creation logs provide valuable forensic evidence.
- Event ID 4688 is essential for Windows incident investigations.

---

