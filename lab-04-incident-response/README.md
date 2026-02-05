# Lab 04 - Incident Response Investigation

## Overview

Digital forensic procedures serve as a crucial integration with incident response (IR) investigations. IR is an organized approach to managing and addressing the aftermath of a security breach or incident of a cyberattack, and has the objective of limiting damage, reducing recovery time, and minimizing operational and financial impact.

An effective incident response process consists of six core phases
1. **Preparation**
2. **Detection**
3. **Analysis**
4. **Containment**
5. **Eradication and Recovery**
6. **Post-Incident Activity**

While these phases are described sequentially, oftentimes in the real world overlap exists between the Detection, Analysis, and Containment phases as they often inform one another. 
This specific lab focuses primarily on the **Analysis phase** of the incident response lifecycle. Forensic examination of the network traffic and disk-based artifacts were carried out, evidence collected, correlated, and documented to determine the nature and scope of the incident. 

## Incident Response Context

During the Analysis phase, investigators often collect and examine evidence such as
- Network traffic captures
- Disk images
- Log Files
- Running processes and system artifacts

The goal of this lab is to reconstruct the actions of the threat actor, identify the root cause of the incident, gather evidence against the threat actor, and establish a timeline starting from the initial compromise through detection.

In this lab, forensic analysis was performed on both a PCAP file and a disk image, and the findings were documented in an incident response report that continue to evolve as new evidence was discovered. 

## Lab Structure

The lab consisted of 3 sections, progressing from guided analysis to independent investigation:

### Section 1: Guided Investigation 
- Analyzed a PCAP file captured during a suspected security incident
- Identified relevant forensic artifacts related to malicious activity
- Prepared an initial incident response report documenting findings

### Section 2: Expanded Analysis 
- Analyzed additional forensic evidence with less procedural guidance
- Correlated artifacts across multiple sources
- Updated the incident response report to reflect new findings and conclusions

### Section 3: Independent Investigation
- Explored the virtual environment without step-by-step instructions
- Answered investigative questions based on observed evidence
- Applied learned techniques in a manner consistent with real-world incident response scenarios

## Learning Objectives
The following skills were demonstrated upon completion of the lab: 
- Performing forensic analysis as part of an incident response investigation
- Conducting network forensic analysis on PCAP files using **NetWitness Investigator**
- Conducting disk forensic analysis using **Paraben’s E3**
- Correlating evidence from multiple sources to develop a cohesive case
- Producing a structured incident response report to document findings and conclusions

## Environment and Topology
The lab consisted of a the following virtual machine: **vWorkstation** Windows server 2019 

## Tools used
- **NetWitness Investigator** – Network traffic and PCAP analysis
- **Paraben’s E3** – Disk image and artifact analysis

## Evidence and Deliverables

### Section 1 Evidence
- Network time graph analysis
- Detailed review of a specific session timestamped *2021-07-13 15:33:00*
- Email containing FTP credentials with associated timestamps
- Initial incident response report

### Section 2 Evidence
- Emails directing installation of a keylogger
- Registry key values associated with the keylogger and related services
- Scheduled task metadata, including author and creation date
- Identification of keylogger executable location and inbound communication port
- Determination of keylogger execution timeline and user interaction
- Updated incident response report reflecting expanded findings

### Section 3 Evidence
- Identification of exfiltrated files within an Outlook database
- Email containing instructions for installing additional spyware


## Key Takeaways and Real-World Relevance

Lab closely mirrors real-world incident response investigations by requiring:
- Evidence collection from multiple forensic sources
- Correlation of host based and network artifacts
- Continuous reporting as new information emerges
- Analytical reasoning to differentiate valid user activity from malicious behavior

This experience reinforces the importance of structured documentation, evidence integrity, and clear communication during incident response activities, specifically in scenarios that may require legal or executive review. 


## Supporting Evidence

### Data Exfiltration Evidence



