# Technical Analysis

> [!IMPORTANT]
> This document describes the observed behavior of the MAYUNDO USB Worm based on field observations and Windows malware analysis principles.
>
> Unless explicitly stated otherwise, behaviors described as **observed** refer to real-world infections. Behaviors marked as **potential** are common techniques used by similar malware families but may require additional reverse engineering to confirm.

---

# Table of Contents

- [Overview](#overview)
- [Malware Classification](#malware-classification)
- [Attack Objectives](#attack-objectives)
- [Execution Chain](#execution-chain)
- [Observed Behaviour](#observed-behaviour)
- [File Manipulation](#file-manipulation)
- [Persistence Mechanisms](#persistence-mechanisms)
- [Potential Capabilities](#potential-capabilities)
- [Risk Assessment](#risk-assessment)
- [Summary](#summary)

---

# Overview

The MAYUNDO malware is primarily designed to spread through removable USB storage devices.

Unlike destructive malware such as ransomware or disk wipers, MAYUNDO focuses on **propagation**, **deception**, and **persistence**.

Its primary objective is to convince the victim to execute a malicious program while making legitimate files appear to have disappeared.

The malware relies more on **social engineering** than on advanced exploitation techniques.

---

# Malware Classification

| Property | Value |
|----------|-------|
| Malware Family | MAYUNDO |
| Malware Type | USB Worm |
| Category | Trojan / Shortcut Virus |
| Platform | Microsoft Windows |
| Propagation | USB Removable Drives |
| Primary Goal | Self Propagation |
| Secondary Goal | Persistence |
|User Interaction Required|Yes|

---

# Attack Objectives

The observed objectives of the malware include:

- Hiding legitimate user folders.
- Creating deceptive executable files.
- Infecting additional USB drives.
- Remaining active after system reboot.
- Encouraging accidental execution by users.

Unlike ransomware, the malware does **not normally encrypt files**.

---

# Execution Chain

```text
USB Inserted
      │
      ▼
Malware Detects Drive
      │
      ▼
Legitimate Files Hidden
      │
      ▼
Fake Executable Created
      │
      ▼
Victim Executes File
      │
      ▼
Malware Installed
      │
      ▼
Persistence Established
      │
      ▼
Future USB Devices Become Infected
```

---

# Observed Behaviour

## 1. Detection of a Removable Drive

The malware monitors removable storage devices connected to the infected system.

Once a new USB drive becomes available, the infection routine begins.

---

## 2. Hiding User Data

Instead of deleting documents, the malware typically changes Windows file attributes.

Observed attributes include:

- Hidden
- System

As a result:

- folders disappear from Windows Explorer;
- users believe their files have been deleted.

---

## 3. Creation of Fake Executables

The malware places deceptive files at the root of the USB drive.

Examples include:

```text
USB-Explorer.exe
USB-Explorer.lnk
```

The executable usually imitates the appearance of a folder or Windows Explorer icon.

Victims are encouraged to click it in an attempt to access their documents.

---

## 4. Installation on the Host System

Once executed, the malware may copy itself into user-accessible directories.

Common locations include:

```text
%AppData%

%LocalAppData%

%Temp%
```

The exact installation path depends on the malware variant.

---

## 5. Automatic Propagation

After installation, every newly connected USB drive becomes a potential target.

The infection process repeats automatically.

---

# File Manipulation

The malware primarily manipulates file visibility rather than file contents.

Typical operations include:

| Operation | Effect |
|-----------|--------|
|Hide folders|User believes files disappeared|
|Create executable|Social engineering|
|Copy malicious payload|USB propagation|
|Preserve original files|Allows deception to continue|

This explains why file recovery is often possible.

---

# Persistence Mechanisms

Field observations suggest that MAYUNDO attempts to survive system reboot.

Possible persistence mechanisms include:

- Registry Run Keys
- Startup Folder
- Scheduled Tasks
- Startup Scripts

Some variants may use only one technique while others combine multiple methods.

Detailed analysis is provided in:

➡ **04-Persistence.md**

---

# Potential Capabilities

Although the primary function appears to be USB propagation, malware of this category can theoretically be extended with additional capabilities.

Examples include:

## Credential Theft

Possible collection of:

- saved passwords;
- browser credentials;
- authentication tokens.

No evidence currently confirms that the observed sample performs these actions.

---

## Keylogging

A secondary payload could theoretically record keyboard input.

Again, this behavior has **not** been confirmed for the analyzed sample.

---

## Remote Control

If connected to a command-and-control (C2) infrastructure, similar malware could receive additional instructions.

No active network communication has yet been confirmed.

---

## Botnet Integration

Some USB worms are capable of enrolling infected machines into botnets.

This remains **hypothetical** until verified through reverse engineering or network traffic analysis.

---

# Risk Assessment

| Category | Risk |
|----------|------|
|Propagation|High|
|File Loss|Low|
|Data Encryption|Not Observed|
|Persistence|Medium|
|Social Engineering|High|
|Network Propagation|Potential|
|Credential Theft|Unconfirmed|

---

# Technical Characteristics

| Characteristic | Observation |
|---------------|-------------|
|Requires user interaction|Yes|
|Uses removable media|Yes|
|Deletes files|No evidence|
|Hides files|Observed|
|Creates deceptive executable|Observed|
|Persists after reboot|Observed on some infections|
|Encrypts files|No|
|Spreads automatically|Yes|

---

# Key Findings

The technical analysis indicates that MAYUNDO relies on a relatively simple but highly effective strategy.

Its success is based on four principles:

1. Hide legitimate files.
2. Create a convincing fake executable.
3. Wait for the victim to execute it.
4. Repeat the infection on every removable drive.

Rather than exploiting complex Windows vulnerabilities, the malware primarily abuses user trust.

---

# Summary

The MAYUNDO malware should be considered a **USB propagation worm** whose effectiveness relies on social engineering and Windows file attribute manipulation.

Although current observations do not indicate destructive behavior such as encryption or file deletion, infected systems should always be treated as potentially compromised until fully analyzed and cleaned.

---

# Next Document

Continue with:

➡ **[03-Infection-Workflow.md](03-Infection-Workflow.md)**

The next document provides a detailed step-by-step description of the complete infection lifecycle, from the first USB insertion to the propagation of the malware across multiple systems.