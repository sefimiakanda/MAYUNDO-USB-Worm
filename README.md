# MAYUNDO USB Worm

![Banner](images/banner.png)

![Platform](https://img.shields.io/badge/Platform-Windows-blue)

![Malware](https://img.shields.io/badge/Malware-USB%20Worm-red)

![Status](https://img.shields.io/badge/Status-Research-green)

![License](https://img.shields.io/badge/License-MIT-yellow)

## Overview

This repository documents the MAYUNDO USB Worm, a malware widely spreading through removable USB drives in Central and Southern Africa.

The project explains:

- how it infects Windows

- how it spreads

- how to remove it

- how to recover hidden files

> [!WARNING]
> This repository is intended for **educational, research, and defensive cybersecurity purposes only**.
>
> It does **not** contain malware or malicious code.
>
> The objective is to understand the MAYUNDO USB Worm and learn how to detect, remove, and prevent infections.

## Infection Workflow

```mermaid
flowchart TD

A[Clean USB Drive]

--> B[Inserted into Infected Computer]

--> C[Malware Copies Itself]

--> D[Original Folders Hidden]

--> E[USB-Explorer.exe Created]

--> F[Victim Executes File]

--> G[Computer Infected]

--> H[Next USB Gets Infected]
```
### Key Facts

| Property       | Value            |
| -------------- | ---------------- |
| Malware Name   | MAYUNDO          |
| Category       | USB Worm         |
| Target OS      | Windows          |
| Propagation    | USB Flash Drives |
| Language       | Unknown          |
| First Observed | Unknown          |
| Risk Level     | Medium           |

### Repository Structure
MAYUNDO-USB-Worm
│
├── README.md          # Documentation principale
├── docs               # Analyses détaillées
├── images             # Captures et diagrammes
├── LICENSE
└── SECURITY.md

## Table of Contents

- Overview

- Infection Workflow

- Technical Analysis

- Indicators of Compromise

- Removal

- Recovery

- Prevention