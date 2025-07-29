Tags: [[Ethical Hacking]] [[Notes]]

# Module 4 -- Social Engineering Attacks

| Topic Title                                  | Topic Objective                                                  |
| -------------------------------------------- | ---------------------------------------------------------------- |
| Pretexting for an Approach and Impersonation | explain how pretexting is used in social engineering attacks     |
| Social Engineering Attacks                   | explain different types of social engineering attacks            |
| Physical Attacks                             | explain different types of physical attacks                      |
| Social Engineering Tools                     | explain how social engineering attack tools facilitate attacks   |
| Methods of Influence                         | explain how social engineering attacks enlist user participation |
## 4.2 – Social Engineering Attacks
### 4.2.2 – Email Phishing
An attacker presents a user with a link or an attachment that looks valid, but when the user clicks it they are prompted to disclose confidential information such as his or her username and password
**Spear Phishing**
- phishing attempt that is constructed very specifically
	- directly targeted at a specific individual or group of individuals
	- usually management or users who may have elevated privileges
**Whaling**
- targeted at high-profile business execs and key individuals in a company
- along with phishing, this can include fake emails and web pages that serve malware or collect sensitive information
### 4.2.3 – Vishing
**Vishing** is a social engineering attack carried out in a phone conversation
- goal is to steal credit card numbers, SSNs, and other info that can be used in ID theft schemes
### 4.2.4 – SMS Phishing
**SMSishing** is the bitcoin-related SMS scams that have surfaced in recent years
- don’t click on links from unknown messages
### 4.2.5 – USB Drop Key
**USB Drop Key** attacks compromise victim systems
- usually left out somewhere intentionally to take advantage of natural human curiosity
### 4.2.6 – Watering Hole Attacks
**Watering Hole Attack** is a targeted attack that occurs when an attacker profiles websites that the intended victim accesses
- scans websites for vulnerabilities and if it has them they will use code injection to redirect the user when they return to that site
## 4.3 – Physical Attacks
### 4.3.2 – Tailgating
**Tailgating** is essentially the same as piggybacking, but it occurs without the authorized person’s consent
- can be combated with access control vestibules, where the second set of doors cannot be opened until the first set is closed
	- creates a sort of waiting room that can keep a tailgater from escaping
### 4.3.3 – Dumpster Diving
**Dumpster Diving** is when a person scavenges for private information in someone’s trash
- sensitive documents should be stored securely and then destroyed when no longer needed
### 4.3.4 – Shoulder Surfing
**Shoulder Surfing** is when someone obtains information by looking over a victim’s shoulder
### 4.3.5 – Badge Cloning
**Badge Cloning** is when an attacker clones an id badge in order to gain access to a building
## 4.4 – Social Engineering Tools
### 4.4.2 – Social-Engineer Toolkit (SET)
**Step 1**
- launch SET by using the `setoolkit` command
**Step 2**
- Select *1) Social-Engineering Attacks* from the menu to start the social engineering attack
**Step 3**
- Select *1) Spear-Phishing Attack Vectors* from the menu to start the spear-phishing attack
**Step 4**
- create a file format payload automatically by selecting *2) Create a FileFormat Payload*
**Step 5**
- Select *13) Adobe PDF Embedded EXE Social Engineering* as the file format
**Step 6**
- to have SET generate a normal PDF with embedded EXE and use a built-in blank PDF file for the attack, select *2) Use built-in BLANK PDF for attack*
**Step 7**
- To use Windows reverse TCP shell, select *1) Windows Reverse TCP Shell*
**Step 8-9**
- When SET asks you to enter the IP address of the URL for the payload listener, select the IP address of your attacking system
	- default selection
	- default port is 443
- When SET asks if you want to rename the payload, select *2. Rename the file, I want to be cool*
**Step 10**
- Select *1. E-Mail Attack Single Email Address*
**Step 11-14**
- When SET asks if you want to use a predefined email template or create a one-time email template, select *2. One-Time  Use Email Template*
- Follow along as SET guides you through the steps to create the one-time email message and enter the subject of the email
- When SET asks if you want to send the message as an HTML message or in plaintext, select the default, *plaintext*
- Enter the body of the message
**Step 15-19**
- Enter the recipient email address and specify whether you want to use a Gmail account or use your own email server or an open mail relay
- Enter the “from” email address and the “from name” the user will see
- If you selected to use your own email server or open relay, enter the open-relay username and password when asked to do so
- Enter the SMTP email server address and the port number
	- when asked if you want to flag this email as a high-priority message, make a selection
	- email is sent to victim
- When asked if you want to set up a listener for the reverse TCP connection from the compromised system, make a selection
### 4.4.3 – Browser Exploitation Framework (BeEF)
**Launching BeEF**
- tool starts with service on port 3000 by default
	- attacker can log into a web console and manipulate users who are victims of XSS attacks
**Stealing a Browser Cookie**
- using XSS and BeEF
**Sending a Fake Notification**
- once the system is compromised, the attacker can use BeEF to perform numerous attacks
	- can send fake notis to the victim’s browser
**Fake Notification in Browser**
### 4.4.5 – Call Spoofing Tools
It is very easy to change the caller ID information that is displayed on a phone
- SpoofApp
	- Apple iOS and Android app that can be used to easily spoof a phone number
- SpoofCard
	- Apple iOS and Android app that can spoof a number and change your voice, record calls, generate different background noises, and send calls straight to voicemail
- Asterisk
	- legit VoIP management tool that can also be used to impersonate caller ID
## 4.5 – Methods of Influence
| **Social Engineering Motivation Technique** | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authority                                   | a social engineer shows confidence and perhaps authority – whether legal, organizational, or social authority                                                                                                                                                                                                                                                                                                                                                                          |
| Scarcity and Urgency                        | it is possible to use scarcity to create a feeling of urgency in a decision-making context. specific language can be used to heighten urgency and manipulate the victim. Salespeople often use scarcity to manipulate client (for example, telling a customer that an offer is only for today or that there are limited supplies). Social engineers use similar techniques                                                                                                             |
| Social Proof                                | Social proof is a psychological phenomenon in which an individual is not able to determine the appropriate mode of behavior. For example, you might see other acting or doing something in a certain way and might assume that it is appropriate. Social engineers may take advantage of social proof when an individual enters an unfamiliar situation that he or she doesn’t know how to deal with. Social engineers may manipulate multiple people at once by using this technique. |
| Likeness                                    | individuals can be influenced by things or people they like. social engineers strive for others to like they way they behave, look, and talk. most individuals like what is aesthetically pleasing. people also like to be appreciated and to talk about themselves. social engineers take advantage of these human vulnerabilities to manipulate their victims                                                                                                                        |
| Fear                                        | it is possible to manipulate a person with fear to prompt him or her to act promptly. fear is an unpleasant emotion based on the belief that something bad or dangerous may take place. using fear, social engineers force their victims to act quickly to avoid or rectify a dangerous or painful situation.                                                                                                                                                                          |
