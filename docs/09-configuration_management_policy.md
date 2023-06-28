# 9. Configuration Management Policy

WayToHealth standardizes and automates configuration management through the use of Ansible and Terraform scripts as well as documentation of all changes to production systems and networks. Ansible automatically configures all WayToHealth systems according to established and tested policies, and are used as part of our Disaster Recovery plan and process.

## 9.1 Applicable Standards

### 9.1.1 Applicable Standards from the HITRUST Common Security Framework

* 06 - Configuration Management

### 9.1.2 Applicable Standards from the HIPAA Security Rule

* 164.310(a)(2)(iii) Access Control & Validation Procedures

## 9.2 Configuration Management Policies

1. Ansible is used to standardize and automate configuration management.
2. No systems are deployed into WayToHealth environments without approval of the WayToHealth Engineering Lead.
3. All changes to production systems are approved by the WayToHealth Engineering Lead before they are implemented to assure they comply with business and security requirements.
4. All changes to production systems are tested before they are implemented in production.
5. Implementation of approved changes are only performed by authorized personnel.
6. An up-to-date inventory of systems, including corresponding architecture diagrams for related products and services, is maintained in Confluence pages in the WayToHealth TQMS.
   * All systems are categorized as production, test, staging, and utility to differentiate based on criticality.
   * These reports are used to generate and / or maintain the diagrams and asset lists required by the Risk Assessment phase of WayToHealth's Risk Management procedures ([§4.3.1](#4-3-risk-management-procedures)).
   * On a regular frequency, currently quarterly, the Security Officer or designated personnel will verify the accuracy of the reports by reconciling their output with recent changes to production systems. The Security Officer or designated personnel will address any discrepancies immediately with changes to the scripts.
7. All frontend functionality (admin dashboards and portals) is separated from backend (database and app servers) systems by being deployed on separate servers or containers.
8. All software and systems are tested using unit tests and end to end tests.
9. All committed code is reviewed using pull requests to assure software code quality and proactively detect potential security issues in development.
10. WayToHealth utilizes test (development) and staging environments that mirror production to assure proper function.
11. WayToHealth also deploys environments locally to assure functionality before moving to staging or production.
12. All change requests must be formally filed and authorized before implementation.
13. WayToHealth uses the [Security Technical Implementation Guides (STIGs)](http://iase.disa.mil/stigs/) published by the Defense Information Systems Agency as a baseline for hardening systems.
14. Clocks are continuously synchronized to an authoritative source across all systems using NTP or a platform-specific equivalent. Modifying time data on systems is restricted.

## 9.3 Provisioning Production Systems

1. Before provisioning any systems, engineering team members must file a request in the WayToHealth TQMS.
   * TQMS access requires authenticated users.
   * The Engineering Lead grants access to the TQMS following the procedures covered in the [Access Establishment and Modification section](#7-2-access-establishment-and-modification).
2. The Engineering Lead, or an authorized delegate of the Engineering Lead, must approve the provisioning request before any new system can be provisioned.
3. Once provisioning has been approved, the Infrastructure team member must configure the new system according to the standard baseline chosen for the system's role.
   * For Linux systems, this means adding the appropriate configurations to the Ansible and / or Terraform configuration file.
4. If the system will be used to house production data (ePHI), the engineering team member must encrypt the associated data volume of the VM during provisioning.
   * For systems on cloud providers, the engineering team member must add a block data volume and set up OS-level data encryption using Ansible or Terraform.
5. The default set up configurations (which cannot be changed unless approved by the relevant Security Officer) and maintained with version control on Gitlab ensure the following items are always implemented on every new system provisioned:
   * Removal of default users used during provisioning.
   * Network configuration for system.
   * Data volume encryption settings.
   * Antivirus/antimalware protection.
   * Server is added to vulnerability scanning service (Nessus Security Center)
   * Server is added to IPS service (Fortigate on Fortinet firewalls) 
   * All items listed below in the operating system-specific subsections below.
6. Once the Engineering Lead has verified the new system is correctly configured, the team member must add that system to the security scanner configuration.
7. The new system may be rotated into production once the Engineering Lead verifies all the provisioning steps listed above have been correctly followed and has marked the Ticket with the `Approved` state.

### 9.3.1 Provisioning Linux Systems

1. Linux systems have their baseline security configuration applied via Ansible and/or Terraform states. These baseline Ansible states cover:
   * Ensuring that the machine is up-to-date with security patches and is configured to apply patches in accordance with our policies.
   * Stopping and disabling any unnecessary OS services.
   * Configuring 15-minute session inactivity timeouts.
   * Installing and configuring the NTP daemon, including ensuring that modifying system time cannot be performed by unprivileged users.
   * Configuring LUKS volumes (where necessary) for providers that do not have native support for encrypted data volumes, including ensuring that encryption keys are protected from unauthorized access.
   * Configuring IDS and antivirus/antimalware agents.
   * Configuring authentication to the centralized LDAP servers.
   * Configuring audit logging as described in the [Auditing Policy section](#8-auditing-policy).
2. Any additional Ansible states applied to the Linux system must be clearly documented by the engineering team member in the request by specifying the purpose of the new system.

### 9.3.2 Provisioning Management Systems

1. Provisioning management systems such as Ansible servers, LDAP servers, or VPN appliances follows the same procedure as provisioning a production system.
2. Critical infrastructure services such as logging, monitoring and LDAP servers must be configured with appropriate Ansible states.
   * These Ansible states have been approved by the Engineering Lead, or an authorized delegate of the Engineering Lead or by the underlying hosting providers Infrastructure team, to be in accordance with all WayToHealth policies, including setting appropriate:
     * Audit logging requirements.
     * Password size, strength, and expiration requirements.
     * Transmission encryption requirements.
     * Network connectivity timeouts.
4. Critical infrastructure roles applied to new systems must be clearly documented by the infrastructure team member in the provisioning request.

## 9.4 Changing Existing Systems

1. Subsequent changes to already-provisioned systems are unconditionally handled by one of the following methods:
   * Changes to Ansible states.
   * Changes to Terraform recipes.
   * For configuration changes that cannot be handled by Terraform or Ansible, a runbook describing exactly what changes will be made and by whom.
2. Configuration changes to Terraform recipes or Ansible states must be initiated by creating a Merge Request in GitLab.
   * The engineering team member will create a feature branch and make their changes on that branch.
   * The engineering team member must test their configuration change locally when possible, or on a development and/or staging sandbox otherwise.
   * At least one other engineering team member must review the Terraform or Ansible change before merging the change into the main branch.
3. In all cases, before rolling out the change to production, the engineering team member must file an Ticket describing the change. This Ticket must link to the reviewed Merge Request and/or include a link to the runbook.
4. Once the request has been approved by the Engineering Lead, the engineering team member may roll out the change into production environments.

## 9.5 Patch Management Procedures

1. WayToHealth uses a combination of manual processes and automated tooling to ensure systems are up-to-date with the latest security patches.
2. On CentOS Linux systems, the cron tool is used to apply security patches in phases.
   * The security team maintains a mirrored snapshot of security patches from the upstream OS vendor. This mirror is synchronized bi-weekly and applied to development and staging systems monthly.
   * If the development and staging systems function properly after a one-week testing period, these patches will be applied to all production systems during the next patch run.
   * Patches for critical kernel security vulnerabilities may be applied to production systems using hot-patching tools at the discretion of the Security Officer or designated personnel. These patches must follow the same phased testing process used for non-kernel security patches; this process may be expedited for severe vulnerabilities.

## 9.6 Software Development Procedures

1. All development uses feature branches based on the main branch used for the current release. Any changes required for a new feature or defect fix are committed to that feature branch.
   * These changes must be covered under 1) a unit test where possible, or 2) integration tests.
   * Integration tests are _required_ if unit tests cannot reliably exercise all facets of the change.
2. Developers are strongly encouraged to follow the [commit message conventions suggested by GitHub](https://github.com/blog/926-shiny-new-commit-styles).
   * Commit messages should be wrapped to 72 characters.
   * Commit messages should be written in the present tense. This convention matches up with commit messages generated by commands like git merge and git revert.
3. Once the feature and corresponding tests are complete, a pull request will be created using the GitLab web or command line interface. The pull request should indicate which feature or defect is being addressed and should provide a high-level description of the changes made.
4. Code reviews are performed as part of the pull request procedure. Once a change is ready for review, the designated technical reviewer will be notified using an appropriate mechanism, typically via an `@user` message in Slack.
   * The designated engineer(s) will review the changes, using the guidelines above.
   * Engineers should note all potential issues with the code; it is the responsibility of the author(s) to address those issues or explain why they are not applicable.
5. If the feature or defect interacts with ePHI, or controls access to data potentially containing ePHI, the code changes must be reviewed as follows before the feature is marked as complete.
   * Perform a security analysis of features to ensure they satisfy WayToHealth's compliance and security commitments.
   * Perform a security analysis for potential vulnerabilities such as those listed in the [OWASP Top 10](https://www.owasp.org/index.php/Top10) or the [CWE top 25](http://cwe.mitre.org/top25/).
   * Verify that any actions performed by authenticated users will generate appropriate audit log entries.
   * Designated engineers will be required to undergo annual training on identifying the most common software vulnerabilities and will receive ongoing training on WayToHealth's compliance and security requirements.
6. Once the review process finishes, each reviewer should leave a comment on the pull request saying "looks good to me" (often abbreviated as "LGTM") or similar, at which point the original author(s) may merge their change into the release branch.

## 9.7 Software Release Procedures

1. Software releases are treated as changes to existing systems and thus follow the procedure described in [§9.4](#9-4-changing-existing-systems).
