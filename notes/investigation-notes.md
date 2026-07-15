# Investigation Notes

## Incident Summary

The SOC received an alert indicating suspicious command execution that may represent credential theft preparation.

The objective was to determine whether the executed commands indicated malicious reconnaissance activity.

---

# Investigation Steps

## Step 1

Enabled Process Creation auditing.

Purpose:

Generate Windows Security Event ID 4688 for executed processes.

---

## Step 2

Created investigation workspace.

Location:

C:\CredentialLab

---

## Step 3

Executed Windows reconnaissance commands.

Observed commands:

- whoami
- whoami /priv
- whoami /groups
- cmdkey /list
- net user
- net localgroup administrators
- tasklist
- systeminfo

---

## Step 4

Executed PowerShell.

Purpose:

Generate PowerShell process creation event.

---

## Step 5

Opened Event Viewer.

Location:

Windows Logs

Security

---

## Step 6

Filtered Event ID 4688.

Verified process creation events.

Collected:

- Process Name
- User
- Parent Process
- Timestamp
- Command Line (when available)

---

# Investigation Findings

Observed user reconnaissance.

Privilege enumeration performed.

Administrator group enumeration performed.

Cached credential inspection attempted.

PowerShell executed.

No evidence of credential dumping.

No malicious binaries executed.

---

# Timeline

Example

09:10

User login

↓

09:11

whoami

↓

09:11

whoami /priv

↓

09:12

cmdkey /list

↓

09:12

net user

↓

09:13

tasklist

↓

09:14

systeminfo

↓

09:15

PowerShell execution

---

# Indicators Observed

User Enumeration

Privilege Enumeration

System Enumeration

Process Discovery

PowerShell Activity

Administrative Reconnaissance

---

# Assessment

The observed activity resembles attacker reconnaissance commonly performed before credential theft.

Although no credential dumping occurred, the command sequence warrants further investigation in a production environment.

---

# Lessons Learned

Process creation logs are valuable forensic artifacts.

Legitimate Windows commands can become suspicious when correlated together.

Credential theft investigations rely heavily on behavioral analysis rather than a single event.

Proper logging significantly improves investigation quality.
