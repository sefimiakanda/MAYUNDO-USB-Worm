# Introduction

> [!NOTE]
> This repository provides a technical and educational analysis of the **MAYUNDO USB Worm**, a malware that propagates through removable USB storage devices by abusing Windows file attributes and social engineering techniques.
>
> The objective of this project is to document its observed behavior, explain its infection chain, and provide safe recovery procedures for affected users.

---

# Table of Contents

- [Background](#background)
- [What is MAYUNDO?](#what-is-mayundo)
- [Objectives of this Repository](#objectives-of-this-repository)
- [Scope](#scope)
- [Target Audience](#target-audience)
- [Repository Structure](#repository-structure)
- [Legal Disclaimer](#legal-disclaimer)

---

# Background

USB flash drives remain one of the most widely used methods for transferring files between computers, particularly in:

- Universities
- Schools
- Internet cafés
- Offices
- Public institutions

Although cloud storage solutions have become increasingly popular, removable media continue to play a critical role in environments where Internet access is limited or unreliable.

Unfortunately, USB devices also represent one of the oldest and most effective malware propagation vectors.

A single infected computer can silently compromise dozens of removable drives within minutes, allowing malware to spread rapidly across multiple systems without requiring an Internet connection.

One malware family frequently reported by users in several African countries is commonly known as **MAYUNDO**.

Although there is currently very little public documentation describing its behavior, field observations suggest that it operates primarily as a **USB Shortcut Worm**, relying on hidden files and deceptive executable names to trick victims into executing malicious code.

---

# What is MAYUNDO?

MAYUNDO is a Windows malware family primarily designed to propagate through removable USB drives.

Unlike ransomware, MAYUNDO generally does **not encrypt or permanently delete user files**.

Instead, it performs three main actions:

1. Hides legitimate folders.
2. Creates deceptive executable files.
3. Spreads itself to every removable drive connected to an infected computer.

Its success depends largely on **social engineering**, encouraging victims to execute a fake program that appears to be their USB contents.

Typical malicious filenames include:

```text
USB-Explorer.exe
USB-Explorer.lnk
```

while legitimate user files are hidden inside folders such as:

```text
MAYUNDO
```

using Windows **Hidden** and **System** attributes.

---

# Objectives of this Repository

This project was created to fill the lack of publicly available technical documentation regarding the MAYUNDO malware.

Its primary objectives are:

- Document observed malware behavior.
- Explain the infection lifecycle.
- Describe persistence mechanisms.
- Identify common Indicators of Compromise (IoCs).
- Help victims recover hidden files safely.
- Promote cybersecurity awareness.
- Encourage defensive security practices.

---

# Scope

This repository focuses exclusively on defensive cybersecurity.

The documentation covers:

- Malware analysis
- Infection workflow
- Persistence mechanisms
- File recovery
- Detection techniques
- Prevention strategies
- Windows artifacts
- Indicators of Compromise (IoCs)

This repository **does not** include:

- Malware source code
- Exploit development
- Offensive techniques
- Weaponization
- Payload creation
- Instructions intended to facilitate cyberattacks

---

# Target Audience

This documentation is intended for:

- Students
- System administrators
- Cybersecurity researchers
- Incident responders
- Digital forensic analysts
- IT professionals
- Windows users interested in malware analysis

No prior reverse engineering experience is required.

---

# Repository Structure

```text
MAYUNDO-USB-Worm
│
├── README.md
├── LICENSE
├── SECURITY.md
│
├── docs
│   ├── 01-Introduction.md
│   ├── 02-Technical-Analysis.md
│   ├── 03-Infection-Workflow.md
│   ├── 04-Persistence.md
│   ├── 05-Indicators-of-Compromise.md
│   ├── 06-Removal-Guide.md
│   ├── 07-Prevention.md
│   ├── 08-FAQ.md
│   └── 09-References.md
│
└── images
```

Each document covers a specific aspect of the malware to make navigation easier and improve maintainability.

---

# Documentation Roadmap

| Document | Description |
|----------|-------------|
| 01-Introduction | Project overview |
| 02-Technical-Analysis | Internal malware behavior |
| 03-Infection-Workflow | Complete infection lifecycle |
| 04-Persistence | Windows persistence mechanisms |
| 05-Indicators-of-Compromise | Detection artifacts |
| 06-Removal-Guide | Safe malware removal |
| 07-Prevention | Best security practices |
| 08-FAQ | Frequently Asked Questions |
| 09-References | Research sources |

---

# Why This Documentation Matters

Many users mistakenly believe that MAYUNDO permanently deletes files.

In most observed cases, this is **not** what happens.

Instead, the malware changes Windows file attributes to make legitimate folders invisible while presenting a fake executable to the victim.

Understanding this behavior helps users:

- Recover files without formatting the USB drive.
- Avoid reinfecting cleaned systems.
- Detect suspicious behavior earlier.
- Reduce malware propagation within organizations.

---

# Legal Disclaimer

> [!WARNING]
>
> This repository is intended **solely for educational, research, incident response, and defensive cybersecurity purposes**.
>
> The authors do not encourage or support the creation, modification, or distribution of malware.
>
> Any information provided in this repository should only be used to improve cybersecurity awareness and defensive capabilities.

---

# Next Document

Continue with:

➡ **[02-Technical-Analysis.md](02-Technical-Analysis.md)**

This document explains the internal behavior of the MAYUNDO malware, including its execution flow, file manipulation techniques, and observed Windows artifacts.