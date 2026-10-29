# 🔐 NetworkWalks Week 1 — Cybersecurity Lab Setup & SOC Practice

A hands-on cybersecurity project completed as part of the **NetworkWalks Cybersecurity and Ethical Hacking Internship — Batch B084**.

This repository documents the required Week 1 cybersecurity lab setup using Oracle VirtualBox and Kali Linux, along with three optional projects covering Windows 10 virtualization, Android-x86 virtualization, and SOC/Wireshark practice.

The repository separates the mandatory assignment from the optional extensions to make the implementation, documentation, and supporting evidence easier to review.

## 📌 Project Overview

The main objective was to establish a virtual cybersecurity testing environment using VirtualBox and Kali Linux, configure the required network settings, verify connectivity, enable host–guest integration, and create a baseline virtual machine snapshot.

The optional projects extended the lab with additional operating systems and practical network traffic investigation exercises.

### Project Components

| Category              | Project                     | Purpose                                                     |
| --------------------- | --------------------------- | ----------------------------------------------------------- |
| **Required — Week 1** | Kali Linux Lab Setup        | Configure and verify the primary cybersecurity lab          |
| Optional Project 1    | Windows 10 Virtual Machine  | Extend the lab with a Windows environment                   |
| Optional Project 2    | Android-x86 Virtual Machine | Add an Android-based virtual machine                        |
| Optional Project 3    | SOC/Wireshark Practice      | Investigate network traffic in six educational browser labs |

---

# PART A — REQUIRED WEEK 1 ASSIGNMENT

## 1. Kali Linux Cybersecurity Lab

### Objective

Build a controlled virtual cybersecurity testing environment using Oracle VirtualBox and Kali Linux.

### Tools and Technologies

* Oracle VirtualBox
* Kali Linux
* VirtualBox NAT Network
* NetworkManager
* Linux networking commands
* Virtual machine snapshots
* Shared folders and host–guest integration

### Network Configuration

The lab was configured according to the NetworkWalks Week 1 project requirements.

| Parameter                  | Configuration                                     |
| -------------------------- | ------------------------------------------------- |
| Virtualization platform    | Oracle VirtualBox                                 |
| Virtual machine            | Kali Linux                                        |
| Network type               | NAT Network                                       |
| Network name               | `NatNetwork`                                      |
| IPv4 subnet                | `10.0.0.0/24`                                     |
| Required Kali IPv4 address | `10.0.0.2/24`                                     |
| Gateway                    | `10.0.0.1`                                        |
| DNS server                 | `8.8.8.8`, or the alternative actually configured |
| Shared Clipboard           | Bidirectional                                     |
| Drag-and-Drop              | Bidirectional                                     |
| Shared folder              | Windows host folder named `downloads`             |
| Recovery point             | Virtual machine snapshot                          |

### Implementation

The main project involved:

1. Installing Oracle VirtualBox and preparing the virtualization environment.
2. Importing the Kali Linux virtual machine.
3. Creating the custom NAT Network.
4. Configuring the Kali virtual network adapter.
5. Setting the required static IPv4 address.
6. Configuring the gateway and DNS settings.
7. Enabling bidirectional clipboard and drag-and-drop.
8. Configuring the host shared folder.
9. Testing the IP configuration and routing.
10. Checking gateway connectivity, Internet access, and DNS resolution.
11. Testing shared-folder access and host–guest integration.
12. Creating a baseline snapshot of the configured virtual machine.

### Verification

The lab verification process included checking the assigned IPv4 address, routing table, network connectivity, Internet access, shared-folder functionality, and saved virtual machine snapshot.

The screenshots listed below provide supporting evidence for the required assignment.

## 2. Required Week 1 Screenshots

**Screenshot directory:** `screenshots/kali/`

| No. | Screenshot                                                                     | Evidence                                |
| --- | ------------------------------------------------------------------------------ | --------------------------------------- |
| 1   | [NAT Network Configuration](screenshots/kali/01-nat-network-configuration.png) | Network name, subnet, and DHCP settings |
| 2   | [Kali Network Adapter](screenshots/kali/02-kali-network-adapter.png)           | Virtual network adapter configuration   |
| 3   | [Clipboard and Drag-and-Drop](screenshots/kali/03-clipboard-dragdrop.png)      | Host–guest integration settings         |
| 4   | [Shared Folder Configuration](screenshots/kali/04-shared-folder.png)           | Shared-folder setup                     |
| 5   | [Kali IP Configuration](screenshots/kali/05-kali-ip-configuration.png)         | Static IPv4 settings                    |
| 6   | [IP and Route Verification](screenshots/kali/06-ip-and-route-verification.png) | Actual IP address and routing output    |
| 7   | [Internet Connectivity](screenshots/kali/07-internet-connectivity.png)         | Connectivity test results               |
| 8   | [Shared Folder Test](screenshots/kali/08-shared-folder-test.png)               | Evidence of shared-folder access        |
| 9   | [Kali VM Snapshot](screenshots/kali/09-kali-snapshot.png)                      | Saved baseline snapshot                 |

*The screenshot paths must match the files uploaded to the repository. Each image should demonstrate the corresponding configuration or test.*

---

# PART B — OPTIONAL PROJECTS

The following projects were completed as additional practical exercises alongside the mandatory Week 1 assignment.

They extend the lab and provide further experience with virtualization, networking, and network traffic investigation.

# 3. Optional Project 1 — Windows 10 Virtual Machine

## Objective

Install Windows 10 inside VirtualBox, connect it to the same NAT Network as Kali Linux, configure the required network settings, and test connectivity.

### Target Configuration

| Parameter        | Value           |
| ---------------- | --------------- |
| Virtual machine  | `Windows10-Lab` |
| Operating system | Windows 10      |
| Network type     | NAT Network     |
| IPv4 address     | `10.0.0.10/24`  |
| Gateway          | `10.0.0.1`      |
| Preferred DNS    | `8.8.8.8`       |

### Implementation

1. Obtained the Windows 10 installation ISO from Microsoft's official source.
2. Created the Windows 10 virtual machine.
3. Configured its virtual hardware and virtual disk.
4. Installed Windows 10.
5. Connected the VM to the existing `NatNetwork`.
6. Configured the required static IPv4 address.
7. Tested connectivity from Windows to Kali Linux.
8. Tested external IP connectivity.
9. Tested connectivity from Kali to Windows.

### Connectivity Verification

From Windows Command Prompt:

```cmd
ping 10.0.0.2
ping 8.8.8.8
```

From Kali Linux:

```bash
ping -c 4 10.0.0.10
```

The actual results should be interpreted using the captured terminal output. Ping failures may have several causes, including firewall rules or restrictions on ICMP traffic.

### Windows 10 Screenshot Evidence

**Screenshot directory:** `screenshots/windows10/`

| No. | Screenshot                                                                        | Evidence                   |
| --- | --------------------------------------------------------------------------------- | -------------------------- |
| 1   | [Windows VM Configuration](screenshots/windows10/01-windows-vm-configuration.png) | VM settings                |
| 2   | [Windows IP Configuration](screenshots/windows10/02-windows-ip-configuration.png) | Static IPv4 settings       |
| 3   | [Windows-to-Kali Ping](screenshots/windows10/03-windows-to-kali-ping.png)         | Connectivity test          |
| 4   | [Windows Internet Test](screenshots/windows10/04-windows-internet-test.png)       | External connectivity test |
| 5   | [Kali-to-Windows Ping](screenshots/windows10/05-kali-to-windows-ping.png)         | Reverse connectivity test  |

---

# 4. Optional Project 2 — Android-x86 Virtual Machine

## Objective

Install Android-x86 in VirtualBox, connect it to the shared NAT Network, configure its IP address, and test connectivity with Kali Linux and the Internet.

### Target Configuration

| Parameter        | Value           |
| ---------------- | --------------- |
| Virtual machine  | `Android9-Lab`  |
| Operating system | Android-x86 9.0 |
| Network type     | NAT Network     |
| IPv4 address     | `10.0.0.9/24`   |
| Gateway          | `10.0.0.1`      |
| DNS server       | `8.8.8.8`       |

### Implementation

1. Obtained the Android-x86 ISO from the official project source.
2. Created the Android virtual machine.
3. Configured memory, virtual disk, and display settings.
4. Installed Android-x86.
5. Connected the VM to the same `NatNetwork`.
6. Configured the required static IPv4 address.
7. Tested connectivity from Android to Kali Linux.
8. Tested external IP connectivity.
9. Tested connectivity from Kali to Android.

### Connectivity Verification

From Android, using an available terminal application:

```bash
ping 10.0.0.2
ping 8.8.8.8
```

From Kali Linux:

```bash
ping -c 4 10.0.0.9
```

The results should be supported by the actual captured evidence.

### Android-x86 Screenshot Evidence

**Screenshot directory:** `screenshots/android/`

| No. | Screenshot                                                                      | Evidence                    |
| --- | ------------------------------------------------------------------------------- | --------------------------- |
| 1   | [Android VM Configuration](screenshots/android/01-android-vm-configuration.png) | Virtual machine settings    |
| 2   | [Android Desktop](screenshots/android/02-android-desktop.png)                   | Running Android environment |
| 3   | [Android IP Configuration](screenshots/android/03-android-ip-configuration.png) | Static IPv4 configuration   |
| 4   | [Android-to-Kali Ping](screenshots/android/04-android-to-kali-ping.png)         | Connectivity test           |
| 5   | [Android Internet Test](screenshots/android/05-android-internet-test.png)       | External connectivity test  |
| 6   | [Kali-to-Android Ping](screenshots/android/06-kali-to-android-ping.png)         | Reverse connectivity test   |

---

# 5. Optional Project 3 — SOC/Wireshark Practice

## Objective

Complete six educational, browser-based SOC labs provided by NetworkWalks.

Each lab contains ten tasks focused on investigating supplied network traffic captures.

### Lab 1 — Identify the Attacker's IP

Investigate the provided traffic capture and identify the IP address associated with the suspected attacker.

### Lab 2 — Follow TCP Stream 1

Reconstruct a TCP conversation and examine the data exchanged between endpoints.

### Lab 3 — Follow TCP Stream, Part 2

Continue TCP stream analysis using another capture and investigate the hidden data in the exercise.

### Lab 4 — HTTP Plain Text Credentials

Examine the supplied capture to identify credentials transmitted in clear text over HTTP.

### Lab 5 — Catch the Brute Force Attacker

Investigate repeated authentication attempts and identify the source associated with the activity.

### Lab 6 — Catch the Call Scammer

Investigate the supplied capture and call recording to identify the suspected scammer.

### Skills Practised

* Identifying suspicious IP addresses.
* Reconstructing TCP conversations.
* Examining application-layer traffic.
* Recognizing insecure transmission of credentials.
* Identifying repeated login attempts.
* Investigating a VoIP-related scam scenario.
* Recording findings from supplied evidence.

The exercises provide introductory practical experience in network traffic analysis and security operations.

### SOC/Wireshark Screenshot Evidence

**Screenshot directory:** `screenshots/wireshark/`

| No. | Screenshot                                                                             | Evidence                             |
| --- | -------------------------------------------------------------------------------------- | ------------------------------------ |
| 1   | [Identify Attacker's IP](screenshots/wireshark/01-identify-attacker-ip.png)            | Attacker identification lab          |
| 2   | [Follow TCP Stream 1](screenshots/wireshark/02-follow-tcp-stream-1.png)                | TCP conversation analysis            |
| 3   | [Follow TCP Stream, Part 2](screenshots/wireshark/03-follow-tcp-stream-part-2.png)     | Additional stream analysis           |
| 4   | [HTTP Plain Text Credentials](screenshots/wireshark/04-http-plaintext-credentials.png) | Credential investigation             |
| 5   | [Brute Force Attacker](screenshots/wireshark/05-brute-force-attacker.png)              | Repeated login attempt investigation |
| 6   | [Call Scammer Investigation](screenshots/wireshark/06-call-scammer-investigation.png)  | VoIP-related investigation           |

These exercises were performed in the designated educational environment. The supplied captures are training material, not authorization to inspect unrelated networks.

---

# 6. Overall Project Verification

| Area                   | Verification focus                               |
| ---------------------- | ------------------------------------------------ |
| VirtualBox NAT Network | Network name, subnet, and adapter settings       |
| Kali Linux             | IP address, routing, and connectivity            |
| Windows 10             | Connectivity with Kali and external connectivity |
| Android-x86            | Connectivity with Kali and external connectivity |
| Shared folder          | Host–guest folder access                         |
| Clipboard              | Clipboard transfer between host and guest        |
| Drag-and-drop          | Supported file transfer                          |
| VM snapshot            | Saved recovery point                             |
| SOC/Wireshark labs     | Completion of the six educational exercises      |

The screenshots provide supporting evidence for the documented implementation and test results.

## 7. Troubleshooting and Lessons Learned

This project highlighted the importance of verifying actual network behavior instead of relying only on graphical configuration settings.

Important troubleshooting considerations included:

* Selecting the correct NAT Network.
* Verifying the IPv4 address and subnet.
* Checking for duplicate IP address assignments.
* Confirming gateway and DNS settings.
* Distinguishing external connectivity problems from DNS problems.
* Checking host–guest integration support.
* Verifying shared-folder permissions.
* Investigating firewall restrictions when connectivity tests fail.

Any specific issue and resolution should be documented using the real symptoms, troubleshooting actions, and results observed during implementation.

## 8. Repository Structure

The screenshot directory is organized into separate folders for the required assignment and optional projects.

```text
NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/
│
├── README.md
│
└── screenshots/
    ├── kali/
    │   ├── 01-nat-network-configuration.png
    │   ├── 02-kali-network-adapter.png
    │   ├── 03-clipboard-dragdrop.png
    │   └── ...
    │
    ├── windows10/
    │   ├── 01-windows-vm-configuration.png
    │   └── ...
    │
    ├── android/
    │   ├── 01-android-vm-configuration.png
    │   └── ...
    │
    └── wireshark/
        ├── 01-identify-attacker-ip.png
        └── ...
```

The repository contains project documentation and screenshots rather than complete virtual machine disk images.

## 9. Conclusion

The required Week 1 project established a virtual cybersecurity lab using Oracle VirtualBox and Kali Linux.

The additional Windows 10 and Android-x86 projects extended the environment, while the six SOC/Wireshark labs provided structured practice in examining network traffic and investigating common security scenarios.

Together, these exercises provided practical exposure to virtualization, network configuration, connectivity verification, troubleshooting, and introductory security operations.

The project is documented as a technical portfolio entry with separate sections for the required assignment and the optional extensions.

**Program:** NetworkWalks Cybersecurity and Ethical Hacking Internship
**Batch:** B084
**Assignment:** Week 1 — Project Module 1
**Author:** Muhammad Abdal Khan
