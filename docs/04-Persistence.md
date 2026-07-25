# Persistence Mechanisms

> [!IMPORTANT]
> Persistence refers to the techniques used by malware to remain active after a system reboot.
>
> This document distinguishes between:
>
> - 🟢 **Observed**: behaviors confirmed during field observations.
> - 🟡 **Common Technique**: persistence mechanisms commonly used by USB worms but **not yet confirmed** for MAYUNDO.
>
> Additional reverse engineering would be required to confirm every persistence mechanism used by a specific MAYUNDO sample.

---

# Table of Contents

- [What is Persistence?](#what-is-persistence)
- [Observed Behavior](#observed-behavior)
- [Common Persistence Techniques](#common-persistence-techniques)
- [Where to Investigate](#where-to-investigate)
- [Detection Tips](#detection-tips)
- [Incident Response](#incident-response)
- [Summary](#summary)

---

# What is Persistence?

Persistence is the ability of malware to survive after:

- a reboot;
- user logoff;
- Windows restart.

Without persistence, malware disappears once the infected process stops.

Persistent malware automatically launches again when Windows starts.

---

# Why Persistence Matters

Imagine the following scenario.

```text
User executes malware

↓

Computer becomes infected

↓

Computer is restarted

↓

Malware launches automatically

↓

USB propagation continues
```

If persistence succeeds, the user may believe the malware was removed even though it is still active.

---

# Observed Behavior

During field observations, infected computers continued infecting newly connected USB drives even after reboot.

This strongly suggests that the malware establishes some form of persistence.

However, the exact persistence mechanism has **not yet been confirmed through reverse engineering**.

Therefore:

|Behavior|Status|
|---------|------|
|Persists after reboot|🟢 Observed|
|Registry modification|🟡 Not yet confirmed|
|Scheduled Task|🟡 Not yet confirmed|
|Startup Folder|🟡 Not yet confirmed|
|Windows Service|🔴 Not observed|

---

# Common Persistence Techniques

The following techniques are frequently used by USB worms and should be investigated when analyzing MAYUNDO samples.

## 1. Registry Run Keys

Windows allows applications to start automatically through Registry keys.

Common locations include:

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Run

HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

A malware may create an entry pointing to its executable.

---

## 2. Startup Folder

Windows automatically launches every shortcut placed inside the Startup folder.

Typical locations include:

```text
%AppData%\Microsoft\Windows\Start Menu\Programs\Startup
```

This technique is simple and commonly used.

---

## 3. Scheduled Tasks

Another common technique consists of creating a Scheduled Task.

This allows malware to execute:

- at logon;
- at startup;
- every hour;
- at a specific time.

Analysts can inspect scheduled tasks using:

```powershell
schtasks /query
```

---

## 4. Winlogon

Some malware modifies Windows authentication settings.

Registry example:

```text
HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon
```

This technique is more advanced and has **not been observed** in MAYUNDO.

---

## 5. WMI Event Subscription

Advanced malware sometimes uses Windows Management Instrumentation (WMI).

Advantages include:

- stealth;
- difficult detection;
- persistence without startup folders.

No evidence currently indicates that MAYUNDO uses WMI.

---

## 6. Startup Scripts

Malware may also execute through:

- batch files;
- VBScript;
- PowerShell scripts.

Again, this remains unconfirmed for the analyzed sample.

---

# Where to Investigate

During incident response, analysts should inspect the following locations.

## Registry

```text
HKCU\Software\Microsoft\Windows\CurrentVersion\Run

HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

---

## Startup Folder

```text
%AppData%\Microsoft\Windows\Start Menu\Programs\Startup
```

---

## Temporary Directories

```text
%Temp%

%LocalAppData%

%AppData%
```

---

## Scheduled Tasks

Use:

```cmd
schtasks /query
```

to inspect suspicious scheduled jobs.

---

## Running Processes

Inspect:

- Task Manager
- Process Explorer
- Autoruns (Sysinternals)

Look for unknown executables launched from unusual directories.

---

# Detection Tips

Signs suggesting persistence may include:

- malware returns after reboot;
- unknown startup applications;
- repeated USB infections;
- suspicious executables in AppData;
- unexpected scheduled tasks.

---

# Incident Response Recommendations

If persistence is suspected:

1. Disconnect the computer from the network.

2. Perform a full antivirus scan.

3. Remove detected threats.

4. Inspect startup locations.

5. Inspect scheduled tasks.

6. Reboot the computer.

7. Verify that no suspicious process relaunches.

Only after confirming that the host system is clean should removable USB drives be disinfected.

---

# Summary

Current observations indicate that MAYUNDO survives system reboot on some infected machines.

However, the exact persistence mechanism remains to be confirmed.

Until reverse engineering is completed, analysts should treat Registry Run Keys, Startup folders, and Scheduled Tasks as **investigation targets rather than confirmed behaviors**.

Maintaining this distinction between confirmed observations and hypotheses is essential for accurate malware documentation.

---

# Next Document

➡ **[05-Indicators-of-Compromise.md](05-Indicators-of-Compromise.md)**

The next chapter lists common Indicators of Compromise (IoCs), including suspicious files, folders, Registry locations, and forensic artifacts that may help identify an infected system.