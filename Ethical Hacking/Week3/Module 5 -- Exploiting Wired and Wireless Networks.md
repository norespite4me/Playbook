Tags: [[Ethical Hacking]] [[Notes]]

# Module 5 -- Exploiting Wired and Wireless Networks
| Topic Title                              | Topic Objectives                                     |
| ---------------------------------------- | ---------------------------------------------------- |
| Exploiting Network-Based Vulnerabilities | explain how to exploit network-based vulnerabilities |
| Exploiting Wireless Vulnerabilities      | Explain how to exploit wireless vulnerabilities      |
## 5.1 – Exploiting Network-Based Vulnerabilities
### 5.1.2 – Windows Name Resolution and SMB Attacks
Name resolution is one of the most fundamental aspects of networking, operating systems, and applications
**NetBIOS Name Service and LLMNR**
- NetBIOS and LLMNR are protocols that are used primarily by Microsoft Windows for host identification
- LLMNR
	- based on DNS protocol format
	- allows hosts on the same local link to perform name resolution for other hosts
- provides three different services
	- *NetBIOS Name Service (NetBIOS-NS)* for name registration and resolution
	- *Datagram Service (NetBIOS-DGM)* for connectionless communication
	- *Session Service (NetBIOS-SSN)* for connection-oriented communication
- NetBIOS-related operations use the following ports and protocols
	- *TCP port 135:* Microsoft Remote Procedure Call (MS-RPC) endpoint mapper, used for client-to-client and server-to-client communication
	- *UDP port 137:* NetBIOS Name Service
	- *UDP port 138:* NetBIOS Datagram Service
	- *UDP port 139:* NetBIOS Session Service
	- *TCP port 445:* SMB protocol, used for sharing files between different operating, including Windows and Unix-based systems

In windows, a workgroup is a LAN p2p network that can support a maximum of 10 hosts in the same subnet
- no centralized admin
- each user controls resources and security locally on their own system

A common vulnerability in LLMNR involves an attacker spoofing an authoritative source for name resolution on a victim system by responding to LLMNR traffic over UDP port 5355 and NBT-NS traffic over UDP port 137
- essentially poisons the LLMNR service
- can be conducted by several tools
	- NBNSpoof
	- Metasploit
	- Responder

**SMB Exploits**
- historically suffered from numerous catastrophic vulnerabilities
- most common in recent is ExternalBlue
	- leaked by entity called Shadow Brokers
		- stole many exploits from the NSA
	- allows unauthenticated remote attacker to compromise an affected system and execute arbitrary code
	- WannaCry and NYET
### 5.1.4 – Lab: Scanning for SMB Vulnerabilities with enum4linux
**Relative Identifier (RID)** –  a variable length number that is assigned to objects at creation and becomes part of the object’s security identifier
**Security Identifier (SID)** – primary key fort something in active directory (AD)
**Domain Controller (DC)** – a server that manages user authentication and access to resources within a network domain
**Lightweight Directory Access Protocol** – a protocol used to access and manage directory information services over a network
**Workgroup** – a collection of computers connected on a local area network (LAN) that share resources and responsibilities without centralized control
### 5.1.5 – DNS Cache Poisoning
**DNS Cache Poisoning** is another popular attack leveraged by threat actors
- manipulates DNS resolver cache through the injection of corrupted DNS data
**Step 1**
- attacker corrupts data of the DNS server cache to impersonate a website
**Step 2**
- after attacker executes the DNS poisoning attack, the DNS server resolves to the IP address of the attacker’s system
**Step 3**
- victim sends a request to the DNS server to obtain the IP address of the domain
**Step 4**
- The DNS server replies with the IP address of the attacker’s system
**Step 5**
- The victim sends an HTTP GET to the attacker’s system, and the attacker impersonates the domain
### 5.1.7 – SNMP Exploits
*Simple Network Management Protocol (SNMP)* is a protocol that many individuals and organizations use to manage network devices
- uses UDP port 161
- in SNMP implementations, every network device contains an SNMP agent that connects with an independent SNMP server
- managed device is kept in a database called the *Management Information Base (MIB)*
- Common attack involves attacker enumerating SNMP services and then checking for configured default SNMP passwords
### 5.1.8 – SMTP Exploits
Attackers may leverage insecure SMTP servers to send spam and conduct phishing and other email-based attacks
- SMTP is a server-to-server protocol, which is different from client/server protocols such as POP3 or IMAP
**SMTP Open Relays**
- the term used for an email server that accepts and relays emails from any user
	- can abuse this to send spoofed emails, spam, phishing, and other email-related scams
	- nmap has an NSE script to test for open relay configs
**Useful SMTP Commands**
- HELO
	- used to initiate an SMTP convo with an email server
		- followed by IP address or domain name
- EHLO
	- used to initiate a conversation with an Extended SMTP server
	- used in same way as HELO command
- STARTTLS
	- used to start a Transport Layer Security (TLS) connection to an email server
- RCPT
	- used to denote the email address of the recipient
- DATA
	- used to initiate the transfer of the contents of an email message
- RSET
	- used to reset/cancel an email transaction
- MAIL
	- used to denote the email address of the sender
- QUIT
	- used to close a connection
- HELP
	- used to display a help menu
- AUTH
	- used to verify whether a user’s email mailbox exists
- VRFY
	- used to verify whether a user’s email mailbox exists
- EXPN
	- used to request, or expand, a mailing list on the remote server

The *smtp-user-enum* tool enables you to automate these information-gathering steps

**Known SMTP Server Exploits**
It is possible to take advantage of exploits that have been created to leverage known SMTP-related vulnerabilities
### 5.1.10 – FTP Exploits
Attackers often abuse FTP servers to steal information
- legacy FTP protocol doesn’t use encryption or perform any kind of integrity validation

The SFTP and FTPS protocols use encryption to protect data; however, some implementations – such as Blowfish and DES – offer weak encryption ciphers
- use stronger such as AES
- SFTP and FTPS servers use hashing algs to verify the integrity of file transmission

FTP servers often enable anonymous user auth, which an attacker may abuse to store unwanted files in your server, potentially for exfiltration
- an attacker who compromises a system and extracts sensitive information can store that information to any FTP server that may be available and allows any user to connect using the anonymous account

**Some Best Practices for Mitigating FTP Server Abuse & Attacks**
- use strong passwords and MFA
- implement file and folder security
- use encryption at rest
- lock down administration accounts
- keep the FTPS or SFTP server software up-to-date
- use the US gov FIPS 140-2 validation encryption ciphers for general guidance on what encryption algs to use
- keep any back-end database on a diff server than the FTP server
- require re-auth of inactive sessions
### 5.1.11 – Pass-the-Hash Attacks
All versions of Windows store passwords as hashes in a file called the *Security Accounts Manager (SAM)* file
- OS does not know what the actual pass is because it stores only a hash of the pass

Microsoft has it’s own suite of security protocols
- New Technology LAN Manager (NTLM)
	- two versions
		- NTLMv1/2
- since win2k, they have used Kerberos in windomains

A *Pass-the-Hash Attack* is when, instead of trying to figure out the password, the attacker can just use a password hash and then use that to login to another client or server system
- instead of entering a password, the has is authenticated
- Mimikatz thru Metasploit
### 5.1.12 – Kerberos and LDAP-based Attacks
*Kerberos* is an authentication protocol defined in RFC 4120 that has been used by Windows for a number of years
- also used by numerous apps and OSes
- contains three basic elements
	- Client
	- Server
	- Key Distribution Center (KDC), including the authentication server and the ticket-granting server

**Step 1**
- the client send a request to the auth server within the KDC
**Step 2**
- The authentication server sends a session key and a ticket-granting ticket (TGT) that is used to verify the client’s identity
**Step 3**
- The client sends the TGT to the ticket-granting server
**Step 4**
- The ticket-granting server generates and sends a ticket to the client
**Step 5**
- The client presents the ticket to the server
**Step 6**
- The server grants access to the client

AD uses LDAP as an access protocol
- windows LDAP supports Kerberos authentication
- LDAP uses inverted tree called Directory Information Tree (DIT)
- every entry has a defined position
- the Distinguished Name (DN) represents the full path of the entry

One of the most common attacks is the Kerberos Golden Ticket Attack
- manipulates Kerberos tickets based on available hashes by compromising a vulnerable system and obtaining the local user credentials and password hashes
- similar is the Silver Ticket Attack
	- forged service tickets for a given service on a particular server
	- Windows Common Internet File System (CIFS) allows you to access files on a particular server, and the HOST service allows you to execute schtasks.exea or Windows Management Instrumentation (WMI) ona  given server

Another Kerberos weakness is the use of unconstrained Kerberos delegation
- allows an application to reuse the end-user credentials to access resources hosted on a different server
### 5.1.13 – Kerberoasting
*Kerberoasting* is a post-exploitation activity that is used by an attacker to extract service account credential hashes from AD for offline cracking
### 5.1.14 – On-Path Attacks
*On-Path Attack* is when an attacker places themself in-line between two devices or individuals that are communicating in order to eavesdrop
- used to be called Man-in-the-Middle (MITM) attacks

**ARP Spoofing and ARP Cache Poisoning**
*ARP Cache Poisoning* is an example of an attack that leads to an on-path attack
- targets hosts, switches, and routers connected to a layer 2 network by poisoning the ARP caches of systems connected to the subnet and intercepting traffic intended for other hosts on the subnet
*Media Access Control (MAC) Spoofing* is an attack in which a threat actor impersonates the MAC address of another device

**Layer 2 Security Best Practices**
- select an unused VLAN and use it as the native VLAN for all your trunks. do not use this native VLAN for any of your enabled access ports. Avoid using VLAN 1 anywhere because it is the default
- Administratively configure switch ports as access ports so that users cannot negotiate a trunk; also disable the negotiation of trunking
- limit the number of MAC addresses learned on a given port using the port security feature
- control spanning tree to stop users or unknown devices from manipulating it. you can do so by using the BPDU Guard and Root Guard features
- turn off Cisco Discover Protocol (CDP) on ports facing untrusted or unknown networks that do not require CDP for anything
- on a new switch, shut down all ports and assign them to a VLAN that is not used for anything other than a parking lot. then bring up the ports and assign correct VLANs as the ports are allocated and needed
- use Root Guard to control which ports are not allowed to become root ports to remote switches
- use DAI
- use IP source Guard to prevent spoofing of Layer 3 information by hosts
- implement 802.1X when possible to authenticate and authorize users before allowing them to communicate to the rest of the netwrok
- use Dynamic Host Configuration Protocol (DHCP) snooping to prevent rogue DHCP servers from impacting the network
- use storm control to limit the amount of broadcast or multicast traffic flowing through a switch. an attacker could perform a *packet storm* attack to cause a DoS condition. the attacker does this by sending excessive transmissions of IP packets in a network
- deploy access control lists (ACLs), such as layer 3 and layer 2 ACLs, for traffic control and policy enforcement

**Downgrade Attacks**
*Downgrade Attack* is when an attacker forces a system to favor a weak encryption protocol or hashing alg that may be susceptible to other vulnerabilities
- Padding Oracle on Downgraded Legacy Encryption (POODLE) vulnerability in OpenSSL
	- has been patched since 2014
### 5.1.17 – Route Manipulation Attacks
Many route manip attacks exist
- one of most common is BGP hijacking
	- Border Gateway Protocol is a dynamic routing protocol used to route internet traffic
- attacker can launch BGP hijacking attack by configuring or compromising an edge router to announce prefixes that have not been assigned to his or her organization
### 5.1.18 – DoS and DDoS Attacks
| **DoS Attack**                 | **Desc**                                                                                                                                                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Direct DoS Attack              | source of attack generates packets, regardless of protocol, application, and so on, that are sent directly to the victim                                                                                            |
| Botnet                         | collection of compromised machines that the attacker can manipulate from a  command and control system to participate in DDoS attack, send spam emails, and perform other illicit activities                        |
| Reflected DoS and DDoS Attacks | attackers send to sources spoofed packets that appear to be from the victim, and then the sources become unwitting participants in the reflected attack by sending the response traffic back to the intended victim |
| Amplification DDoS Attacks     | kind of reflected attack where the response traffic is made up of packets that are much larger than those that were initially sent by the attacker                                                                  |
### 5.1.20 – Network Access Control (NAC) Bypass
NAC is a tech designed to interrogate endpoints before joining a wired or wireless network
- NAC-enabled devices can use several detection techniques to detect the endpoint trying to connect to the network
	- intercepts DHCP requests from endpoints
	- broadcast listener is used to look for network traffic
- can allow specific nodes such as printers, IP phones, and video conferencing equipment to join the network by using an allow list of MAC addresses corresponding to such devices
### 5.1.23 – DHCP Starvation Attacks and Rogue DHCP Servers
- most orgs run DHCP servers
- two most popular attacks are starvation and spoofing
	- in starvation an attacker broadcasts a large number of DHCP REQUEST messages with spoofed source MAC addresses
	- if DHCP server responds to all, available addresses will be taken
## 5.2 – Exploiting Wireless Vulnerabilities
### 5.2.2 – Rogue Access Points
One of the most simplistic wireless attacks involves an attacker installing a rogue AP in a network to fool users to connect to that AP
### 5.2.3  – Evil Twin Attacks
Attacker creates a rogue access point and configures it exactly the same as the existing corporate network
- attacker will use DNS spoofing to redirect victim to cloned captive portal or a website
### 5.2.4 – Disassociation/Deauthentication Attacks
Attackers can cause clients to deauthenticate from APs to either perform a DoS condition or make those clients connect to evil twins
- can use Kismet or KisMAC to listen and capture SSIDs and other wireless network traffic
- airmon-ng command, which is a part of the aircrack-ng suite
### 5.2.5 – Preferred Network List Attacks
- OSes and wireless clients maintain a list of trusted or preferred wireless networks
	- Preferred Network List (PNL)
	- includes wireless network SSID, plaintext passwords, or WEP or WPA passwords
### 5.2.6 – Wireless Signal Jamming and Interference
The purpose of Jamming wireless signals or causing wireless network interference is to create a full or partial DoS condition in the wireless network
### 5.2.7 – War Diving
A method attackers use to find wireless access points wherever they might be
### 5.2.8 – Initialization Vector (IV) Attacks and Unsecured Wireless Protocols
An attacker can cause modificiation on the initialization vector of a wireless packet that is ecnrypted during transmission
- goal is to obtain a lot of information about the plaintext of a single packet and generate another encryption key that can then be used to decrypt other packets using the same IV

**Attacks Against WEP**
- WEP is susceptible to many attacks
	- considered obsolete

**Attacks Against WPA**
- WPA/2 are both susceptible to different vulnerabilities that WPA3 addresses
	- all versions support different authentication methods
- Steps
	- an attacker monitors the wifi network and finds wireless clients connected to the corp-net SSID
	- the attacker sends DeAuth packets to deauth the wireless client
	- the attacker captures the WPA four-way handshake and cracks the WPA PSK

**KRACK Attacks**
- published by Mathy Vanhoef and Frank Piessens from Uni of Leuven
- depends on specific device config
	- could allow unauthenticated attackers to reinstall a previously used encryption or integrity key

**WPA3 Vulnerabilities**
- no tech or protocol is perfect
- dragonfly handshake that uses Extensible Authentication Protocol (EAP)
	- several vulnerabilities can allow an attacker to perform different side-channel attacks, downgrade attacks, and DoS conditions

**Wi-Fi Protected Setup**
- WPS is a protocol that simplifies the deployment of wireless networks
### 5.2.9 – KARMA Attacks
- Karma Attacks Radio Machines Automatically
- on-path attack that involves creating a rogue AP and allowing an attacker to intercept wireless traffic
### 5.2.10 – Fragmentation Attacks
- can be used to acquire 1500 bytes of pseudo-random generation algorithm (PRGA) elements
	- can be launched against WEP-configured devices
### 5.2.12 – Credential Harvesting
- attack that involves obtaining or compromising user credentials
	- can be launched using common social engineering
- Ettercap can spoof DNS replies and divert a user visiting a given website to an attacker’s system
### 5.2.13 – Bluejacking and Bluesnarfing
*Bluejacking* is an attack that can be performed using bluetooth with vulnerable devices in range
*Bluesnarfing* is an attack that gives unauthorized access to information from a bluetooh-enabled device
### 5.2.14 – Bluetooth Low Energy (BLE) Attacks
- many IoT devices use BLE for comms
	- susceptible to on-path attacks
	- attacker can modify BLE messages between systems
### 5.2.15 – Radio-Frequency Identification (RFID) Attacks
- tech that uses electromagnetic fields to identify and track tags that hold electronically stored info
### 5.2.16 – Password Spraying
- a type of credential attack in which an attacker brute-forces logins based on a list of usernames with default passwords of common systems or applications
### 5.2.17 – Exploit Chaining
- most sophisticated attacks leverage multiple vulnerabilities to compromise systems
