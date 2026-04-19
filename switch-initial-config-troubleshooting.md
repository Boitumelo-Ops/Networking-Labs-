# Troubleshooting Case Study — Cisco Switch Initial Configuration

## Overview
This case study documents a troubleshooting scenario encountered while completing a Cisco Packet Tracer lab on initial switch configuration. The issue required identifying configuration gaps, verifying CLI settings, and correcting errors to meet grading requirements.

---

## Problem
The Packet Tracer activity did not complete successfully and returned a score of **54/72**.

Issues identified:
- Enable password marked incorrect on both switches (S1 and S2)
- Startup configuration not saved on S1
- Hostname incorrectly configured on S2
- Activity flagged as incomplete despite most steps appearing correct

---

## Investigation
To diagnose the problem, I followed a structured troubleshooting approach:

### 1. Reviewed Lab Requirements
- Verified required configurations:
  - Hostname
  - Console password
  - Enable password and enable secret
  - MOTD banner
  - Password encryption
  - Saving configuration to NVRAM

### 2. Used CLI Verification Commands
```
show running-config
show startup-config
```

### 3. Cross-Checked Command Sequence
```
enable
configure terminal
hostname S1
line console 0
password letmein
login
enable password c1$c0
enable secret itsasecret
service password-encryption
banner motd "Authorized Access Only"
copy running-config startup-config
```

### 4. Identified Root Causes
- Missing or incorrect use of `enable secret`
- Configuration not saved to NVRAM
- Hostname mismatch on S2
- Packet Tracer requires exact command syntax and sequence

---

## Solution
The issue was resolved by correcting and verifying the configuration:

### Fixes Applied
```
enable password c1$c0
enable secret itsasecret
service password-encryption
hostname S2
copy running-config startup-config
```

### Final Verification
```
show running-config
show startup-config
```

After applying these fixes, the configuration aligned with lab requirements and resolved grading issues.

---

## What I Learned
- Always save configurations using:
  ```
  copy running-config startup-config
  ```
- `enable secret` overrides `enable password` and must be configured correctly
- Packet Tracer grading is strict — precision matters
- Small misconfigurations (like hostname or missing commands) can impact results
- Always verify configurations before submission

---

## Tools Used
- Cisco Packet Tracer CLI
- `show running-config`
- `show startup-config`
- Configuration cheat sheets and lab instructions

---

## Key Takeaway
Troubleshooting is a structured process. Instead of guessing, I learned to:
- Verify configurations step-by-step
- Use CLI tools effectively
- Identify root causes through comparison and validation

This experience reflects real-world IT problem-solving, where attention to detail and persistence are critical.
