<div align="center">

<img src="https://img.shields.io/badge/Process%20Explorer-Process%20Analysis-1679A7?style=for-the-badge" alt="Process Explorer">

# EX. NO. 09

## Identifying Suspicious Processes Using Sysinternals Process Explorer

</div>

---

## 🎯 Aim

To examine active Windows processes using Sysinternals Process Explorer and analyze process hierarchy, executable properties, digital signatures, execution paths, thread information, and security indicators for identifying potentially suspicious processes.

---

## 🛠️ Software and Tools

| Requirement | Details |
| ----------- | ------- |
| Operating System | Windows |
| Forensic Tool | Sysinternals Process Explorer |
| Executable | `procexp64.exe` |
| Execution Privilege | Administrator |
| Threat Intelligence | VirusTotal |
| Security Tool | Windows Security / Microsoft Defender |
| Evidence Type | Active system processes |

### Utilities / Components Used

- **Process Explorer** – Used to monitor and examine active processes.
- **Process Properties** – Used to inspect executable and security information.
- **Thread Analysis** – Used to examine process execution details.
- **VirusTotal** – Used for threat-intelligence verification.
- **Windows Security** – Used to verify system security status.

---

## 📚 Theory

Process Explorer is an advanced Windows process-monitoring utility from Microsoft Sysinternals. It provides detailed information about running processes and displays them in a hierarchical parent-child process structure.

It provides information such as Process ID, CPU usage, memory usage, process description, company name, executable path, and process properties.

Potentially suspicious processes can be investigated by examining:

- Process hierarchy and parent-child relationships
- Process names and descriptions
- Company and publisher information
- Digital signatures
- Executable paths
- Resource usage
- Thread information
- Network activity
- Threat-intelligence information

The general investigation workflow is:

**Process Enumeration → Process Hierarchy → Process Properties → Signature Verification → Path Analysis → Thread Analysis → Threat Intelligence → Security Verification**

---

## ⚙️ Procedure

### Step 1: Launch Process Explorer

Open Process Explorer with administrator privileges.

The main interface displays active processes along with their Process IDs, resource usage, descriptions, and company information.

**Figure 1: Process Explorer interface displaying active Windows processes.**

---

### Step 2: Examine the Process Hierarchy

Examine the process tree to understand the parent-child relationships between running processes.

The hierarchical structure provides useful information about process creation and execution relationships.

**Figure 2: Process Explorer displaying the hierarchical parent-child process structure.**

---

### Step 3: Examine Process Properties

Select a process and open its **Properties** window.

Examine the available executable information, including description, path, command line, user information, and other process details.

**Figure 3: Process Properties window displaying executable and process information.**

---

### Step 4: Verify Digital Signature

Examine the selected process for publisher and digital-signature information.

Digital-signature verification helps determine whether an executable is associated with a trusted software publisher.

**Figure 4: Verification of the digital signature and publisher information of the selected process.**

---

### Step 5: Verify Execution Path

Examine the executable path of the selected process.

Unexpected or unusual executable locations may require additional investigation.

**Figure 5: Verification of the executable path of the selected process.**

---

### Step 6: Examine Thread Information

Open the Threads section of the Process Properties window.

Examine available information such as thread identifiers, CPU activity, start addresses, and execution state.

**Figure 6: Thread information associated with the selected process.**

---

### Step 7: Perform Threat-Intelligence Verification

Use VirusTotal to obtain additional security information about the selected executable.

Review the available detection information to determine whether security vendors have identified the executable as potentially malicious.

**Figure 7: VirusTotal threat-intelligence analysis of the selected executable.**

---

### Step 8: Verify System Security Status

Open Windows Security and examine the current virus and threat-protection status.

Review the available protection and scan information.

**Figure 8: Windows Security displaying the system's virus and threat-protection status.**

---

### Step 9: Security Response

If a process is confirmed to be malicious after proper investigation, Process Explorer can be used to suspend or terminate the process.

The source executable should only be removed after appropriate verification and authorization.

A security scan should be performed using Windows Defender or another trusted anti-malware solution after containment.

---

## 📊 Observations and Results

- Process Explorer provided a detailed view of active Windows processes.
- The process hierarchy allowed parent-child relationships to be examined.
- Process Properties provided executable and security information.
- Digital signatures could be examined for process verification.
- Executable paths could be inspected for unusual locations.
- Thread information provided additional details about process execution.
- Threat-intelligence verification provided additional information about executable reputation.
- Windows Security provided information about the system's current threat-protection status.

---

## ⚠️ Limitation

Process Explorer provides process-level information but cannot by itself conclusively determine whether a process is malicious.

Additional forensic analysis, threat-intelligence sources, and security scanning may be required before taking containment or removal actions.

---

## 📌 Conclusion

The experiment demonstrated the use of Sysinternals Process Explorer for monitoring and examining active Windows processes.

Process hierarchy, process properties, digital signatures, execution paths, thread information, threat-intelligence results, and system security status were examined as part of the process-investigation workflow.

---

## 📋 Rubrics

| Criteria | Marks Allotted | Marks Awarded |
| -------- | -------------- | ------------- |
| GitHub Activity & Submission Regularity | 3 | |
| Application of Forensic Tools & Practical Execution | 3 | |
| Documentation & Reporting | 2 | |
| Engagement, Problem-Solving & Team Collaboration | 2 | |
| **Total** | **10** | |

---

## ✅ Result

The experiment successfully demonstrated the use of Sysinternals Process Explorer for examining active processes, process hierarchy, executable properties, digital signatures, execution paths, thread information, and security indicators. The observations were documented through the corresponding figures.

---

<div align="center">

**Digital Forensics Laboratory**

213CSE4307 - DIGITAL FORENSICS

</div>