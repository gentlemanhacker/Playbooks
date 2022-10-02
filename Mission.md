# Generic Mission Flow

### All Teams
Inventory Equipment <br>
Identify Threat Agent

### Intel Team
Intelligence Report <br>
- Educate cyber defenders and improve their understanding of cyber threat tactics, techniques and procedures (TTPs)
- Replicate representative threats to support risk-mitigation efforts
- Provide advice on the conduct of cyber defense from an adversary perspective
Identify Critical Assets <br>


### NETWORK Team:
Configure Security Onion / Network Sensor <br>
Create IOC from Snort/Surricata based on Intel <br>
Review Network Topology from Customer <br>
Document Network Topology from Scans <br>
- Network Map
- Ping Scan

#### Look for
C2 <br>
Beacon <br>
Unusual Traffic <br>

Send any IP/Machine's for inspection to host team

#### Tools:
NMAP
- nmap -sV --script=banner <target>
Network Miner
Wireshark
- Statistics Menu
- Conversations
- Protocol Heirarchy 
Security Onion


### HOST Team:
Review Customer Host Baseline Image <br>
Configure GRR / Velocirapter for deployment/use (If applicable) <br>
If agents cannot be deployed, revise powershell script <br>

Analyze security event logs <br>
Analyze suspicious files <br>
Registry Entries <br>
Scheduled Tasks <br>

#### Watch for:
Data Exfil <br>
Keylogger Artifacts <br>
Malware <br>
Ransomware <br>

#### Tools:
GRR / Velociraptor <br>
Rekall <br>
Powershell <br>
Volatility <br>
FileAnalyzer <br>
  
### Web Team:
 
#### Tools:
  NMAP
- nmap -sV -T4 -F website.com
