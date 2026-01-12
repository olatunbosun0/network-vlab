# Virtual Network Security Lab (pfSense + Windows 10)

## 📌 Overview
This project demonstrates the design and deployment of a **virtual enterprise-style network** using **pfSense** as a firewall/router and a **Windows 10 client** behind it.  
The lab focuses on routing, NAT, DHCP, DNS, and connectivity validation, serving as a foundation for future security testing.

This lab was built entirely in **Oracle VirtualBox** and is intended for hands-on learning in networking and cybersecurity.

---

## 🧱 Lab Architecture



---

## 🖥️ Environment Details

### Hypervisor
- Oracle VirtualBox

### Firewall / Router
- pfSense CE
- WAN Interface: NAT (Internet-facing)
- LAN Interface: Internal Network (`intnet`)
- LAN IP Address: `10.10.10.1/24`
- DHCP Server: Enabled

### Client Machine
- OS: Windows 10
- Network Adapter: Internal Network (`intnet`)
- IP Assignment: DHCP from pfSense

---

## 🌐 Network Configuration

### pfSense LAN
| Setting | Value |
|------|------|
| Interface | LAN |
| IP Address | 10.10.10.1 |
| Subnet | /24 |
| DHCP Range | Assigned dynamically |

### Windows 10 Client
| Setting | Value |
|------|------|
| IPv4 Address | 10.10.10.100 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.10.10.1 |
| DNS | Provided by pfSense |

---

## ✅ Connectivity Validation

All tests were executed from the Windows 10 client.

### 1️⃣ IP Configuration
```cmd
ipconfig

