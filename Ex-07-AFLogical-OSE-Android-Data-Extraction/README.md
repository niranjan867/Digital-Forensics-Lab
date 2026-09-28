<div align="center">

<img src="https://img.shields.io/badge/ADB-Android%20Forensics-1679A7?style=for-the-badge" alt="ADB Android Forensics">

# EX. NO. 07

## Logical Data Acquisition from an Android Device Using ADB

</div>

---

## 🎯 Aim

To establish an authorized ADB connection with an Android device, verify device and storage access, acquire controlled test data from the device, and verify the acquired evidence on a Windows forensic workstation.

---

## 🛠️ Software and Tools

| Requirement | Details |
| ----------- | ------- |
| Operating System | Windows |
| Acquisition Tool | Android Debug Bridge (ADB) |
| Platform | Android SDK Platform-Tools |
| Target Device | Android Device |
| Connection | USB Data Cable |
| Evidence Type | Controlled Test Files |

---

## 📚 Theory

Android Debug Bridge (ADB) is a command-line tool provided as part of the Android SDK Platform-Tools. It allows a computer to communicate with an Android device through an authorized debugging connection.

In digital forensics, **logical acquisition** involves collecting accessible files and information through the operating system or available interfaces rather than creating a physical image of the device's complete storage.

ADB can be used to:

- Detect and verify an Android device.
- Obtain basic device information.
- Access authorized shared storage.
- Transfer files between the workstation and device.
- Acquire selected files from the device.
- Verify the acquired evidence on the forensic workstation.

The general forensic workflow is:

**Forensic Workstation → ADB Connection → Android Device → Accessible Storage → Logical Acquisition → Evidence Verification**

> **Note:** ADB logical acquisition is different from physical acquisition. It does not provide a complete bit-by-bit image of the device's internal storage.

---

## ⚙️ Procedure

### Step 1: Configure ADB

Open PowerShell or Command Prompt and navigate to the Android SDK Platform-Tools directory.

```text
cd <Platform-Tools-Directory>
```

Verify the ADB installation:

```text
adb version
```

The installed ADB and Platform-Tools versions should be displayed.

---

### Step 2: Enable USB Debugging

On the Android device:

1. Enable **Developer Options**.
2. Enable **USB Debugging**.
3. Connect the device to the forensic workstation using a USB data cable.
4. Authorize the workstation when the USB debugging prompt appears.

---

### Step 3: Verify the Device Connection

Check whether the Android device is detected by ADB:

```text
adb devices
```

The connected device should appear with the status:

```text
device
```

This confirms that an authorized ADB connection has been established.

---

### Step 4: Identify the Device

Retrieve basic device information using ADB:

```text
adb shell getprop ro.product.model
```

Retrieve the Android version:

```text
adb shell getprop ro.build.version.release
```

The returned information can be recorded as part of the acquisition documentation.

---

### Step 5: Verify Accessible Storage

List the contents of the accessible shared storage:

```text
adb shell ls /sdcard/
```

Directories available to the authorized ADB session can be examined.

For example:

```text
adb shell ls -lah /sdcard/Download/
```

This step verifies that the required storage location can be accessed before acquisition.

---

### Step 6: Prepare Controlled Test Data

A controlled test-data directory containing non-sensitive files is used for the experiment.

The test data may be transferred to the Android device using:

```text
adb push "<TestData-Directory>" /sdcard/Download/
```

Verify the transferred data:

```text
adb shell ls -lah /sdcard/Download/<TestData-Directory>/
```

The files should be visible in the specified directory.

---

### Step 7: Acquire the Test Data

Create a dedicated evidence directory on the forensic workstation:

```text
New-Item -ItemType Directory -Force "<Evidence-Directory>"
```

Acquire the selected files or directory from the Android device:

```text
adb pull "/sdcard/Download/<TestData-Directory>" "<Evidence-Directory>"
```

ADB copies the selected logical data from the Android device to the forensic workstation.

---

### Step 8: Verify the Acquired Evidence

Verify that the acquired files are present in the evidence directory:

```text
Get-ChildItem -Recurse "<Evidence-Directory>"
```

The acquired files should be listed in the designated evidence directory.

Where required, file hashes can also be calculated for evidence verification:

```text
Get-FileHash "<Evidence-File>"
```

The hash values can be recorded for integrity documentation.

---

## 📊 Observations and Results

| Parameter             | Observation                        |
| --------------------- | ---------------------------------- |
| ADB Installation      | Successfully verified              |
| Device Detection      | Device successfully detected       |
| ADB Authorization     | Successfully authorized            |
| Device Information    | Successfully retrieved             |
| Storage Access        | Authorized shared storage accessed |
| Test Data             | Controlled files used              |
| Data Transfer         | Successfully performed             |
| Logical Acquisition   | Successfully performed             |
| Evidence Verification | Successfully completed             |

### Observations

* ADB was successfully configured on the forensic workstation.
* The Android device was detected through the ADB interface.
* The device connection was authorized before acquisition.
* Basic device information was retrieved using ADB commands.
* Authorized shared storage was successfully accessed.
* Controlled test data was transferred and verified on the device.
* The selected data was acquired from the Android device using `adb pull`.
* The acquired evidence was verified in the designated forensic evidence directory.
* Hash verification can be used to support evidence-integrity documentation.

---

## 📌 Conclusion

This experiment demonstrated the use of **Android Debug Bridge (ADB)** for logical acquisition of controlled data from an Android device.

The device was successfully connected and verified, accessible storage was examined, controlled test data was transferred and acquired, and the acquired evidence was verified on the forensic workstation.

Thus, ADB provides a practical method for performing **authorized logical data acquisition** from an Android device for digital forensic examination.

---

## 📋 Result

The Android device was successfully connected using ADB, controlled test data was logically acquired, and the acquired evidence was verified on the forensic workstation.

---

<div align="center">

**Digital Forensics Laboratory**

**213CSE4307 - DIGITAL FORENSICS**

</div>
