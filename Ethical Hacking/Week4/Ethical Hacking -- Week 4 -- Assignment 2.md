**What specific data were you able to enumerate?**
- I was able to enumerate usernames and password hashes using SQL injection to attack a Damn Vulnerable Web Application (DVWA) using MySQL
	- credentials for the admin account, and also pablo because he was cool
**How did the vulnerability scan complement your enumeration results?**
- Used Nikto and GVM to scan for vulnerabilities
	- detected rexec and SMB, which are exploitable, but I’ve already done SMB
	- Nikto presented known CVEs that are susceptible so SQL injection\
**Why is enumeration considered a high-risk activity from an ethical standpoint?**
- enumeration is a form of active recon, so you can trip IDS/IPS and then get caught! 💀
**What could go wrong if enumeration is performed without permission?**
- enumerating without permissions may trigger alerts, cause congestion, and may violate laws
	- HIPAA, GDPR
