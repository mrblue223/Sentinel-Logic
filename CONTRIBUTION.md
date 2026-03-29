# 🤝 Contributing to Sentinel-Logic

Thank you for your interest in contributing! This repository grows stronger with community input. Whether you're fixing a bug in a query, adding a new detection, or improving documentation — every contribution matters.

Please take a moment to read these guidelines before submitting.

---

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [What We're Looking For](#what-were-looking-for)
- [Getting Started](#getting-started)
- [Query Standards](#query-standards)
- [Folder Structure](#folder-structure)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Reporting Issues](#reporting-issues)

---

## 📜 Code of Conduct

This project follows a simple rule: **be respectful**. We welcome contributors of all skill levels. Constructive feedback is encouraged; personal attacks are not. By participating, you agree to keep this a positive space for the security community.

---

## ✅ What We're Looking For

We welcome the following types of contributions:

- ✅ New KQL detection or hunting queries
- ✅ Improvements to existing queries (accuracy, performance, false positive reduction)
- ✅ New query categories or folders
- ✅ Documentation improvements
- ✅ Bug reports or incorrect query logic reports

We are **not** currently accepting:

- ❌ Queries targeting non-Sentinel environments without clear documentation
- ❌ Offensive/red team tooling
- ❌ Queries without the standard comment header

---

## 🚀 Getting Started

1. **Fork** the repository by clicking "Fork" at the top right of the page
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/Sentinel-Logic.git
   cd Sentinel-Logic
   ```
3. **Create a branch** for your contribution:
   ```bash
   git checkout -b add/detect-pass-the-hash
   ```
4. Make your changes, then **commit** with a clear message:
   ```bash
   git add .
   git commit -m "feat: add Pass-the-Hash detection query"
   ```
5. **Push** to your fork:
   ```bash
   git push origin add/detect-pass-the-hash
   ```
6. Open a **Pull Request** on GitHub

---

## 📐 Query Standards

Every `.kql` file **must** include the following comment header at the top:

```kql
// ============================================================
// Query Name   : <Descriptive Name>
// Description  : <One or two sentences describing what it detects>
// Table(s)     : <Comma-separated list of Sentinel tables used>
// MITRE Tactic : <ATT&CK Tactic Name>
// MITRE Tech   : <T#### - Technique Name>
// Severity     : Critical | High | Medium | Low | Informational
// Author       : <Your GitHub username>
// Last Updated : <YYYY>
// ============================================================
```

### Style Guidelines

- Use **descriptive variable names** — avoid single-letter variables unless in an `mv-expand` or `extend`
- **Comment non-obvious logic** inline
- Prefer `summarize` over raw table dumps for alert rules
- Use `let` statements to define thresholds at the top of the query so they're easy to tune:
  ```kql
  let FailureThreshold = 10;
  let TimeWindow = 1h;
  ```
- Always include a `| project` or `| project-away` to remove noise from the output
- Test your query in a live Sentinel workspace before submitting

### Naming Convention

| Type | Format | Example |
|---|---|---|
| File name | `kebab-case.kql` | `brute-force-login.kql` |
| Branch name | `add/<query-name>` | `add/mfa-fatigue-detection` |
| PR title | `feat: <short description>` | `feat: add DNS tunneling detection` |

---

## 📁 Folder Structure

Place your query in the most appropriate folder:

| Folder | Use For |
|---|---|
| `most_used_attacks/` | Common, high-frequency attack detections |
| `threat-hunting/` | Proactive, lower-signal hunting queries |
| `incident-response/` | IR triage and timeline reconstruction |
| `network/` | Network anomaly and C2 detection |
| `identity/` | Identity threats, privilege abuse, account takeover |

If your query doesn't fit any existing folder, propose a new one in your PR description.

---

## 🔃 Submitting a Pull Request

When opening your PR, please include:

- **What the query detects** — 1–2 sentence summary
- **Which table(s) it queries** — e.g., `SigninLogs`, `SecurityEvent`
- **MITRE ATT&CK mapping** — tactic and technique
- **Testing notes** — did you validate this in a live workspace? Any known false positives?
- **Screenshot (optional but appreciated)** — showing sample output

PRs will be reviewed within a few days. We may request changes before merging.

---

## 🐛 Reporting Issues

Found a broken query, a false positive problem, or incorrect MITRE mapping? Please open an [Issue](../../issues) and include:

- The file name / query in question
- A description of the problem
- Your suggested fix (if you have one)

---

Thank you for helping make **Sentinel-Logic** a better resource for the entire blue team community! 🔵
