# NetworkWalks Week 1 — Cybersecurity Lab Setup

**Program:** NetworkWalks Cybersecurity and Ethical Hacking Internship  
**Batch:** B084  
**Project:** WK1-PM1 — VirtualBox and Kali Linux Lab Setup  
**Author:** Muhammad Abdal Khan

This repository documents my required Week 1 lab setup and the three optional projects I completed: Windows 10 virtualization, Android-x86 virtualization, and six SOC/Wireshark browser labs.

## Project Overview

| Type | Project | Description |
|---|---|---|
| **Required Week 1 task** | Kali Linux lab setup | Configure VirtualBox, Kali Linux, the NAT Network, host–guest integration, connectivity, and a VM snapshot. |
| Optional project 1 | Windows 10 VM | Install Windows 10 in VirtualBox and test network connectivity with Kali Linux. |
| Optional project 2 | Android-x86 VM | Install Android-x86 in VirtualBox and test network connectivity with Kali Linux. |
| Optional project 3 | SOC/Wireshark labs | Complete six browser-based network traffic investigation labs. |

**Screenshots:** [Open the screenshots folder](https://github.com/mabdalkhan/NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main/screenshots)

---

# Part 1 — Required Week 1 Assignment

## 1. Kali Linux Lab Setup

### Objective

Set up Kali Linux in Oracle VirtualBox, configure the required NAT Network and static IP address, enable host–guest integration, test connectivity, and create a VM snapshot.

### Configuration

| Setting | Required value |
|---|---|
| Virtualization platform | Oracle VirtualBox |
| Virtual machine | Kali Linux |
| Network type | NAT Network |
| NAT Network name | `NatNetwork` |
| Network subnet | `10.0.0.0/24` |
| Kali IPv4 address | `10.0.0.2/24` |
| Default gateway | `10.0.0.1` |
| DNS server | `8.8.8.8` or the DNS value actually configured |
| Shared Clipboard | Bidirectional |
| Drag-and-Drop | Bidirectional |
| Shared folder | Host folder named `downloads` |
| Snapshot | `WK1-PM1-Kali-Lab-Configured` |

### Work Completed

1. Installed VirtualBox and imported Kali Linux.
2. Created the `NatNetwork` NAT Network with the required subnet.
3. Connected the Kali VM to the NAT Network.
4. Configured the required static IPv4 address, gateway, and DNS settings.
5. Enabled bidirectional shared clipboard and drag-and-drop.
6. Configured the shared folder between Windows and Kali Linux.
7. Checked IP addressing and routing.
8. Tested gateway, external IP, DNS, and Internet connectivity.
9. Tested shared-folder access and host–guest integration.
10. Created a baseline snapshot of the Kali VM.

### Evidence — Required Week 1 Task

The screenshots for the main assignment are stored in the repository's `screenshots` folder.

**[Open Week 1 screenshots](https://github.com/mabdalkhan/NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main/screenshots)**

The evidence covers the NAT Network, Kali adapter, clipboard and drag-and-drop settings, shared-folder configuration, IP configuration, connectivity checks, shared-folder test, and VM snapshot.

---

# Part 2 — Optional Projects

## 2. Optional Project: Windows 10 Virtual Machine

### Objective

Install Windows 10 in VirtualBox, connect it to the same NAT Network as Kali Linux, set its required IPv4 configuration, and test connectivity.

### Network Configuration

| Setting | Target value |
|---|---|
| VM name | `Windows10-Lab` |
| Network type | NAT Network |
| IPv4 address | `10.0.0.10/24` |
| Gateway | `10.0.0.1` |
| DNS | `8.8.8.8` |

### Work Completed

1. Obtained the Windows 10 installation ISO.
2. Created and configured the Windows 10 VM.
3. Installed Windows 10.
4. Connected the VM to `NatNetwork`.
5. Configured its IPv4 settings.
6. Tested Windows-to-Kali connectivity.
7. Tested external IP connectivity.
8. Tested Kali-to-Windows connectivity.

### Connectivity Commands

From Windows Command Prompt:

```cmd
ping 10.0.0.2
ping 8.8.8.8
```

From Kali Linux:

```bash
ping -c 4 10.0.0.10
```

### Evidence — Windows 10

**[Open screenshots folder](https://github.com/mabdalkhan/NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main/screenshots)**

The relevant evidence includes the Windows VM settings, IPv4 configuration, Windows-to-Kali test, external connectivity test, and Kali-to-Windows test.

---

## 3. Optional Project: Android-x86 Virtual Machine

### Objective

Install Android-x86 in VirtualBox, connect it to the shared NAT Network, configure the required IPv4 address, and test connectivity with Kali Linux and the Internet.

### Network Configuration

| Setting | Target value |
|---|---|
| VM name | `Android9-Lab` |
| Operating system | Android-x86 9.0 |
| Network type | NAT Network |
| IPv4 address | `10.0.0.9/24` |
| Gateway | `10.0.0.1` |
| DNS | `8.8.8.8` |

### Work Completed

1. Obtained the Android-x86 ISO.
2. Created and configured the Android VM.
3. Installed Android-x86.
4. Connected it to `NatNetwork`.
5. Configured its IPv4 settings.
6. Tested Android-to-Kali connectivity.
7. Tested external IP connectivity.
8. Tested Kali-to-Android connectivity.

### Connectivity Commands

From Android, using an available terminal application:

```bash
ping 10.0.0.2
ping 8.8.8.8
```

From Kali Linux:

```bash
ping -c 4 10.0.0.9
```

### Evidence — Android-x86

**[Open screenshots folder](https://github.com/mabdalkhan/NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main/screenshots)**

The relevant evidence includes the Android VM configuration, desktop, IPv4 settings, Android-to-Kali test, external connectivity test, and Kali-to-Android test.

---

## 4. Optional Project: SOC/Wireshark — Six Labs

### Objective

Complete the six NetworkWalks browser-based SOC labs, each containing ten tasks involving analysis of supplied network traffic captures.

### Labs Completed

1. **Identify the Attacker's IP** — inspect the capture to identify the suspected attacker's address.
2. **Follow TCP Stream 1** — reconstruct and inspect a TCP conversation.
3. **Follow TCP Stream, Part 2** — continue TCP stream analysis and investigate hidden data.
4. **HTTP Plain Text Credentials** — inspect the supplied capture for credentials transmitted over HTTP.
5. **Catch the Brute Force Attacker** — investigate repeated authentication attempts.
6. **Catch the Call Scammer** — investigate the supplied capture and call recording.

### Skills Practised

- Network traffic analysis
- Source IP identification
- TCP stream reconstruction
- HTTP traffic inspection
- Identification of clear-text credentials
- Analysis of repeated login attempts
- Investigation of a VoIP-related scenario

### Evidence — SOC/Wireshark

**[Open screenshots folder](https://github.com/mabdalkhan/NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/tree/main/screenshots)**

The relevant evidence includes completion screenshots from the six labs. Where one image does not show all tasks for a lab, include additional screenshots as needed.

---

## Verification Summary

| Area | Checks performed |
|---|---|
| Kali Linux | IP address, routing, gateway, Internet and DNS connectivity |
| VirtualBox NAT Network | Network prefix and VM adapter configuration |
| Shared folder | Host-to-Kali file access |
| Clipboard and drag-and-drop | Host–guest integration tests |
| Snapshot | Saved Kali baseline snapshot |
| Windows 10 | Connectivity to Kali and external IP |
| Android-x86 | Connectivity to Kali and external IP |
| SOC/Wireshark | Completion of the six browser-based labs |

## Troubleshooting Notes

The main checks during troubleshooting were the NAT Network selection, IP address and subnet, duplicate IP conflicts, gateway and DNS settings, connectivity versus DNS resolution, and host–guest integration support. Any specific issue and fix should be documented using the actual symptoms and results from the lab.

## Repository Layout

```text
NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/
├── README.md
└── screenshots/
    └── [screenshots uploaded to this folder]
```

## Conclusion

I completed the required Week 1 Kali Linux lab setup and the additional Windows 10, Android-x86, and SOC/Wireshark projects. The work covered virtual machine configuration, static IP setup, connectivity testing, shared-folder and guest integration, snapshots, and network traffic investigation.
