# Digital-Forensic-Investigation
**Project: Forensic Examination of Digital Media (ACE Sailboats Case)**
In this project, I performed a forensically sound examination of a USB disk image to identify proprietary assets and determine timelines of use. By utilizing Autopsy and FTK Imager, I indexed over 2,500 files and recovered deleted artifacts, specifically focusing on images modified between April 2006 and January 2007. Investigate the USB to find if suspect has been involved in illicit or against company policy. This project demonstrates the ability to maintain evidence integrity and perform targeted data recovery in a corporate investigation context.

## Technical Implementation

### 1. Evidence Acquisition & Environment
* **Environment:** Configured a virtualized testing environment using **VMware** to isolate the forensic tools and the target disk image.
* **Imaging:** Performed a bit-by-bit physical image of the USB media using **FTK Imager**. I chose the **Raw (dd)** format to ensure the capture of unallocated space and deleted file headers.

### 2. Forensic Analysis
* **Tool:** Utilized **Autopsy** & **OSForensics** for deep-dive artifact analysis.

**Forensic Findings & Evidence Analysis**
* **File System Exploration:** Navigated the **Tree Viewer** to filter files by extension (.JPG) and analyzed the **Result Viewer Pane** to establish a timeline based on **Modified Time** (focusing on the April 2006 – Jan 2007 window).
* **Cross-Platform Artifacts:** Identified `.Spotlight-V100` folders, providing evidence that the media was used on a Macintosh device, despite being a Windows-formatted drive.
* 
1. Unauthorized System Manipulation (Host: Terry’s Personal Computer)
Operating System: Windows (confirmed via Command Line Interface (CLI) screen captures).

Volatile Data Acquisition: Recovered artifacts indicate the subject performed an unauthorized Physical Memory Dump (509.9MB) via the CLI. This suggests an intent to harvest sensitive data from RAM, such as active credentials or encryption keys.

Privilege Escalation: Forensic images reveal active manipulation of Windows Computer Management, specifically the unauthorized activation of the "Guest" account and modifications to administrative password configurations.

2. Insider Threat & Network Staging
Data Staging: Evidence of persistent Network Drive Mapping to a remote shared folder (IP: 192.166.1.1). This indicates a designated location for staging tools or exfiltrating proprietary data.

Unauthorized Access: Screen captures provide evidence of the subject successfully accessing a secondary workstation ("Pat’s Computer") via the network.

3. Advanced Tooling & Automation
Malicious Software: Discovered an Advanced Keylogger (Binary modified: 12/03/2009). This tool was utilized for covert surveillance, including keystroke logging and screen recording of corporate activities.

Forensic Automation Script: Recovered a custom Python-based automation suite designed to interact with browser sessions via a Telnet bridge (Port 4242). This script was used to systematically extract URL history and session data from multiple third-party organizations.

Cross-Platform Activity: The presence of macOS-specific system artifacts (.Spotlight-V100) on a Windows-formatted USB drive confirms cross-platform media usage. This pattern is often associated with obfuscating data movement across different operating systems.
