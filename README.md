# Cybersecurity Lab Environment Setup

Building an isolated virtual lab for penetration testing and ethical hacking practice.

## Project Overview
This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using Oracle VM VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

## Objectives
The main objectives of this project are to:
* Install and configure VirtualBox.
* Install/import Kali Linux as a virtual machine.
* Create a private NAT Network for the cybersecurity lab.
* Configure network connectivity for the Kali Linux.
* Assign a consistent IP address to the Kali VM.
* Verify network connectivity and DNS resolution.
* Take a clean VM snapshot for recovery.
* Document the complete setup process.
* Prepare the environment for future cybersecurity projects.

## Purpose of the Lab
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:
* Network reconnaissance
* Port scanning
* Vulnerability assessment
* Packet analysis
* Web security testing
* Exploitation practice
* Security-tool experimentation

> **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

## Lab Configuration

| Component | Configuration |
| :--- | :--- |
| **Host OS** | Windows (HP Laptop) |
| **Hypervisor** | Oracle VM VirtualBox |
| **Security OS** | Kali Linux |
| **Virtual Network** | NAT Network |
| **Network Address** | 10.0.0.0/24 |
| **Kali IP Address** | 10.0.0.2/24 |
| **Default Gateway** | 10.0.0.1 |
| **DNS Server** | 8.8.8.8 |

## Lab Setup Procedure

### Step 1: Install VirtualBox
VirtualBox was installed as the hypervisor.

### Step 2: Create the NAT Network
A dedicated NAT Network was created in VirtualBox.
* **Configuration Name:** NatNetwork
* **IPv4 Prefix:** 10.0.0.0/24
* **DHCP:** Enabled

### Step 3: Configure Kali Linux Network Adapter
The VM network adapter was configured as follows:
* **Adapter 1:** Attached to -> **NAT Network**
* **Name:** NatNetwork

### Step 4: Configure Static IP & Network Verification
The Kali Linux network configuration was checked and configured with a consistent IPv4 address:
* **IP Address:** 10.0.0.2
* **Subnet Mask:** 255.255.255.0
* **Gateway:** 10.0.0.1
* **DNS:** 8.8.8.8

## Lab Verification

| Test | Command | Expected Result |
| :--- | :--- | :--- |
| **Check IP address** | `ip a` | Correct Kali IP displayed |
| **Test gateway** | `ping 10.0.0.1` | Successful replies |
| **Test Internet connectivity** | `ping 8.8.8.8` | Successful replies |
| **Test DNS resolution** | `nslookup networkwalks.com` | Domain resolves |

## Problems Encountered & Solutions
* **Problem:** Network adapter drop-down field greyed out or unclickable when migrating from bridged to NAT Network.
* **Solution:** Navigated to VirtualBox Global Preferences/Tools > Network > NAT Networks, created a dedicated NAT Network object (`NatNetwork`), and enabled DHCP to initialize the routing driver pool.

## What I Learned
Through this project, I learned how to create and configure a virtual environment for cybersecurity practice, specifically mastering hypervisor network isolation, NAT network configuration, and terminal-based network diagnostics.

---
## Project Demonstration Video
The complete video walkthrough (

https://github.com/user-attachments/assets/844b2709-fb54-47f0-83f7-f170783f50e4

) detailing the lab setup and verification is included in this repository.
