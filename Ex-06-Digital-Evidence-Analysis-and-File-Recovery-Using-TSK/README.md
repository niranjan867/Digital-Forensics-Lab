<div align="center">

<img src="https://img.shields.io/badge/The%20Sleuth%20Kit-Digital%20Forensics-1679A7?style=for-the-badge" alt="The Sleuth Kit">

# EX. NO. 06

## Digital Evidence Analysis and File Recovery Using The Sleuth Kit

</div>

---

## 🎯 Aim

To perform forensic analysis of a disk image using The Sleuth Kit, examine file-system structures and metadata, identify deleted files, recover deleted data, and generate information for forensic timeline analysis.

---

## 🛠️ Software and Tools

| Requirement | Details |
| ----------- | ------- |
| Operating System | Windows |
| Forensic Tool | The Sleuth Kit |
| Evidence Type | Forensic disk image |
| File System | NTFS |
| Analysis Type | Disk and file-system analysis |
| Output | Recovered files and forensic analysis data |

### TSK Utilities Used

| Utility | Purpose |
| ------- | ------- |
| `mmls` | Analyzes partition structures and layouts |
| `fsstat` | Displays file-system information |
| `fls` | Lists files, directories, and deleted entries |
| `istat` | Displays metadata and timestamp information |
| `icat` | Extracts file contents from forensic images |
| `mactime` | Converts body-file information into a forensic timeline |

---

## 📚 Theory

The Sleuth Kit (TSK) is an open-source collection of command-line tools used for digital forensic investigation of disk images and file systems.

TSK allows investigators to examine storage media while preserving the original evidence. It provides utilities for analyzing partitions, identifying file-system structures, locating deleted files, examining metadata, recovering file contents, and supporting forensic timeline analysis.

The general forensic workflow is:

**Disk Image → Partition Analysis → File-System Analysis → File Identification → Metadata Analysis → File Recovery → Timeline Analysis**

### Partition Analysis

The `mmls` utility is used to identify partitions within a disk image and determine their starting offsets.

### File-System Analysis

The `fsstat` utility provides detailed information about the file system, including its structure and configuration.

### File Identification

The `fls` utility lists files and directories contained within a file system. It can also identify deleted file entries.

### Metadata Analysis

The `istat` utility examines file-system metadata and provides information such as file attributes and timestamps.

### File Recovery

The `icat` utility extracts file contents associated with a particular metadata entry from the forensic image.

### Timeline Analysis

The `fls` utility can generate a machine-readable body file containing file-system timestamp information. This information can be further processed using `mactime` to support forensic timeline analysis.

---

## ⚙️ Procedure

### Step 1: Verify The Sleuth Kit

Open the command-line environment and navigate to the directory containing the TSK utilities.

Verify that The Sleuth Kit is installed correctly and check its version.

```text
fls -V
````

---

### Step 2: Analyze the Partition Structure

Use `mmls` to examine the partition layout of the forensic disk image.

```text
mmls <disk-image>
```

Identify the partition structure and determine the appropriate partition offset for further analysis.

---

### Step 3: Examine the File System

Use `fsstat` to obtain information about the file system.

```text
fsstat -o <offset> <disk-image>
```

Examine details such as:

* File-system type
* Volume information
* Sector size
* Cluster information
* File-system structure

---

### Step 4: Identify Files and Deleted Entries

Use `fls` to list files and directories recursively.

```text
fls -o <offset> -r <disk-image>
```

Search the generated file listing to identify deleted files or other relevant evidence.

---

### Step 5: Analyze File Metadata

Use `istat` to examine the metadata associated with a selected file entry.

```text
istat -o <offset> <disk-image> <metadata-address>
```

Review the available metadata and timestamp information.

---

### Step 6: Recover Deleted Data

Use `icat` to extract the contents associated with a selected metadata entry.

```text
icat -o <offset> <disk-image> <metadata-address> > recovered_file
```

Verify that the recovered file has been successfully created.

---

### Step 7: Generate a Forensic Body File

Generate a machine-readable body file using `fls`.

```text
fls -o <offset> -m / -r <disk-image> > body.txt
```

The generated body file can be examined and used for further forensic timeline analysis.

If available, `mactime` can be used to convert the body-file information into a human-readable timeline.

---

### Observations

* The Sleuth Kit provides multiple utilities for disk-image investigation.
* Partition information can be examined using `mmls`.
* File-system details can be obtained using `fsstat`.
* Deleted files can be identified using `fls`.
* Metadata and timestamps can be examined using `istat`.
* File contents can be recovered using `icat`.
* Machine-readable forensic timeline information can be generated using `fls`.
* The generated body file can be processed for further timeline analysis.

---

## ⚠️ Limitation

The effectiveness of deleted-file recovery depends on the condition of the file system and the availability of the required file data.

Some deleted files may be partially overwritten or corrupted and may not be completely recoverable.

Timeline generation also depends on the availability and compatibility of the required forensic utilities.

---

## 📌 Conclusion

This experiment demonstrates the use of The Sleuth Kit for forensic disk-image and file-system analysis.

The experiment covers partition analysis, file-system examination, deleted-file identification, metadata analysis, file recovery, and forensic timeline preparation. These techniques provide useful capabilities for examining and recovering digital evidence during forensic investigations.

---

<div align="center">

**Digital Forensics Laboratory**

213CSE4307 - DIGITAL FORENSICS

</div>
```
