<div align="center">

<img src="https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=for-the-badge&logo=microsoft&logoColor=white"/>
<img src="https://img.shields.io/badge/KQL-Query%20Language-blue?style=for-the-badge"/>
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Maintained-Yes-brightgreen?style=for-the-badge"/>

# 🛡️ Sentinel-Logic

**A curated collection of production-ready KQL queries for Microsoft Sentinel — built for threat hunters, SOC analysts, and blue teamers.**

[Queries](#-query-categories) · [Usage](#-how-to-use) · [Contributing](#-contributing) · [License](#-license)

</div>

---

## 📖 Overview

**Sentinel-Logic** is an open-source repository of KQL (Kusto Query Language) queries designed to accelerate detection engineering and threat hunting in **Microsoft Sentinel**. Whether you're building detection rules, investigating incidents, or hunting for adversarial behavior, this library gives you a head start.

> All queries are written against standard Microsoft Sentinel tables and are ready to use in your workspace with minimal modification.

---

## 📁 Repository Structure

```
Sentinel-Logic/
│
├── most_used_attacks/          # High-frequency attack pattern detections
│   ├── brute-force-login.kql
│   ├── password-spray.kql
│   ├── lateral-movement.kql
│   └── ...
│
├── threat-hunting/             # Proactive hunting queries
│   ├── suspicious-powershell.kql
│   ├── lolbins-execution.kql
│   └── ...
│
├── incident-response/          # IR triage and investigation queries
│   ├── user-activity-timeline.kql
│   ├── host-forensics.kql
│   └── ...
│
├── network/                    # Network-based detections
│   ├── dns-tunneling.kql
│   ├── c2-beaconing.kql
│   └── ...
│
├── identity/                   # Identity & access detections
│   ├── impossible-travel.kql
│   ├── mfa-fatigue.kql
│   └── ...
│
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 🎯 Query Categories

| Category | Description | # Queries |
|---|---|---|
| 🔴 **Most Used Attacks** | Detections for the most commonly observed attack techniques | Growing |
| 🔍 **Threat Hunting** | Proactive queries for hunting low-and-slow adversarial behavior | Growing |
| 🚨 **Incident Response** | Fast triage queries for active investigations | Growing |
| 🌐 **Network** | Network anomaly and C2 detection | Growing |
| 👤 **Identity** | Identity-based threats, privilege abuse, account compromise | Growing |

---

## ⚙️ Prerequisites

- An active **Microsoft Sentinel** workspace
- Appropriate **Log Analytics** data connectors enabled (e.g., Azure AD, Defender for Endpoint, Syslog)
- Reader or Contributor access to the workspace
- Basic familiarity with KQL

---

## 🚀 How to Use

### Option 1 — Run in Microsoft Sentinel

1. Navigate to your **Microsoft Sentinel** workspace
2. Go to **Logs** (or **Hunting** for threat hunting queries)
3. Copy the contents of any `.kql` file
4. Paste into the query editor and click **Run**

### Option 2 — Create an Analytics Rule

1. Go to **Analytics** → **Create** → **Scheduled query rule**
2. Paste the KQL query into the rule editor
3. Configure the alert threshold, frequency, and severity
4. Review and create the rule

### Option 3 — Add to a Workbook

1. Navigate to **Workbooks** → **New**
2. Add a query step and paste the KQL
3. Customize the visualization and save

> 💡 **Tip:** Each `.kql` file includes a comment header describing the query purpose, required tables, MITRE ATT&CK mapping, and expected output — read it before running.

---

## 🗺️ MITRE ATT&CK Coverage

Queries in this repository are mapped to the [MITRE ATT&CK Framework](https://attack.mitre.org/) where applicable. Each query file includes a header comment with the relevant tactic and technique IDs.

Example header format used in every query:

```kql
// ============================================================
// Query Name   : Brute Force Login Detection
// Description  : Detects multiple failed sign-in attempts
//                followed by a successful login from the same IP
// Table(s)     : SigninLogs
// MITRE Tactic : Credential Access
// MITRE Tech   : T1110 - Brute Force
// Severity     : High
// Author       : mrblue223
// Last Updated : 2024
// ============================================================
```

---

## 🤝 Contributing

Contributions are welcome and encouraged! Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

**Quick contribution steps:**
1. Fork the repository
2. Create a new branch (`git checkout -b add/my-new-query`)
3. Add your `.kql` file with the standard comment header
4. Submit a Pull Request with a clear description

---

## ⭐ Show Your Support

If this repository has been useful to you, please consider giving it a **star** ⭐ — it helps others discover the project and motivates continued development.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact & Community

- **Author:** [@mrblue223](https://github.com/mrblue223)
- **Issues / Feature Requests:** Open an [Issue](../../issues)
- **Discussions:** Open a [Discussion](../../discussions)

---

<div align="center">
  <sub>Built for the blue team community 🔵 | Defender-first, always.</sub>
</div>
