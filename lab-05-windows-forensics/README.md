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
