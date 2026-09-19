* **Repository Name:** `godfred-cybersecurity-portfolio`
* **Repository Description:** `Hands-on cybersecurity portfolio featuring network reconnaissance, vulnerability assessments, system hardening, and threat remediation labs.`
* **Directory Path inside Repository:** `project-6-vulnerability-assessment/`

---

### Complete GitHub `README.md` Draft (with Header Context)

```markdown
# Project #6: Vulnerability Assessment & Remediation Lab

**Repository:** `godfred-cybersecurity-portfolio`  
**Path:** `project-6-vulnerability-assessment/`  
**Description:** Hands-on vulnerability assessment, threat detection, active exploitation analysis, and host-level service remediation against a Metasploitable2 target.

---

## Executive Summary
This lab demonstrates an end-to-end vulnerability assessment, risk identification, active exploitation verification, and remediation lifecycle. Using an Ubuntu attack workstation targeting a Metasploitable2 virtual machine in an isolated lab environment, network reconnaissance and vulnerability scans were conducted using Nmap. A high-risk backdoor vulnerability on port 6667 (UnrealIRCd) was remediated, and post-remediation re-scanning confirmed successful service termination and port closure.

---

## Environment & Target Configuration
- **Attacker Workstation:** Ubuntu Linux (`Cybersecurity-Lab` / `192.168.56.102`)
- **Target System:** Metasploitable2 (`192.168.56.101`)
- **Network Layout:** VirtualBox Host-Only Isolated Network (`192.168.56.0/24`)

---

## Key Findings & Vulnerability Analysis

| Port / Service | Identified Vulnerability | Severity | Impact / Remediation |
| :--- | :--- | :--- | :--- |
| **6667/TCP (IRC)** | UnrealIRCd 3.2.8.1 Backdoor | **Critical** | Allows remote execution of arbitrary system commands. Service terminated (`sudo pkill unrealircd`). |
| **80/TCP (HTTP)** | Slowloris DoS (CVE-2007-6750) | **High** | Starves HTTP server connection pool causing Denial of Service. |
| **21/TCP (FTP)** | ProFTPD 1.3.1 Exploitable | **Medium** | Known authentication bypass and command execution bugs. |

---

## Remediation & Verification
To remediate the critical UnrealIRCd backdoor finding:
1. Terminated the running IRC service process on the target machine:
   ```bash
   sudo pkill unrealircd

```

2. Executed a targeted Nmap verification scan against port 6667:
```bash
sudo nmap -p 6667 192.168.56.101

```


3. Confirmed port state transitioned to **`6667/tcp closed irc`**.

---

## Evidence & Artifacts

* **Network Connectivity:** `screenshots/02-network-ping-test.png`
* **Initial Reconnaissance:** `screenshots/03-nmap-stealth-scan.png`
* **Vulnerability Assessment:** `screenshots/04-nmap-vuln-scan.png`
* **Post-Remediation Verification:** `screenshots/05-post-remediation-verification.png`
* **Raw Scan Logs:** `nmap_initial_scan.txt`, `nmap_vuln_scan.txt`

```

```
