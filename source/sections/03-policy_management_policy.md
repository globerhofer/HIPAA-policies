# 3. Policy Management Policy

Datica implements policies and procedures to maintain compliance and integrity of data. The Security Officer and Privacy Officer are responsible for maintaining policies and procedures and assuring all Datica workforce members, business associates, customers, and partners are adherent to all applicable policies. Previous versions of policies are retained to assure ease of finding policies at specific historic dates in time.

## 3.1 Applicable Standards

### 3.1.1 Applicable Standards from the HITRUST Common Security Framework

* 12.c - Developing and Implementing Continuity Plans Including Information Security

### 3.1.2 Applicable Standards from the HIPAA Security Rule

* 164.316(a) - Policies and Procedures
* 164.316(b)(1)(i) - Documentation

## 3.2 Maintenance of Policies

1. All policies are stored and up to date to maintain Datica compliance with HIPAA, HITRUST, NIST, and other relevant standards. Updates and version control are done similar to source code control.
2. Policy update requests can be made by any workforce member at any time. Furthermore, all policies are reviewed annually by both the Security and Privacy Officer to assure they are accurate and up-to-date.
3. Edits and updates made by appropriate and authorized workforce members are done on their own versions, or branches. These changes are only merged back into final, or master, versions by the Privacy or Security Officer, similar to a pull request. All changes are linked to workforce personnel who made them and the Officer who accepted them.
4. All policies are made accessible to all Datica workforce members. The current master policies are published at [https://policy.datica.com](https://policy.datica.com).
   * Changes can be requested to policies using this [form](https://docs.google.com/a/catalyze.io/forms/d/1sJ_8DcbbW8i2i85pqXU7JrjHLFYBhFj_TP5uAG4QFZE/viewform).
   * Once the change has been approved to a Datica Policy we implement the policy change using Chef/Salt. The process for that is spelled out in the Datica Configuration Management Policy.
   * Changes are automatically communicated to all Datica team members through integrations between GiHhub and Slack that log all GitHub policy channels to a dedicated Datica Slack Channel.
5. All policies, and associated documentation, are retained for 6 years from the date of its creation or the date when it last was in effect, whichever is later
   1. Version history of all Datica policies is done via GitHub.
   2. Backup storage of all policies is done with Box.
6. The policies and information security policies are reviewed and audited annually. Issues that come up as part of this process are reviewed by Datica management to assure all risks and potential gaps are mitigated and/or fully addressed. The process for reviewing polices is outlined below:
  1. The Security Officer initiates the policy review by creating an issue in the JIRA Compliance Review Activity (CRA) project.
  2. The Security Officer or the Privacy Officer is assigned to review the current Datica policies ([https://policy.datica.com/](https://policy.datica.com/)).
  3. If changes are made, the above process is used. All changes are documented in the Issue.
  4. Once the review is completed, the Security Officer approves or rejects the Issue. If the Issue is rejected, it goes back for further review and documentation.
  5. If the review is approved, the Security Officer then marks the issue as Done, adding any pertinent notes required.
  6. Policy review is monitored on a quarterly basis using JIRA reporting to assess compliance with above policy.
7. Datica utilizes the HITRUST MyCSF framework to track compliance with the HITRUST CSF on an annual basis. Datica also tracks compliance with HIPAA and publishes results at [https://hipaa.datica.com](https://hipaa.datica.com). In order to track and measure adherence on an annual basis, Datica uses the following process to track HITRUST audits, both full and interim:
  1. The Security Officer initiates the HITRUST audit activity by creating an issue in the JIRA Compliance Review Activity (CRA) project.
  2. The Security Officer or the Privacy Officer is assigned to own and manage the HITRUST activity.
  3. Once the HITRUST activity is completed, the Security Officer approves or rejects the Issue.
  5. If the review is approved, the Security Officer then marks the issue as Done, adding any pertinent notes required.
  6. Compliance with annual compliance assessments, utilizing the HITRUST CSF as a framework, is monitored on a quarterly basis using JIRA reporting to assess compliance with above policy.

Additional documentation related to maintenance of policies is outlined in [§5.3.1](#5.3-security-officer).
