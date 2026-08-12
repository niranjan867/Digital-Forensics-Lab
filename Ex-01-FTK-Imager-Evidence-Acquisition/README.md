<div align="center">

<img src="https://img.shields.io/badge/Wireshark-Network%20Analysis-1679A7?logo=wireshark&logoColor=white&style=for-the-badge" alt="Wireshark">

# EX. NO. 03

## Password Capturing and HTTP Credential Analysis Using Wireshark

</div>

---

## 🎯 Aim

To capture and analyze network traffic using Wireshark, identify HTTP GET and POST requests, and examine form data transmitted through unencrypted HTTP traffic.

---

## 🛠️ Software and Tools

| Requirement | Details |
|---|---|
| Operating system | Windows / Linux |
| Packet analyzer | Wireshark |
| Web browser | Google Chrome / Mozilla Firefox |
| Network interface | Wi-Fi / Ethernet |
| Test environment | Authorized local HTTP test application |
| Credentials | Dummy laboratory credentials |

---

## 📚 Theory

Wireshark is a network protocol analyzer used to capture and inspect data transmitted over a network.

When communication uses an unencrypted protocol such as HTTP, FTP, or Telnet, sensitive information may be visible in captured packets. This may include:

- HTTP requests.
- Usernames.
- Passwords.
- Email addresses.
- Form data.
- Other application information.

HTTP forms commonly use two request methods:

| Method | Description |
|---|---|
| `GET` | Used mainly to request information. Parameters may appear in the URL. |
| `POST` | Used to submit form data to a server. Data may be visible when HTTP is unencrypted. |

This experiment demonstrates why sensitive information should not be transmitted over plaintext HTTP.

---

## 🔎 Wireshark Filters Used

```text
http
```

```text
http.request.method == "GET"
```

```text
http.request.method == "POST"
```

---

## 📊 Observations and Results

| Field | Captured Key | Extracted Value |
|---|---|---|
| Username | `uname` | `lab_user` |
| Password | `pass` | `DemoPass123!` |

The values above are dummy laboratory credentials and must not be replaced with real credentials in a public repository.

### Observations

- HTTP packets were successfully captured using Wireshark.
- HTTP GET requests were identified using the GET display filter.
- The login form submission was identified as an HTTP POST request.
- The POST request contained URL-encoded form data.
- Dummy credentials were visible because the test communication was not encrypted.
- Plaintext HTTP can expose sensitive information to an authorized packet observer.

---

## 📌 Conclusion

This experiment demonstrated the security risk of transmitting login information over unencrypted HTTP. Wireshark was used to identify HTTP traffic, analyze GET and POST requests, and inspect URL-encoded form data.
---

<div align="center">

**Digital Forensics Laboratory**

Made for authorized cybersecurity education and practical learning.

</div>