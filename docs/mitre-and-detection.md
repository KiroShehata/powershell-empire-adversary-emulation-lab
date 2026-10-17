# MITRE ATT&CK & defensive visibility

**Observed:** Ingress Tool Transfer (T1105): Windows successfully retrieved a hosted batch file using certutil.

**Not verified:** Windows batch-file execution, PowerShell-based execution (T1059.001), and HTTP-based command-and-control (T1071.001). Do not label these as confirmed without process and network telemetry.

## Defensive questions

- Does a signed Windows utility retrieve a script from an unexpected host?
- Is the destination file followed by unusual command-shell or PowerShell process creation?
- Does the endpoint initiate recurring network connections after retrieval?
- Can Sysmon, Windows event logs, web-server logs, and SIEM alerts be correlated on a timeline?

## Log sources

- Windows Security 4688: process creation when auditing is enabled
- Sysmon 1: process creation, if Sysmon is installed
- Sysmon 3: network connections, if enabled
- PowerShell 4104: script block logging, when enabled and supported
- Web-server / firewall / proxy logs: HTTP request evidence
