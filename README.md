# Network-Traffic-Analysis-Lab

# Network Traffic Analysis Lab (Wireshark)

This lab focuses on capturing and analyzing network traffic between two virtual machines using Wireshark. The goal was to understand how different protocols behave and how data appears in packet captures.

---

## Objective

Capture and analyze network traffic between a Windows VM and a Kali Linux VM to understand the differences between HTTP, HTTPS, and ICMP traffic, while troubleshooting connectivity and packet capture issues.

---

## Skills Learned

- Basic **network traffic analysis** using Wireshark  
- Understanding differences between **HTTP vs HTTPS traffic**  
- Analyzing **ICMP (ping) behavior and responses**  
- Troubleshooting **VM networking and firewall issues**  
- Using **Wireshark filters** to isolate traffic  
- Gaining familiarity with **packet structures and protocol behavior**  

---

## Tools Used

- **Wireshark** – packet capture and analysis  
- **Kali Linux** – used as the attacking/scanning machine  
- **Windows 10 VM** – target machine generating traffic  
- **VirtualBox / VMware** – virtualization platform (whichever you used)  

---

## Lab Setup

- Two virtual machines:
  - Kali Linux (attacker/analysis machine)  
  - Windows 10 (target machine)  
- Both VMs connected to the same **NAT network** to allow communication  
- Wireshark installed on Kali Linux  

---

## Steps to Show

1. **Initial Setup & Issues**
   - Wireshark was not capturing traffic  
   - Ping requests were failing between VMs  
   - Limited familiarity with Wireshark interface  

2. **Troubleshooting**
   - Connected both VMs to the same NAT network  
   - Disabled Windows Firewall temporarily to allow ICMP traffic  
   - Verified connectivity using ping  

3. **Traffic Capture**
   - Captured traffic in Wireshark on Kali Linux  
   - Generated traffic using:
     - `ping <Windows_VM_IP>` (ICMP)
     - `http://example.com` (HTTP)
     - `https://example.com` (HTTPS)

4. **Traffic Analysis**
   - Applied filters to isolate:
     - ICMP traffic  
     - HTTP traffic  
     - HTTPS traffic  

---

## Key Observations

### HTTP Traffic
- Visible **GET requests** in packet details  
- Full request data shown in the **Info tab**  
- Data is **unencrypted and readable**
  
- [HTTP Get Request]
--- ![HTTP](https://github.com/user-attachments/assets/d7b69561-8a8d-41a8-bb45-0e732ef1f7d2)


### HTTPS Traffic
- Only shows **TLS handshake (SYN, ACK, Client Hello, Server Hello)**  
- No readable request data  
- Demonstrates **encryption in transit**

-[HTTPS Handshake]
--- ![HTTPS](https://github.com/user-attachments/assets/e859c0e2-09ba-4f16-94e7-7b3ce16ee46c)


### ICMP (Ping) Traffic
- Shows **echo request and reply packets**  
- Confirms connectivity between machines  
- Initially blocked by firewall until adjusted
 
-[ICMP Traffic]
--- ![ICMP](https://github.com/user-attachments/assets/47a03472-8301-418b-bef4-f4dd9cabf923)

## Challenges & Solutions

| Challenge | Solution |
|----------|---------|
| No traffic captured in Wireshark | Verified correct network interface and VM network configuration |
| Ping not working | Disabled Windows Firewall (or allow ICMP) |
| Overwhelming packet data | Focused on specific protocols using filters |
| Limited Wireshark knowledge | Used basic filters (HTTP, HTTPS, ICMP) |

---

## Takeaways

- Learned how to **capture and filter network traffic** effectively  
- Understood the **visibility difference between HTTP and HTTPS**  
- Gained experience troubleshooting **real networking issues in a lab**  
- Developed foundational knowledge of **packet-level analysis**  

---

## Future Improvements

- Learn advanced **Wireshark filters**  
- Explore methods to **decrypt HTTPS traffic**  
- Configure firewall rules instead of disabling it  
- Expand analysis to include **DNS and other protocols**  

---
