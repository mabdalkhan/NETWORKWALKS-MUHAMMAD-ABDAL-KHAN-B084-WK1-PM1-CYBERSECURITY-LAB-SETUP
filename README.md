# NetworkWalks Week 1 — Cybersecurity Lab Setup

This repository contains my completed Week 1 project for the **NetworkWalks Cybersecurity and Ethical Hacking Internship — Batch B084**.

The main assignment involved setting up Kali Linux in VirtualBox and configuring the virtual network, connectivity, shared folders, and VM snapshot. I also completed three optional projects covering Windows 10, Android-x86, and SOC/Wireshark practice.

## Project Overview

| Section            | Project                     | Status    |
| ------------------ | --------------------------- | --------- |
| Main Assignment    | Kali Linux Lab Setup        | Completed |
| Optional Project 1 | Windows 10 Virtual Machine  | Completed |
| Optional Project 2 | Android-x86 Virtual Machine | Completed |
| Optional Project 3 | SOC/Wireshark — Six Labs    | Completed |

---

# Part 1 — Main Week 1 Assignment

## 1. Kali Linux Lab Setup

### Objective

Set up a Kali Linux virtual machine in Oracle VirtualBox, configure the required NAT Network, verify connectivity, enable host–guest integration, and create a VM snapshot.

### Tools Used

* Oracle VirtualBox
* Kali Linux
* VirtualBox NAT Network
* NetworkManager
* Linux networking commands

### Network Configuration

| Parameter        | Configuration                 |
| ---------------- | ----------------------------- |
| Network Name     | `NatNetwork`                  |
| Network Type     | NAT Network                   |
| Subnet           | `10.0.0.0/24`                 |
| Kali Linux IP    | `10.0.0.2/24`                 |
| Default Gateway  | `10.0.0.1`                    |
| DNS Server       | `8.8.8.8`                     |
| Shared Clipboard | Bidirectional                 |
| Drag-and-Drop    | Bidirectional                 |
| Shared Folder    | `downloads`                   |
| VM Snapshot      | `WK1-PM1-Kali-Lab-Configured` |

### Work Completed

1. Installed VirtualBox and imported Kali Linux.
2. Created the required NAT Network.
3. Configured the Kali virtual network adapter.
4. Set the required static IPv4 address.
5. Configured the gateway and DNS settings.
6. Enabled shared clipboard and drag-and-drop.
7. Configured the shared folder between Windows and Kali.
8. Checked the IP address and routing configuration.
9. Tested network connectivity and Internet access.
10. Checked shared-folder access and host–guest integration.
11. Created a snapshot of the configured Kali Linux VM.

### Screenshots — Main Week 1 Assignment

All screenshots for the required assignment are organized in `screenshots/kali/`.

| No. | Screenshot                                                                     | Description                           |
| --- | ------------------------------------------------------------------------------ | ------------------------------------- |
| 1   | [NAT Network Configuration](screenshots/kali/01-nat-network-configuration.png) | NAT Network settings                  |
| 2   | [Kali Network Adapter](screenshots/kali/02-kali-network-adapter.png)           | Virtual network adapter configuration |
| 3   | [Clipboard and Drag-and-Drop](screenshots/kali/03-clipboard-dragdrop.png)      | Host–guest integration settings       |
| 4   | [Shared Folder](screenshots/kali/04-shared-folder.png)                         | Shared-folder configuration           |
| 5   | [Kali IP Configuration](screenshots/kali/05-kali-ip-configuration.png)         | Static IPv4 settings                  |
| 6   | [IP and Route Verification](screenshots/kali/06-ip-and-route-verification.png) | IP address and routing output         |
| 7   | [Internet Connectivity](screenshots/kali/07-internet-connectivity.png)         | Connectivity test results             |
| 8   | [Shared Folder Test](screenshots/kali/08-shared-folder-test.png)               | Shared-folder access                  |
| 9   | [Kali VM Snapshot](screenshots/kali/09-kali-snapshot.png)                      | Saved VM snapshot                     |

---

# Part 2 — Optional Projects

The following projects were completed in addition to the main Week 1 assignment.

## 2. Windows 10 Virtual Machine

### Objective

Install Windows 10 in VirtualBox, connect it to the same NAT Network as Kali Linux, configure the network, and test connectivity between the two machines.

### Configuration

| Parameter        | Value           |
| ---------------- | --------------- |
| Virtual Machine  | `Windows10-Lab` |
| Operating System | Windows 10      |
| Network Type     | NAT Network     |
| IPv4 Address     | `10.0.0.10/24`  |
| Gateway          | `10.0.0.1`      |
| DNS              | `8.8.8.8`       |

### Work Completed

1. Obtained the Windows 10 installation ISO.
2. Created and configured the virtual machine.
3. Installed Windows 10.
4. Connected the VM to `NatNetwork`.
5. Configured the required IPv4 settings.
6. Tested connectivity from Windows to Kali.
7. Tested external IP connectivity.
8. Tested connectivity from Kali to Windows.

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

### Screenshots — Windows 10

All Windows 10 evidence is organized in `screenshots/windows10/`.

| No. | Screenshot                                                                        | Description               |
| --- | --------------------------------------------------------------------------------- | ------------------------- |
| 1   | [Windows VM Configuration](screenshots/windows10/01-windows-vm-configuration.png) | Virtual machine settings  |
| 2   | [Windows IP Configuration](screenshots/windows10/02-windows-ip-configuration.png) | IPv4 settings             |
| 3   | [Windows-to-Kali Ping](screenshots/windows10/03-windows-to-kali-ping.png)         | Connectivity test         |
| 4   | [Windows Internet Test](screenshots/windows10/04-windows-internet-test.png)       | External connectivity     |
| 5   | [Kali-to-Windows Ping](screenshots/windows10/05-kali-to-windows-ping.png)         | Reverse connectivity test |

---

## 3. Android-x86 Virtual Machine

### Objective

Install Android-x86 in VirtualBox, connect it to the shared NAT Network, configure the required IP address, and test connectivity with Kali Linux.

### Configuration

| Parameter        | Value           |
| ---------------- | --------------- |
| Virtual Machine  | `Android9-Lab`  |
| Operating System | Android-x86 9.0 |
| Network Type     | NAT Network     |
| IPv4 Address     | `10.0.0.9/24`   |
| Gateway          | `10.0.0.1`      |
| DNS              | `8.8.8.8`       |

### Work Completed

1. Obtained the Android-x86 ISO.
2. Created and configured the Android virtual machine.
3. Installed Android-x86.
4. Connected the VM to `NatNetwork`.
5. Configured the required IPv4 settings.
6. Tested connectivity between Android and Kali.
7. Tested external IP connectivity.
8. Tested connectivity from Kali to Android.

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

### Screenshots — Android-x86

All Android evidence is organized in `screenshots/android/`.

| No. | Screenshot                                                                      | Description                 |
| --- | ------------------------------------------------------------------------------- | --------------------------- |
| 1   | [Android VM Configuration](screenshots/android/01-android-vm-configuration.png) | Virtual machine settings    |
| 2   | [Android Desktop](screenshots/android/02-android-desktop.png)                   | Running Android environment |
| 3   | [Android IP Configuration](screenshots/android/03-android-ip-configuration.png) | IPv4 settings               |
| 4   | [Android-to-Kali Ping](screenshots/android/04-android-to-kali-ping.png)         | Connectivity test           |
| 5   | [Android Internet Test](screenshots/android/05-android-internet-test.png)       | External connectivity       |
| 6   | [Kali-to-Android Ping](screenshots/android/06-kali-to-android-ping.png)         | Reverse connectivity test   |

---

## 4. SOC/Wireshark — Six Labs

### Objective

Complete six NetworkWalks SOC browser labs involving network traffic analysis and investigation.

### Labs Completed

| No. | Lab                            | Main Task                                                |
| --- | ------------------------------ | -------------------------------------------------------- |
| 1   | Identify the Attacker's IP     | Identify the suspected attacker's IP address             |
| 2   | Follow TCP Stream 1            | Reconstruct and inspect a TCP conversation               |
| 3   | Follow TCP Stream, Part 2      | Continue TCP stream analysis and investigate hidden data |
| 4   | HTTP Plain Text Credentials    | Identify credentials in the supplied HTTP capture        |
| 5   | Catch the Brute Force Attacker | Investigate repeated login attempts                      |
| 6   | Catch the Call Scammer         | Analyze the supplied traffic and call recording          |

Each lab contained ten tasks.

### Skills Practised

* Network traffic investigation
* IP address identification
* TCP stream analysis
* HTTP traffic inspection
* Clear-text credential identification
* Brute-force activity investigation
* VoIP-related incident analysis

### Screenshots — SOC/Wireshark

All Wireshark evidence is organized in `screenshots/wireshark/`.

| No. | Screenshot                                                                             | Description                     |
| --- | -------------------------------------------------------------------------------------- | ------------------------------- |
| 1   | [Identify Attacker's IP](screenshots/wireshark/01-identify-attacker-ip.png)            | Attacker identification         |
| 2   | [Follow TCP Stream 1](screenshots/wireshark/02-follow-tcp-stream-1.png)                | TCP stream analysis             |
| 3   | [Follow TCP Stream, Part 2](screenshots/wireshark/03-follow-tcp-stream-part-2.png)     | Additional stream analysis      |
| 4   | [HTTP Plain Text Credentials](screenshots/wireshark/04-http-plaintext-credentials.png) | HTTP credential investigation   |
| 5   | [Brute Force Attacker](screenshots/wireshark/05-brute-force-attacker.png)              | Authentication attempt analysis |
| 6   | [Call Scammer Investigation](screenshots/wireshark/06-call-scammer-investigation.png)  | Call investigation              |

---

## 5. Troubleshooting and Key Takeaways

During this project, I worked with virtual machine configuration, network settings, static IP addressing, connectivity testing, and host–guest integration.

The main things I focused on were:

* Checking IP addresses and subnet configuration.
* Verifying the correct NAT Network was selected.
* Checking routing and gateway settings.
* Testing IP connectivity separately from DNS resolution.
* Checking shared-folder access and permissions.
* Verifying configurations through actual command output.
* Organizing screenshots and technical documentation.

Any specific issue and its solution should match the troubleshooting actually performed during the project.

## 6. Repository Structure

```text
NETWORKWALKS-MUHAMMAD-ABDAL-KHAN-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP/
│
├── README.md
│
└── screenshots/
    ├── kali/
    ├── windows10/
    ├── android/
    └── wireshark/
```

The `kali/` directory contains screenshots for the required Week 1 assignment. The other three directories contain evidence for the optional projects.

## Conclusion

I completed the required NetworkWalks Week 1 lab setup and worked through the optional Windows 10, Android-x86, and SOC/Wireshark projects.

These tasks gave me practical experience with VirtualBox, network configuration, connectivity testing, troubleshooting, and network traffic investigation.

This repository brings together the project configurations and supporting screenshots in one place.

**Program:** NetworkWalks Cybersecurity and Ethical Hacking Internship
**Batch:** B084
**Project:** Week 1 — Cybersecurity Lab Setup and Optional Projects
**Author:** Muhammad Abdal Khan
