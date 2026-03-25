# Snort: Network Intrusion Detection and Prevention System

**Network Security Project** | Siddartha Bandi

---

## Overview

This project presents a comprehensive technical analysis of **Snort**, the world's most widely deployed open-source Network Intrusion Detection and Prevention System (IDS/IPS). Originally developed by Martin Roesch in 1998 and now maintained by Cisco Systems under the GNU General Public License (GPL), Snort inspects real-time network traffic against a library of rules to identify malicious patterns, policy violations, and anomalous activity.

The paper covers Snort's architecture, operational modes, installation procedures across major operating systems, rule authoring, and practical deployment configurations for both detection and inline prevention use cases.

---

## Topics Covered

### 1. Overview & Core Features
- **Packet Sniffing** — real-time traffic capture (similar to tcpdump/Wireshark)
- **Packet Logging** — recording traffic to disk in pcap, text, or unified2 format
- **Signature-Based Detection** — rule-driven pattern matching on network packets
- **Preprocessors & Decoders** — stream reassembly (stream5), HTTP Inspector, portscan detection
- **Protocol Analysis** — Deep Packet Inspection (DPI) across TCP, UDP, ICMP, HTTP, FTP, SMTP, DNS
- **Inline IPS Mode** — active packet dropping/rejection between network segments
- **Output Plugins** — syslog, MySQL/PostgreSQL, unified2 (Barnyard2 compatible), PCAP

### 2. Installation Guides
Step-by-step installation instructions for:
- **Windows** — installer package + Npcap
- **macOS** — Homebrew installation (`brew install snort`)
- **Linux (Debian/Ubuntu)** — `apt` package manager
- **Linux (RHEL/CentOS)** — `yum`/`dnf` package manager
- **Source compilation** — custom builds with libpcap, libdnet, PCRE, DAQ dependencies

### 3. Operational Modes & Command Reference
Representative command lines for all primary modes:
```bash
snort -V                            # Version check
sudo snort -v -i eth0              # Packet sniffer mode
sudo snort -l /var/log/snort -i eth0  # Packet logger mode
sudo snort -c /etc/snort/snort.conf -i eth0  # NIDS mode
```

### 4. Rule Language
- Rule syntax: `action protocol src_ip src_port -> dst_ip dst_port (options)`
- Rule actions: `alert`, `log`, `pass`, `drop`, `reject`
- Writing custom detection rules for specific threats
- Community rulesets vs. Snort VRT registered/subscriber rules

---

## Repository Contents

```
Project_Snort/
├── README.md
├── Siddartha_Bandi_Snort.pdf     # Full technical paper (PDF)
```

---

## Key Concepts

| Concept | Description |
|---------|-------------|
| IDS | Intrusion Detection System — monitors and alerts on suspicious traffic |
| IPS | Intrusion Prevention System — actively blocks malicious packets inline |
| DAQ | Data Acquisition library — Snort's packet I/O abstraction layer |
| Unified2 | Binary output format for high-performance logging (used with Barnyard2) |
| stream5 | Preprocessor for TCP stream reassembly and stateful inspection |
| VRT Rules | Snort's official Vulnerability Research Team ruleset |

---

## Technologies & Tools

| Category | Tools |
|----------|-------|
| IDS/IPS Engine | Snort 2.9.x |
| Packet Capture | libpcap, Npcap (Windows), WinPcap |
| Rule Management | Snort VRT, Community Rules, PulledPork |
| Log Processing | Barnyard2, unified2 |
| Supported Platforms | Linux, macOS, Windows |

---

## Author

**Siddartha Bandi**
Network Security — Snort IDS/IPS Analysis
