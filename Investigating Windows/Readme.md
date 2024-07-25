# Incident Response & Forensics
## Challenge: [Investigating Windows](https://tryhackme.com/r/room/investigatingwindows) 
Description: A windows machine has been hacked, its your job to go investigate this windows machine and find clues to what the hacker might have done.

### Whats the version and year of the windows machine?

__Answer: Windows Server 2016__

### Which user logged in last?


__Answer: Administrator__

### When did John log onto the system last?


__Answer: 03/02/2019 5:48:32 PM__

### What IP does the system connect to when it first starts?

The Registry Editor window will pop up. Follow this path, HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Run. Once you reach that location, you will see two values. The UpdateSvc looks sus, checking it out reveals the IP address that the remote machine connects to when it starts up.
__Answer: 10.34.2.3__

### What two accounts had administrative privileges (other than the Administrator user)?

__Answer: Jenny Guest__

### Whats the name of the scheduled task that is malicous.

__Answer: Clean file system__

### What file was the task trying to run daily?

__Answer: nc.ps1__

### What port did this file listen locally for?

__Answer: 1348__

### When did Jenny last logon?

__Answer: Never__

### At what date did the compromise take place?

__Answer: 03/02/2019__

### At what time did Windows first assign special privileges to a new logon?

__Answer: 03/02/2019 4:04:49 PM__

### What tool was used to get Windows passwords?

__Answer: Mimikatz__

### What was the attackers external control and command servers IP?

__Answer: 76.32.97.132__

### What was the extension name of the shell uploaded via the servers website?

__Answer: .jsp__

### What was the last port the attacker opened?

__1337__

### Check for DNS poisoning, what site was targeted?
__google.com__
