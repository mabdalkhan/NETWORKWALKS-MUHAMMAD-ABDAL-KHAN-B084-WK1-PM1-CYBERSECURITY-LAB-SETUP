# NetworkWalks Week 1 — Cybersecurity Lab Setup and SOC Practice

A practical cybersecurity project completed as part of the **NetworkWalks Cybersecurity and Ethical Hacking Internship**.

This repository documents the setup and verification of a virtual cybersecurity lab using VirtualBox, Kali Linux, Windows 10, and Android-x86. It also includes the optional Week 1 SOC practice module covering six browser-based network traffic investigation labs.

The project combines virtual machine configuration, network connectivity testing, host–guest integration, troubleshooting, and introductory security operations practice.

## Project Objectives

The main objectives of this project were to:

* Build a working cybersecurity lab using Oracle VirtualBox.
* Configure a custom NAT Network for the virtual machines.
* Assign the required static IPv4 addresses.
* Verify connectivity between virtual machines and test Internet access.
* Configure shared folders, clipboard integration, and drag-and-drop.
* Create a baseline snapshot of the Kali Linux virtual machine.
* Extend the lab with Windows 10 and Android-x86.
* Practise network traffic investigation through the NetworkWalks SOC/Wireshark browser labs.
* Document the implementation and verification process with screenshots.

## Project Components

| Component                           | Purpose                                  | Status    |
| ----------------------------------- | ---------------------------------------- | --------- |
| Kali Linux                          | Main cybersecurity testing machine       | Completed |
| VirtualBox NAT Network              | Network for the virtual lab              | Completed |
| Windows 10 VM                       | Additional lab machine                   | Completed |
| Android-x86 9.0 VM                  | Additional lab machine                   | Completed |
| Shared folder and guest integration | Host–guest file and clipboard operations | Completed |
| VM snapshot                         | Baseline recovery point                  | Completed |
| Six SOC/Wireshark browser labs      | Network traffic investigation exercises  | Completed |

## 1. Lab Architecture

The virtual machines were configured to use the same VirtualBox NAT Network.

```text
                     Windows Host
                           |
                     Oracle VirtualBox
                           |
                NAT Network: NatNetwork
                    10.0.0.0/24
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
      Kali Linux        Windows 10      Android-x86
       10.0.0.2          10.0.0.10        10.0.0.9
          |                |                |
          +----------------+----------------+
                           |
                    Gateway: 10.0.0.1
                    DNS: 8.8.8.8
```

The Windows 10 and Android-x86 machines are optional extensions to the required Kali Linux lab.

The addresses above represent the assignment's intended configuration. The screenshots and verification records in this repository provide the evidence for the actual implementation.

## 2. Network Configuration

The virtual network was configured according to the Week 1 assignment.

| Parameter                | Configuration     |
| ------------------------ | ----------------- |
| Virtualization platform  | Oracle VirtualBox |
| Network type             | NAT Network       |
| Network name             | `NatNetwork`      |
| IPv4 subnet              | `10.0.0.0/24`     |
| Kali Linux IPv4 address  | `10.0.0.2/24`     |
| Windows 10 IPv4 address  | `10.0.0.10/24`    |
| Android-x86 IPv4 address | `10.0.0.9/24`     |
| Default gateway          | `10.0.0.1`        |
| DNS server               | `8.8.8.8`         |

These are the target values specified in the project guides. If a machine used a different DNS server during troubleshooting, its actual configuration should be documented accordingly.

## 3. Required Project: Kali Linux Lab

The primary Week 1 project involved preparing Kali Linux as the main virtual cybersecurity testing environment.

### Implementation

1. Installed Oracle VirtualBox.
2. Downloaded and imported the Kali Linux virtual machine.
3. Created the custom `NatNetwork` virtual network.
4. Configured the Kali virtual network adapter to use the NAT Network.
5. Assigned the required static IPv4 address.
6. Configured the gateway and DNS settings.
7. Enabled bidirectional shared clipboard and drag-and-drop.
8. Configured a shared folder from the Windows host.
9. Tested the network configuration and connectivity.
10. Created a baseline VM snapshot.

### Verification

The following checks were performed during the lab setup:

* Inspected the assigned IPv4 address.
* Checked the routing configuration.
* Tested connectivity to the configured gateway.
* Tested external IP connectivity and DNS resolution.
* Checked Internet access.
* Tested shared-folder access.
* Checked clipboard and drag-and-drop functionality.
* Confirmed the saved virtual machine snapshot.

### Kali Linux Evidence

| Evidence                             | Screenshot                                          |
| ------------------------------------ | --------------------------------------------------- |
| NAT Network configuration            | `screenshots/kali/01-nat-network-configuration.png` |
| Kali network adapter                 | `screenshots/kali/02-kali-network-adapter.png`      |
| Clipboard and drag-and-drop settings | `screenshots/kali/03-clipboard-dragdrop.png`        |
| Shared-folder configuration          | `screenshots/kali/04-shared-folder.png`             |
| Static IPv4 configuration            | `screenshots/kali/05-kali-ip-configuration.png`     |
| IP address and routing verification  | `screenshots/kali/06-ip-and-route-verification.png` |
| Internet connectivity tests          | `screenshots/kali/07-internet-connectivity.png`     |
| Shared-folder access test            | `screenshots/kali/08-shared-folder-test.png`        |
| Baseline VM snapshot                 | `screenshots/kali/09-kali-snapshot.png`             |

## 4. Optional Project: Windows 10 Virtual Machine

The Windows 10 extension added a second operating system to the virtual lab.

### Implementation

1. Obtained the Windows 10 installation ISO from Microsoft's official source.
2. Created a Windows 10 virtual machine in VirtualBox.
3. Configured its virtual hardware and virtual disk.
4. Installed Windows 10.
5. Connected the VM to the same `NatNetwork` used by Kali Linux.
6. Configured the required static IPv4 address.
7. Tested connectivity between Windows 10 and Kali Linux.
8. Tested external network connectivity.

### Target Network Settings

| Parameter       | Value           |
| --------------- | --------------- |
| Virtual machine | `Windows10-Lab` |
| Network type    | NAT Network     |
| IPv4 address    | `10.0.0.10/24`  |
| Default gateway | `10.0.0.1`      |
| Preferred DNS   | `8.8.8.8`       |

### Verification

The connectivity tests included:

```cmd
ping 10.0.0.2
ping 8.8.8.8
```

The Kali-to-Windows test was performed from Kali Linux:

```bash
ping -c 4 10.0.0.10
```

The actual screenshots document the results of the tests.

### Windows 10 Evidence

| Evidence                     | Screenshot                                              |
| ---------------------------- | ------------------------------------------------------- |
| VM configuration             | `screenshots/windows10/01-windows-vm-configuration.png` |
| Static IPv4 settings         | `screenshots/windows10/02-windows-ip-configuration.png` |
| Windows-to-Kali connectivity | `screenshots/windows10/03-windows-to-kali-ping.png`     |
| External connectivity test   | `screenshots/windows10/04-windows-internet-test.png`    |
| Kali-to-Windows connectivity | `screenshots/windows10/05-kali-to-windows-ping.png`     |

## 5. Optional Project: Android-x86 Virtual Machine

The Android-x86 extension introduced an Android-based virtual machine into the same lab environment.

### Implementation

1. Obtained the Android-x86 9.0 ISO from the official project download source.
2. Created the `Android9-Lab` virtual machine.
3. Configured its memory, virtual disk, and display settings.
4. Installed Android-x86.
5. Connected the VM to the shared `NatNetwork`.
6. Configured the required static IPv4 address.
7. Tested connectivity between Android-x86 and Kali Linux.
8. Tested external network connectivity.

### Target Network Settings

| Parameter        | Value           |
| ---------------- | --------------- |
| Virtual machine  | `Android9-Lab`  |
| Operating system | Android-x86 9.0 |
| Network type     | NAT Network     |
| IPv4 address     | `10.0.0.9/24`   |
| Default gateway  | `10.0.0.1`      |
| DNS server       | `8.8.8.8`       |

### Verification

The Android-to-Kali connectivity test used:

```bash
ping 10.0.0.2
```

The external connectivity test used:

```bash
ping 8.8.8.8
```

The reverse connectivity test was performed from Kali Linux:

```bash
ping -c 4 10.0.0.9
```

### Android-x86 Evidence

| Evidence                     | Screenshot                                            |
| ---------------------------- | ----------------------------------------------------- |
| Android VM configuration     | `screenshots/android/01-android-vm-configuration.png` |
| Android desktop              | `screenshots/android/02-android-desktop.png`          |
| Static IPv4 settings         | `screenshots/android/03-android-ip-configuration.png` |
| Android-to-Kali connectivity | `screenshots/android/04-android-to-kali-ping.png`     |
| Android Internet test        | `screenshots/android/05-android-internet-test.png`    |
| Kali-to-Android connectivity | `screenshots/android/06-kali-to-android-ping.png`     |

## 6. Optional Project: SOC and Wireshark Practice

The additional NetworkWalks SOC project consisted of six browser-based labs. Each lab contained ten tasks focused on investigating supplied network traffic captures.

The exercises provided practice in network traffic analysis, identifying suspicious activity, reconstructing conversations, and investigating potential security incidents.

### Completed Labs

**1. Identify the Attacker's IP**

Practised examining network traffic to identify an attacker's IP address.

**2. Follow TCP Stream 1**

Practised reconstructing a TCP conversation to inspect the data exchanged between endpoints.

**3. Follow TCP Stream, Part 2**

Continued TCP stream investigation using another capture, with attention to finding hidden data.

**4. HTTP Plain Text Credentials**

Practised identifying credentials transmitted in clear text over HTTP within the supplied exercise capture.

**5. Catch the Brute Force Attacker**

Practised recognizing repeated login attempts and identifying the source associated with the activity.

**6. Catch the Call Scammer**

Investigated a supplied capture and call recording as part of the exercise to identify the suspected scammer.

### Learning Objectives

The six labs covered:

* Identifying suspicious source addresses.
* Following TCP streams.
* Inspecting application-layer data.
* Recognizing insecure transmission of credentials.
* Identifying repeated authentication attempts.
* Investigating a VoIP-related scam scenario.

These exercises were performed in the supplied educational lab environment.

### Wireshark/SOC Evidence

Organize the completion screenshots under:

`screenshots/wireshark/`

Suggested filenames:

```text
screenshots/wireshark/
├── 01-identify-attacker-ip.png
├── 02-follow-tcp-stream-1.png
├── 03-follow-tcp-stream-part-2.png
├── 04-http-plaintext-credentials.png
├── 05-brute-force-attacker.png
└── 06-call-scammer-investigation.png
```

Use screenshots that genuinely demonstrate completion of the relevant exercises. Where a single screenshot does not show all ten tasks, include additional evidence as needed.

## 7. Overall Verification Summary

The project included configuration checks and functional tests for the main lab and its optional extensions.

| Area                     | Verification performed                                    |
| ------------------------ | --------------------------------------------------------- |
| NAT Network              | Confirmed the virtual network configuration               |
| Kali Linux               | Checked IP address, routing, and connectivity             |
| Windows 10               | Tested connectivity with Kali and external network access |
| Android-x86              | Tested connectivity with Kali and external network access |
| Shared folder            | Tested access between the Windows host and Kali           |
| Clipboard                | Tested host–guest clipboard functionality                 |
| Drag-and-drop            | Tested supported file transfer between host and guest     |
| Virtual machine snapshot | Confirmed the baseline snapshot                           |
| SOC/Wireshark exercises  | Completed the six browser-based labs                      |

The screenshots included in this repository serve as evidence of the implementation and the tests performed.

## 8. Troubleshooting and Lessons Learned

This project reinforced the importance of verifying a lab configuration instead of relying only on the settings displayed in a graphical interface.

Important areas to check when troubleshooting a virtual network include:

* Correct NAT Network selection.
* Correct IP address and subnet mask.
* Duplicate IP address conflicts.
* Default gateway and DNS settings.
* Internet reachability versus DNS resolution.
* Host–guest integration support.
* Shared-folder access permissions.

Any specific problem and its resolution should be documented alongside the relevant evidence, using the actual issue encountered during implementation.

## 9. Repository Structure

The project files and screenshots are organized into the following suggested structure:

```text
NETWORKWALKS-WK1-PM1-CYBERSECURITY-LAB-SETUP/
│
├── README.md
│
├── screenshots/
│   ├── kali/
│   ├── windows10/
│   ├── android/
│   └── wireshark/
│
└── docs/
    └── project-notes.md
```

The repository contains project documentation and screenshots rather than full virtual-machine disk images.

## 10. Responsible Use

This project was created for educational cybersecurity practice within virtualized lab environments and instructor-provided exercises.

Network testing and security analysis should be limited to systems owned by the tester, isolated lab environments, or systems for which explicit authorization has been granted.

The provided SOC exercises were used as educational practice material, not as authorization to inspect unrelated traffic or access real systems.

## 11. Conclusion

The NetworkWalks Week 1 project brought together virtual lab setup, network configuration, connectivity verification, and introductory SOC investigation exercises.

The required Kali Linux environment established the foundation for further cybersecurity practice. The optional Windows 10 and Android-x86 machines expanded the lab, while the six SOC exercises provided structured practice in examining network traffic and recognizing common security indicators.

The project also provided practical experience in documenting configurations, validating results, organizing evidence, and maintaining a technical portfolio on GitHub.

**Program:** NetworkWalks Cybersecurity and Ethical Hacking Internship
**Project:** Week 1 — Required Lab Setup and Optional Extensions
**Author:** Muhammad Abdal Khan
