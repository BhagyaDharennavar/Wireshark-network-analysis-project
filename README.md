# Network Traffic Monitoring & Threat Detection Using Wireshark

### A Cybersecurity & SOC Analyst Project by **Bhagya Dharennavar**

---

## 📌 Project Overview
This project demonstrates practical network traffic analysis using **Wireshark**, focusing on detecting:
- Normal vs abnormal network behaviors  
- Port scanning (Nmap SYN Scan)  
- DNS anomalies  
- Packet-level forensics  
- Threat detection workflow  
- *(FTP brute-force will be added later)*

The goal is to understand attacker behavior and how SOC analysts detect early cyber threats using packet captures.

---

## 📌 1. Project Objectives
By completing this project, I learned:
- How Wireshark captures and interprets packets  
- How to differentiate normal vs abnormal traffic  
- How to detect reconnaissance attempts  
- How to identify DNS-based anomalies  
- How to analyze TCP flags and DNS responses  
- How to document findings like a SOC analyst  

---

## 📌 2. Tools Used
- **Wireshark**  
- **Nmap**  
- **Windows PC**  
- **(Upcoming)** FileZilla Server + Client  

---

## 📌 3. Normal Traffic Baseline
PCAP: `normal_traffic.pcapng`  
Normal traffic contains:
- DNS lookups  
- HTTPS traffic  
- OS background connections  
- No suspicious patterns  

A baseline helps compare normal vs abnormal activity.

---

## 📌 4. Port Scan Detection (Nmap SYN Scan)
PCAPs:
- `portscan_full_capture.pcapng`  
- `portscan_syn_only.pcapng`

A SYN scan is a stealth scan using:
```
SYN → SYN/ACK → RST
```

### 🔍 Indicators in Wireshark:
- Large burst of SYN packets  
- Ports scanned sequentially (1–2000)  
- RST responses from victim  
- No full TCP handshake  

Meaning: **Attacker reconnaissance activity**.

---

## 📌 5. DNS Anomaly Detection
PCAPs:
- `dns_anomaly.pcapng`  
- `dns_full_capture.pcapng`

### 🔍 Indicators:
- Random domain queries  
- Multiple failed lookups  
- NXDOMAIN errors  
- Suspicious TLDs (.xyz, .zip, .ru)  

Meaning: **Possible malware, botnet, or misconfiguration**.

---

## 📌 6. Packet-Level Threat Detection Skills Learned
- TCP 3-way handshake analysis  
- DNS query/response inspection  
- Identifying suspicious patterns  
- Understanding attacker techniques  
- SOC-level alerting and documentation  

---

## 📌 7. Findings Summary
✔ Normal traffic: clean  
✔ Port scan: detected  
✔ DNS anomalies: detected  
✔ FTP brute-force: *(to be added)*  

---

## 📌 8. FTP Brute-Force (Coming Soon)
Will include:
- Clear-text FTP credential leak  
- Brute-force sequence  
- 530/230 response code analysis  
- SOC investigation  

---

## 📌 9. Project Folder Structure
```
wireshark-network-analysis-project/
│
├── README.md
├── pcap-files/
│   ├── normal_traffic.pcapng
│   ├── portscan_full_capture.pcapng
│   ├── portscan_syn_only.pcapng
│   ├── dns_anomaly.pcapng
│   └── dns_full_capture.pcapng
└── screenshots/
```

---

## 📌 10. How to Run This Project
1. Install Wireshark  
2. Load `.pcapng` files  
3. Use filters:
```
tcp.flags.syn==1 && tcp.flags.ack==0
dns
dns.flags.rcode != 0
```
4. Analyze streams  
5. Document findings  

---

## 📌 11. Conclusion
This project teaches SOC-level packet analysis and threat detection.  
Once FTP is added, it becomes a fully advanced network forensic project.

---

### Author: **Bhagya Dharennavar**
# Wireshark-network-analysis-project
