
# POWERSHELL ABUSE DETECTION & THREAT HUNTING

## Objective

This project aimed to simulate and detect malicious PowerShell activity within a Windows environment. The primary focus was to generate PowerShell telemetry using Sysmon and Windows Event Logs, ingest the data into Splunk SIEM, and investigate suspicious behaviors such as encoded commands, command spawning, and script execution.

The project was designed to strengthen threat hunting, endpoint monitoring, and incident investigation skills by analyzing attacker techniques commonly used for execution, persistence, and defense evasion.

### Skills Learned

* PowerShell Threat Hunting
* Windows Event Log Analysis
* Sysmon Monitoring and Detection
* Detection Engineering
* Security Investigation Methodology
* SIEM Query Development (Splunk SPL)
* Malware Execution Analysis
* Endpoint Visibility and Monitoring
* Threat Intelligence Enrichment
* Incident Documentation

### Tools Used

* Splunk Enterprise
* Sysmon
* Windows 10
* Windows Event Viewer
* PowerShell
* Sysmon Modular Configuration
* n8n Automation Platform
* VirusTotal API
* VirtualBox Lab Environment

## Steps

### Step 1: Configure Sysmon Telemetry

Sysmon was deployed to provide enhanced endpoint visibility and collect detailed process creation, command-line execution, and PowerShell activity.

**Ref 1: Sysmon Configuration**

<img width="617" height="350" alt="sysmon " src="https://github.com/user-attachments/assets/f6f3f657-fea5-40f6-87a9-703465a64915" />

The screenshot shows Sysmon successfully generating telemetry required for PowerShell monitoring and threat hunting.

---

### Step 2: Enable PowerShell Script Block Logging

PowerShell Script Block Logging (Event ID 4104) was enabled to capture the contents of executed PowerShell scripts.

**Ref 2: Event ID 4104 Logging**

<img width="382" height="362" alt="even id 4104" src="https://github.com/user-attachments/assets/c3023c86-cbec-49ca-9837-4edf2c9c476c" />

This event provides visibility into executed PowerShell commands, including obfuscated and encoded scripts.

---

### Step 3: Simulate Encoded PowerShell Commands

A Base64-encoded PowerShell command was executed to emulate common attacker behavior.

**Ref 3: Encoded PowerShell Command**

<img width="470" height="77" alt="encoded command" src="https://github.com/user-attachments/assets/7a9c2543-8ca5-4202-9b18-7b09636a71fa" />

Attackers frequently use encoded commands to evade detection and hide malicious activity.

---

### Step 4: Detect Suspicious PowerShell Activity in Splunk

Splunk searches were used to identify PowerShell abuse patterns and suspicious command-line activity.

**Ref 4: PowerShell Detection Query**

<img width="951" height="346" alt="detect" src="https://github.com/user-attachments/assets/e13b20b1-fab3-4e2d-b977-4e3697f0fa90" />

Detection logic was developed to identify abnormal PowerShell execution behavior.

---

### Step 5: Investigate Additional Detection Results

Additional threat hunting queries were performed to identify indicators of malicious execution.

**Ref 5: Detection Investigation**

<img width="952" height="307" alt="detect 2" src="https://github.com/user-attachments/assets/bccecc6e-6e1b-45af-825b-570d26a35e6f" />

The screenshot demonstrates how suspicious PowerShell activity can be identified through log analysis.

---

### Step 6: Analyze Advanced Detection Findings

Further analysis was performed to validate findings and investigate command execution patterns.

**Ref 6: Advanced Detection**

<img width="946" height="284" alt="detect 3" src="https://github.com/user-attachments/assets/b52c4cb9-7472-4bf2-b64b-d4a2802ac13e" />

The investigation focused on identifying potentially malicious PowerShell usage.

---

### Step 7: Review High-Risk Activity

Security events were correlated to determine the scope and impact of suspicious activity.

**Ref 7: Threat Hunting Results**

<img width="952" height="254" alt="detect 4" src="https://github.com/user-attachments/assets/722be4e9-85ca-4563-98c1-59f344f3eeb2" />

This analysis helped distinguish legitimate administrative activity from potentially malicious behavior.

---

### Step 8: Monitor Command Spawning Behavior

PowerShell spawning command prompt processes was investigated as a common indicator of malicious execution.

**Ref 8: Command Spawning**

<img width="458" height="91" alt="cmd spawing" src="https://github.com/user-attachments/assets/29e70d66-66db-4d0a-9036-61cf7b40a184" />

Attackers frequently use PowerShell to launch additional processes for lateral movement or payload execution.

---

## Key Findings

* PowerShell provides attackers with powerful native capabilities for execution and automation.
* Encoded commands can be detected through command-line monitoring and Script Block Logging.
* Sysmon significantly improves visibility into PowerShell activity.
* Event ID 4104 is critical for detecting obfuscated scripts.
* Splunk enables effective threat hunting through centralized log analysis.
* Process creation telemetry helps identify suspicious parent-child process relationships.

## Conclusion

This project successfully demonstrated how PowerShell abuse can be detected and investigated using Sysmon, Windows Event Logs, and Splunk SIEM. Through telemetry analysis, encoded command detection, and threat hunting activities, valuable experience was gained in identifying attacker techniques and building effective detection strategies for enterprise environments.
