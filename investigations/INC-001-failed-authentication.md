# INC-001 — Repeated Failed Authentication Attempts

## 1. Incident Summary

A series of failed authentication events was detected on the monitored
Windows endpoint.

The events were correlated by a custom Wazuh detection rule designed to
identify repeated authentication failures within a defined time window.

---

## 2. Detection Information

| Field | Value |
|---|---|
| Windows Event ID | 4625 |
| Wazuh Rule | 60122 |
| Custom Rule | 100100 |
| Alert Level | 10 |
| Detection Threshold | 3 events |
| Timeframe | 120 seconds |
| MITRE ATT&CK | T1110 — Brute Force |

---

## 3. Affected Endpoint

| Field | Value |
|---|---|
| Agent ID | 001 |
| Hostname | WIN-0FRK8N5L1E3 |
| Channel | Security |

---

## 4. Event Evidence

The detected authentication failures contained the following information:

- **Target Account:** Administrator
- **Source Address:** 127.0.0.1
- **Logon Type:** 7
- **Authentication Package:** Negotiate
- **Failure Reason:** Unknown user name or bad password
- **Process:** C:\Windows\System32\svchost.exe

---

## 5. Detection Logic

The custom Wazuh Rule `100100` was configured to trigger when:

> Three events matching Wazuh Rule `60122` occur within 120 seconds.

Detection flow:

```text
Windows Event ID 4625
        ↓
Wazuh Rule 60122
        ↓
3 Matching Events
        ↓
120-Second Window
        ↓
Custom Rule 100100
        ↓
Level 10 Alert
