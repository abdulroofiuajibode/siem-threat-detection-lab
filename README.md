# 🔐 SIEM Threat Detection Lab

> A hands-on Wazuh SIEM laboratory demonstrating Windows security
> monitoring, custom detection engineering, event correlation, and
> SOC incident investigation.

---

## 📌 Project Overview

This project simulates a Security Operations Center (SOC) environment
using **Wazuh** to monitor a Windows endpoint, collect security
telemetry, detect suspicious authentication activity, correlate
security events, and investigate alerts.

The project focuses on developing practical experience with the
security monitoring lifecycle:

**Collect → Detect → Correlate → Investigate → Classify → Document**

---

## 🎯 Objectives

- Deploy a functional Wazuh SIEM environment
- Connect and monitor a Windows endpoint
- Collect Windows security events
- Analyze authentication failures
- Develop custom Wazuh detection rules
- Correlate multiple security events
- Investigate generated alerts
- Map detections to MITRE ATT&CK
- Document incidents using a SOC-style workflow

---

## 🏗️ Lab Architecture

```text
                ┌─────────────────────┐
                │   Windows Endpoint  │
                │                     │
                │ Windows Security    │
                │ Events              │
                └──────────┬──────────┘
                           │
                           │ Wazuh Agent
                           ▼
                ┌─────────────────────┐
                │   Wazuh Manager     │
                │                     │
                │ Event Analysis      │
                │ Rule Processing     │
                └──────────┬──────────┘
                           │
                           ▼
                ┌─────────────────────┐
                │   Wazuh Dashboard   │
                │                     │
                │ Alerts &             │
                │ Investigation       │
                └─────────────────────┘
