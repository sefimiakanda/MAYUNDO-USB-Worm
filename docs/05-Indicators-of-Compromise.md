# Indicators of Compromise (IoCs)

> [!IMPORTANT]
> Indicators of Compromise (IoCs) are observable artifacts that may indicate a system has been infected.
>
> This document separates:
>
> - 🟢 **Observed IoCs** — confirmed during field observations.
> - 🟡 **Investigation Targets** — locations that should be examined during incident response.
> - 🔴 **Not Confirmed** — behaviors commonly associated with similar malware but not verified for MAYUNDO.

---

# Table of Contents

- [Overview](#overview)
- [Observed IoCs](#observed-iocs)
- [File Artifacts](#file-artifacts)
- [Folder Artifacts](#folder-artifacts)
- [Registry Locations](#registry-locations)
- [Process Investigation](#process-investigation)
- [USB Artifacts](#usb-artifacts)
- [Detection Checklist](#etection-checklist)
- [Incident Response Checklist](#incident-response-checklist)

---

# Overview

Indicators of Compromise help investigators determine whether a Windows system or removable USB device has likely been infected.

An individual indicator does not necessarily confirm an infection.

However, multiple indicators observed together significantly increase confidence.

---

# Observed IoCs

The following artifacts were directly observed during field analysis.

| Indicator | Status |
|-----------|--------|
|Original folders hidden|🟢 Confirmed|
|USB-Explorer.exe|🟢 Confirmed|
|Folder named MAYUNDO|🟢 Observed on analyzed sample|
|Repeated infection of clean USB drives|🟢 Confirmed|

---

# File Artifacts

Investigators should inspect removable drives for suspicious executable files.

Common examples include:

```text
USB-Explorer.exe

USB-Explorer.lnk
```

Characteristics:

- Located at the USB root.
- Executable instead of folder.
- Similar appearance to Windows Explorer.
- Intended to deceive users.

---

# Folder Artifacts

Observed folder:

```text
MAYUNDO
```

This directory may contain the user's original files after they have been hidden.

> [!NOTE]
> Folder names may vary depending on the malware variant.

---

# Hidden Files

Windows Explorer may hide the original documents because malware applies attributes such as:

```text
Hidden

System
```

The files are generally still present.

---

# USB Root Structure

Example of an infected USB drive.

```text
USB Drive
│
├── MAYUNDO
│   ├── Documents
│   ├── Projects
│   ├── Photos
│   └── Notes
│
└── USB-Explorer.exe
```

---

# Registry Locations

No Registry modification has yet been confirmed.

However, analysts should inspect the following locations.

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Run

HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

Look for:

- unknown executables;
- references to AppData;
- suspicious startup entries.

---

# Startup Folder

Inspect:

```text
%AppData%\Microsoft\Windows\Start Menu\Programs\Startup
```

Unexpected executables located here deserve further investigation.

---

# Temporary Directories

Inspect:

```text
%Temp%

%LocalAppData%

%AppData%
```

Look for:

- recently created executables;
- unknown scripts;
- suspicious filenames.

---

# Running Processes

Use:

- Task Manager
- Process Explorer
- Autoruns

Investigate processes executing from:

```text
AppData

Temp

Downloads
```

These locations are uncommon for legitimate Windows applications.

---

# Scheduled Tasks

Review scheduled tasks using:

```cmd
schtasks /query
```

Look for:

- unknown task names;
- recently created tasks;
- executables stored in user directories.

---

# USB Artifacts

Signs of an infected USB include:

- folders suddenly disappear;
- USB-Explorer.exe appears;
- executable icons imitate folders;
- every connected computer becomes infected.

---

# Detection Checklist

Use the following checklist during investigations.

| Check | Status |
|--------|--------|
|Original folders hidden|⬜|
|USB-Explorer.exe present|⬜|
|Unknown executable at USB root|⬜|
|Repeated USB infections|⬜|
|Suspicious AppData executable|⬜|
|Unknown startup entry|⬜|
|Unknown scheduled task|⬜|

---

# Incident Response Checklist

If these indicators are present:

- Disconnect the computer from the network.
- Do not execute suspicious files.
- Perform a full antivirus scan.
- Clean the host computer before cleaning USB drives.
- Restore file attributes.
- Delete malicious executables.
- Verify that persistence has been removed.

---

# False Positives

Some legitimate software stores files inside:

```text
AppData

Temp
```

Therefore:

Finding an executable in these directories **alone** is not sufficient to conclude that a system is infected.

Investigators should always correlate multiple indicators before making a decision.

---

# Confidence Levels

| Indicator | Confidence |
|-----------|------------|
|USB-Explorer.exe|High|
|Hidden original folders|High|
|Folder named MAYUNDO|Medium|
|Registry persistence|Low (Unconfirmed)|
|Scheduled Task|Low (Unconfirmed)|

---

# Key Findings

The strongest indicators currently associated with MAYUNDO are:

✅ Hidden original folders

✅ Fake executable placed at the USB root

✅ Automatic infection of newly connected USB drives

Additional forensic analysis would be required to identify hashes, digital signatures, network indicators, or command-and-control infrastructure.

---

# Next Document

➡ **[06-Removal-Guide.md](06-Removal-Guide.md)**

The next document provides a complete step-by-step procedure to safely remove the malware, recover hidden files, and prevent reinfection without formatting the USB drive.