**🛡️ SOC Home Lab — Attack & Defense Simulation**
Wazuh • TheHive • Sysmon • Shuffle SOAR • Mimikatz Detection

This repository documents a full SOC Attack & Defense Simulation Lab, built entirely using free, open-source tools:

Windows 11 VM

Sysmon (high-fidelity EDR telemetry)

Wazuh SIEM (log analysis + detection engine)

TheHive (case management)

Shuffle SOAR (automation orchestration)

VirusTotal API (hash enrichment)

Mimikatz Attack Simulation

The lab performs end-to-end detection, enrichment, case creation, and automated email notification.

**📘 Table of Contents**

Overview

Architecture

Tools Used

Setup Documentation

Attack Scenario

Automation Workflow

Screenshots

Future Enhancements

**⚡ Overview**

This project replicates a modern SOC workflow:

Sysmon logs → Wazuh

Wazuh detects malicious activity → sends alert

Shuffle receives webhook → extracts data

Hash is enriched via VirusTotal

Shuffle creates a case in TheHive

Shuffle sends an email notification

This is the exact workflow analysts follow in real SOC environments.


**🧰 Tools Used**

Tool	Purpose,
VirtualBox	Windows 11 VM environment,
Sysmon	Detailed Windows telemetry (process, network, registry),
Wazuh	SIEM & agent management,
TheHive	Incident response & case handling,
Shuffle	Automation & integrations,
VirusTotal API	Threat intel enrichment, and
Mimikatz	Credential theft attack simulation

**📄 Setup Documentation**

All installation steps are in the /docs/ folder:

Step	Document
Windows 11 VM Setup	01_virtualbox_windows_setup.md

Sysmon Installation	02_sysmon_installation.md

Wazuh Setup	03_wazuh_installation.md

TheHive Setup	04_thehive_installation.md

Wazuh Agent + Sysmon Ingestion	05_wazuh_agent_sysmon_ingestion.md

Custom Mimikatz Rule	06_custom_mimikatz_rule.md

Shuffle Automation	07_shuffle_automation.md

**🎯 Attack Scenario (Mimikatz)**

Defender disabled

Sysmon monitors process creation (EventID 1)

Mimikatz execution generates telemetry

Wazuh detects the process name mimikatz.exe

Custom rule triggers an alert

Alert flows into the automation pipeline.

**🤖 Automation Workflow**

Shuffle receives the Wazuh webhook and:

Extracts SHA256 hash from Wazuh alert

Enriches the hash using VirusTotal

Creates a case in TheHive

Sends an email to the analyst

This simulates real automated incident response.

**🚀 Future Enhancements**

Add Sigma rules → Wazuh

Integrate Cortex analyzers for automated malware analysis

Add Elastic Stack dashboards

Add Atomic Red Team attack library

Add PowerShell Empire C2 Simulation

Add ELK + Fleet Server for unified log ingestion

**🎉 Final Notes**

This project demonstrates:

✔ SOC analysis fundamentals
✔ SIEM engineering
✔ Detection engineering
✔ Automation (SOAR)
✔ Incident response workflow
✔ Threat intelligence enrichment
