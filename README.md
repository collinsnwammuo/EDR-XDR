# 🛰️ EDR/XDR Lab

A hands-on comparison of endpoint detection and response platforms, deployed against the same Windows 10 VM used throughout my SOC lab. This repo covers Microsoft Defender for Endpoint and CrowdStrike Falcon, and eventually a direct comparison between them, plus how endpoint-level detection compares to the network-level detection I've already built out in my Suricata and SIEM repos.

## 🖥️ Lab Environment

- **Target/test endpoint**: Windows 10 VM (`desktop-go39uhn`, IP `10.0.3.15`), the same host used throughout my Nmap, Suricata, Splunk, ELK, and OpenVAS projects
- **Tenant**: Microsoft 365/Defender trial tenant, created specifically for this lab
- Both platforms deployed as lightweight agents on the same VM, testing whether they can coexist and produce comparable telemetry from identical trigger events

## 📁 Projects

| # | Project | Status |
|---|---|---|
| 01 | [Microsoft Defender for Endpoint](https://github.com/collinsnwammuo/Microsoft-Defender-for-Endpoint) | ✅ Complete |
| 02 | CrowdStrike Falcon | ⏳ Trial pending sales review |
| 03 | Defender vs Falcon Comparison | 🔜 Planned |

### 🟦 [Project 01: Microsoft Defender for Endpoint](https://github.com/collinsnwammuo/Microsoft-Defender-for-Endpoint)
Full deployment: tenant signup, device onboarding via local script, and a real triggered detection using the industry-standard EICAR test file. Covers the actual device timeline showing the full detection chain from browser download through cloud-side alert generation, a real ~15-minute cloud sync delay, and a genuinely interesting nuance where the top-level alert showed no MITRE ATT&CK tagging while a related timeline event was independently tagged T1559 (Inter-Process Communication).

### 🟧 Project 02: CrowdStrike Falcon (Pending)
Falcon's trial signup goes through a sales review process rather than instant self-serve access. Request submitted, response expected within 24 hours per CrowdStrike's confirmation. This project will follow the same pattern as Project 01 once access is granted: deploy the sensor, trigger a detection, document the alert and timeline.

### ⚖️ Project 03: Defender vs Falcon Comparison (Planned)
Once both platforms have a documented detection, a side-by-side comparison covering alert depth, time-to-cloud-alert, ATT&CK mapping consistency, and process tree/timeline visualization quality. Will also tie back to my existing network-level detection stack (Suricata/Splunk/Kibana) to compare what endpoint telemetry catches versus what network telemetry catches for the same category of activity.
