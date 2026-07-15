# Troubleshooting Notes

## Issue

Event ID 4688 not generated.

### Resolution

Enable Process Creation auditing.

Run:

gpupdate /force

Restart the VM if required.

---

## Issue

No command line visible.

### Resolution

Enable:

Include command line in process creation events

through Local Group Policy.

---

## Issue

Security log does not contain recent events.

### Resolution

Verify auditing is enabled.

Execute commands again after policy refresh.

---

## Issue

PowerShell event not found.

### Resolution

Launch PowerShell again using:

powershell

or

powershell -Command "Write-Host Test"

---

## Issue

cmdkey returned no stored credentials.

### Resolution

Expected behavior.

The command still generates valuable process creation evidence.

---

## Issue

Unable to filter Event ID 4688.

### Resolution

Event Viewer

Windows Logs

Security

Filter Current Log

4688

---

## Issue

No Process Creation auditing after enabling policy.

### Resolution

Run:

gpupdate /force

Verify audit policy:

auditpol /get /subcategory:"Process Creation"

---

## Best Practices

Enable command-line auditing.

Preserve Security Logs before investigation.

Document timestamps.

Correlate multiple commands instead of relying on a single IOC.

Investigate parent-child process relationships whenever possible.

Always build a timeline before reaching conclusions.
