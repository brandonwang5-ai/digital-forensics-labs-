# Lab 5: Windows Live Analysis and Registry Forensics

## Overview

Microsoft Windows is the most widely used operating system in enterprise and personal computing environments. Because of its dominance in the global market, Windows systems are frequently encountered in digital forensic investigations.

Windows forensic analysis involves examining both **live system artifacts** and **disk-based evidence**, including the **Windows Registry**, **NTFS file system structures**, **user activity artifacts**, and **installed applications**.

In this lab, live forensic analysis was conducted on a **Windows Server 2019** system. Registry artifacts were examined using built-in Windows tools, and a forensic drive image was analyzed using **Paraben’s E3** to identify suspicious files, installed software, link files, and browser activity.

## Lab Objectives

Once completing this lab, I will have demonstrated the ability to: 

- **Perform live forensic analysis** using native Windows utilities  
- **Collect and interpret Windows Registry artifacts**  
- **Examine NTFS file system structures** using Paraben’s E3  
- **Analyze link (.lnk) files** to determine file access history  
- **Identify suspicious application installations**  
- **Investigate browser history and keyword artifacts**  
- **Conduct independent forensic analysis with minimal guidance**  

---

## Lab Environment

**Virtual Machine**
- vWorkstation (**Windows Server 2019**)

---

## Tools Used

- **Task Manager**
- **Resource Monitor**
- **Fsutil**
- **Registry Editor (regedit)**
- **Paraben’s E3**

---

## Section 1: Live Windows System Analysis

### Process Identification and Analysis

Task Manager was used to examine active processes and select one for further investigation.

![Process Properties Window](screenshots/Lab-5-SS1.png)
)

**Key Observations**
- Documented **Process ID (PID)**, memory usage, and executable path  
- Evaluated process legitimacy based on system location and behavior  

---

### Listening Ports Examination

Resource Monitor was used to identify processes with active listening ports.

![Listening Ports List](screenshots/Lab-5-SS2.png)

**Findings**
- Identified open ports and associated services  
- Correlated network bindings with specific running processes  

---

### C: Drive and USN Journal Analysis

The `fsutil` utility was used to gather information about the **C: drive** and inspect the **Update Sequence Number (USN) Journal**.

![C Drive Information](screenshots/Lab-5-SS3.png)

![USN Journal Information](screenshots/Lab-5-SS4.png)

**Findings**
- Confirmed NTFS configuration details  
- Verified the presence and operational status of the USN Journal  

---

### Windows Installation Timestamp

The Windows installation date was extracted and converted into a **human-readable format**.

![Windows Installation Timestamp](screenshots/Lab-5-SS5.png)

**Significance**
- Assists with **timeline reconstruction**  
- Establishes system age and investigative scope  

---

### Registry Analysis Using regedit

The Windows Registry was examined to identify configuration settings and user activity artifacts.

#### Default Network Interface

![Default Network Interface Key](screenshots/Lab-5-SS6.png)

**Significance**
- Identifies active network configuration  
- Useful in network attribution and system profiling  

---

#### Winlogon Key Values

![Winlogon Key Values](screenshots/Lab-5-SS7.png)

**Significance**
- Determines logon behavior and configured shell  
- Can reveal persistence mechanisms  

---

#### ShellBag Artifacts

![ShellBag Key Values](screenshots/Lab-5-SS8.png)

**Significance**
- Reveals historical folder browsing activity  
- Persists even if folders are deleted  

---

#### RecentDocs Artifacts

![RecentDocs Key Values](screenshots/Lab-5-SS9.png)

**Significance**
- Identifies recently opened documents  
- Assists in reconstructing user behavior  

---

## Section 2: Drive Image Analysis with Paraben’s E3

### Sorted File Analysis

Files were sorted within Paraben’s E3 to identify potentially suspicious artifacts.

![Sorted Files View](screenshots/Lab-5-SS10.png)

---

### Analysis of 777.jpg

The file `777.jpg` was examined using **Document View**.

![777.jpg Document View](screenshots/Lab-5-SS11.png)

**Findings**
- Reviewed file metadata and content  
- Determined relevance to investigation  

---

### Analysis of 777.lnk

The link file `777.lnk` was analyzed to extract original file path and metadata.

**Findings**
- Identified original file location  
- Reviewed access timestamps  
- Confirmed associated executable or document  

---

### Suspicious Application Installations

Installation files located in the **Downloads category** were examined for potentially suspicious applications.

![Suspicious Installation Files](screenshots/Lab-5-SS12.png)

---

### VPN Application Identification (Speedify)

The **Uninstall registry folder** was reviewed to identify installed applications, including **Speedify VPN**.

![Speedify Uninstall Entry](screenshots/Lab-5-SS13.png)

**Significance**
- VPN usage may indicate attempts to obscure IP address or network activity  

---

### User Account Enumeration

The system’s user accounts were examined.

![Users List](screenshots/Lab-5-SS14.png)

**Findings**
- Identified active and historical user accounts  
- Assisted in attributing activity  

---

### Beverly Gates Run Folder Analysis

The **Run folder** associated with Beverly Gates was analyzed for startup persistence entries.

![Beverly Gates Run Folder](screenshots/Lab-5-SS15.png)

**Significance**
- Run keys may indicate persistence mechanisms  
- Useful in identifying unauthorized startup programs  

---

### Browser History and Keyword Analysis

Browser artifacts were examined to identify suspicious activity.

**Findings**
- Identified browsing activity relevant to investigation  
- Detected suspicious search terms  

---

## Section 3: Independent Investigation and Artifact Analysis

### Suspicious File Examination

A suspicious file discovered during analysis was examined for malicious indicators.

![Suspicious File Contents](screenshots/Lab-5-SS16.png)

**Findings**
- Reviewed file contents and metadata  
- Assessed potential malicious characteristics  

---

### Registry Keys Associated with Tor and Firefox

Registry artifacts associated with **Tor** and **Mozilla Firefox** were identified and analyzed.

![Tor and Firefox Registry Key](screenshots/Lab-5-SS17.png)

**Significance**
- Tor artifacts may indicate anonymized browsing activity  
- Firefox registry entries assist in correlating user behavior  

---

## Summary and Key Takeaways

After working through this lab, it was truly amazing and such a great learning experience of how much useful evidence is actually embedded within normal activity on Windows. System components like the Registry, link files, and browser artifacts are proverbial treasure troves for historical data. 
By examining ShellBag and RecentDocs entries revealed the practical aspects of how investigators can use artifacts to reconstruct user behavior, even without malicious files obviously present. I was also enlightened about how registry keys such as Winlogon and network interface entries give context about system configs and user logins, both of which serve critical components in a digital forensic investigation.
Analyzing the drive image in E3 also connected the technical artifacts to reveal a broader narrative of events. Through sorting files, reviewing .Ink paths, and identifying suspicious browsing activity through analysis reveal how small traces across different system areas contribute to the larger picture and timeline. 
Overall, this lab strengthened my understanding and proficiency on Windows-specific artifacts and how it supports forensic investigations. Especially when combining live system analysis with offline disk image examinations. 

