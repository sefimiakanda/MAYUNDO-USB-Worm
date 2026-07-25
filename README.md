# MAYUNDO USB Worm

![Banner](images/banner.png)

![Platform](https://img.shields.io/badge/Platform-Windows-blue)

![Malware](https://img.shields.io/badge/Malware-USB%20Worm-red)

![Status](https://img.shields.io/badge/Status-Research-green)

![License](https://img.shields.io/badge/License-MIT-yellow)

## Why this project?

The MAYUNDO USB Worm is one of the most widespread USB malware families observed across several universities and public computers in parts of Central, Eastern and Southern Africa.

Despite its prevalence, very little public technical documentation exists.

This repository aims to document its behavior and help users recover safely from an infection.

## Overview

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
├── README.md          
├── docs              
├── images             
├── LICENSE
└── SECURITY.md
## Screenshots

### Infected USB

![Infected USB](images/infection.png)

### Fake Explorer

![USB Explorer](images/usb-explorer.png)

## Documentation

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

