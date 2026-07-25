# Removal Guide

> [!IMPORTANT]
> This guide explains how to safely remove the MAYUNDO malware from a Windows computer and recover hidden files from an infected USB drive.
>
> **Always clean the infected computer first.** Cleaning the USB drive before the host computer may result in immediate reinfection.

---

# Table of Contents

- [Overview](#overview)
- [Before You Begin](#before-you-begin)
- [Step 1 – Isolate the Computer](#step-1--isolate-the-computer)
- [Step 2 – Scan the System](#step-2--scan-the-system)
- [Step 3 – Remove Detected Threats](#step-3--remove-detected-threats)
- [Step 4 – Recover Hidden Files](#step-4--recover-hidden-files)
- [Step 5 – Remove Malicious Files](#step-5--remove-malicious-files)
- [Step 6 – Verify the Cleanup](#step-6--verify-the-cleanup)
- [Recovery Checklist](#recovery-checklist)
- [Frequently Asked Mistakes](#frequently-asked-mistakes)

---

# Overview

In most observed cases, MAYUNDO does **not permanently delete user files**.

Instead, it:

- hides folders;
- creates deceptive executable files;
- propagates through USB devices.

This means that formatting the USB drive is usually unnecessary and may lead to avoidable data loss.

---

# Before You Begin

Before attempting recovery:

✅ Disconnect unnecessary USB devices.

✅ Save any ongoing work.

✅ Ensure your antivirus definitions are up to date.

❌ Do **not** execute suspicious files such as:

```text
USB-Explorer.exe
USB-Explorer.lnk
```

---

# Step 1 – Isolate the Computer

If the computer is connected to:

- Wi-Fi
- Ethernet
- Shared network

disconnect it temporarily.

Although MAYUNDO primarily spreads through USB drives, isolating the host reduces additional risks during investigation.

---

# Step 2 – Scan the System

Perform a **Full Scan** using a trusted antivirus solution.

Examples include:

- Microsoft Defender
- Malwarebytes
- Bitdefender
- ESET
- Kaspersky

Allow the scan to complete before proceeding.

---

# Step 3 – Remove Detected Threats

After the scan:

- Quarantine detected malware.
- Remove malicious files if recommended by the antivirus.
- Restart the computer if requested.

Do **not** reconnect USB drives until the scan is complete.

---

# Step 4 – Recover Hidden Files

Once the computer is clean, reconnect the USB drive.

Open **Command Prompt** as Administrator.

Navigate to the USB drive:

```cmd
E:
```

Replace **E:** with the actual drive letter.

Run:

```cmd
attrib -h -r -s /s /d *.*
```

---

## What does this command do?

| Option | Description |
|---------|-------------|
|`-h`|Removes the Hidden attribute|
|`-r`|Removes the Read-only attribute|
|`-s`|Removes the System attribute|
|`/s`|Applies to all subfolders|
|`/d`|Includes directories|

This command restores the visibility of legitimate files and folders.

---

# Step 5 – Remove Malicious Files

After restoring file visibility:

Inspect the USB drive.

Typical structure:

```text
USB
│
├── MAYUNDO
│   ├── Documents
│   ├── Projects
│   └── Photos
│
└── USB-Explorer.exe
```

Move your legitimate folders back to the root of the USB drive if necessary.

Then delete:

```text
USB-Explorer.exe
```

and remove the empty malware-created folder if it is no longer needed.

> [!CAUTION]
> Verify that your original files have been recovered before deleting any folders.

---

# Step 6 – Verify the Cleanup

Reconnect the USB drive to the cleaned computer.

Confirm that:

- folders are visible;
- no suspicious executable appears;
- no new hidden folders are created.

If the USB becomes infected again immediately, the host computer is likely still compromised.

---

# Recovery Checklist

| Task | Completed |
|------|-----------|
|Computer isolated|⬜|
|Full antivirus scan completed|⬜|
|Threats removed|⬜|
|Computer restarted|⬜|
|USB reconnected|⬜|
|Files restored using `attrib`|⬜|
|Malicious executable deleted|⬜|
|USB verified clean|⬜|

---

# Frequently Asked Mistakes

## ❌ Formatting the USB drive immediately

Formatting removes both the malware and the user's data.

Attempt file recovery first.

---

## ❌ Cleaning the USB before the computer

The malware will simply infect the USB drive again.

Always clean the computer first.

---

## ❌ Double-clicking the fake executable

Executing:

```text
USB-Explorer.exe
```

infects the host computer.

---

## ❌ Ignoring antivirus warnings

If your antivirus detects malware, investigate the alert rather than dismissing it.

---

# After Recovery

Once recovery is complete:

- Enable Microsoft Defender real-time protection.
- Keep Windows updated.
- Scan removable drives before opening them.
- Enable file name extensions in File Explorer.
- Maintain regular backups of important documents.

---

# Summary

Successful recovery generally follows this sequence:

```text
Isolate Computer
        │
        ▼
Antivirus Scan
        │
        ▼
Remove Threats
        │
        ▼
Restart Computer
        │
        ▼
Reconnect USB
        │
        ▼
Restore Hidden Files
        │
        ▼
Delete Malicious Files
        │
        ▼
Verify USB
```

Following this order significantly reduces the risk of reinfection while preserving user data.

---

# Next Document

➡ **[07-Prevention.md](07-Prevention.md)**

The next chapter describes practical security measures that help prevent future MAYUNDO infections and improve the safe use of removable USB devices.