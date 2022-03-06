## Playbook: Unauthorized Remote and VDI Access

### MITRE

| Tactic | Technique ID | Technique Name | Sub-Technique Name | Platforms | Permissions Required |
| ------ | ------------ | -------------- | ------------------ |---------- |--------------------- |
|Initial Access|T1133|External Remote Services|               |Containers, Linux, Windows|User|


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
1. Monitor for:
    * Remote access during unusual hours/days
    * Remote access from unusual sources (i.e. geographic locations, IPs, etc.)
    * Excessive failed login attempts
    * IPS/IDS alerts
    * Antivirus/Endpoint alerts
2.    Investigate and clear ALL alerts associated with the impacted assets
3.    Contact the user out of band to determine the legitimacy of the detected activity
4.  Look for Compromise
    * Compromised accounts
    * Compromised domains
    * Compromised machines
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
4.    Issue perimeter enforcement for known threat actor locations
5.    Block access from the compromised user, update FW, Proxy, etc...
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
3.    Ensure Antivirus/Endpoint Protection software is installed on workstations and laptops
4.    Prohibit non-employees from accessing company devices
5.    Ensure that all remotely accessible services are logging to a central location
6.    Provide security awareness training to employees
7.    Use multifactor authentication where possible
8.    Ensure proper network segmentation/firewall rules are in place for remote users
9.    Update FW rules
10.   Update EDR rules

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
1.    Restore to the RPO within the RTO
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
- https://www.dfir.training/
- https://www.gov.scot/publications/cyber-resilience-incident-management/
- https://github.com/certsocietegenerale/IRM/tree/master/EN
- https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf
- https://github.com/austinsonger/Incident-Playbook
