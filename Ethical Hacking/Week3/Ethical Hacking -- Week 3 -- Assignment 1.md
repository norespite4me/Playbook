# Screenshots
![[Pasted image 20250729021620.png]]
# Recap
## 5.1.4 Lab – Scanning for SMB Vulnerabilities with enum4linux
- used nmap to search for hosts that are using samba services
- use enum4linux to enumerate users, file shares, groups, password policies, and printers
	- -U, -S, -G, -P, -i
		- respectively
- smbclient to trasnfer malicious files to the fileshare

## 5.1.16 Lab – On-Path Attacks with Ettercap (there is no lab in 5.2)
- initiated an ssh connection to a host and spoofed MAC address to intercept data
- used ettercat to analyze traffic and export pcap to make it readable for wireshark
- observed arp spoofing attack in wireshark to verify that the two IP addresses had the same MAC address