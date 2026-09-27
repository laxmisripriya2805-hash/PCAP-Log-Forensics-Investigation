# PCAP & Linux Log Forensics Investigation

A practical cybersecurity investigation involving **PCAP analysis, Linux authentication log analysis, SSH brute-force detection, session reconstruction, persistence analysis, and attacker activity investigation**.

This project documents the analysis of network traffic and Linux authentication artifacts to reconstruct attacker activity and identify evidence of compromise.

---

## 🔎 Investigation Overview

The investigation consisted of two forensic analysis tasks:

### 1. Linux Authentication & Log Investigation

Analysis of Linux authentication artifacts was performed to identify:

- SSH brute-force activity
- Attacker IP address
- Successful account compromise
- Attacker terminal sessions
- Session identifiers
- Persistence mechanisms
- Privilege escalation through account modification
- Post-compromise command execution
- Relevant MITRE ATT&CK mapping

### 2. PCAP / HTTP Investigation

A provided PCAP file was analyzed using Wireshark to identify login-related information from HTTP traffic.

The investigation involved:

- HTTP traffic analysis
- HTTP object extraction
- TCP stream analysis
- Identification of login requests
- Examination of server responses
- Validation of discovered authentication information

---

## 🛠️ Tools Used

### Linux Log Investigation

- Ubuntu Terminal
- Python 3
- `grep`
- `utmp.py`

### Network / PCAP Investigation

- Wireshark
- Export Objects → HTTP
- Follow TCP Stream

---

## 📂 Evidence & Artifacts

The investigation used the following artifacts:

```text
auth
wtmp
utmp
questions
PCAP investigation report