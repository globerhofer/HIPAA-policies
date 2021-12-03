# 1. Introduction

PennMedicine Way To Health, Inc ("WayToHealth") is committed to ensuring the confidentiality, privacy, integrity, and availability of all electronic protected health information (ePHI) it receives, maintains, processes and/or transmits on behalf of its Customers. As a patient engagement and health research technology organization, WayToHealth strives to maintain compliance, proactively address information security, mitigate risk for its Customers, and assure known breaches are completely and effectively communicated in a timely manner. The following documents address core policies used by WayToHealth to maintain compliance and assure the proper protections of infrastructure used to store, process, and transmit ePHI for WayToHealth Customers.

WayToHealth provides secure and compliant software to administer behavioral change and patient engagement programs. Customers utilize the hosted software and infrastructure from WayToHealth to research and deploy evidence-based approches to engage patients in their health. WayToHealth makes every effort to reduce the risk of unauthorized disclosure, access, and/or breach of Customer data through network (firewalls, dedicated IP spaces, etc), server settings (encryption at rest and in transit etc), and application security requirements (password strength rules, account roles/privileges, etc).

WayToHealth signs business associate agreements (BAAs) with its Customers. These BAAs outline WayToHealth obligations and Customer obligations, as well as liability in the case of a breach. In providing infrastructure and managing security configurations that are a part of the technology requirements that exist in HIPAA and HITRUST, as well as future compliance frameworks, WayToHealth manages various aspects of compliance for Customers. The aspects of compliance that WayToHealth manages for Customers are inherited by Customers, and WayToHealth assumes the risk associated with those aspects of compliance as defined in the BAA. In doing so, WayToHealth achieves and maintains compliance, while mitigating Customer risk.

WayToHealth does not act as a covered entity but rather as a provider of services to covered entities and other organizations. Certain aspects of our compliance are inherited from our hosting provider, Azure or [Digital Academic Research Transformation Services (DART)](https://www.med.upenn.edu/dart/), part of Penn Medicine Corporate IS as appropriate. More details about Azure's HITRUST and HIPAA compliance posture is available for review [here](https://www.microsoft.com/en-us/trustcenter/Compliance/HITRUST). Penn Medicine's policies and procedures are also incorporated into this document as relevant given that WayToHealth operates within the Penn Medicine umbrella. 

Certain aspects of compliance cannot be inherited. Because of this, WayToHealth, in order to achieve full compliance or HITRUST Certification, has implemented certain organizational policies. 

Mappings of HIPAA Rules to WayToHealth controls are covered in [§2](#2-hipaa-inheritance).

## 1.1 WayToHealth Organizational Concepts

The physical infrastructure environment is hosted at [Microsoft Azure](https://azure.microsoft.com/) or on DART. In either case, the network components and supporting network infrastructure are contained within the relevant infrastructure and is managed by the provider. WayToHealth does not have physical access into the network components. The WayToHealth environment consists of Fortinet firewalls and CentOS-based Virtual servers running Apache and/or nginx web servers; PHP and Node.js application servers; MariaDB and PostgreSQL database servers; Logstash logging servers; Ansible configuration management servers; OSSEC IDS services and / or Fortigate IPS services; Docker containers; and developer tool servers.

Within the WayToHealth Platform, all data transmission is encrypted and all hard drives are encrypted so data at rest is also encrypted; this applies to all servers - those hosting Docker containers, databases, APIs, log servers, etc. WayToHealth assumes all data *may* contain ePHI, even though our Risk Assessment does not indicate this is the case, and provides appropriate protections based on that assumption.

WayToHealth additionally restricts, secures, and assures the privacy of all ePHI data at the Application Level.

WayToHealth has implemented strict logical access controls so that only authorized personnel are given access to the internal management servers. The environment is configured so that data is transmitted from the load balancers to the application servers over an encrypted session.

Once the data is received from the application server, a series of Application Programming Interface (API) calls or SQL queries is made to the database servers where the ePHI resides.

The VPN server and Apache web server are externally facing and accessible via the Internet. The application and database servers, where the ePHI resides, are located on the internal WayToHealth network and can only be accessed through a bastion host over a VPN connection. Access to the internal database is restricted to a limited number of personnel and strictly controlled to only those personnel with a business-justified reason.

Application, database and operating systems are tested end-to-end for usability, security, and impact prior to deployment to production.

## 1.2 Requesting Audit and Compliance Reports

WayToHealth, at its sole discretion, can share audit reports, including its planned HITRUST reports and Corrective Action Plans (CAPs), with customers on a case by case basis. All audit reports are shared under explicit NDA in Penn Medicine's format between Penn Medicine and party to receive materials. Audit reports can be requested by WayToHealth workforce members for Customers or directly by WayToHealth Customers.

The following process is used to request audit reports:

1. Email is sent to your implementation lead. In the email, please specify the type of report being requested and any required timelines for the report.
2. WayToHealth staff will log an issue with the details of the request into the WayToHealth Ticketing and Quality Management System (TQMS). The WayToHealth TQMS is used to track requests' status and outcomes.
3. WayToHealth will confirm if a current NDA is in place with the party requesting the audit report. If there is no NDA in place, WayToHealth will send one for execution.
4. Once it has been confirmed that an NDA is executed, WayToHealth staff will move the issue to "Under Review".
5. The WayToHealth / PennMedicine Security Officer or Privacy Officer must Approve or Reject the Issue. If the Issue is rejected, WayToHealth will notify the requesting party that we cannot share the requested report.
6. If the issue has been Approved, WayToHealth will send the customer the requested audit report and close the TQMS issue for the request.

## 1.3 Version Control

These policies are managed in a private Gitlab repository managed within the University of Pennsylvania network for source control. The most recent version of the policies is available at <https://policy.waytohealth.org>.

These policies were last updated on December 2nd, 2021.
