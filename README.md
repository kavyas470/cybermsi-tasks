# cybermsi-tasks

Port Scanning Task – Cybersecurity Internship

 Task Objective
Perform a network reconnaissance exercise using **Nmap** to identify open ports on devices within the local network, understand service exposure, and analyze potential risks.



 Tools Used
- **Nmap** – For TCP SYN scanning of the local IP range
- *(Optional)* **Wireshark** – For packet inspection and deeper analysis



 Steps Performed

1. Installed Nmap from the official site.
2. Identified the local IP address using `ipconfig`.
3. Determined the subnet as `192.168.1.0/24`.
4. Ran the Nmap TCP SYN scan:
   ```bash
   nmap -sS 192.168.1.0/24
Scan Summary: 

Open Ports Identified:

135

139

445

902

912

1521

3306

7070

16992

Open Ports and Their Descriptions
1. Port 135 (msrpc)
Used by Microsoft RPC (Remote Procedure Call) services. Often exploited in Windows environments for lateral movement and remote code execution. Notably targeted by malware like WannaCry.

2. Port 139 (netbios-ssn)
Part of the NetBIOS protocol suite used for file and printer sharing in Windows networks. Exposing this port can allow attackers to enumerate shares, users, and attempt unauthorized access.

3. Port 445 (microsoft-ds)
Supports SMB (Server Message Block) over TCP/IP. This port is a common target for exploits such as EternalBlue, which led to global ransomware outbreaks. Should never be exposed to the internet.

4. Port 902 (VMware)
Typically used for VMware remote management. If not secured properly, it may allow unauthorized control of virtual machines.

5. Port 912 (apex-mesh)
May be related to custom or enterprise software. Unknown ports should always be investigated, especially if not intentionally deployed.

6. Port 1521 (oracle)
Default port for Oracle Database. An exposed Oracle service can be brute-forced or exploited if it has known vulnerabilities or default credentials.

7. Port 3306 (mysql)
Default MySQL database port. Databases exposed without proper authentication and encryption can leak sensitive data or be used in SQL injection attacks.

8. Port 7070 (realserver)
Often used by RealAudio streaming servers. These are typically outdated and can be vulnerable to remote code execution or buffer overflow attacks.

9. Port 16992 (amt-soap-http)
Used by Intel AMT (Active Management Technology). If AMT is enabled and misconfigured, attackers can remotely access the system even when it's powered off.
