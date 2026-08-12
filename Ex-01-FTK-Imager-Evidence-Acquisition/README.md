<div align="center">

<img src="https://img.shields.io/badge/FTK%20Imager-Evidence%20Acquisition-1679A7?logo=databricks&logoColor=white&style=for-the-badge" alt="FTK Imager">

# EX. NO. 01

## Evidence Acquisition Using AccessData FTK Imager

</div>

---

## 🎯 Aim

To acquire volatile memory and non-volatile storage evidence using AccessData FTK Imager and verify the integrity of the acquired disk image using cryptographic hash values.

---

## 🛠️ Software and Tools

| Requirement      | Details                       |
| ---------------- | ----------------------------- |
| Operating system | Windows                       |
| Forensic tool    | AccessData FTK Imager         |
| Source device    | Authorized USB storage device |
| Image format     | Raw (dd)                      |
| Output           | Forensic evidence image       |

---

## 📚 Theory

FTK Imager is a forensic acquisition and preview tool used to collect and examine digital evidence.

Digital evidence can be broadly divided into two categories:

| Evidence Type            | Description                                                         |
| ------------------------ | ------------------------------------------------------------------- |
| **Volatile Memory**      | Data stored in RAM that may be lost when the system is powered off. |
| **Non-Volatile Storage** | Data stored on devices such as hard disks, SSDs, and USB drives.    |

FTK Imager can acquire both types of evidence. During live acquisition, volatile memory can be captured from a running Windows system. For non-volatile evidence, a physical storage device can be acquired as a forensic image.

A **write blocker** should be used whenever possible when acquiring evidence from an external or powered-off storage device. It provides read-only access to the source and helps prevent accidental modification of the original evidence.

Cryptographic hash algorithms such as **MD5** and **SHA1** are used to verify the integrity of acquired forensic images. Matching hash values indicate that the acquired image is consistent with the source evidence at the time of verification.

---

## 🧠 Volatile-Memory Acquisition

### Step 1: Open Memory Capture

Open FTK Imager and select the **Memory Capture** function.

### Step 2: Configure Memory Capture

Configure the memory acquisition settings using an appropriate forensic evidence directory.

| Setting          | Configuration               |
| ---------------- | --------------------------- |
| Destination      | Forensic evidence directory |
| Memory file      | `memory_dump.mem`           |
| Include pagefile | Enabled                     |
| Create AD1 file  | Enabled                     |
| AD1 file         | `memory_capture.ad1`        |

The pagefile option can be enabled because Windows may store memory pages in the pagefile. The AD1 option creates an FTK-compatible evidence container.

### Step 3: Capture RAM

Start the memory capture process.

FTK Imager displays the acquisition progress, including the amount of memory processed and the total memory size.

Wait for the acquisition to complete successfully.

### Step 4: Verify the Memory Capture

After completion, the memory dump is saved as:

```text
memory_dump.mem
```

The AD1 evidence container may be created as segmented files:

```text
memory_capture.ad1
memory_capture.ad2
memory_capture.ad3
...
```

### Volatile-Memory Hashes

FTK Imager generates cryptographic checksums for the captured memory evidence.

| Hash | Status    |
| ---- | --------- |
| MD5  | Generated |
| SHA1 | Generated |

Actual evidence hash values are excluded from this public repository.

---

## 💾 Non-Volatile Physical-Drive Acquisition

### Step 1: Select the Source Type

Open FTK Imager and select:

**File → Create Disk Image**

In the **Select Source** window, choose:

**Physical Drive**

### Step 2: Select the Evidence Drive

Select the **authorized USB storage device** that is intended for forensic acquisition.

Verify the selected device carefully before proceeding. The system's primary internal drive should not be selected unless it is the authorized evidence source.

### Step 3: Select the Image Format

Select:

```text
Raw (dd)
```

The Raw/DD format creates a bitstream image that can be processed by forensic-analysis tools.

### Step 4: Enter Evidence Information

Enter the required case and evidence information.

Avoid entering personal, confidential, or case-sensitive information into public documentation.

### Step 5: Acquire the Physical Drive

Select an appropriate forensic evidence directory as the destination and start the acquisition.

FTK Imager displays the source size, sector information, and acquisition progress.

After completion, the Raw/DD image may be stored as segmented files:

```text
disk_image.001
disk_image.002
disk_image.003
disk_image.004
...
```

---

## 🔎 Disk-Image Verification

After acquiring the physical drive, verify the forensic image using FTK Imager's verification functionality.

FTK Imager calculates and compares cryptographic hashes for the source and acquired image.

| Hash | Verification |
| ---- | ------------ |
| MD5  | Match        |
| SHA1 | Match        |

Matching values indicate that the acquired image is consistent with the source evidence.

---

## 📊 Observations and Results

| Field                       | Result               |
| --------------------------- | -------------------- |
| Volatile memory acquisition | Successful           |
| Memory dump                 | Successfully created |
| AD1 evidence container      | Successfully created |
| Pagefile                    | Included             |
| Physical-drive acquisition  | Successful           |
| Image format                | Raw (dd)             |
| Disk image                  | Successfully created |
| MD5 verification            | Match                |
| SHA1 verification           | Match                |
| Bad blocks                  | None reported        |

### Observations

* FTK Imager was successfully used for volatile and non-volatile evidence acquisition.
* Volatile memory was captured as a memory dump.
* An AD1 evidence container was created.
* The pagefile option was enabled during memory capture.
* An authorized USB storage device was acquired as forensic evidence.
* The physical drive was acquired using the Raw/DD format.
* The disk image was created as segmented files.
* MD5 verification returned **Match**.
* SHA1 verification returned **Match**.
* No bad blocks were reported during acquisition.
* Cryptographic hashes were generated for evidence verification.

---

## 📌 Conclusion

This experiment demonstrated the acquisition of both volatile and non-volatile digital evidence using AccessData FTK Imager. RAM was successfully captured as a memory dump and AD1 evidence container, while an authorized USB storage device was acquired as a Raw/DD forensic image.

The acquired disk image produced matching **MD5** and **SHA1** values during verification, confirming that the forensic image was consistent with the source evidence.

---

<div align="center">

**Digital Forensics Laboratory**

Made for authorized cybersecurity education and practical learning.

</div>
