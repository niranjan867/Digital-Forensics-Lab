<div align="center">

<img src="https://img.shields.io/badge/Autopsy-Case%20Analysis-1679A7?logo=databricks&logoColor=white&style=for-the-badge" alt="Autopsy Case Analysis">

# EX. NO. 05

## Case Creation and Evidence Import Using Autopsy

</div>

---

## 🎯 Aim

To create a forensic case in Autopsy, import a disk-image evidence source, configure ingest modules, examine forensic artifacts, and generate a forensic report.

---

## 🛠️ Software and Tools

| Requirement | Details |
| ----------- | ------- |
| Operating system | Windows |
| Forensic tool | Autopsy |
| Evidence type | Disk image |
| Image format | E01 |
| Data-source type | Disk Image or VM File |
| Output | Forensic analysis report |

---

## 📚 Theory

Autopsy is a digital-forensics platform used to create cases, process forensic evidence, and examine artifacts recovered from disk images.

A forensic case stores investigation information, evidence-source details, ingest results, analysis findings, and generated reports in one case environment.

A disk image is a bit-by-bit copy of a storage device. The E01 format may contain multiple image segments. All segments must be kept in the same directory so that Autopsy can process the complete evidence source.

Autopsy uses ingest modules to identify and organize useful forensic artifacts. These artifacts may include file types, deleted files, operating-system information, web activity, e-mail, file hashes, encryption indicators, and other analysis results.

The case report should be generated after ingest processing has completed to ensure that the report contains the available analysis results.

---

## 🗂️ Case Creation

### Step 1: Open Autopsy

Open Autopsy and select the option to create a new case.

### Step 2: Enter Case Information

Enter the required case name, case number, examiner information, and case directory.

Select the **Single-user** case option when working on an individual laboratory system.

---

## 💽 Evidence Import

### Step 1: Add the Data Source

Select **Add Data Source** and choose:

```text
Disk Image or VM File
```

### Step 2: Select the Evidence Image

Select the first segment of the forensic disk image.

If the image contains additional segments, such as E02, E03, or E04, keep all segments in the same directory.

### Step 3: Configure the Time Zone

Select the appropriate time zone for the investigation.

Correct time-zone selection is important when interpreting file timestamps, browser activity, and other time-based artifacts.

---

## ⚙️ Ingest Configuration

Select the required ingest modules for evidence processing. Common modules include:

- Recent Activity.
- Hash Lookup.
- File Type Identification.
- Extension Mismatch Detector.
- Embedded File Extractor.
- Picture Analyzer.
- Keyword Search.
- E-mail Parser.
- Encryption Detection.
- Interesting Files Identifier.

Start the ingest process and wait until the analysis services have completed.

---

## 🔍 Evidence Examination

The following areas can be examined in Autopsy:

| Category | Examples |
| -------- | -------- |
| File analysis | File types, file size, file paths, and timestamps |
| Deleted content | Deleted files and deleted-file categories |
| Data artifacts | Artifacts extracted from the evidence image |
| Operating system | System information and user activity |
| Recent activity | Recent documents and executed programs |
| External devices | USB devices connected to the system |
| Web activity | Bookmarks, cookies, history, and searches |
| E-mail | E-mail-related artifacts |
| Analysis results | Results produced by the ingest modules |
| Image analysis | File metadata, hash values, and preview |

Autopsy can display the file name, path, type, size, timestamps, allocation status, cryptographic hashes, and preview of selected files.

---

## 📄 Report Generation

### Step 1: Generate the Report

Select the report-generation option in Autopsy after ingest processing has completed.

### Step 2: Select the Report Format

Choose the required report format, such as PDF, and select the required report modules or result types.

### Step 3: Export the Report

Save the generated report in a suitable forensic-report directory.

The exported report contains case information, evidence-source details, Autopsy information, and the artifacts identified during processing.

---

## 📊 Observations and Results

| Field | Result |
| ----- | ------ |
| Case creation | Successful |
| Evidence-source import | Successful |
| Ingest-module configuration | Completed |
| Evidence processing | Completed or started successfully |
| File-type analysis | Available |
| Deleted-file analysis | Available |
| Web-artifact analysis | Available |
| Operating-system analysis | Available |
| Image-file examination | Completed |
| Forensic report generation | Successful |

### Observations

* A forensic case was created successfully in Autopsy.
* A disk-image evidence source was imported into the case.
* Multiple ingest modules were selected for artifact processing.
* File types, deleted files, data artifacts, and operating-system information were examined.
* Web activity, recent activity, and external-device artifacts were available for analysis.
* File metadata, hash values, and previews could be examined.
* A forensic report was generated and viewed successfully.

---

## ⚠️ Limitation

If a report is generated before ingest services have completed, some analysis results may not be included. The final report should therefore be generated after all required ingest modules show a completed status.

Original evidence images and complete case databases should not be shared publicly because they may contain sensitive forensic information.

---

## 📌 Conclusion

This experiment demonstrated how Autopsy can be used to create a forensic case, import a disk-image evidence source, configure ingest modules, and examine digital artifacts.

File metadata, deleted files, operating-system information, web activity, recent activity, and other forensic results were analyzed. A forensic report was generated and viewed successfully, completing the practical exercise.

---

<div align="center">

**Digital Forensics Laboratory**

213CSE4307 - DIGITAL FORENSICS

</div>
