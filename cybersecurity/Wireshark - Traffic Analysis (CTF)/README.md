# 🔍 Network Traffic Analysis & Cybersecurity Investigation Project

## 📊 Project Overview

**Advanced Wireshark Traffic Analysis – TryHackMe Walkthrough**  

A comprehensive cybersecurity project demonstrating advanced network traffic analysis techniques using Wireshark.  
This project showcases practical skills in network forensics, anomaly detection, and security incident investigation through hands-on analysis of various attack scenarios.

### 🎯 Project Objectives
- Master advanced packet analysis and filtering techniques
- Detect and analyze various network-based attacks
- Develop practical skills in network forensics and security investigation
- Create educational content for the cybersecurity community

---

## 🛠️ Technical Skills Demonstrated

### Core Competencies
- **Network Protocol Analysis**: TCP/IP, HTTP/HTTPS, DNS, DHCP, ARP, FTP, Kerberos
- **Traffic Filtering & Analysis**: Advanced Wireshark filtering techniques
- **Attack Detection**: Identifying scan patterns, tunneling, and malicious activities
- **Forensic Investigation**: Evidence correlation and attack timeline reconstruction
- **Encryption Handling**: HTTPS decryption using key materials

### Specialized Techniques
- **Nmap Scan Detection**: TCP Connect, SYN, and UDP scan identification
- **ARP Poisoning Analysis**: MITM attack detection and credential harvesting
- **Protocol Tunneling**: ICMP and DNS covert channel identification
- **Log4j Vulnerability Analysis**: CVE-2021-44228 exploitation detection
- **Credential Hunting**: Cleartext password extraction and analysis

---

## 🎯 Key Achievements & Findings

### 🔍 Attack Scenarios Analyzed

| Attack Type       | Packets Analyzed          | Key Findings                                  |
|-------------------|---------------------------|-----------------------------------------------|
| **Nmap Scanning** | 1,000+ TCP Connect scans  | Port 80 reconnaissance detected               |
| **ARP Poisoning** | 284 malicious ARP packets | 6 credentials harvested via MITM              |
| **DNS Tunneling** | Anomalous queries to `dataexfil[.]com` | Covert data exfiltration channel |
| **Log4j Exploit** | Base64 encoded payload    | Remote code execution attempt                 |
| **Brute Force**   | 737 failed FTP logins     | Credential stuffing attack                    |

### 🎯 Critical Security Indicators
- Reconnaissance activities from multiple scanning techniques
- Credential compromise: 6 username/password pairs intercepted
- Malware C2 communication over ICMP protocol
- Data exfiltration via DNS tunneling
- Remote shell deployment via Log4j exploit

---

## 🔧 Tools & Technologies

### Primary Analysis Tools
- **Wireshark** – Network protocol analyzer  
- **TryHackMe** – Hands-on cybersecurity training platform  
- **CyberChef** – Data transformation and analysis

### Supporting Technologies
- **Protocols**: TCP/IP Stack, HTTP/HTTPS, DNS, DHCP, ARP, FTP, Kerberos  
- **Attack Frameworks**: Nmap scanning, ARP spoofing, Traffic tunneling  
- **Cryptography**: TLS/SSL decryption, Base64 encoding/decoding

---

## 📈 Project Highlights

### 🏆 Advanced Filtering Examples

Below are some of the advanced Wireshark filters used in this project for precision traffic analysis and threat hunting:

| Purpose | Filter Expression | Description |
|---------|------------------|-------------|
| Identify SYN-ACK packets | `tcp.flags.syn == 1 && tcp.flags.ack == 1` | Finds handshake responses from target hosts |
| Detect non-standard ports | `tcp.port == 3333 || tcp.port == 4444 || tcp.port == 9999` | Flags unusual ports for investigation |
| Regex email detection | `frame matches "[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}"` | Extracts email addresses from packet payloads |
| High TTL anomaly check | `ip.ttl > 200` | Detects packets with unusually high TTL values |
| Bad checksum identification | `tcp.checksum_bad == 1` | Finds packets with invalid TCP checksums |
| Specific DNS query type | `dns.qry.type == 1` | Filters only A record queries |
| HTTP GET requests only | `http.request.method == "GET"` | Focuses on HTTP GET traffic |

These filters were crucial in isolating key traffic patterns, detecting anomalies, and investigating suspicious network activities.

---

### 🌐 Live Demonstration & Full Write-Up

You can read the **full 4,000-word technical walkthrough** with screenshots, explanations, and real packet capture examples here:

**[📄 Mastering Wireshark Packet Operations — A Comprehensive TryHackMe Walkthrough](https://medium.com/@aa7661538/mastering-wireshark-packet-operations-a-comprehensive-tryhackme-walkthrough-75c9bd6ea995)**

---

### 📌 Key Insights

- **Custom filtering** in Wireshark drastically improves investigation efficiency.
- **Regex matching** allows for advanced payload data extraction.
- **Port profiling** can uncover suspicious activity often missed in default scans.
- **Geolocation mapping** enhances threat intelligence correlation.
- **Baseline metrics** provide a reference point for anomaly detection.

---



