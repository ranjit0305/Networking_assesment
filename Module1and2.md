# Networking – Module 1 & 2 Assessment

## 📌 Objective

This assignment covers basic Linux networking commands, FTP/SFTP configuration, SCP usage, DHCP concepts, and remote connectivity tools.

---

# 1️) Copying a Folder Using `cp` and `scp`

## Local Copy

```bash
cp -r project/ backup/
```

## Remote Copy using SCP

```bash
scp -r project/ user@192.168.1.5:/home/user/
```

SCP works over SSH (port 22).

---
<img width="874" height="81" alt="image" src="https://github.com/user-attachments/assets/9a529b0b-03d7-4d29-a8c1-d6c719e96817" />
<img width="940" height="62" alt="image" src="https://github.com/user-attachments/assets/9c079d74-b3f0-48c8-b15b-dbb9252866d6" />
<img width="940" height="142" alt="image" src="https://github.com/user-attachments/assets/99c8e102-cf70-4ded-a4da-23b95a8bc9bd" />

# 2️) FTP & SFTP Server Setup

## Install FTP Server

```bash
sudo apt install vsftpd
sudo systemctl start vsftpd
sudo systemctl enable vsftpd
```

## Connect to FTP

```bash
ftp 127.0.0.1
```

## FTP Commands

* put filename → Upload
* get filename → Download
* ls → List files
* pwd → Remote directory
* !ls → Local directory
<img width="938" height="789" alt="image" src="https://github.com/user-attachments/assets/a00e0845-52d0-42c5-9c1f-a5b649e12fe4" />


## SFTP (Secure)

```bash
sftp user@192.168.1.5
```

SFTP is encrypted (uses SSH).

---
<img width="940" height="534" alt="image" src="https://github.com/user-attachments/assets/43d3f4bc-f1cf-4e6f-a2ea-6c27c590392d" />

# 3️) Packet Analysis Tools

## Wireshark

GUI-based packet capture and analysis.

## tcpdump

```bash
sudo tcpdump -i eth0
sudo tcpdump port 21
```

## Cisco Packet Tracer

Used for network simulation and configuration practice.

---
<img width="914" height="622" alt="image" src="https://github.com/user-attachments/assets/3452f698-c95d-49b3-987a-ca65aa6b77dc" />

# 4️) Linux Networking Commands

## ping

```bash
ping 8.8.8.8
ping -c 4 google.com
```

## arp

```bash
arp -a
```

## ifconfig / ip

```bash
ifconfig
ip addr
```

Parameters:

* inet → IP Address
* netmask
* broadcast
* MTU
* MAC Address

---
<img width="940" height="305" alt="image" src="https://github.com/user-attachments/assets/0aecef77-5121-488d-802e-7e4645f01987" />


# 5️) Duplicate IP Address Issue

## What is a Duplicate IP?

A duplicate IP address occurs when **two or more devices in the same network are assigned the same IP address**, causing conflicts in communication.

## How Duplicate IPs Are Configured

### 1️) Manual (Static IP) Configuration

- Most common cause of duplicate IP
- Occurs when users manually assign the same IP to multiple devices

**Example:**
- PC1 → 192.168.1.100  
- PC2 → 192.168.1.100 ❌  

---

### 2️) DHCP Conflict

- DHCP server assigns IP addresses automatically
- Duplicate IP may occur due to:
  - Server misconfiguration
  - Lease issues
  - Device reusing an old IP

---

### 3️) Mixing Static and DHCP IPs

- Occurs when:
  - DHCP assigns IPs in a range
  - A user manually assigns an IP within the same range

**Example:**
- DHCP range: 192.168.1.2 – 192.168.1.100  
- Manual IP assigned: 192.168.1.50 ❌  

---

### 4️) Virtual Machine / Cloning Issues

- Happens when:
  - System configurations are copied
  - Same IP is duplicated across systems

---

## Result of Duplicate IP

- Network confusion
- ARP conflicts
- Packet loss
- Unstable communication

---

## Prevention

- Use DHCP properly  
- Avoid assigning IPs within DHCP range  
- Maintain proper IP address management  


# 6️) Remote Access Tools

* VNC Viewer
* AnyDesk
* TeamViewer
* SSH
* Telnet

SSH:

```bash
ssh user@192.168.1.5
```

Telnet:

```bash
telnet 192.168.1.5
```

---

# 7️) Checking Default Gateway

```bash
ip route
ping 192.168.1.1
```

---
<img width="940" height="202" alt="image" src="https://github.com/user-attachments/assets/bee2e9fa-6314-4098-9449-5254124498c1" />

# 8️) Network Interface Details

```bash
ethtool eth0
```

Check:

* Speed
* Duplex
* MTU
* State (UP/DOWN)

---

# 9️) Router Configuration

Access:

```
http://127.0.0.1
```

Check:

* Connected devices
* DHCP list
* WAN IP

Images:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9670bfd5-4e28-4cb5-bbf2-1625c08dccf8" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/43c28930-5006-43b3-9eed-d0ce3041ba92" />


---

# 10) DHCP Working (DORA Process)

1. Discover
2. Offer
3. Request
4. Acknowledge

Assigns:

* IP Address
* Subnet Mask
* Gateway
* DNS

---

# 11) SSH and Telnet Connection

SSH (Secure):

```bash
ssh user@remote_ip
```

Telnet (Not Secure):

```bash
telnet remote_ip
```

---

