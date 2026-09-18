# Metasploitable2 Security Assessment Report

A structured penetration testing portfolio documenting vulnerability analysis, exploitation proofs of concept (PoCs), and remediation strategies against a Metasploitable2 target environment.

---

## 🎯 Target Overview
* **Target OS:** Metasploitable2 (Linux 2.6.24)
* **Target IP:** `192.168.56.20`
* **Attacker Machine:** Kali Linux (`192.168.56.10`)
* **Scope:** Systematic network reconnaissance, service exploitation, and reporting following industry best practices.

---

## 📊 Summary of Findings

| ID | Vulnerability / Service | Severity | CVE | Impact | Status | Report Link |
|---|---|---|---|---|---|---|
| **F02** | vsftpd 2.3.4 Backdoor | Critical (10.0) | CVE-2011-2523 | Remote Code Execution (Root) | Exploded / Documented | [F02 Report](reports/F02-vsftpd-234-backdoor-rce.md) |
| **F03** | UnrealIRCd 3.2.8.1 Backdoor | Critical (10.0) | CVE-2010-2075 | Remote Code Execution (Root) | Exploded / Documented | [F03 Report](reports/F03-unrealircd-3281-backdoor-rce.md) |
| **F04** | Samba `usermap_script` | Critical (10.0) | CVE-2007-2447 | Remote Code Execution (Root) | Exploded / Documented | [F04 Report](reports/F04-samba-usermap-script-rce.md) |

---

## 🛠️ Tooling & Methodology
* **Reconnaissance:** `Nmap` service and OS enumeration
* **Exploitation Framework:** `Metasploit Framework (msfconsole)`
* **Version Control:** `Git` / GitHub documentation workflow
* **Standards Framework:** Mapped to **MITRE ATT&CK** enterprise techniques and **CVSS v3** scoring metrics.

---

## 🔒 Methodology & Ethics
* All assessments conducted exclusively within an isolated virtual lab network (`192.168.56.0/24`).
* Authorized testing conducted strictly for educational and professional skill development purposes.
