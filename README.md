# Segmentation Lab



## Objective

The objective of this lab is to demonstrate my ability to use network segmentation and firewall controls to contain security incidents. I walk through the full process—from starting in a flat network, to introducing segmentation, to enforcing least‑privilege access, and finally isolating an infected system. By completing this lab, I show how segmentation, controlled communication, and quarantine techniques play a critical role in preventing lateral movement during attacks such as ransomware.

### Skills Learned
Network segmentation fundamentals
Firewall configuration using UFW
Understanding flat vs. segmented networks
Containment strategies during ransomware incidents
Practical incident response decision‑making
Quarantine procedures and isolation techniques
### Tools Used

Ubuntu 24.04 (UFW firewall)
Windows 10 VM
ICMP (Ping)
SSH
Virtualized lab environment
Git & GitHub
## Steps

Part 1 – Verify a Flat Network
Ping the Ubuntu VM from the Windows VM.
Ping the Windows VM from the Ubuntu VM.
Confirm that both systems communicate freely.

Part 2 – Simulate a Firewall Between Segments

Enable UFW on Ubuntu:

sudo ufw enable
sudo ufw status

Set default firewall rules:

sudo ufw default deny incoming
sudo ufw default allow outgoing

Test connectivity again by pinging Ubuntu from Windows.

Part 3 – Allow Limited Access Between Segments

Allow SSH access from the Windows VM only:
sudo ufw allow from <Windows-IP> to any port 22

Attempt to ping Ubuntu from Windows.
Attempt to SSH into Ubuntu from Windows.

Part 4 – Simulate a Quarantine Network

Block all traffic from the Windows VM:
sudo ufw deny from <Windows-IP>
Test connectivity again from Windows to confirm isolation.
