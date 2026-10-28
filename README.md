# NetworkWalks Week 1 - Cybersecurity Lab Setup

## Project Overview

This project documents the setup of a cybersecurity testing
environment using Oracle VirtualBox and Kali Linux.

The goal was to configure a custom NAT Network, assign a static
IPv4 address to Kali Linux, enable host-guest integration,
verify connectivity, and save a baseline VM snapshot.

## Lab Environment

- Host OS: [Enter your Windows version]
- Virtualization Software: Oracle VirtualBox
- Virtual Machine: Kali Linux
- Network Type: NAT Network

## Network Configuration

| Parameter | Configuration |
|---|---|
| Network Name | NatNetwork |
| Network Subnet | 10.0.0.0/24 |
| Kali IPv4 Address | 10.0.0.2/24 |
| Gateway | 10.0.0.1 |
| DNS Server | [Enter the DNS actually used] |

## Implementation Steps

1. Installed VirtualBox.
2. Imported the Kali Linux virtual machine.
3. Created the NatNetwork virtual network.
4. Configured the Kali network adapter.
5. Assigned the static IPv4 address.
6. Enabled shared clipboard and drag-and-drop.
7. Configured the Windows shared folder.
8. Tested network connectivity and shared-folder access.
9. Created a baseline VM snapshot.

## Verification Results

### IP Address and Routing

[Describe the actual results of your IP and routing tests.]

### Internet Connectivity

[Describe which connectivity tests succeeded and any failures.]

### Shared Folder

[Describe the actual shared-folder test result.]

### Clipboard and Drag-and-Drop

[Describe the features you tested and their actual results.]

## Troubleshooting

[Document the actual issue you faced and how you solved it.
If there were no issues, state that honestly.]

## Evidence

### NAT Network

![NAT Network Configuration](screenshots/01-nat-network-configuration.png)

### Kali Network Adapter

![Kali Network Adapter](screenshots/02-kali-network-adapter.png)

### Clipboard and Drag-and-Drop

![Clipboard and Drag-and-Drop Settings](screenshots/03-clipboard-dragdrop.png)

### Shared Folder

![Shared Folder Configuration](screenshots/04-shared-folder.png)

### Kali IP Configuration

![Kali IPv4 Settings](screenshots/05-kali-ip-configuration.png)

### IP and Route Verification

![IP and Route Verification](screenshots/06-ip-and-route-verification.png)

### Internet Connectivity

![Internet Connectivity](screenshots/07-internet-connectivity.png)

### Shared Folder Test

![Shared Folder Test](screenshots/08-shared-folder-test.png)

### VM Snapshot

![Kali Snapshot](screenshots/09-kali-snapshot.png)
