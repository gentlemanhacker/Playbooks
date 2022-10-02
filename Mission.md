# Generic Mission Flow

### All Teams
Inventory Equipment <br>
Identify Threat Agent

### Intel Team
Intelligence Report
- Educate cyber defenders and improve their understanding of cyber threat tactics, techniques and procedures (TTPs)
- Replicate representative threats to support risk-mitigation efforts
- Provide advice on the conduct of cyber defense from an adversary perspective
Identify Critical Assets


### NETWORK Team:
Configure Security Onion / Network Sensor
Create IOC from Snort/Surricata based on Intel
Review Network Topology from Customer
Document Network Topology from Scans
- Network Map
- Ping Scan

#### Look for
C2
Beacon
Unusual Traffic

Send any IP/Machine's for inspection to host team

#### Tools:
NMAP
Network Miner
Wireshark
Security Onion


### HOST Team:
Review Customer Host Baseline Image
Configure GRR / Velocirapter for deployment/use (If applicable)
If agents cannot be deployed, revise powershell script

Analyze security event logs
Analyze suspicious files

#### Watch for:
Data Exfil
Keylogger Artifacts
Malware
Ransomware

#### Tools:
GRR / Velociraptor
Rekall
Powershell
Volatility
FileAnalyzer
