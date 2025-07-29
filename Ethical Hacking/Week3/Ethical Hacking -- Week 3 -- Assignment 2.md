**What scan type did you use this week (TCP, SYN, UDP, etc)?**
- TCP
	- 135 – Microsoft Remote Procedure Call
	- 445 – SMB Protocol
		- mostly looking for Samba services to enumerate users, fileshares, groups, password polices, and printers
- UDP
	- 5355 – LLMNR
	- 137 – NBT-NS
	- 161 – SNMP

**What did your scan results reveal about the system or target?**
- nmap scans revealed which ports were open on network devices
	- targeted devices that used samba services
- revealed target users, fileshares, workgroups, password policies, and printers
	- looking for ports that have SMB services because those are exploitable

**What are some risks of active scanning in a real environment?**
- disruption of normal user workflows because of network congestion
- being detected by IDS/IPS

**How can ethical hackers avoid crossing legal or ethical lines during this phase?**
- Make sure they always have written permission, a statement of work, some sort of contract that outlines the scope of their job and the timeframe they are performing it
- Research and follow local laws and regulations