# network-vlab
Build a virtual enterprise-style network lab to understand networking fundamentals, routing, NAT, DHCP, DNS, and prepare for security testing and firewall policy enforcement.

Why this lab matters:
This lab simulates how real corporate networks are designed:

Clients sit behind a firewall

Traffic is routed, filtered, and NATed

Security policies can be enforced and tested safely

Lab Architecture (High-Level)
[ Windows 10 Client ]
        |
        |  (Internal Network: intnet)
        |
[ pfSense Firewall / Router ]
        |
        |  (NAT)
        |
     Internet

Virtualization Platform

Hypervisor: Oracle VirtualBox

Host OS: Windows

Networking Mode Used: Internal Network + NAT

4. Virtual Machines
🔹 pfSense Router VM

Role: Firewall, Router, DHCP, DNS

OS: pfSense CE

Interfaces:

WAN: NAT (Internet access)

LAN: Internal Network (intnet)

LAN IP Address: 10.10.10.1/24

DHCP: Enabled

🔹 Windows 10 Client VM

Role: Internal LAN client

OS: Windows 10

Network Adapter:

Internal Network → intnet

IP Assignment: DHCP (from pfSense)

5. IP Addressing Plan
Device	Interface	IP Address
pfSense	LAN	10.10.10.1
Windows 10	Ethernet	10.10.10.100
Subnet	—	255.255.255.0
6. Network Validation & Testing
✅ DHCP Verification

Command:

ipconfig


Result:

IP assigned: 10.10.10.100

Gateway: 10.10.10.1

✅ Internal Connectivity Test

Command:

ping 10.10.10.1


Result:

Successful replies

Confirms LAN connectivity to pfSense

✅ Internet Connectivity Test (Routing & NAT)

Command:

ping 8.8.8.8


Result:

Successful replies

Confirms pfSense NAT and routing

✅ DNS Resolution Test

Command:

ping google.com


Result:

Successful replies

Confirms DNS forwarding/resolution via pfSense

Key Learning Outcomes (So Far)

-Installed and configured pfSense as a firewall/router

-Built an isolated internal LAN using VirtualBox

-Deployed a Windows 10 client via ISO (virtual imaging)

-Validated DHCP, routing, NAT, and DNS

-Gained hands-on experience with enterprise-style network design

Current Lab Status
✔ pfSense operational
✔ Windows 10 client operational
✔ Internal network functional
✔ Internet access controlled via pfSense
✔ Ready for security policy testing
