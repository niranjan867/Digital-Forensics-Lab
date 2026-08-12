<div align="center">

<img src="https://img.shields.io/badge/Email%20Forensics-Header%20Analysis-1679A7?style=for-the-badge" alt="Email Forensics">

# EX. NO. 04

## Analyze Email Headers and Detect Email Spoofing Using MHA

</div>

---

## 🎯 Aim

To analyze the raw header of a received email using Microsoft Message Header Analyzer (MHA) and MXToolbox Email Header Analyzer, trace the email delivery path, verify SPF, DKIM, and DMARC authentication results, perform a WHOIS lookup on the originating IP address, and determine whether the email contains any signs of spoofing.

---

## 📝 Description

Email header analysis is the process of examining the metadata attached to an email message to verify its authenticity and trace its delivery route.

Important header fields such as:

* `From`
* `To`
* `Return-Path`
* `Received`
* `Message-ID`
* SPF
* DKIM
* DMARC

help determine whether an email genuinely originated from the claimed sender or domain.

Tools such as **Microsoft Message Header Analyzer (MHA)** and **MXToolbox Email Header Analyzer** automatically decode complex email headers into a readable format, while **WHOIS** lookup services help verify the ownership and registration information associated with an originating IP address.

---

## 🛠️ Tools Used

| Tool                                    | Purpose                                                             |
| --------------------------------------- | ------------------------------------------------------------------- |
| Microsoft Message Header Analyzer (MHA) | Parse raw email headers into a readable format                      |
| MXToolbox Email Header Analyzer         | Verify relay path and SPF/DKIM/DMARC authentication                 |
| WHOIS                                   | Verify ownership and registration information of the originating IP |
| Email Client                            | Extract the raw email header                                        |

---

## 🔬 Procedure

1. Open an authorized test email.
2. Extract the raw email header.

   * **Gmail:** More → Show Original
3. Copy the complete raw header, excluding the email body.
4. Identify important header fields:

   * `From`
   * `To`
   * `Date`
   * `Subject`
   * `Return-Path`
   * `Received`
   * `Message-ID`
5. Analyze the `Received` headers from bottom to top to trace the delivery path.
6. Identify the originating IP address from the appropriate `Received` header.
7. Perform a WHOIS lookup on the originating IP address.
8. Verify SPF, DKIM, and DMARC authentication results.
9. Compare the `Message-ID`, `Return-Path`, and `From` domains.
10. Look for anomalies such as:

    * Domain mismatches
    * Suspicious IP addresses
    * Abnormal timestamps
    * Unexpected mail servers
11. Analyze the header using:

    * Microsoft Message Header Analyzer (MHA)
    * MXToolbox Email Header Analyzer
12. Record the observations and determine whether the email appears legitimate or contains spoofing indicators.

---

## 📧 Sample Email Details

The following values are represented generically to avoid exposing personal or confidential email information.

| Field       | Value                          |
| ----------- | ------------------------------ |
| Subject     | Sample Test Email              |
| From        | Authorized Test Sender         |
| To          | Test Recipient                 |
| Date        | Sample Email Date and Time     |
| Return-Path | Authorized Mail Service Domain |
| Message-ID  | Sample Message Identifier      |

> Personal email addresses, names, message identifiers, and complete header values have been excluded from this public repository.

---

## 🔎 Step 4: Received Header / Relay Path Analysis

### MXToolbox Analysis

The `Received` headers were analyzed to identify the sequence of mail servers involved in delivering the email.

| Hop | Delay  | From                   | By                      | Protocol | Time          |
| --: | ------ | ---------------------- | ----------------------- | -------- | ------------- |
|   1 | —      | Authorized Mail Server | Destination Mail Server | ESMTPS   | Recorded Time |
|   2 | Normal | Internal Mail Server   | Mail Service            | SMTP     | Recorded Time |

### Observation

* The email passed through the expected mail relay infrastructure.
* No abnormal delivery delay was observed.
* No unexpected mail server was identified.
* The delivery path appeared consistent with a normal email transmission.

---

## 🌐 Step 5: WHOIS Lookup of Originating IP Address

The originating IP address identified from the email header was submitted to a WHOIS lookup service.

For privacy and security reasons, the actual IP address and registration details are not included in this public repository.

| Field                    | Result   |
| ------------------------ | -------- |
| IP Address               | Redacted |
| Network Range            | Verified |
| Organization             | Verified |
| Network Name             | Verified |
| Location                 | Verified |
| Registration Information | Verified |

### Observation

The WHOIS lookup was used to determine whether the originating IP address belonged to an expected mail service provider or an unrelated network.

The identified network information was consistent with the expected email delivery infrastructure.

---

## 🔐 Step 6: SPF, DKIM and DMARC Authentication

The email authentication results were analyzed using the raw header and email header analysis tools.

| Authentication | Result | Purpose                                                          |
| -------------- | ------ | ---------------------------------------------------------------- |
| SPF            | ✅ Pass | Verifies whether the sending server is authorized by the domain. |
| DKIM           | ✅ Pass | Verifies the digital signature associated with the email domain. |
| DMARC          | ✅ Pass | Checks domain alignment and authentication policy.               |

The actual domain names and authentication-specific identifiers have been omitted from the public documentation.

---

## 🔍 Step 7 & 8: Message-ID and Anomaly Analysis

### Domain Comparison

| Header Field | Domain Status            |
| ------------ | ------------------------ |
| From         | Authorized Sender Domain |
| Return-Path  | Mail Service Domain      |
| Message-ID   | Mail Service Domain      |

### Analysis

The `Return-Path` and `Message-ID` domains may differ from the visible `From` domain when an organization uses a third-party email delivery service.

Therefore, a domain difference alone does not necessarily indicate spoofing.

The authentication results, particularly **DKIM and DMARC**, should be considered when determining whether the sender domain is properly authenticated.

The analyzed email showed successful authentication and no significant anomalies in the examined header information.

---

## 📊 Results

| Parameter            | Result     |
| -------------------- | ---------- |
| SPF Authentication   | ✅ Passed   |
| DKIM Authentication  | ✅ Passed   |
| DMARC Authentication | ✅ Passed   |
| Relay Path           | ✅ Normal   |
| Originating Network  | ✅ Verified |
| Domain Alignment     | ✅ Valid    |
| Spoofing Indicators  | ❌ None     |

---

## 🧰 Tools and Their Purpose

| Tool                                    | Purpose                                                               |
| --------------------------------------- | --------------------------------------------------------------------- |
| Microsoft Message Header Analyzer (MHA) | Parsed raw email headers into a readable format                       |
| MXToolbox Email Header Analyzer         | Verified relay path and SPF/DKIM/DMARC authentication                 |
| WHOIS                                   | Verified ownership and registration information of the originating IP |

---

## 📌 Conclusion

The email header was successfully analyzed using **Microsoft Message Header Analyzer (MHA)** and **MXToolbox Email Header Analyzer**.

The `Received` headers were examined to trace the email delivery path, while WHOIS information was used to investigate the originating network. SPF, DKIM, and DMARC authentication results were also examined to determine whether the sender domain was properly authenticated.

The analyzed authentication results passed successfully, and no significant spoofing indicators were identified.

Personal email addresses, names, IP addresses, message identifiers, domain-specific header values, and other confidential evidence details have been excluded from this public repository.

---

## 🏁 Final Verdict

| Parameter               | Status               |
| ----------------------- | -------------------- |
| Email Authenticity      | **LEGITIMATE**       |
| Email Spoofing Detected | **NO**               |
| Overall Verdict         | **LEGITIMATE EMAIL** |

---

<div align="center">

**Digital Forensics Laboratory**

213CSE4307 - DIGITAL FORENSICS

</div>
