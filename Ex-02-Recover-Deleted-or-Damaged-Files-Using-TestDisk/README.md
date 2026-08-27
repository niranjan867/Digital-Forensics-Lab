<div align="center">

<img src="https://img.shields.io/badge/TestDisk-Data%20Recovery-1679A7?logo=databricks&logoColor=white&style=for-the-badge" alt="TestDisk Data Recovery">

# EX. NO. 02

## Recover Deleted or Damaged Files from a Storage Device Using TestDisk

</div>

---

## 🎯 Aim

To recover deleted files or damaged partition data from an authorized storage device using TestDisk.

---

## 🛠️ Software and Tools

| Requirement | Details |
| ----------- | ------- |
| Operating system | Windows |
| Forensic tool | TestDisk |
| Source device | Authorized USB storage device |
| Source type | Physical storage device |
| Supported file systems | FAT, exFAT, NTFS, ext2/ext3/ext4 |
| Output | Recovered files and partition-analysis results |

---

## 📚 Theory

TestDisk is a free and open-source data-recovery utility used to recover deleted files, locate lost partitions, repair partition tables, and repair certain file-system structures.

When a file is deleted, its directory entry may be removed while the file data can remain on the storage device. If the storage location has not been overwritten, the deleted file may be recoverable.

TestDisk can analyze a storage device, display its partition layout, list files and deleted entries, and copy selected files to another location.

Recovered files should always be saved to a different storage device. Writing recovered files back to the source device may overwrite deleted data and reduce the chance of successful recovery.

---

## 💽 Source Device Preparation

### Step 1: Connect the Storage Device

Connect an authorized USB storage device to the computer.

Use only a practice device or an approved evidence device. Do not use a storage device containing important personal or confidential files.

### Step 2: Create Test Data

Copy one or more sample files to the authorized storage device.

Delete a selected sample file for recovery testing.

After deleting the file, do not copy additional data to the source device because new data may overwrite the deleted file.

### Step 3: Create a Recovery Folder

Create a separate recovery folder on the computer drive or another storage device.

The recovery folder must not be located on the source storage device.

---

## ⚙️ TestDisk Recovery Process

### Step 1: Open TestDisk

Open TestDisk with administrator privileges.

Select the **Create** option to create a log file containing technical information about the recovery process.

### Step 2: Select the Source Disk

TestDisk displays all available physical storage devices.

Select the authorized source storage device by checking its device name and size.

Do not select the internal system disk or an unrelated external drive.

### Step 3: Select the Partition Table Type

TestDisk displays the detected partition-table type.

In most cases, accept the automatically detected option and press **Enter**.

### Step 4: Analyze the Partition

Select:

```text
[Analyse]
```

This option examines the current partition structure and searches for missing or damaged partitions.

### Step 5: Perform Quick Search

Select:

```text
[Quick Search]
```

TestDisk searches the storage device for available partitions.

If the required partition is not found, select:

```text
[Deeper Search]
```

Deeper Search performs a more detailed scan and may require additional time.

### Step 6: List the Files

Highlight the required partition and press:

```text
p
```

TestDisk displays the files and folders inside the selected partition.

Deleted entries may be displayed in red.

### Step 7: Recover a Deleted File

Highlight the required deleted file and press:

```text
c
```

Select the separate recovery destination.

Press:

```text
C
```

to confirm the copy operation.

Do not select the source storage device as the recovery destination.

---

## 🔍 Recovery Verification

After TestDisk completes the copy operation, verify that the recovered file is present in the separate recovery folder.

Check the file name, file size, and whether the recovered file can be opened successfully.

---

## ⚠️ Precautions

| Precaution | Status |
| ---------- | ------ |
| Authorized practice or evidence device used | Required |
| Recovered files saved to a separate drive | Required |
| Files written back to the source device | Not allowed |
| Source device formatted | Not allowed |
| `Write` option selected without verification | Not allowed |
| `Backup BS` used without a backup | Not allowed |
| Source device repaired using `chkdsk` | Not recommended |
| Partition table modified during basic file recovery | Not required |

---

## 📌 Conclusion

This experiment demonstrated the use of TestDisk to analyze an authorized storage device and recover deleted files.

The Analyse and Quick Search options were used to examine the partition structure, while the file-listing feature was used to locate deleted entries. The recovered file was copied to a separate destination, preserving the source storage device.

TestDisk provides a useful method for recovering deleted files and examining damaged partitions during authorized digital-forensics laboratory exercises.

---

<div align="center">

**Digital Forensics Laboratory**

213CSE4307 - DIGITAL FORENSICS

</div>