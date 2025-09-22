# Cyber Security Internship – Task 1  
**Scan Your Local Network for Open Ports**  

---

## 📌 Objective  
Learn to discover open ports on devices in your local network to understand network exposure.  

---

## 🛠️ Tools Used  
- Nmap   

---

## 📖 Steps Followed  
1. Installed Nmap.  
2. Found my local IP range (e.g., `192.168.1.0/24`).  
3. Performed TCP SYN scan:  
   ```bash
   nmap -sS 192.168.1.0/24

Noted down IP addresses and open ports.

Researched common services on those ports.

Identified possible security risks.

Saved results.

📊 Results

IP addresses detected:

192.168.29.97

Open ports identified:

PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
3306/tcp open  mysql
6646/tcp open  unknown

🔒 Risks Identified

135 (RPC):** remote code execution if unpatched.  
139/445 (NetBIOS/SMB):** data exposure, ransomware/SMB exploits.  
3306 (MySQL):** unauthorized DB access if weak creds/exposed.  
6646 (Unknown):** possible unpatched/custom service — needs enumeration.

✅ Possible Security Measures

Patch OS/services.  
Close/restrict unnecessary ports via firewall.  
Disable SMBv1; harden share permissions.  
Bind DB to localhost or restrict access; use strong passwords and TLS.  
Segment network and enable logging/IDS.  
Re-scan after fixes.

❓ Interview Questions & Answers

1. What is an open port?
A port that accepts incoming connections.

2. How does Nmap perform a TCP SYN scan?
It sends SYN packets and waits for SYN-ACK responses without completing the handshake.

3. What risks are associated with open ports?
Unauthorized access, exploitation of vulnerabilities, data breaches

4. Explain the difference between TCP and UDP scanning.
TCP scanning requires connection attempts, while UDP scanning checks connectionless services.

5. How can open ports be secured?
Disable unused ports, enable firewalls, and patch services

6. What is a firewall’s role regarding ports?
It filters incoming/outgoing traffic and blocks unwanted ports

7. What is a port scan and why do attackers perform it?
A technique to discover open ports/services; attackers use it for reconnaissance.

8. How does Wireshark complement port scanning?
It captures and analyzes packets to verify scan activity and detect anomalies.

📂 Repository Structure
├── results/
│   ├── tcp-syn-scan.txt
├── README.md
