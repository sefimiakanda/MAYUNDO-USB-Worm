# Prevention

> [!TIP]
> Preventing a malware infection is significantly easier than recovering from one.
>
> The recommendations in this document focus on reducing the risk of infection by USB-propagated malware such as MAYUNDO.

---

# Table of Contents

- [Overview](#overview)
- [Safe USB Practices](#safe-usb-practices)
- [Windows Security Configuration](#windows-security-configuration)
- [Antivirus Protection](#antivirus-protection)
- [File Explorer Configuration](#file-explorer-configuration)
- [Backup Strategy](#backup-strategy)
- [Cybersecurity Awareness](#cybersecurity-awareness)
- [Security Checklist](#security-checklist)
- [Summary](#summary)

---

# Overview

Most USB malware infections are successful because users unknowingly execute malicious files.

Good cybersecurity habits can dramatically reduce this risk.

This chapter presents practical defensive measures suitable for:

- Students
- Universities
- Offices
- Internet cafés
- Home users

---

# Safe USB Practices

## Never execute unknown files

If a USB drive suddenly displays files such as:

```text
USB-Explorer.exe

USB-Explorer.lnk
```

do **not** open them.

Instead:

- scan the USB drive;
- inspect the file extensions;
- verify that your original folders are still present.

---

## Scan Every USB Drive

Before opening any removable drive:

1. Right-click the USB drive.
2. Select **Scan with Microsoft Defender** (or your antivirus).
3. Wait for the scan to complete.

This simple habit prevents many infections.

---

## Avoid Public Computers

Computers located in:

- Internet cafés
- Shared laboratories
- Public libraries

may already be infected.

If you must use one:

- avoid saving sensitive information;
- scan your USB drive immediately afterward.

---

# Windows Security Configuration

## Disable AutoPlay

AutoPlay can automatically launch programs from removable media.

To disable it:

1. Open **Settings**.
2. Navigate to **Bluetooth & devices**.
3. Select **AutoPlay**.
4. Turn **AutoPlay** off.

This prevents automatic execution from removable devices.

---

## Keep Windows Updated

Install security updates regularly.

Updates often include:

- security fixes;
- malware detection improvements;
- Windows Defender enhancements.

---

# Antivirus Protection

A modern antivirus should remain enabled at all times.

Recommended practices:

- Enable real-time protection.
- Update virus definitions frequently.
- Perform periodic full scans.
- Never ignore malware alerts.

---

# File Explorer Configuration

One of the most effective defenses is displaying file extensions.

Enable:

```text
View

↓

Show

↓

File name extensions
```

Instead of seeing:

```text
USB-Explorer
```

you will immediately recognize:

```text
USB-Explorer.exe
```

This makes deceptive files much easier to identify.

---

# Hidden Files

Enable the display of hidden files when investigating suspicious USB drives.

This allows users to determine whether folders have been hidden instead of deleted.

---

# Backup Strategy

No security solution is perfect.

Regular backups remain essential.

Recommended locations:

- External hard drive
- Cloud storage
- University storage services
- Network Attached Storage (NAS)

Follow the **3-2-1 Backup Rule** whenever possible:

- **3** copies of important data.
- **2** different storage media.
- **1** copy stored off-site or in the cloud.

---

# Cybersecurity Awareness

Technology alone cannot prevent every attack.

Users should understand common social engineering techniques.

Remember:

- Do not trust unexpected executable files.
- Verify file extensions.
- Question unusual behavior.
- Ask for assistance when uncertain.

Awareness is one of the strongest security controls.

---

# Security Checklist

Use this checklist regularly.

| Security Measure | Status |
|------------------|--------|
|Windows updated|⬜|
|Microsoft Defender enabled|⬜|
|Real-time protection enabled|⬜|
|USB drives scanned before use|⬜|
|AutoPlay disabled|⬜|
|File extensions visible|⬜|
|Hidden files enabled when investigating|⬜|
|Backups available|⬜|

---

# Common Mistakes

## Ignoring antivirus warnings

Security alerts should always be investigated.

---

## Double-clicking unknown executables

Never assume a file is safe simply because it has a familiar icon.

---

## Sharing USB drives without scanning

Every removable drive should be treated as potentially untrusted until verified.

---

## Assuming files were deleted

Many USB worms hide files rather than deleting them.

Investigate before formatting.

---

# Recommendations for Educational Institutions

Universities and schools can reduce USB malware propagation by:

- Keeping laboratory computers updated.
- Installing reputable antivirus software.
- Restricting unnecessary executable launches.
- Promoting cybersecurity awareness among students.
- Encouraging cloud-based file sharing where appropriate.

---

# Summary

Good security practices dramatically reduce the likelihood of infection.

The most effective defenses include:

- Keep Windows updated.
- Keep antivirus enabled.
- Scan removable drives.
- Display file extensions.
- Disable AutoPlay.
- Maintain regular backups.
- Stay vigilant against social engineering.

Security is not a single tool—it is a combination of technology, procedures, and informed users.

---

# Next Document

➡ **[08-FAQ.md](08-FAQ.md)**

The next chapter answers the most frequently asked questions about the MAYUNDO malware, including file recovery, reinfection, antivirus detection, and safe handling of infected USB drives.