# 🚀 Cisco Packet Tracer Lab: Initial Router Configuration

## 📌 Overview

This lab demonstrates foundational network engineering skills using Cisco Packet Tracer. It focuses on configuring a router from a default state, securing access, and ensuring persistence of configurations.

Rather than just following commands, this exercise reinforces **how network devices are accessed, secured, and managed in real-world environments**.

---

## 🧠 Key Concepts Demonstrated

- Console access vs direct device interaction  
- Privileged vs user EXEC modes  
- Router hardening (passwords + encryption)  
- Configuration persistence (RAM vs NVRAM vs Flash)  
- CLI navigation and operational awareness  

---

## 🔌 Step 1: Establish Console Access

### Why this matters
In production environments, routers are often accessed via console during initial setup or troubleshooting.

### Steps

1. Select **Console Cable (light blue)**
2. Connect:
   - PC → **RS-232**
   - Router → **Console**
3. Open:
   - PC → Desktop → Terminal
4. Accept default settings → Click **OK**
5. Press `ENTER`

### Expected Output

Router>

---

## 🔐 Step 2: Enter Privileged EXEC Mode

enable

Expected:
Router#

---

## 🔍 Step 3: Verify Default Configuration

show running-config

---

## 💾 Step 4: Check Startup Configuration

show startup-config

Expected:
startup-config is not present

---

## ⚙️ Step 5: Enter Global Configuration Mode

configure terminal

---

## 🏷️ Step 6: Configure Hostname

hostname R1

---

## 🚨 Step 7: Configure MOTD Banner

banner motd #Unauthorized access is strictly prohibited.#

---

## 🔑 Step 8: Configure Passwords

enable password cisco  
enable secret itsasecret  
service password-encryption  

---

## 🖥️ Step 9: Secure Console Access

line console 0  
password letmein  
login  
exit  

---

## 🔎 Step 10: Verify Configuration

show running-config

---

## 🔄 Step 11: Test Login Security

exit  
(Press ENTER)  

Enter password: letmein  

enable  
Enter password: itsasecret  

---

## 💾 Step 12: Save Configuration

copy running-config startup-config  

Shortcut: copy run start  

---

## 🧱 Step 13: Backup to Flash (Optional)

show flash  
copy startup-config flash  

---

## 💡 High-Level Takeaways

- Always secure access points
- Always save configurations
- Understand memory types (RAM vs NVRAM vs Flash)
- Console access is critical for setup and recovery

---

## 🏁 Final Command Summary

enable  
show running-config  
show startup-config  
configure terminal  
hostname R1  
banner motd #Unauthorized access is strictly prohibited.#  
enable password cisco  
enable secret itsasecret  
service password-encryption  
line console 0  
password letmein  
login  
exit  
end  
show running-config  
exit  
copy running-config startup-config  

---

## 👩🏾‍💻 Author

Boitumelo Moshoete  
Aspiring Network & Cloud Engineer
