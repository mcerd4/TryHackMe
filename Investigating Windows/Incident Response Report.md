# Incident Response Report: Investigating Windows

## 1. Executive Summary
On July 25, 2024, a security incident was identified during the "Investigating Windows" Capture The Flag (CTF) challenge on TryHackMe. A Windows Server 2016 machine had been compromised, and the objective was to investigate the system to determine the actions taken by the attacker. This report details the findings, methods used to uncover the malicious activity, and recommendations for preventing future incidents.

## 2. Incident Description
- Challenge Name: Investigating Windows
- Affected System: Windows Server 2016 (Hostname: WIN-CTF01)
- Nature of Incident: Unauthorized access, malware installation, and data exfiltration

### Summary of Events:
- The CTF involved compromising a Windows server to capture specific flags representing sensitive information.
- Unauthorized access was gained by an attacker who exploited vulnerabilities and escalated privileges to the administrator level.
- Various suspicious activities were observed, including the creation of malicious scheduled tasks, unauthorized file execution, and network connections to external IP addresses.

## 3. Detection and Identification
### Detection Method:
The incident was detected during a CTF challenge, where participants were tasked with investigating the compromised Windows machine. Key findings included:
- **Windows Version:** The machine was identified as Windows Server 2016 using the systeminfo command in PowerShell.
- **Last User Login:** The last user to log in was the Administrator.
- **User Account Access:** The net user command revealed that the "Administrator" was the last user to access the system.

### Initial Response:
Upon detection, the following steps were taken:
- Collected logs and evidence from the system, including user activity, scheduled tasks, and network connections.
- Isolated the machine from the network to prevent further data exfiltration.
- Began a detailed forensic investigation to identify the scope and impact of the breach.

## 4. Investigation Findings
- **Windows Version and Year:** Windows Server 2016
- **Last User Login:** Administrator
- **John's Last Login:** 03/02/2019 5:48:32 PM
- **Initial Network Connection IP:** 10.34.2.3
- **Accounts with Administrative Privileges (excluding Administrator):** Jenny, Guest
- **Malicious Scheduled Task:** Clean file system
- **File Executed by Malicious Task:** nc.ps1
- **Port Listened by Malicious File:** 1348
- **Jenny's Last Login:** Never
- **Date of Compromise:** 03/02/2019
- **Time Special Privileges Assigned:** 03/02/2019 4:04:49 PM
- **Tool Used to Steal Passwords:** Mimikatz
- **External Command and Control Server IP:** 76.32.97.132
- **Extension Name of Uploaded Shell:** .jsp
- **Last Port Opened by Attacker:** 1337
- **DNS Poisoning Target:** google.com

## 5. Impact Assessment
### Data Compromised:
- Sensitive system information, including password hashes, was compromised using tools like Mimikatz.
- The attacker established persistent access by creating malicious scheduled tasks and opening network ports.

### Operational Impact:
- The system's integrity was significantly compromised, and the attacker had full administrative control during the breach.

## 6. Mitigation and Containment
### Immediate Actions Taken:
- Removed the malicious scheduled task and stopped the associated script (nc.ps1).
- Closed all unauthorized ports opened by the attacker.
- Updated all security patches and ensured that Mimikatz and similar tools could no longer operate effectively on the system.
### Long-term Recommendations:
- Implement Multi-Factor Authentication (MFA) for all users with administrative privileges.
- Regularly audit user accounts and access privileges to identify and remove unnecessary administrative rights.
- Conduct thorough security assessments to detect and mitigate vulnerabilities in remote access configurations.

## 7. Lessons Learned
This incident underscores the importance of maintaining strict access controls and monitoring system activities, particularly on critical servers. The use of strong, unique passwords and the disabling of unnecessary services (such as Guest accounts) are vital to prevent similar breaches.  

## 8. Conclusion
The investigation of the compromised Windows Server 2016 machine revealed several weaknesses that were exploited by the attacker. Through detailed forensic analysis, the attacker's methods were uncovered, and steps were taken to prevent future incidents. Continuous monitoring and proactive security measures are essential to safeguard against such threats.
