#Enterprise SOC Home Lab

A hands-on Security Operations Centre (SOC) lab built to develop practical experience in SIEM monitoring, endpoint telemetry, threat detection, incident investigation, MITRE ATT&CK mapping, and detection engineering.

The environment uses **Wazuh, Sysmon, Windows 11, Kali Linux, Ubuntu Server, and VMware** to simulate security activity in an isolated network and investigate the resulting telemetry from a SOC analyst perspective.

> All attack simulations are performed in an isolated virtual lab against systems that I own and control.


#Project Objectives

This project was created to develop practical experience in:

- SIEM deployment and administration
- Windows endpoint monitoring
- Sysmon telemetry collection
- Wazuh agent deployment
- Security alert triage
- Threat hunting
- MITRE ATT&CK mapping
- PowerShell activity analysis
- Process and command-line investigation
- Network reconnaissance
- Incident documentation
- Detection engineering
- Custom Wazuh rules
- SOC investigation workflows


# Lab Architecture

The lab currently consists of three virtual machines running inside VMware Workstation.

 
 
                         VMware Workstation
                                |
             +------------------+------------------+
             |                                     |
             v                                     v

      SOC-KALI-ATTACKER                     SOC-WAZUH-SERVER
      Kali Linux                            Ubuntu Server
      Attacker VM                           192.168.x.x
             |                                     |
             |                                     |
             |                              Wazuh Manager
             |                                     |
             |                              Wazuh Indexer
             |                                     |
             |                              Wazuh Dashboard
             |
             | Controlled attack traffic
             v
      SOC-WINDOWS-01
      Windows 11 Pro
      192.168.x.x
             |
          Sysmon
             |
        Wazuh Agent
             |
             | Security telemetry
             +-----------------------------> Wazuh Manager



### Network Design

The lab uses two VMware network interfaces:

NAT— provides internet access for updates, package installation, and software downloads.
Host-only— provides an isolated private network used for SOC monitoring and controlled attack simulations.

Exact internal host addresses are intentionally masked in the public repository.
