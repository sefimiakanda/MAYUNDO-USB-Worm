# References

> [!NOTE]
> This repository combines field observations with publicly available cybersecurity knowledge to document the MAYUNDO USB Worm from a defensive perspective.

---

# Standards and Frameworks

## MITRE ATT&CK®

MITRE ATT&CK is a globally recognized knowledge base describing adversarial tactics and techniques.

https://attack.mitre.org/

---

## MITRE D3FEND

Knowledge base for defensive cybersecurity techniques.

https://d3fend.mitre.org/

---

## NIST Cybersecurity Framework (CSF)

National Institute of Standards and Technology.

https://www.nist.gov/cyberframework

---

# Microsoft Documentation

## Microsoft Defender

https://learn.microsoft.com/microsoft-365/security/defender/

---

## Windows Security

https://learn.microsoft.com/windows/security/

---

## Windows Command Reference

https://learn.microsoft.com/windows-server/administration/windows-commands/

---

# Malware Analysis Resources

## Malware Traffic Analysis

https://www.malware-traffic-analysis.net/

Provides malware traffic captures and educational exercises.

---

## ANY.RUN Interactive Sandbox

https://any.run/

Interactive malware analysis platform.

---

## Hybrid Analysis

https://www.hybrid-analysis.com/

Online malware analysis service.

---

## VirusTotal

https://www.virustotal.com/

Used to compare antivirus detections and malware reputation.

---

# Digital Forensics

## Sysinternals Suite

https://learn.microsoft.com/sysinternals/

Includes:

- Process Explorer
- Autoruns
- Procmon

Useful during Windows malware investigations.

---

## FTK Imager

https://accessdata.com/

Widely used forensic imaging software.

---

# Windows Utilities

## Microsoft Defender Offline Scan

Useful for removing persistent malware.

---

## Command Prompt

Important command used in this project:

```cmd
attrib -h -r -s /s /d *.*
```

Used to restore visibility of hidden files.

---

# Academic References

Readers are encouraged to consult current research papers on:

- USB malware
- Windows persistence
- Social engineering
- Digital forensics
- Incident response

through databases such as:

- IEEE Xplore
- ACM Digital Library
- SpringerLink
- Google Scholar

---

# Repository Documents

This documentation consists of:

| Document | Description |
|----------|-------------|
|01-Introduction|Project overview|
|02-Technical-Analysis|Technical behavior|
|03-Infection-Workflow|Attack chain|
|04-Persistence|Persistence mechanisms|
|05-Indicators-of-Compromise|Detection artifacts|
|06-Removal-Guide|Recovery procedure|
|07-Prevention|Security recommendations|
|08-FAQ|Frequently Asked Questions|

---

# Disclaimer

This repository is intended exclusively for:

- cybersecurity education;
- malware awareness;
- defensive security research;
- incident response.

No offensive or malicious use is intended or supported.

---

# Acknowledgements

This project was inspired by field observations of USB malware infections affecting students, public computers, and removable media users.

Its goal is to improve cybersecurity awareness and encourage responsible defensive practices within the community.