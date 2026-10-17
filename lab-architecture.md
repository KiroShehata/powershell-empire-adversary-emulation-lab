# Lab architecture

The evidence shows a VMware Workstation-based Windows 7 x64 endpoint and a Kali Linux system reachable on an RFC 1918 private subnet (`172.20.10.0/24`). The Kali host served the test batch file via a Python HTTP server on TCP port 8000, and the Windows system used built-in tools to retrieve it. A separate screenshot depicts an Empire console; the relationship between that console and this exact endpoint is unverified from the surviving captures.

```text
Kali Linux test VM (172.20.10.5)
    |  Python HTTP server / file delivery
    |  private lab connectivity
Windows 7 x64 test VM (IP not established in screenshots)
    |  ping + certutil download + directory listing
```

For a future repeat, keep the network isolated from any production or third-party systems, use snapshots, and document endpoint address, network mode, and telemetry instrumentation.
