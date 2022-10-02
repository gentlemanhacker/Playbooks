## Playbook: Website Defacement

### MITRE

| Tactic | Technique ID | Technique Name | Sub-Technique Name | Platforms | Permissions Required |
| ------ | ------------ | -------------- | ------------------ |---------- |--------------------- |
|Impact|T1491|Defacement|               |IaaS, Windows, Linux, MacOS ||



### HUNT

Hunt operations involve active reconnaissance and counter-reconnaissance on the supported network to gain and maintain
contact with an adversary and develop the situation. Discovery of threats during hunt operations
may, but do not always, result in immediate clearing or removal of identified threats. Operational
Commanders, or those with delegated authorities, monitor and characterize the threat as the first
step to develop appropriate follow-on actions, identify current risk, and assess residual risk levels.  CWP 3-33.4


<!--
`TODO: Expand investigation steps, including key questions and strategies, for Unauthorized VPN and VDI Access.`
-->
```
Review 
- All Event Logs
- All IIS logs (this includes FTP and logs for all Web Sites within IIS)
- A complete dump of the file system metatadata e.g. file names along with date created/date modified/date accessed

- When was the defacement first seen
- Is this affecting a single web site or multiple web sites
- If multiple sites are they on the same system
- What are the characteristics of the defacement, i.e. was the whole page replaced, was a portion of content on the page replaced, was only content that is sourced from a backend database modified?
```

```
1. Data on the file system was modified
- WEBDAV http extension permissions issues
- Frontpage server extension permissions issues
- Files modified via FTP
- Files modified via SMB
- Files modified interactively on the system either via local/RDP/Other logged on user

2. Data in a database that sources the web site was modified
- This is typically due to SQL Injection

```

```
Collect other important information from the page that has been defaced such as:
- Screenshot of the defacement
- The domain and IP address of the page
- Details of the web server
- Page's source code
- Analyze this carefully to identify the problem and ensure that it is on a server belonging to the company
- Information on the attacker
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
4.    With owner permission, immediately take the defaced server offline for further investigation. This is especially important if the defacement is insulting or triggering in any way. Remove this from the public eye as quickly as possible to avoid harm as well as to mitigate business impact. The defacement message may also contain false information that could mislead users or put them at risk.
5.    Determine the system's source of vulnerability that was used by the attacker.
	- SQL Injection
	- Remote File Attack
	- Webshell
	- Vulnerability Exploit
6.    Take down any endpoints that may have lateral movement to it




```
#### Reference: Remediation Resources

`TODO: Specify financial, personnel, and logistical resources to accomplish remediation.`

--------------
### HARDEN

Maintain and update network or system hardening recommendations for the duration of hunting and clearing operations.   CWP 3-33.4
```

Backup data
Edit access rights as needed

1.    Patch asset vulnerabilities
2.    Perform routine inspections of controls/weapons
3.    
4.    
5.    Ensure that all remotely accessible services are logging to a central location
6.    Provide security awareness training to employees
7.    Baseline security configuration to limit unnecessary protocols
8.    Ensure proper network segmentation/firewall rules are in place for remote users
9.    Update FW rules
10.   Update EDR rules on endpoint
11.   A PAM tool can limit authorized administrators to modify web pages

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
`TODO: Customize recovery s

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
7.    Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.
```
Validate Countermeasures
--------------


### Resources

- https://www.jcs.mil/Doctrine/Joint-Doctrine-Pubs/3-0-Operations-Series/
- https://github.com/certsocietegenerale/IRM/tree/master/EN
- https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf
- https://github.com/austinsonger/Incident-Playbook
- https://attack.mitre.org/techniques/
