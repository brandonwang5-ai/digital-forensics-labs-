# Lab 9: Network Forensics and Packet Analysis

## Overview

Network forensics involves the investigation of **network traffic patterns** and data captured in transit between computing devices. These techniques provide insight into the **source, scope, and methodology of attacks**, while supplementing traditional host-based forensic investigations.

With the rapid shift to remote work and the exponential rise in ransomware, breaches, and other cyber incidents, the importance of **network forensic analysis** has increased significantly. Organizations rely on network monitoring and packet analysis to detect anomalous behavior, reconstruct communication streams, and strengthen security controls.

Network forensics serves two primary purposes:

- **Monitoring networks for anomalous traffic and intrusions** as part of a security operations program  
- **Analyzing captured traffic to reconstruct files and communication streams**, often for investigative or law enforcement purposes  

In this lab, network traffic was captured and analyzed using **Wireshark**, and forensic evidence was collected directly from **routers and a firewall** in a multi-device virtual environment.

---

## Lab Objectives

Upon completing this lab, I demonstrated the ability to:

- **Perform packet capture** using Wireshark  
- **Conduct packet analysis** using protocol and field filters  
- **Analyze router configurations for forensic evidence**  
- **Examine firewall logs for suspicious activity**  
- **Identify and interpret suspicious network traffic**  
- **Reassemble transmitted files from captured packets**  

---

## Lab Environment

**Virtual Machines**

- vWorkstation (**Windows Server 2019**)  
- router1 (**Ubuntu 16**)  
- router2 (**Ubuntu 16**)  
- router3 (**Ubuntu 16**)  
- pfSense (**FreeBSD 2.4**)  
- AttackLinux01 (**Kali Linux**)  

---

## Tools Used

- **Wireshark**
- **PuTTY**
- **Quagga**
- **pfSense**

---
