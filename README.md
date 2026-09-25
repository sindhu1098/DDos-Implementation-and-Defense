# DDos-Implementation-and-Defense
B.Tech Capstone Project focusing on DNS Tunneling data exfiltration modeling and priority-queue based DDoS mitigation simulations.

# IMPLEMENTATION AND DEFENSE OF DDoS ATTACK

A Project Report submitted in partial fulfillment for the award of the degree of **Bachelor of Technology in Computer Science and Engineering** at **Presidency University, School of Engineering, Bengaluru** (May 2020).

## 👥 Authors & Guidance
*   **Team Members:** Nandini K, Sindhura, Anupam Anurag, Kruthika MB [1]
*   **University Project Guide:** Mr. Sanjeev P Kaulgud (Professor, Dept. of CSE) [1]
*   **External Project Guide:** Mr. Yogeen Honnawar (**Indian Space Research Organisation - ISRO**) [1, 0.7.2]
*   **HOD:** Dr. Mohan K G [1]
*   **Project Endorsement:** Fully certified bonafide work with an official completion certificate issued upon final submission [1, 0.7.2].

---

## 📄 Project Abstract
The Distributed Denial of Service (DDoS) attack is an active attack targeting system bandwidth and resources, causing severe damage to multimedia network services and Internet Service Providers (ISPs). Botnet attackers exploit vulnerabilities in protocols like the Domain Name System (DNS) to send garbage requests to servers. 

This paper analyzes packet flow behavior and implements a **priority queue-based algorithm** within the network simulator **NS2**. The algorithm categorizes incoming packet flows by assigning normal legitimate user packets to a high-priority queue and suspected attacker packets to a low-priority queue to maintain constant uptime for legitimate users during an active traffic spike.

---

## 🛠️ Experimental Setup & System Analysis
The project is built on a server-client model configured to test security vulnerabilities, malware-free intrusions, and traffic exfiltration over live network links.

### 💻 Software & Simulation Stack
*   **Network Simulator:** NS2 for simulating wired network configurations, botnets (zombies), UDP connections, and Constant Bit Rate (CBR) applications.
*   **Operating Systems:** Kali Linux (Attacker machine), Fedora Linux (DNS Server environment on Oracle VM VirtualBox), Windows 7, and Windows (Victim endpoints).
*   **Tunneling Frameworks:** Dnscat2 (utilized over PowerShell script pathways for file transfer simulation and client-server initialization).
*   **Analysis Tools:** Wireshark Packet Analyzer (for tracking random packet captures, traffic streams during active Chrome browsing sessions, and real-time network flow analysis).
*   **Defensive Rule-Based Firewalls:** Windows Defender Firewall with Advanced Security (Outbound Rules interface configuration).

### 📊 Threat Modeling & Indicators of Compromise (IoCs)
1. **The Attack Network Graph:** Structured as a Directed Acyclic Graph (DAG) using Bayesian network statistics to track path likelihood across four distinct states: `entry nodes`, `critical node` (\(n_{Cr}\)), `pivot nodes`, and `goal node` (\(n_G\) for DNS tunneling exfiltration).
2. **DNS Tunnel Traffic Signatures:** Isolated via Wireshark logs during active data transfer based on three anomalous patterns:
   * High traffic volume originating exclusively from a single IP address without any outside requests.
   * Exceptionally high number of hostnames per target domain.
   * Outbound traffic to the targeted domain completely dominating standard requests within the subnet.

---

## 🛡️ Mitigation Methodologies Tested

### 1. Priority Queue Allocation (NS2)
Packets are filtered automatically based on flow characteristics. Malicious state-exhaustion SYN floods, HTTP GET floods, and UDP/ICMP amplification requests are routed into low-priority buffers while standard user paths retain high-priority scheduling.

### 2. Manual Firewall Rule Enforcement (Windows Defender)
Real-time traffic flows were captured and monitored using Wireshark. Upon observing malicious volumetric spikes, defensive mitigation was applied by setting custom block actions inside Windows Defender Firewall Outbound Rules to isolate target attacker IP addresses (e.g., `192.168.29.1`).

---

## 📚 References & Bibliography

[1] Aaron Zimba, Zhaoshun Wang, "Malware-Free Intrusions: Exploitation of Built-in Pre-Authentication Services for APT Attack Vectors", International Journal of Computer Network and Information Security (IJCNIS), Vol.9, No.7, pp.1-10, 2017. DOI: 10.5815/ijcnis.2017.07.01 [1]

[2] Kao, Da-Yu. "Performing an APT Investigation: Using People-Process-Technology-Strategy Model in Digital Triage Forensics." In Computer Software and Applications Conference (COMPSAC), 2015 IEEE 39th Annual, vol. 3, pp. 47-52. IEEE, 2015. [1]

[3] Zhou, Y., Li, Q.S., Miao, Q. and Yim, K., 2013. DGA-Based Botnet Detection Using DNS Traffic. J. Internet Serv. Inf. Secur., 3(3/4), pp.116-123 [1]

[4] Arun Raj P. Kumar and S. Selvakumar, "Distributed Denial of Service (DDoS) Threat in Collaborative Environment-A Survey on DDoS Attack Tools and Traceback Mechanisms", International Advance Computing Conference (IACC 2009), pp. 1275-1280, March 2009. [1]

[5] Poongothai Sathyakala, "Simulation and Analysis of DDoS Attacks", International Conference on Emerging Trends in Science Engineering and Technology, pp. 78-85, 2012. [1]

[6] P.J. Criscuolo, "Distributed Denial of Service Trinoo Tribe Flood Network Tribe Flood Network 2000 and Stacheldraht CIAC-2319" in, Department of Energy Computer Incident Advisory (CIAC), Rev., Lawrence Livermore National Laboratory, February 2000. [1]

[7] J. Ahmed, H. H. Gharakheili, Q. Raza, C. Russell and V. Sivaraman, "Monitoring Enterprise DNS Queries for Detecting Data Exfiltration From Internal Hosts," in IEEE Transactions on Network and Service Management, vol. 17, no. 1, pp. 265-279, March 2020. doi: 10.1109/TNSM.2020.2965258.

[8] A. Almusawi and H. Amintoosi, "DNS Tunneling Detection Method Based on Multilabel Support Vector Machine," Security and Communication Networks, vol. 2018, Article ID 6137098, 2018. doi: 10.1155/2018/6137098.

[9] R. Burton, "Unsupervised Learning Techniques for Malware Characterization: Understanding Certain DNS-Based DDoS Attacks," ACM Digital Threats: Research and Practice, vol. 1, no. 3, pp. 1–24, 2020. doi: 10.1145/3391261.

[10] S. Gao, Z. Li, Y. Yao, B. Xiao, S. Guo, and Y. Yang, "Software-Defined Firewall: Enabling Malware Traffic Detection and Programmable Security Control," in Proceedings of the ACM Asia Conference on Computer and Communications Security (ASIACCS), New York, NY, USA, 2018, pp. 413–424. doi: 10.1145/3196494.3196524.

[11] A. Praseed and P. S. Thilagam, "Multiplexed Asymmetric Attacks: Next-Generation DDoS on HTTP/2 Servers," IEEE Transactions on Information Forensics and Security, vol. 15, pp. 1790–1800, 2020. doi: 10.1109/TIFS.2019.2950121.

