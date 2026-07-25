# Frequently Asked Questions (FAQ)

> [!NOTE]
> This FAQ answers the most common questions regarding the MAYUNDO USB Worm, including infection, file recovery, prevention, and system cleanup.

---

# Table of Contents

- [General Questions](#general-questions)
- [File Recovery](#file-recovery)
- [System Cleaning](#system-cleaning)
- [USB Safety](#usb-safety)
- [Technical Questions](#technical-questions)

---

# General Questions

## What is MAYUNDO?

MAYUNDO is a USB-propagated Windows malware commonly observed on removable flash drives.

Its primary objective is to spread itself to additional computers by hiding legitimate files and replacing them with deceptive executable files.

---

## Does MAYUNDO delete my files?

**Usually, no.**

In observed infections, the malware hides original folders instead of permanently deleting them.

This is why file recovery is often possible.

---

## Is MAYUNDO ransomware?

No.

No evidence currently indicates that MAYUNDO encrypts user files or demands payment.

Its primary objective appears to be propagation.

---

## Can MAYUNDO spread without Internet access?

Yes.

Unlike many modern malware families, MAYUNDO mainly spreads through USB drives.

Internet connectivity is not required.

---

# File Recovery

## Should I format my USB drive?

No.

Formatting should be considered **only after** attempting to recover your files.

Formatting permanently removes both the malware and your documents.

---

## Why did all my folders disappear?

The malware usually changes Windows file attributes to:

- Hidden
- System

The folders often remain on the USB drive.

---

## Why do I see USB-Explorer.exe?

This executable is typically created by the malware to trick users into launching it.

Do **not** execute it.

---

## How can I restore hidden files?

After ensuring the computer is clean, use:

```cmd
attrib -h -r -s /s /d *.*
```

from an elevated Command Prompt while inside the USB drive.

---

# System Cleaning

## Should I clean the USB drive first?

No.

Always clean the infected computer before reconnecting or cleaning removable media.

Otherwise, the USB drive may become infected again immediately.

---

## Which antivirus should I use?

Any reputable and up-to-date antivirus solution is acceptable, including:

- Microsoft Defender
- Malwarebytes
- Bitdefender
- ESET
- Kaspersky

---

## Can Windows Defender detect MAYUNDO?

Detection depends on:

- malware variant;
- signature updates;
- heuristic analysis.

Always keep Microsoft Defender updated.

---

# USB Safety

## Can one infected USB infect multiple computers?

Yes.

An infected USB drive may spread the malware to every vulnerable computer where the malicious executable is launched.

---

## Can one infected computer infect multiple USB drives?

Yes.

This is the primary propagation mechanism observed for MAYUNDO.

---

## Is it safe to use public computers?

Public computers should always be considered potentially untrusted.

Whenever possible:

- scan your USB afterwards;
- avoid executing unknown files;
- maintain backups.

---

# Technical Questions

## Does MAYUNDO use Registry persistence?

Persistence has been observed.

However, the exact Registry modifications have **not yet been confirmed**.

---

## Does MAYUNDO steal passwords?

There is currently **no confirmed evidence** supporting credential theft by the analyzed sample.

Further reverse engineering would be required.

---

## Does MAYUNDO communicate with a Command-and-Control (C2) server?

No network communication has been confirmed during current observations.

---

## Why is this repository cautious about technical claims?

Cybersecurity documentation should distinguish between:

- Confirmed observations
- Hypotheses
- Common malware techniques

This improves the reliability of the analysis.

---

# Reporting New Variants

If you encounter a MAYUNDO variant that behaves differently, consider documenting:

- screenshots;
- filenames;
- observed folders;
- antivirus detections;
- Windows version.

Comparing multiple samples helps improve the understanding of the malware.

---

# Summary

The most important recommendations are:

- Never execute suspicious USB files.
- Clean the computer before the USB drive.
- Recover hidden files before formatting.
- Keep Windows and antivirus software updated.
- Maintain regular backups.

---

# Next Document

➡ **[09-References.md](09-References.md)**

The final document lists the technical references and cybersecurity resources used throughout this repository.