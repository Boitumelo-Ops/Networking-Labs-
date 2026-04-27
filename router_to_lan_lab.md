# 🌐 Cisco Packet Tracer Lab: Connect a Router to a LAN

## Overview

This lab demonstrates how to connect routers to local area networks (LANs), configure interfaces, and verify connectivity across multiple devices. It builds practical skills in network configuration, troubleshooting, and verification using Cisco CLI.

---

## Key Concepts

- Interface configuration and activation
- IP addressing and subnetting
- Routing tables and connected routes
- Network verification and troubleshooting
- End-to-end connectivity testing

---

## Access Router CLI

Open each router → CLI tab

Console password:
cisco

Privileged EXEC password:
class

Enter privileged mode:
enable

---

## Part 1: Display Router Information

### Show all interfaces
show interfaces

### Show specific interface
show interfaces serial 0/0/0

### Show interface summary
show ip interface brief

### Show routing table
show ip route

---

## Part 2: Configure Router Interfaces

### Configure R1

enable
configure terminal

interface gigabitethernet 0/0
ip address 192.168.10.1 255.255.255.0
description LAN connection to S1
no shutdown
exit

interface gigabitethernet 0/1
ip address 192.168.11.1 255.255.255.0
description LAN connection to S2
no shutdown
exit

end

copy running-config startup-config

---

### Configure R2

enable
configure terminal

interface gigabitethernet 0/0
ip address 10.1.1.1 255.255.255.0
description LAN connection to S3
no shutdown
exit

interface gigabitethernet 0/1
ip address 10.1.2.1 255.255.255.0
description LAN connection to S4
no shutdown
exit

end

copy running-config startup-config

---

##  Part 3: Verify Configuration

### Check interface status
show ip interface brief

Look for:
Status: up
Protocol: up

---

### Verify routing table
show ip route

---

##  Test Connectivity

From PC1:
ping 10.1.2.10

From R2:
ping 192.168.11.10

---

##  Common Issues

- Interface is down → missing 'no shutdown'
- Wrong IP address → check addressing table
- Cannot ping → check cables and gateway
- Config not saved → use 'copy run start'

---

##  Key Takeaways

- Always verify after configuration
- Interfaces must be manually enabled
- Routing tables show network awareness
- Connectivity testing confirms success

---

## 👩🏾‍💻 Author

Boitumelo Lux  
Aspiring Network & Cloud Engineer  
