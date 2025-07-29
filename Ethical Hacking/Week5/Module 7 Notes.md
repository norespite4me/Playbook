Tags: [[Ethical Hacking]] [[Notes]]

# Module 7 -- Cloud, Mobile, and IoT Security
## 7.0 – Introduction
### 7.0.1 – Learning Objectives
| **Topic Title**                                                           | **Topic Objective**                                |
| ------------------------------------------------------------------------- | -------------------------------------------------- |
| Researching Attack Vectors and Performing Attacks on Cloud Technologies   | Explain how to attack cloud technologies           |
| Explaining Common Attacks and Vulnerabilities Against Specialized Systems | Explain common attacks against specialized systems |
## 7.1 – Researching Attack Vectors and Performing Attacks on Cloud Technologies
### 7.1.1 – Overview
NIST authored SP 800-145 “The Definition of Cloud Computing” and compares cloud services
- benefits of cloud
	- distributed storage
	- scalability
	- resource pooling
	- access from any location
	- measured service
	- automated management
- essential characteristics of cloud computing
	- on-demand self-service
	- broad network access
	- resource pooling
	- rapid elasticity
	- measured service
- cloud deployment models include the following
	- public cloud
	- private cloud
	- community cloud
	- hybrid cloud

**Three Basic Models of Cloud Computing**
Infrastructure as a Service (IaaS)
- cloud solution in which you rent infrastructure
Platform as a Service (PaaS)
- provides everything except applications
Software as a Service
- complete package solution
- service normally through some sort of web portal

**Some Cloud Tech Attacks**
- credential harvesting
- privilege escalation
- account takeover
- metadata service attacks
- attacks against misconfigured cloud assets
- resource exhaustion and DoS attacks
- cloud malware injection attacks
- side-channel attacks
- direct-to-origin attacks
### 7.1.3 – Credential Harvesting
*Credential Harvesting* is the act of gathering and stealing valid usernames, passwords, tokens, PINs, and any other credentials through infrastructure breaches
- phishing and spear phishing
Many cloud services now use SSO or let you sign on using another, linked, credential (Google, Facebook, Apple)
- attackers can clone these sites and redirect users to fake ones in order to steal info

**SET Steps**
1. launch SET by entering `setoolkit`
2. Select `1) Social-Engineering Attacks`
3. Select `2) Website Attack Vectors`
4. Select `3) Credential Harvester Attack Method`
5. Select `1) Web Templates`
6. Enter the IP address of the host that you would like to harvest
7. Select Your choice of site template
After completing all these steps, you can redirect users to the fake twitter by sending a spear phishing email or taking advantage of XSS
### 7.1.5 – Privilege Escalation
*Privilege Escalation* is the act of exploiting a bug or design flaw in a software or firmware application to gain access to resources that normally would have been protected from an application or a user
*Vertical Privilege Escalation* occurs when a lower-privileged user accesses functions reserved for higher-privileged users
*Horizontal Privilege Escalation* occurs when a normal user accesses functions or content reserved for other normal users
### 7.1.6 – Account Takeover
**Login Location**
- The location of the user can clue you into a takeover
**Failed Login Attempts**
- It is now fairly easy to detect and block failed login attempts from a user or an attacker
**Lateral Phishing Emails**
- These are phishing emails that originate from an account that has already been compromised by the attacker
**Malicious OAuth, SAML, or OpenID Connect Connection**
- Attackers can create fake applications that require read, write, and send permissions for email SaaS offerings such as Office 365 and Gmail
**Abnormal File Sharing and Downloading**
- May suspect an account takeover attack if you notice that a particular user is suddenly sharing or downloading a large number of files
### 7.1.7 – Metadata Service Attacks
Traditionally, software developers used hard-coded credentials to access different services, such as databses and shared files on an FTP server
- to reduce exposure, cloud providers have implemented metadata services
- metadata can provide with AWS credentials to interface with the API
	- software developers often include sensitive info in user startup scripts
### 7.1.8 – Attacks Against Misconfigured Cloud Assets
**Identity and Access Management (IAM) Implementations**
- used to administer user and application authentication and authorization
	- SSO, MFA, user provisioning, lifecycle management
**Federation Misconfiguration**
- method of associating a user’s identity across different identity management systems
	- every time you access a website, web app, or mobile app that allows you to log in or register with your Facebook, Google, or Twitter account, that is FedAuth
**Object Storage**
- Insecure permission configurations for cloud object storage services, such as Amazon’s AWS S3 buckets, are often the cause of data breaches
**Containerization Technologies**
- attacks against container-based deployments have led to massive data breaches
### 7.1.9 – Resource Exhaustion and DoS Attacks
Cloud services have distributed and resilient architecture
- helps to minimize impact of a DoS attack
*Direct-to-Origin (D2O)* attacks are a strategy can affect cloud environments
- reveal origin network or IP addresses behind a content delivery network
### 7.1.10 – Cloud Malware Injection Attacks
*Cloud Malware Injection Attacks* happen when the attacker creates a malicious application and injects it into a SaaS, PaaS, or IaaS environment
- can be leveraged to launch more attacks
	- covert channels
	- backdoors
	- eavesdropping
	- data manipulation
	- data theft
### 7.1.11 – Side-Channel Attacks
*Side-Channel Attacks* are often based on information gained from the implementation of the underlying computer system instead of a specific weakness in the implemented technology or algorithm
### 7.1.13 – Tools and Software Development Kits (SDKs)
*Software Development Kits (SDKs)* can provide insight about cloud-hosted apps
- underlying infrastructure
*Cloud Development Kits (CDKs)* help software devs and cloud consumers deploy applications in the cloud and use the resources that the cloud provider offers
## 7.2 – Explaining Common Attacks and Vulnerabilities Against Specialized Systems
### 7.2.2 – Attacking Mobile Devices
**Reverse Engineering**
- the process of analyzing the compiled mobile app to extract information about its source code could be used to understand the underlying architecture of a mobile application and potentially manipulate the mobile device
**Sandbox Analysis**
- iOS and Android apps are isolated from each other via sandbox environments
	- mandatory in mobile devices for access control
**Spamming**
- unsolicited messages are a problem with email and with sms
**Prevalent Vulnerabilities Affecting Mobile Devices**
- Insecure Storage
	- save as little sensitive data as possible in permanent storage
- Passcode Vulnerabilities and Biometric Integration
	- mobile users “unlock" a mobile device by providing a PIN or password or biometric authentication
- Certificate Planning
	- associates mobile app with a particular digital cert of a server
		- avoid accepting any cert signed by a trusted cert authority
- Using Known  Vulnerable Components
	- attackers will leverage known vulnerabilities, so patching as soon as security updates are available is imperative
- Execution of Activities Using Root and Over-Reach of Permissions
	- devs must practice least privilege
		- disallow mobile applications permissions that are not required
- Business Logic Vulnerabilities
	- attackers can use legit transactions and flows of an application in a way that results in a negative behavior or outcome
**Tools Commonly Used to Perform Security Research**
- Burp Suite
	- test mobile apps and determine how the comm with web services and APIs
- Drozer
	- provides access to numerous exploits that can be used to attack android platforms
- needle
	- open source framework used to test the security of iOS applications
- Mobile Security Framework (MobSF)
	- MobSF is an automated mobile application and malware analysis framework
- Postman
	- used to test and develop APIs
- Ettercap
	- used to perform on-path attacks
- Frida
	- dynamic instrumentation toolkit for security researchers and reverse engineers
- Objection
	- runtime mobile platform and app exploration toolkit uses Frida behind the scenes
	- used to bypass cert pinning, dump keychains, perform memory analysis, and launch other mobile attacks
- Android SDK Tools
	- obtains detailed info about the Android environment
- ApkX
	- enables you to decompile Android application package
- APK Studio
	- can use to reverse engineer Android applications
### 7.2.5 – Attacking IoT Devices
- IoT is broad
### 7.2.6 – Analyzing IoT Protocols
**Some Protocols for IoT Implementations**
- wifi
- bluetooth and bluetooth low energy
- zigbee
- z-wave
- lorawan
- insteon
- modbus
- siemens S7comm
### 7.2.8 – IoT Security Special Considerations
**Fragile Environment**
- Many IoT devices have limited compute resources
**Availability Concerns**
- DoS attacks against IoT systems are a major concern
**Data Corruption**
- IoT protocols are often susceptible to input validation vulnerabilities
**Data Exfiltration**
- IoT devices could be manipulated by an attacker and used for sensitive data exfiltration
### 7.2.9 – Common IoT Vulnerabilities
**Insecure Defaults**
- default credentials plague many IoT devices
**Plaintext Communication and Data Leakage**
- some IoT devices do not provide support for encryption
**Hard-Coded Configurations**
- IoT vendors will often sell their products with hard-coded insecure configs or credentials
**Outdated Firmware/Hardware and the Use of Insecure or Outdated Components**
- many orgs continue to run outdated software and hardware in their IoT devices
	- some of these devices are never updated
### 7.2.11 – Data Storage System Vulnerabilities
![[Pasted image 20250729185430.png]]
**Misconfigurations**
- Default/Blank Username/Password
	- hardcoded or default credentials are often left in place by administrators and in some cases by software developers, exposing devices or the cloud environment to different attacks
- Network Exposure
	- Many IoT, ICS, and SCADA systems should never be exposed to the internet
- Lack of User Input Sanitization
	- input validation vulnerabilities in protocols such as Modbus, S7 Communication, DNP3, and Zigbee could lead to DoS and code execution
- Underlying Software Vulnerabilities and Injection Vulnerabilities
	- attackers can inject malicious SQL statements after “escaping input” with a single quote
		- IoT systems may also be susceptible to similar vulnerabilities
- Error Messages and Debug Handling
	- Many IoT systems include details in error messages and debugging output that can allow an attacker to obtain sensitive information from the system and underlying network
### 7.2.12 – Management Interface Vulnerabilities
*Intelligent Platform Management Interface( IPMI)* is a collection of compute interface specifications designed to offer management and monitoring capabilities independently of the host system’s CPU, firmware, and operating system
- sysadmins use IPMI to enable out-of-band management of computer systems and monitor their operation
An IPMI subsystem includes a main controller, called a Baseboard Management Controller (BMC), and other management controllers, called satellite controllers
### 7.2.14 – Exploiting Virtual Machines
VM is supposed to be completely isolated
*Hypervisor* is the entity that controls and manages the VMs
- Type 1 – run directly on physical system
- Type 2 – hosted, runs on top of other VMs
Have been susceptible to many vulnerabilities
- *VM Escape Vulnerabilities*
	- these vulnerabilities allow an attacker to “escape” the VM
- *Hypervisor Vulnerabilities Such as Hyperjacking*
	- vulnerability that could allow attacker to control hypervisor
	- installation of malicious/fake hypervisor
	- operates in stealth mode
- *VM Repository Vulnerabilities*
	- attackers can leverage these vulnerabilities to compromise many systems and apps
### 7.2.15 – Vulnerabilities Related to Containerized Workloads
Applications running in containers often have their vulnerabilities overlooked
- docker, rocket, containerd
**Security Layers to Apply Containerized Workloads**
- the container image
- software inside the container
- host OS
- interaction between containers and host OS
- security in runtime environment and orchestration platforms such as Kubernetes
**Tools to Scan Docker Images for Vulnerabilities**
- Anchor’s Grype
	- open-source container vulnerability scanner
- Clair
- Dagda
	- set of open-source static analysis tools to help detect vulnerabilities, Trojans, backdoors, and malware in docker images and containers
- kube-bench
	- tool that performs a security assessment of Kubernetes clusters based on the CIS Kubernetes Benchmark
- kube-hunter
	- open-source security tool designed to check the security posture of Kubernetes clusters
- Falco
	- threat detection engine for Kubernetes
