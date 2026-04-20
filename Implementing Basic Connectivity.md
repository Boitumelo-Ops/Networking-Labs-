# Cisco Packet Tracer Lab — Implementing Basic Connectivity

## 📌 Project Overview
This lab focuses on implementing **basic network connectivity** by configuring switches and end devices using Cisco Packet Tracer.

The objective is not only to configure devices, but to **understand how communication is established, verified, and troubleshot** in a real network environment.

This lab builds directly on prior work involving **initial switch configuration and security**, progressing from **device setup → actual communication between devices**.

---

## 🎯 Lab Requirements

The lab required the following:

### 🔹 Part 1: Switch Configuration
- Assign hostnames to S1 and S2
- Secure console access using a password
- Configure privileged EXEC mode access
- Configure a Message of the Day (MOTD) banner
- Save configuration to NVRAM

### 🔹 Part 2: End Device Configuration
- Assign IP addresses to PC1 and PC2
- Ensure both PCs are in the same subnet

### 🔹 Part 3: Switch Management Configuration
- Assign IP addresses to VLAN 1 on both switches
- Activate the VLAN interface
- Verify configuration using CLI commands

### 🔹 Part 4: Connectivity Verification
- Use ***ping*** to test communication between:
  - PC1 ↔ PC2
  - PC1 ↔ S1
  - PC1 ↔ S2
- Confirm full network connectivity

---

## 🌐 Network Topology

Devices used:
- 2 × Cisco 2960 Switches (S1, S2)
- 2 × PCs (PC1, PC2)

Each PC connects to a switch, and the switches are interconnected.

---

## 📊 Addressing Scheme

| Device | Interface | IP Address       | Subnet Mask       |
|--------|----------|------------------|-------------------|
| S1     | VLAN 1   | 192.168.1.253    | 255.255.255.0     |
| S2     | VLAN 1   | 192.168.1.254    | 255.255.255.0     |
| PC1    | NIC      | 192.168.1.1      | 255.255.255.0     |
| PC2    | NIC      | 192.168.1.2      | 255.255.255.0     |

---

## 🛠️ Tools & Technologies

- Cisco Packet Tracer
- Cisco IOS CLI
- Ethernet switching
- IPv4 addressing
- VLAN 1 management interface
- ICMP (ping)
- ARP (Address Resolution Protocol)

---

## ⚙️ Implementation Steps

---

### 🔹 Step 1: Configure Switch S1

```bash
enable
configure terminal
hostname S1
line console 0
password cisco
login
interface vlan 1
ip address 192.168.1.253 255.255.255.0
no shutdown
enable secret class
banner motd $ Authorized access only. Violators will be prosecuted to the full extent of the law.$
exit
copy running-config startup-config
