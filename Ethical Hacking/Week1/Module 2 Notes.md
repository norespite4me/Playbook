Tags: [[Ethical Hacking]] [[Notes]]

# Module 2 - Planning and Scoping a Penetration Testing Assessment
### 2.0.1 Why Should I Take This Module?
### 2 .0.2 What Will I Learn in This Module?
**Module Title:** Planning and Scoping a Penetration Testing Assessment
**Module Objective:** Create penetration testing preliminary documents

| Topic Title                                                                           | Topic Objective                                                                                                                |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Comparing and Contrasting Governance, Risk, and Compliance Concepts                   | Explain how governance, risk compliance, and environmental factors in planning penetration testing                             |
| Explaining the Importance of Scoping and Organizational or Customer Requirements      | Create a penetration test scope and plan document that addresses organizational requiremenets for penetration testing services |
| Demonstrating an Ethical Hacking Mindset by Maintaining Professionalism and Integrity | Create your personal code of conduct to provde professionalism and integrity in your ethical hacking practice                  |
## 2.1 Comparing and Contrasting Governance, Risk, and Compliance Concepts
### 2.1.2 Regulatory Compliance Considerations
Must be familiar with several regulatory compliance considerations in order to be successful in ethical hacking and penetration testing – not only to complete compliance-based assessments but also to understand what regulations may affect your and your client
##### PCI DSS
The [**Payment Card Data Security Standard**](https://www.pcisecuritystandards.org) regulation aims to secure the processing of credit card payments and other types of digital payments
##### HIPAA
The original intent of the [**Health Insurance Portability and Accountability Act of 1996**](https://www.cdc.gov/phlp/php/resources/health-insurance-portability-and-accountability-act-of-1996-hipaa.html?CDC_AAref_Val=https://www.cdc.gov/phlp/publications/topic/hipaa.html) regulation was to simplify and standardize healthcare administrative processes. Administrative simplification called for the transition from paper records and transactions to electronic records and transactions. The US Department of Health and Human Services was instructed to develop and publish standards to protect an individual’s electronic health information while permitting appropriate access and use of that information by healthcare providers and other entities.
##### FedRAMP
The US Federal government uses the **[Federal Risk and Authorization Management Program](https://www.fedramp.gov)** standard to authorize the use of cloud service offerings
##### GDPR
Most of these regulations and specifications require the regulated company to hire third-part penetration testing firms to make sure they are compliant and to ensure that their security posture is acceptable.
[**General Data Protection Regulation (GDPR)**](https://gdpr-info.eu)
- includes strict rules about processing data and how it affects privacy
#### Regulations in the Financial Sector
Banks, credit unions, and lending institutions have a responsibility to protect the privacy of consumers
- protect them from harm, like fraud and identity theft

Some examples of regulations in the financial sector
- Title V, Section 501(b) of the Gramm-Leach-Bliley Act (GLBA) and the corresponding guidelines
- The Federal Financial Institutions Examination Council (FFIEC)
- The Federal Deposit Insurance Corporation (FDIC) Safeguards Act and Financial Institutions Letters (FILs)
- The New York Department of Financial Services Cybersecurity Regulation (NY DFS Cybersecurity Regulation; 23 NYCRR Part 500)

GLBA defines a **financial institution** as “any institution the business of which is significantly engaged in financial activities as described in Section 4(k) of the *Bank Holding Company Act*”
- applies to all financial services organizations, regardless of size
	- check-cashing businesses
	- payday lenders
	- nonbank lenders
	- technology vendors providing loans to clients
	- educational institutions providing financial aid
	- debt collectors
	- real estate settlement service providers
	- personal property or real estate appraisers
	- retailers that issue branded credit cards
	- professional tax preparers
	- courier services
The FTC is responsible for enforcing GLBA as it pertains to financial firms that are not covered by federal banking agencies, the Security and Exchange Commission (SEC)m the Commodity Futures Trading Commission (CFTC), and state insurance authorities, which include tax preparers, debt collectors, loan brokers, real estate appraisers ,and nonbank mortgage lenders
#### Regulations in the Healthcare Sector
Feb 20, 2003 – Security Standards for the Protection of Electronic Protected Health Information; aka HIPAA Security Rule was published
- technical and nontechnical safeguards to protect electronic health information
**Expanded Scope and Requirements of Security Rule**
- The 2009 Health Information Technology for Economic and Clinical Health Act (known as the HITECH Act)
- The 2009 Breach Notification Rule
- The 2013 Modifications to the HIPAA Privacy, Security, Enforcement, and Breach Notification Rules under the HITECH Act and the Genetic Information Nondiscrimination Act; Other Modifications to the HIPAA Rules (known as the Omnibus Rule)

| Covered Entity           | Description                                                                                                                                                                                                                                                                 |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Healthcare Provider      | person or an organization that provides patient or medical services, such as doctors, clinics, hospitals, and outpatient services; counseling; nursing home and hospice services; pharmacy services; medical diagnostic and imaging services; and durable medical equipment |
| Health Plan              | an entity that provides payment for medical services, such as health insurance companies, HMOs, government health plans, or government programs that pay for healthcare, such as Medicare, Medicaid, military, and veteran's’ programs                                      |
| Healthcare Clearinghouse | an entity that processes nonstandard health information it receives from another entity into a standard format                                                                                                                                                              |
| Business Associates      | a person or entity that creates, receives, maintains, transmits, accesses, or has the potential to access PHI to perform certain functions or activities on behalf of a covered entity                                                                                      |
#### Payment Card Industry Data Security Standard (PCI DSS)
This was created by Visa, Mastercard, Discover, and AmEx to help protect cardholders.
- must be adopted by any organization that transmits, processes, or stores payment card data or that directly or indirectly affects the security of cardholder data

| Cardholder Terms                  | Definition                                                                                                                                                                                                                                                                |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Acquirer                          | aka ‘acquiring bank’ or ‘acquiring financial institution,’ an entity that initiates and maintains relationships with merchants for the acceptance of payment cards                                                                                                        |
| ASV (Approved Scanning Vendor)    | organization approved by the PCI SSC to conduct external vulnerability scanning services                                                                                                                                                                                  |
| Merchant                          | entity that accepts payment cards bearing the logos of any of the members of PCI SSC as payment for good and/or services                                                                                                                                                  |
| PAN (Primary Account Number)      | payment card number that is up to 19 digits long                                                                                                                                                                                                                          |
| Payment Brand                     | Visa, MasterCard, AmEx, Discover                                                                                                                                                                                                                                          |
| PCI Forensic Investigator (PFI)   | person trained and certified to investigate and contain information about cybersecurity incidents and breaches involving cardholder data                                                                                                                                  |
| Qualified Security Assessor (QSA) | individual trained and certified to carry out PCI DSS compliance assessments                                                                                                                                                                                              |
| Service Provider                  | business entity that is not a payment brand and that is directly involved in the processing, storage, or transmission of cardholder data, such as managed service providers that provide managed firewalls, intrusion detection and other services, and hosting providers |

| Cardholder Data              | Sensitive Authentication Data                          |
| ---------------------------- | ------------------------------------------------------ |
| Primary Account Number (PAN) | Full magnetic stripe data or equivalent data on a chip |
| Cardholder Name              | CAV2/CVC2/CVV2/CID                                     |
| Expiration Date              | PINs/PIB Blocks                                        |
| Service Code                 |                                                        |

Typical Elements on a Credit Card
- Embedded microchip
- PAN
- Expiration date
- Cardholder name
#### Key Technical Elements in Regulations You Should Consider
**Data Isolation**
- Orgs that need to comply with PCI DSS should have a data isolation strategy, aka network isolation or network segmentation
- goal is to implement a completely isolated network that includes all systems involved in payment processing
**Password Management**
- Orgs must not use vendor-supplied defaults for system passwords and security parameters
- Mandate specific implementation standards
	- password length
	- password complexity
	- session timeout
	- multifactor authentication (MFA)
**Key Management**
- key is a value that specifies which part of the algorithm to apply and in which order, as well as what variables to input
- Recommendations for Key Management
		1. General (Revision 4) provides general guidance and best practices for the management of cryptographic keying material
		2. Best Practices for Key Management Organization provides guidance on policy and security planning requirements for US government agencies
		3. Application Specific Key Management Guidance provides guidance when using the cryptographic features of current systems
### 2.1.3 – Local Restrictions
Should be aware of any local restrictions when hired to do pentesting

Examples of constraints in pentesting environment
- Certain areas and technologies that cannot be tested due to operational limitations
- Technologies that might be specific for the organization being tested
- Limitation of known exploits
- Limitation of skill sets
- Systems that are categorized as out of scope because of the criticality or known performance problems
## 2.2 – Explaining the Importance of Scoping and Organizational or Customer Requirements
### 2.2.2 Rules of Engagement
- specifies the conditions under which the security penetration testing engagement will be conducted

| Rule of Engagement Element                                             | Example                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Testing timeline                                                       | Three weeks, as specified in a Gantt chart                                                                                                                                                                                                                                                                                                                                                 |
| Location of the testing                                                | Company’s headquarters in Raleigh, North Carolina                                                                                                                                                                                                                                                                                                                                          |
| Time of window of the testing (times of day)                           | 9am to 5pm EST                                                                                                                                                                                                                                                                                                                                                                             |
| Preferred method of communication                                      | Final report and weekly status update meetings                                                                                                                                                                                                                                                                                                                                             |
| The security controls that could potentially detect or prevent testing | Intrusion prevention systems (IPSs), firewalls, data loss prevention (DLP) systems                                                                                                                                                                                                                                                                                                         |
| IP addresses or networks from which testing will originate             | 10.10.1.0/24, 192.168.66.66, 10.20.15.123                                                                                                                                                                                                                                                                                                                                                  |
| Types of allowed or disallowed tests                                   | Testing only web aplications (app1.secretcorp.org and app2.secretcorp.org)<br>No social engineering attacks are allowed. No SQL injection attacks are allowed in the production environment. SQL injection is only allowed in the development and staging environments at:<br>app1-dev.secretcorp.org<br>app1-stage.secretcorp.org<br>app2-dev.secretcorp.org<br>app2-stage.secretcorp.org |
- Gantt charts and Work Breakdown Structures (WBS) can be used as tools to demonstrate and document the timeline
### 2.2.4 Target List and In-Scope Assets
Scoping is one of the most important elements of the pre-engagement tasks
- carefully document systems, applications, and networks that will be tested
Scope and documentation must include information about what types of networks will be tested

| API Standards | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SOAP          | Simple Object Access Protocol (SOAP) project files: SOAP Is an API standard that relies on XML and related schemas. XML-based specifications are governed by XML Schema Definitions (XSD) documents. Having a good reference of what a specific API supports can be very beneficial for a penetration tester and will accelerate the testing.                                                                                                                                                      |
| Swagger       | Swagger (OpenAPI) documentation is a modern framework of API documentation and fevelopment that is now the basis of the OpenAPI Specifications (OAS). These documents are used in representational state transfer (REST) APIs. REST Is a software architectural style designed to guide development of the architecture for web services (including APIs). REST, or “RESTful,” APIs are the most common types of APIs used today. Swagger documents can be extremely beneficial when testing APIs. |
| WSDL          | Web Service Description Language (WSDL) is an XML-based language that is used to document the functionality of a web service                                                                                                                                                                                                                                                                                                                                                                       |
| GraphQL       | GraphQL is a query language for APIs. It is also a server-side runtime for executing queries using a type system you define for your data                                                                                                                                                                                                                                                                                                                                                          |
| WADL          | Web Application Description Language (WADL) is an XML-based language for describing web applications                                                                                                                                                                                                                                                                                                                                                                                               |
Very important to document the location where testing will be done, as well as the Domain Name System (DNS) fully qualified domain names (FQDNs) of the applications and asset that are allowed (including any subdomains)

Scope creep does not always start as bad, but a client that is satisfied with the work you’re doing may ask you to do additional testing
### 2.2.7 Strategy: Unknown vs Known Environment Testing
When talking about penetration testing strategies, you are likely to hear the terms *unknown-environment testing* and *known=environment testing*

| Testing Type                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Unknown-Environment Testing | in this type of testing, the tester is typically provided only a very limited amount of information. For instance, the tester may be provided only the domain names and IP addresses that are in scope for a particular target. The idea of this type of limitation is to have the tester start out with the perspective that an external attacker might have. Typically, an attacker would first determine more information to use in the attacks. The tester would not have prior knowledge of the target’s organization and infrastructure. Another aspect of unknown-environment testing is that sometimes the network support personnel of the target may be given information about exactly when the test is taking place. This allows for a defense exercise to take place, and it also eliminates the issue of a target preparing for the test and not giving a real-world view of the security posture |
| Known-Environment Testing   | In this type of testing (formerly known as white-box pentesting), the tester starts out with a significant amount of information about the organization and its infrastructure. The tester is normally provided things like network diagrams, IP addresses, configurations, and a set of user credentials. If the scope includes an application assessment, the tester might also be provided the source code of the target application. The idea of this type of testing is to identify as many security holes as possible.                                                                                                                                                                                                                                                                                                                                                                                    |
