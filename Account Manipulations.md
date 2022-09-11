## Playbook: Account Manipulations

### MITRE

| Tactic | Technique ID | Technique Name | Sub-Technique Name | Platforms | Permissions Required |
| ------ | ------------ | -------------- | ------------------ |---------- |--------------------- |
|Initial Access|T1098|Account Manipulation|               |AAD, GCP, AWS, Windows, Linux, macOS ||
|Initial Access|T1136|Create Account|               |AAD, GCP, AWS, Windows, Linux, macOS ||


### HUNT

Hunt operations involve active reconnaissance and counter-reconnaissance on the supported network to gain and maintain
contact with an adversary and develop the situation. Discovery of threats during hunt operations
may, but do not always, result in immediate clearing or removal of identified threats. Operational
Commanders, or those with delegated authorities, monitor and characterize the threat as the first
step to develop appropriate follow-on actions, identify current risk, and assess residual risk levels.  CWP 3-33.4

Adversaries may manipulate accounts to maintain access to victim systems. Account manipulation may consist of any action that preserves adversary access to a compromised account, such as modifying credentials or permission groups. These actions could also include account activity designed to subvert security policies, such as performing iterative password updates to bypass password duration policies and preserve the life of compromised credentials.

Adversaries may create an account to maintain access to victim systems. With a sufficient level of access, creating such accounts may be used to establish secondary credentialed access that do not require persistent remote access tools to be deployed on the system.


<!--
`TODO: Expand investigation steps, including key questions and strategies, for Unauthorized VPN and VDI Access.`
-->
```
1. Monitor for:
    * User Activity Logs for unexpected modifications to Users, Service Principles, Applications
    * Modifications to authorized_keys or /etc/ssh/sshd_config
    * Add-MailboxPermission
    * Event IDs 4738, 4728 and 4670, 4720.
    * sp_addlinkedsrvlogin ms-sql command
    * net localgroup changes
    * mimikatz functions LSADUMP::ChangeNTLM and LSADUMP::SetNTLM
    * WMIC.exe user Additions, net user and useradd
    * net user /add /domain calls as well as \password and \domain
    * PsExec use

2.  Contact the user out of band to determine the legitimacy of the detected activity

```
--------------

### CLEAR

Clear is defined as an operation to target and engage malicious cyberspace activities in order to eliminate or neutralize it from a
network or system, and may include actions to interdict, contain, disrupt, or degrade malicious cyberspace activities.   CWP 3-33.4

* **Plan remediation events** where these steps are launched together (or in coordinated fashion), with appropriate teams ready to respond to any disruption.
* **Consider the timing and tradeoffs** of remediation actions: your response has consequences.

<!--
`TODO: Specify tools and procedures for each step, below.`
-->
```
1.    Inventory (enumerate & assess)
2.    Detect | Deny | Disrupt | Degrade | Deceive | Destroy
3.    Observe -> Orient -> Decide -> Act
4.    Remove all malicious scheduled Tasks
5.    Remove all malicious persistent files
6.    Lock accounts associated with the compromised user
7.    Inspect all potentially compromised systems for IOCs
8.    Close the attack vector
9.    Patch asset vulnerabilities
10.    Perform Endpoint/AV scans on affected systems
11.    Review logs to determine the extent of the unauthorized activity
```
#### Reference: Remediation Resources

`TODO: Specify financial, personnel, and logistical resources to accomplish remediation.`

--------------

### HARDEN

Maintain and update network or system hardening recommendations for the duration of hunting and clearing operations.   CWP 3-33.4
```
1.    Patch asset vulnerabilities
2.    Perform routine inspections of controls/weapons
3.    Enforce MFA
4.    Prohibit non-employees from accessing company devices
5.    Ensure that all remotely accessible services are logging to a central location
6.    Provide security awareness training to employees
7.    Baseline security configuration to limit unnecessary protocols
8.    Ensure proper network segmentation/firewall rules are in place for remote users
9.    Update FW rules
10.   Update EDR rules
11.   A PAM tool can limit authorized administrators to create scheduled tasks

```

Assign steps to individuals or teams to work concurrently, when possible; this playbook is not purely sequential. Use your best judgment.

--------------



--------------

### Recover / ASSESS

Continuous assessment is a doctrinal aspect of military operations planning and
execution. During operations, the CPT will simultaneously assess the effectiveness of clearing
operations, hardening actions taken by local network defenders, and the overall network system
security, and resilience. The goal of assessment is the replication of threat intrusion actions (i.e.,
cyber threat emulation (CTE)) to ensure vulnerabilities were mitigated and attempts by future
threats employing the same intrusion and exploitation TTPs are detected or prohibited. CTE as
conducted by CPTs is discussed in more detail below, and CPTs will ensure CTE is conducted
IAW USCYCBERCOM policies and procedures.  CWP 3-33.4

<!--
`TODO: Customize recovery steps for Unauthorized VPN and VDI Access.`

`TODO: Specify tools and procedures for each step, below.`
-->


In addition to the general steps and guidance in the incident response plan:

```
1.    Restore to the Recovery Point Objective (RPO) within the Recovery Time Objective (RTO)
2.    Address collateral damage
3.    Resolve any related security incidents
4.    Perform routine cyber hygiene due diligence
5.    Engage external cybersecurity-as-a-service providers and response professionals
6.    Routinely audit remote system access
```
Validate Countermeasures
--------------


### Resources

- https://www.jcs.mil/Doctrine/Joint-Doctrine-Pubs/3-0-Operations-Series/
- https://github.com/certsocietegenerale/IRM/tree/master/EN
- https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf
- https://github.com/austinsonger/Incident-Playbook
- https://attack.mitre.org/techniques/
