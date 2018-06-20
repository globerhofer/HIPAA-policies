# 7. System Access Policy

Access to WayToHealth systems and application is limited for all users, including but not limited to workforce members, volunteers, business associates, contracted providers, and consultants. Access by any other entity is allowable only on a minimum necessary basis. All users are responsible for reporting an incident of unauthorized user or access of the organization's information systems. These safeguards have been established to address the HIPAA Security regulations including the following:

## 7.1 Applicable Standards

### 7.1.1 Applicable Standards from the HITRUST Common Security Framework

* 01.d - User Password Management
* 01.f - Password Use
* 01.r - Password Management System
* 01.a - Access Control Policy
* 01.b - User Registration
* 01.h - Clear Desk and Clear Screen Policy
* 01.j - User Authentication for External Connections
* 01.q - User Identification and Authentication
* 01.v - Information Access Restriction
* 02.i - Removal of Access Rights
* 06.e - Prevention of Misuse of Information Assets

### 7.1.2 Applicable Standards from the HIPAA Security Rule

* 164.308a4iiC Access Establishment and Modification
* 164.308a3iiB Workforce Clearance Procedures
* 164.308a4iiB Access Authorization
* 164.312d Person or Entity Authentication
* 164.312a2i Unique User Identification
* 164.308a5iiD Password Management
* 164.312a2iii Automatic Logoff
* 164.310b Workstation Use
* 164.310c Workstation Security
* 164.308a3iiC Termination Procedures

## 7.2 Access Establishment and Modification

### 7.2.1 WayToHealth Personnel

1. Requests for access to WayToHealth systems and applications is made formally using the following process:
  1. A WayToHealth workforce member initiates the access request by creating a Ticket in the WayToHealth TQMS.
     * User identities must be verified prior to granting access to new accounts.
     * Identity verification must be done in person where possible; for remote employees, identities must be verified over the phone.
     * For new accounts, the method used to verify the user's identity must be recorded on the Ticket.
  2. The Security Officer or designated personnel will grant access to systems as dictated by the employee's job title. If additional access is required outside of the minimum necessary to perform job functions, the requester must include a description of why the additional access is required as part of the access request.
  3. Once the review is completed, the Security Officer or designated personnel or Privacy Officer approves or rejects the Ticket. If the Ticket is rejected, it goes back for further review and documentation.
  4. If the review is approved, the Security Officer or designated personnel or Privacy Officer then marks the Ticket as Approved, adding any pertinent notes required. The Security Officer, Privacy Officer, or designated team member then grants requested access and marks the Ticket as Done.
     * For newly created accounts on core WayToHealth applications, an email will be sent to the user with a link to set an initial secure password that meets all requirements from [§7.12](#7-12-password-management).
     * On some ancillary systems, an initial temporary password will be generated, which must also meet all requirements from [§7.12](#7-12-password-management) and must also be changed on the first login. All such password exchanges must occur over an authenticated channel.
2. Access is not granted until review and approval by the WayToHealth Security Officer or Privacy Officer.
3. The request for access is retained for future reference.
4. All access to WayToHealth systems and services is reviewed and updated on a bi-annual basis to ensure proper authorizations are in place commensurate with job functions. The process for conducting reviews is outlined below:
   1. The Security Officer or designated personnel initiates the review of user access by creating an Ticket in the WayToHealth TQMS.
   2. The Security Officer or designated personnel is assigned to review levels of access for each WayToHealth workforce member.
   3. If user access is found during review that is not in line with the least privilege principle, the process below is used to modify user access and notify the user of access changes. Once those steps are completed, the Ticket is then reviewed again.
   4. Once the review is completed, the Security Officer or designated personnel approves or rejects the Ticket. If the Ticket is rejected, it goes back for further review and documentation.
   5. If the review is approved, the Security Officer or designated personnel then marks the Ticket as Done, adding any pertinent notes required.
   6. Review of user access is monitored on a quarterly basis using the TQMS reporting to assess compliance with above policy.
5. Any WayToHealth workforce member can request change of access using the process outlined in [§7.2 paragraph 1](#7-2-access-establishment-and-modification).
6. Access to production systems is controlled using centralized user management and authentication.
7. Account management and access:
   * Temporary accounts are not used unless absolutely necessary for business purposes.
   * Accounts are reviewed every 90 days to ensure temporary accounts are not left unnecessarily active.
   * Accounts that are inactive for over 90 days are removed.
   * User accounts on systems containing highly sensitive or confidential data that have not been accessed for ninety (90) days will be disabled.
   * Privileged users (e.g., system administrators) must have their access rights reviewed at least two (2) times per year by the Information Owner to ensure access to UPHS/SOM information is appropriate.
   * Users with access to privileged accounts must use their non-privileged user account to log into the system. These users must take care to only log into their privileged accounts when necessary, and only for the duration required to complete the task requiring privileged access.
8. In the case of non-personal information, such as generic educational content, identification and authentication may not be required. This is the responsibility of WayToHealth Customers to define, and not WayToHealth.
9. Privileged users must first access systems using standard, unique user accounts before switching to privileged users and performing privileged tasks.
   * For production systems, this is enforced by creating non-privileged user accounts that must invoke `sudo` to perform privileged tasks.
   * Rights for privileged accounts are granted by the Security Officer or designated personnel or Privacy Officer using the process outlined in [§7.2 paragraph 1](#7-2-access-establishment-and-modification).
10. All application to application communication using service accounts is restricted and not permitted unless absolutely needed. 
11. Generic accounts are not allowed on WayToHealth systems.
12. Server access is granted through encrypted, VPN tunnels that utilize two-factor authentication.
    * Two-factor authentication is accomplished using Duo Security.
    * VPN connections use 256-bit AES 256 encryption, or equivalent.
    * VPN sessions are automatically disconnected after 30 minutes of inactivity.
13. In cases of increased risk or known attempted unauthorized access, immediate steps are taken by the Security and Privacy Officer to limit access and reduce risk of unauthorized access.
14. Direct system to system, system to application, and application to application authentication and authorization are limited and controlled to restrict access.

### 7.2.2 Customer Personnel

1. Requests for access to WayToHealth study specific applications is made formally using the following process:
  1. A WayToHealth workforce member initiates the access request by creating an Issue in the WayToHealth TQMS for the Project Manager (PM).
     * User identities must be verified prior to granting access to new accounts.
     * Identity verification must be done in person where possible; for remote employees, identities must be verified over the phone.
     * For new accounts, the method used to verify the user's identity must be recorded on the Issue.
     * No access outside of the minimum necessary to perform job functions will be provided.
2. Once access has been granted to the project PM, s/he will invite other members necessary to accomplish their project objectives as needed via the user interface provided. Invites require names, email addresses and roles at the very minimum. The verification of names and email addresses are the PM's responsibility and is not verified by WayToHealth.
3. Customer personnel, once invited, will be required to set their username and password that meets all requirements from [§7.12](#7-12-password-management).
4. Customer personnel are required to follow their organization's HIPAA and other privacy policies. 
5. Customer personnel are required to sign a [Data Security Agreement](https://atlas.waytohealth.upenn.edu/confluence/download/attachments/13664604/Data%20Security%20Agreement%20Way%20to%20Health.pdf) before getting access to the application.
6. Generic and temporary accounts are not allowed on WayToHealth systems.
7. Personnel who have not accessed the system in more than three (3) months will have their accounts terminated.
8. PMs will be required to actively review the personnel with access to their programs on a quarterly basis.
9. Direct system to system, system to application, and application to application authentication and authorization are limited and controlled to restrict access. This will primarily apply in the case where sysem to system integration is required.


## 7.3 Workforce Clearance

1. The level of security assigned to a user to the organization's information systems is based on the minimum necessary amount of data access required to carry out legitimate job responsibilities assigned to a user's job classification and/or to a user needing access to carry out treatment, payment, or healthcare operations.
2. All access requests are treated on a "least-access principle."
3. WayToHealth maintains a minimum necessary approach to access to Customer data. As such, WayToHealth workforce members, are mandated by policy to only have access to ePHI to provide support services.

## 7.4 Access Authorization

1. Role based access categories for each WayToHealth system and application are pre-approved by the Security Officer or designated personnel.
2. WayToHealth utilizes hardware and software firewalls to segment data, prevent unauthorized access, and monitor traffic for denial of service attacks.

## 7.5 Person or Entity Authentication

1. Each workforce member has and uses a unique user ID and password that identifies him/her as the user of the information system.
2. Each user has and uses a unique user ID and password that identifies him/her as the user of the information system.
3. All Customer support desk interactions must be verified before WayToHealth support personnel will satisfy any request having information security implications.
   * WayToHealth's current support desk software, Service Desk, requires users to authenticate before submitting support tickets.
   * Support issues submitted via WayToHealth's dashboard require that users authenticate with their WayToHealth account before submitting support tickets.
   * Support issues submitted by email must be verified by WayToHealth personnel using a phone number that has been registered with the corresponding account.

## 7.6 Unique User Identification

1. Access to the WayToHealth systems and applications is controlled by requiring unique User Login IDs and passwords for each individual user and developer.
2. Passwords requirements mandate strong password controls (see below).
3. Passwords are not displayed at any time and are not transmitted or stored in plain text.
4. Default accounts on all production systems, including root, are disabled.
5. Shared accounts are not allowed within WayToHealth systems or networks.
6. Automated log-on configurations that store user passwords or bypass password entry are not permitted for use with WayToHealth workstations or production systems. The use of an enterprise-grade password manager (such as LastPass) is required for all workforce members.
7. For server access, users are assigned IDs that are consistent with theur current PennKey IDs. The privilege level of the account should not be identifiable within the userID (e.g., a userID named “sysadmin1” is not permissible).
8. Workforce members are not permitted to have multiple userIDs on the same system without a business need, and the approval of the system administrator

## 7.7 Automatic Logoff

1. Users are required to make information systems inaccessible by any other individual when unattended by the users (ex. by using a password protected screen saver or logging off the system).
2. Information systems automatically log users off the systems after 30 minutes of inactivity.
3. The Security Officer or designated personnel generally rejects but can pre-approve exceptions to automatic log off requirements.

## 7.8 Employee Workstation Use

All workstations at WayToHealth are owned and managed by UPHS and/or PMACS (Penn Medicine Academic Computing Services).

1. Workstations may not be used to engage in any activity that is illegal or is in violation of organization's policies.
2. Access may not be used for transmitting, retrieving, or storage of any communications of a discriminatory or harassing nature or materials that are obscene or "X-rated". Harassment of any kind is prohibited. No messages with derogatory or inflammatory remarks about an individual's race, age, disability, religion, national origin, physical attributes, sexual preference, or health condition shall be transmitted or maintained. No abusive, hostile, profane, or offensive language is to be transmitted through organization's system.
3. Information systems/applications also may not be used for any other purpose that is illegal, unethical, or against company policies or contrary to organization's best interests. Messages containing information related to a lawsuit or investigation may not be sent without prior approval.
4. Solicitation of non-company business, or any use of organization's information systems/applications for personal gain is prohibited.
5. Transmitted messages may not contain material that criticizes the organization, its providers, its employees, or others.
6. Users may not misrepresent, obscure, suppress, or replace another user's identity in transmitted or stored messages.
7. * Must be Apple Macintosh machines only. Windows machines will only be used for end user testing
   * Must have their hard drives encrypted with FileVault 2.0 or equivalent 
   * Must have firewalls enabled to prevent unauthorized access unless explicitly granted
   * Must have the following language added to the lock and login screens: *This computer is owned by Penn Medicine (https://pennmedicine.org). By logging in, unlocking, and/or using this computer you acknowledge you are authorized to use this computer and have seen, and follow, these policies (https://policy.waytohealth.org)* 
7. ~~Workstation hard drives will be encrypted using FileVault 2.0 or equivalent.~~
8. ~~All workstations have firewalls enabled to prevent unauthorized access unless explicitly granted.~~
9. ~~All workstations are to~~ 
   * ~~Have a sticker with the legend "University of Pennsylvania Health System (with the Penn logo), the asset ID and an URL (https://pennmedaccess.uphs.upenn.edu) for polciies and support.~~
   * ~~Have, on login, the following text should always be displayed: Computer Name, Logon ID, Domain (UPHS), Active IP address, Active MAC Address, Physical Location (e.g. HUP - Blockley Hall), Floor (e.g. 11th Floor) and Department (e.g. General Internal Medicine).~~

## 7.9 Wireless Access Use

1. WayToHealth production systems are not accessible directly over wireless channels.
2. Wireless access is disabled on all production systems.
3. When accessing production systems via remote wireless connections, the same system access policies and procedures apply to wireless as all other connections, including wired.
4. Wireless networks managed within WayToHealth non-production facilities (offices, etc.) are secured with the following configurations:
   * Access to the network is only allowed for authorized personnel over the AirPennNet network with an active PennKey
   * All data in transit over wireless is encrypted using WPA2 encryption or similar;
   * Passwords are rotated on a regular basis, presently annually. This process is managed by the WayToHealth Security Officer or designated personnel.
   * System access id further restricted to be over VPN only.

## 7.10 Employee Termination Procedures

1. The Human Resources Department of UPHS (or other designated department), users, and their supervisors are notified by the Security Officer or designated personnel to terminate specific personnel. Based upon the date of termination and upon completion and/or termination of personnel, access is termnated based upon the "Termination Checklist" ticket filed in the TQMS. The ticket is assigned to authorized individual(s) and must be completed within 24 hours.
2. The COO and / or the Security Officer or designated personnel will initiate the termination of a user's access rights if there is evidence or reason to believe the following (these incidents are also reported on an incident report and is filed with the Privacy Officer):
   * The user has been using their access rights inappropriately;
   * A user's password has been compromised (a new password may be provided to the user if the user is not identified as the individual compromising the original password);
   * An unauthorized individual is utilizing a user's User Login ID and password (a new password may be provided to the user if the user is not identified as providing the unauthorized individual with the User Login ID and password).
3. The Security Officer or designated personnel will terminate users' access rights immediately upon notification, and will coordinate with the appropriate WayToHealth employees to terminate access to any non-production systems managed by those employees.
4. The Security Officer or designated personnel audits and may terminate access of users that have not logged into organization's information systems/applications for an extended period of time.

## 7.11 Paper Records

WayToHealth does not use paper records for any sensitive information. Use of paper for recording and storing sensitive data is against WayToHealth policies.

## 7.12 Password Management

1. User IDs and passwords are used to control access to WayToHealth systems and may not be disclosed to anyone for any reason.
2. Users may not allow anyone, for any reason, to have access to any information system using another user's unique user ID and password.
3. Password strength is enforced using the [zxcvbn](https://github.com/dropbox/zxcvbn) password strength estimation algorithm. We use this as an alternative to password composition policy. In practice, it can translate to:
   * 8 or more characters;
   * a mix of upper case characters, lower case characters, and numbers or special characters;
4. Other policies enforced include:
   * a 180-day password expiration, or 90-day password expiration for administrative accounts;
   * prevention of password reuse using a history of the last 6 passwords;
   * where supported, modifying at least 4 characters when changing passwords;
   * account lockout after 5 invalid attempts.
5. All system and application passwords must be stored and transmitted securely.
   * Where possible, passwords should be stored in a hashed format using a salted cryptographic hash function (SHA-256 or equivalent).
   * Passwords that must be stored in non-hashed format must be encrypted at rest pursuant to the requirements in [§17.8](#17-8-production-data-security).
   * Transmitted passwords must be encrypted in flight pursuant to the requirements in [§17.9](#17-9-transmission-security).
6. Each information system automatically requires users to change passwords at a pre-determined interval as determined by the organization, based on the criticality and sensitivity of the ePHI contained within the network, system, application, and/or database.
7. Passwords are deactivated immediately upon an employee's termination (refer to the [Employee Termination Procedures in §7.10](#7-10-employee-termination-procedures)).
8. There are no default system or application passwords.
9. Passwords are not auto-generated for users. Users must set their passwords when invited following the complexity rules defined above.
10. Password change methods must use a confirmation method to correct for user input errors such as matching entries.
11. All passwords used in configuration scripts are secured and encrypted.
12. If a user believes their user ID has been compromised, they are required to immediately report the incident to the Security Officer or designated personnel. A specific form on the user support portal is used for this purpose.
13. In cases where the user has forgotten their passwords, the following procedure is used to reset the password:
    * The user submits a password reset request via the user interface.
    * The system automatically generates a password reset link and sends it to the email address on record for the user.
    * The user can click on the link provided and if the new password passes the complexity check, the password is reset.

## 7.13 Access to ePHI

1. Employees **may not download ePHI to any workstations used to connect to production systems**.
