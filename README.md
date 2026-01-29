# Safe Malware Analysis with VirusTotal (EICAR test file)

**Author:** Mihira Seru
**Description:** Independent research on detecting safe test files (EICAR) using VirusTotal.
**Date:** November 2025

---
## Overview
---

This project demonstrates how to safely perform a basic malware analysis using the **EICAR test file** inside a **virtual machine (VM)** and analyze it using **VirusTotal**.

The goal of this lab is to help beginners understand:
- How antivirus engines detect known signatures
- How SOC analysts use VirusTotal to triage suspicious files
- How to safely handle malware-related experiments without using real malware

> This project does not involve real malware. The EICAR test file is a globally accepted **antivirus test file**.

---
## Lab Environment 
---

- **Virtualization:** Oracle VirtualBox
- **Guest OS:** Ubuntu
- **Tools used:**
    - VirusTotal
    - Nano (text editor)

---
## Why the EICAR test file?
---

The **EICAR (European Institute for Computer Antivirus Research) test file** is a harmless string designed to trigger antivirus alerts.

It is commonly used to:
- Test antivirus detection mechanisms
-  Demonstrate signature based detection
-  Practice malware analysis workflows

without exposing systems to real malware.

---
## Lab Setup
---

The analysis was carried out inside an Ubuntu virtual machine to ensure the testing environment remained isolated and safe. Before starting the experiment, a clean snapshot of the virtual machine was created using VirtualBox. This snapshot acts as a recovery point, allowing the system to be restored if anything goes wrong during testing.

Snapshots are especially useful in malware-related labs because they remove all changes made after the snapshot, making it easy to reset the environment for future experiments.

---
## Creating the EICAR test file
---

To simulate malware detection without using real malware, the EICAR test file was used. This file is a standard, trusted test sample designed specifically to trigger antivirus alerts while remaining completely harmless.

Inside the virtual machine, a file named `EICAR.com` was created using the nano text editor. The official EICAR test string was added to the file and saved. The file’s presence was then verified from the terminal to confirm that the test sample had been created successfully.

---
## Uploading the File to VirusTotal
---

The `EICAR.com` file was uploaded to VirusTotal from within the virtual machine. VirusTotal is an online service that scans files using multiple antivirus engines and provides a consolidated view of detection results.

Uploading the test file allows observation of how different antivirus vendors identify the same sample in real time.

> This step was performed only inside an isolated virtual machine.  
Although harmless, the EICAR file may still trigger antivirus alerts.

---
## Analysis of VirusTotal Results
---

### Detection Overview

VirusTotal reported 61 out of 68 detections, showing that most antivirus engines successfully recognized the EICAR signature. This confirms that signature-based detection is working as expected.

The Community Score also indicates that the file is widely known and recognized as a test sample.

### Popular Threat Label

The file was labeled as `virus.eicar/test`, which confirms that it is an antivirus test file and not real malware. Many vendors clearly identify it as a test artifact using labels such as EICAR-Test-NOT Virus.

### Vendor Analysis

Each antivirus vendor displays its own detection name for the file. While the naming conventions vary, all results consistently classify the file as a test file rather than a real threat.

### Details Tab

The Details tab provides technical information such as cryptographic hash values, file size, file type, and analysis timestamps. This information is commonly used by analysts to verify file identity and integrity.

### Relations Tab

The Relations tab shows any linked files, URLs, or artifacts. Since the EICAR file does not perform any actions, this section contains little or no related data.

### Behaviour Tab

The Behaviour tab displays sandbox execution activity. As expected, no behavior is observed for the EICAR test file because it is non-functional.

### Community Tab

The Community tab contains comments and feedback from other users, further confirming that the file is a well-known antivirus test sample.

---
## Post-Analysis Cleanup
---

After completing the analysis, the test file was optionally removed from the virtual machine. The system was then restored to the clean snapshot to remove all traces of the experiment and prepare the environment for future testing.

---
## Key Takeaways
---

- Understood how antivirus engines use signature-based detection  
- Learned how VirusTotal is used for initial file analysis in SOC workflows  
- Practiced safe malware analysis using an isolated virtual environment
