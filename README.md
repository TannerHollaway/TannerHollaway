<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/TannerHollaway/TannerHollaway/main/assets/banner-dark.svg">
  <img alt="Dakota Hollaway, SOC analyst. I attack my own lab, then build the detections that catch me. Open to Tier 1 SOC roles, remote or in Texas." src="https://raw.githubusercontent.com/TannerHollaway/TannerHollaway/main/assets/banner-light.svg" width="100%">
</picture>

<p>
  <a href="https://www.linkedin.com/in/dakotaholl/"><img alt="LinkedIn" height="28" src="https://img.shields.io/badge/LinkedIn-Message%20me-0A66C2?style=flat-square"></a>
  <a href="https://www.credly.com/users/tanner-hollaway"><img alt="Credly" height="28" src="https://img.shields.io/badge/Credly-Verify%20my%20certs-FF6B00?style=flat-square"></a>
</p>

I'm Dakota (legal name Tanner). I've completed a 6 month SOC analyst internships, and I built a home lab from the firewall up so I can attack it and practice detection end to end. Long term, I'm working toward malware analysis and incident response.

## Experience

| Role | Dates | What I did |
| :-- | :-- | :-- |
| **SOC Analyst Intern** | Feb –⁠ Jul 2026 | Phishing triage, Splunk log review, ticketing, and escalation to Tier 2 |


## Certifications

<p>
  <a href="https://www.credly.com/badges/fee74d29-2be5-4e92-9274-a83b6ed6ad75/public_url"><img alt="CompTIA CySA+" height="28" src="https://img.shields.io/badge/CompTIA-CySA%2B-C8202F?style=flat-square"></a>
  <a href="https://www.credly.com/badges/a16c5c4f-520a-4b38-8507-d6ea522cb425/public_url"><img alt="CompTIA Security+" height="28" src="https://img.shields.io/badge/CompTIA-Security%2B-C8202F?style=flat-square"></a>
  <a href="https://www.credly.com/badges/08cc7d5e-2527-4f83-b2ae-4bb29471d6cc/public_url"><img alt="CompTIA Network+" height="28" src="https://img.shields.io/badge/CompTIA-Network%2B-C8202F?style=flat-square"></a>
  <a href="https://www.credly.com/badges/14c70810-ae17-41f1-b6ee-36fc762ab531/public_url"><img alt="TryHackMe SAL2" height="28" src="https://img.shields.io/badge/TryHackMe-SAL2-212C42?style=flat-square&logo=tryhackme&logoColor=white"></a>
  <a href="https://www.credly.com/badges/abe26ddb-fdce-4d0e-81cb-304966ec1087/public_url"><img alt="TryHackMe SAL1" height="28" src="https://img.shields.io/badge/TryHackMe-SAL1-212C42?style=flat-square&logo=tryhackme&logoColor=white"></a>
</p>

Studying for Blue Team Level 1 (BTL1).

## Featured work

<table>
<tr>
<td width="50%" valign="top">

**[Splunk detection lab](https://github.com/TannerHollaway/Setting-Up-Splunk-and-Simulating-attacks)**

Shipped my AD domain's Security and Sysmon logs into Splunk, attacked it from Kali, and built six ATT&CK-mapped alerts that caught Kerberoasting, privilege creep, and PsExec lateral movement. Then hunted the intrusion from behavior alone.

`Splunk` `SPL` `Sysmon` `Impacket`

</td>
<td width="50%" valign="top">

**[Microsoft Sentinel hybrid SOC](https://github.com/TannerHollaway/sentinel-soc-lab)**

Connected the same domain to Sentinel through Azure Arc, rewrote all six detections in KQL, and re-ran the attack chain: 10 alerts across all six rules. Added a Logic App playbook that enriches attacker IPs automatically.

`Microsoft Sentinel` `KQL` `Azure Arc` `Logic Apps`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Detection as code](https://github.com/TannerHollaway/detection-as-code)**

Five Sigma rules that CI validates and converts to SPL, KQL, and ES|QL whenever a rule changes. I wrote each rule blind, then proved it by firing its Atomic Red Team test at a Windows VM logging to Elastic.

`Sigma` `GitHub Actions` `Elastic` `Atomic Red Team`

</td>
<td width="50%" valign="top">

**[BTLO investigations](https://github.com/TannerHollaway/BTLO-Challenges)**

Write-ups from Blue Team Labs Online: a Dridex infection from a PCAP, an obfuscated PowerShell downloader, a shellcode injection sample, and Sysmon and auditd log analysis.

`Wireshark` `Ghidra` `CyberChef` `Volatility`

</td>
</tr>
</table>

## The lab behind it

Six connected builds that turned my home network into a small, monitored enterprise. See the [series overview](https://github.com/TannerHollaway/MyHomeLab).

| Part | Build |
| :-: | :-- |
| 1 | [OPNsense firewall](https://github.com/TannerHollaway/ReplacingHomeRouterWithOPNsense) replacing my home router |
| 2 | [VLAN segmentation](https://github.com/TannerHollaway/VLAN-Segmentation-and-Multi-SSID-Wireless-Setup) into three isolated networks, with multi-SSID wireless |
| 3 | [Windows Server 2022 Active Directory domain](https://github.com/TannerHollaway/Windows-Server-2022-Active-Directory-Domain) to manage devices and enforce policy |
| 4 | [Domain hardening and Sysmon telemetry](https://github.com/TannerHollaway/Domain-Expansion-Security-Instrumentation) on every host |
| 5 | [Splunk SIEM](https://github.com/TannerHollaway/Setting-Up-Splunk-and-Simulating-attacks), detections, and a threat hunt |
| 6 | [Microsoft Sentinel](https://github.com/TannerHollaway/sentinel-soc-lab) with the same detections in KQL |

<details>
<summary><b>Detection coverage:</b> 11 detections mapped to MITRE ATT&CK, each tested against a simulated attack</summary>
<br>

| Technique | What the detection catches | Fired in |
| :-- | :-- | :-- |
| [T1110](https://attack.mitre.org/techniques/T1110/) Brute Force | Excessive failed logons (4625) | Splunk, Sentinel |
| [T1558.003](https://attack.mitre.org/techniques/T1558/003/) Kerberoasting | RC4 service ticket requests (4769) | Splunk, Sentinel |
| [T1098](https://attack.mitre.org/techniques/T1098/) Account Manipulation | Privileged group changes (4728, 4732, 4756) | Splunk, Sentinel |
| [T1078.002](https://attack.mitre.org/techniques/T1078/002/) Domain Accounts | Tier 0 logon attempts on workstations | Splunk, Sentinel |
| [T1087](https://attack.mitre.org/techniques/T1087/) Account Discovery | Anomalous NTLM authentication | Splunk, Sentinel |
| [T1021.002](https://attack.mitre.org/techniques/T1021/002/) SMB/Windows Admin Shares | Executables dropped to `C:\Windows` (Sysmon 11) | Splunk, Sentinel |
| [T1053.005](https://attack.mitre.org/techniques/T1053/005/) Scheduled Task | Task creation with `schtasks` | Elastic |
| [T1059.001](https://attack.mitre.org/techniques/T1059/001/) PowerShell | Encoded commands | Elastic |
| [T1218.011](https://attack.mitre.org/techniques/T1218/011/) Rundll32 | Rundll32 proxy execution | Elastic |
| [T1003.001](https://attack.mitre.org/techniques/T1003/001/) LSASS Memory | LSASS dumping (comsvcs, ProcDump) | Elastic |
| [T1087.001](https://attack.mitre.org/techniques/T1087/001/), [T1033](https://attack.mitre.org/techniques/T1033/) Discovery | Local account and system enumeration | Elastic |

</details>

## Toolkit

| Area | Tools |
| :-- | :-- |
| SIEM and detection | `Splunk` `SPL` `Microsoft Sentinel` `KQL` `Elastic` `ES\|QL` `Sigma` |
| Endpoint and identity | `Sysmon` `Windows Event Logs` `Active Directory` `Group Policy` `Microsoft Defender` `Entra ID` |
| Cloud | `Azure` `Azure Arc` `Azure Monitor Agent` `Logic Apps` |
| Network | `OPNsense` `VLANs` `Wireshark` `tshark` |
| Analysis | `Ghidra` `Volatility` `CyberChef` `FLOSS` `REMnux` `FlareVM` |
| Attack simulation | `Kali Linux` `Impacket` `Atomic Red Team` `hashcat` |
| Scripting and automation | `Python` `PowerShell` `GitHub Actions` `Docker` |
| Frameworks | `MITRE ATT&CK` `NIST 800-53` |

## More labs

- [Help desk labs](https://github.com/TannerHollaway/HelpDeskLabs): ticket scenarios worked in ServiceDesk Simulator
- [Azure honeynet](https://github.com/TannerHollaway/AzureSentinel), [NIST 800-53 hardening](https://github.com/TannerHollaway/Becoming-NIST-80053-compliant), and [incident response](https://github.com/TannerHollaway/Incident-Response): a deliberately exposed Azure environment, investigated in Sentinel, then hardened
- [Active Directory lab](https://github.com/TannerHollaway/ActiveDirectoryLab): an earlier AD build on Windows Server 2019
