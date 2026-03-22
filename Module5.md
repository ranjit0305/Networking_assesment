#  Module 05 – Layer 3 Networking Assignment

---

##  1. ARP Packet Analysis using Wireshark

### Objective

To capture and analyze ARP request and reply packets using Wireshark.

---

### Network Setup

* PC connected to network
* Wireshark running on system

---

### Steps Performed

1. Opened Wireshark
2. Selected active network interface
3. Applied filter: `arp`
4. Generated traffic using ping
5. Captured ARP packets

---

### Screenshots

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/97d3ce32-b36f-458a-907e-dad91b9bde8a" />


---

### Observations

* ARP Request is broadcast (`ff:ff:ff:ff:ff:ff`)
* ARP Reply is unicast
* Shows mapping of IP address to MAC address

---

### Result

Successfully captured and analyzed ARP packets.

---

### Conclusion

ARP is used to resolve IP addresses into MAC addresses within a local network.

---

##  2. ARP Spoofing Simulation

### Objective

To simulate ARP spoofing and analyze its impact.

---

### Network Setup

<img width="684" height="345" alt="image" src="https://github.com/user-attachments/assets/4252b5c0-5b44-4e30-95d9-0a228f30b16c" />


---

### Steps Performed

1. Observed ARP table using `arp -a`
2. Attempted to modify ARP entries
3. Monitored behavior

---

### Screenshots

<img width="940" height="712" alt="image" src="https://github.com/user-attachments/assets/cfba3a28-3f11-43c9-b0c0-76df5e4b8315" />
<img width="940" height="1011" alt="image" src="https://github.com/user-attachments/assets/127c40a0-0e9f-479d-95a3-f1278f1e4615" />
<img width="906" height="423" alt="image" src="https://github.com/user-attachments/assets/cb9fc074-683f-4298-a182-617987f1d5d7" />

---

### Observations

* ARP table updates dynamically
* Static ARP not supported in Packet Tracer

---

### Result

ARP spoofing simulation is limited in Packet Tracer.

---

### Conclusion

ARP spoofing affects network communication, but full simulation requires advanced tools.

---

## 3. Manual IP Configuration and Connectivity Test

### Objective

To manually configure IP addresses and verify connectivity.

---

### Network Setup

* 2 PCs
* 1 Switch

---

### IP Configuration

| Device | IP Address   | Subnet Mask   | Default Gateway |
| ------ | ------------ | ------------- | --------------- |
| PC0    | 192.168.1.2  | 255.255.255.0 | 192.168.1.1     |
| PC1    | 192.168.1.20 | 255.255.255.0 | 192.168.1.1     |

---

### Steps Performed

1. Opened Desktop → IP Configuration
2. Selected Static
3. Assigned IP details
4. Used ping command

---

### Ping Command

```bash
ping 192.168.1.1
```

---

### Screenshots

<img width="874" height="303" alt="image" src="https://github.com/user-attachments/assets/b47269f3-8ed7-4967-a9ad-94b928da9bc8" />


---

### Observations

* Initial delay due to ARP
* Successful connectivity achieved

---

### Result

Devices communicated successfully.

---

### Conclusion

Manual IP configuration enables communication within LAN.

---

## 4. DHCP Packet Capture

### Objective

To capture DHCP messages using Wireshark.

---

### Steps Performed

1. Enabled DHCP in router
2. Started Wireshark
3. Applied filter: `dhcp`
4. Renewed IP

---

### Screenshots
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/a0dc35bc-1f34-44d1-9cf1-9ff73d0459c3" />
<img width="940" height="980" alt="image" src="https://github.com/user-attachments/assets/fd7e5e9c-edd3-415d-8b29-7ca3818b2dd7" />


---

### Observations

* DHCP Request from client
* DHCP ACK from server

---

### Explanation

DHCP follows DORA process:

1. Discover
2. Offer
3. Request
4. Acknowledge

---

### Result

DHCP packets captured successfully.

---

### Conclusion

DHCP automates IP address assignment.

---

##  5. Subnetting

### Objective

To divide a network into smaller subnets.

---

### Given

```bash
192.168.1.0/24 → 4 subnets
```

---

### New Subnet Mask

```bash
255.255.255.192 (/26)
```

---

### Subnet Table

| Subnet | Network       | Range   | Broadcast |
| ------ | ------------- | ------- | --------- |
| 1      | 192.168.1.0   | 1–62    | 63        |
| 2      | 192.168.1.64  | 65–126  | 127       |
| 3      | 192.168.1.128 | 129–190 | 191       |
| 4      | 192.168.1.192 | 193–254 | 255       |

---

### Screenshots

<img width="744" height="186" alt="image" src="https://github.com/user-attachments/assets/964d1bbb-027b-444a-bb69-34fa401122c9" />
<img width="940" height="896" alt="image" src="https://github.com/user-attachments/assets/ddea5091-9d77-41ae-b38a-9c3efc7a12c1" />
<img width="940" height="940" alt="image" src="https://github.com/user-attachments/assets/33e9fb6f-0891-453f-98c8-8c13c650f9dd" />
<img width="940" height="476" alt="image" src="https://github.com/user-attachments/assets/31187d4f-030b-4ab9-b5cd-7756196ce7d8" />

---

### Observations

* Devices in same subnet communicate directly
* Different subnets require router

---

### Result

Subnetting implemented successfully.

---

### Conclusion

Subnetting improves network efficiency and organization.

---

## 🔹 IP Address Classification

### Objective

To identify IP classes and ranges.

---

### Table

| IP Address  | Class | Default Mask  | Range                       |
| ----------- | ----- | ------------- | --------------------------- |
| 10.1.1.1    | A     | 255.0.0.0     | 1.0.0.0 – 126.255.255.255   |
| 172.16.5.10 | B     | 255.255.0.0   | 128.0.0.0 – 191.255.255.255 |
| 192.168.1.5 | C     | 255.255.255.0 | 192.0.0.0 – 223.255.255.255 |

---

### Result

IP classes identified correctly.

---

### Conclusion

IP classes define network size and structure.

---

## 🔹 7. NAT Configuration

### Objective

To configure NAT and verify internet connectivity.

---

### Network Setup

* 2 PCs
* 1 Router (NAT)
* 1 Router (Internet)

---

### Configuration

```bash
interface g0/0
ip address 192.168.1.1 255.255.255.0
ip nat inside
no shutdown

interface g0/1
ip address 200.0.0.1 255.255.255.0
ip nat outside
no shutdown

access-list 1 permit 192.168.1.0 0.0.0.255

ip nat inside source list 1 interface g0/1 overload

ip route 200.0.0.0 255.255.255.0 200.0.0.2
```

---

### Screenshots

<img width="753" height="333" alt="image" src="https://github.com/user-attachments/assets/4ed2f1d3-ed84-429a-a0f2-c68997427aa4" />

<img width="844" height="281" alt="image" src="https://github.com/user-attachments/assets/265c6f06-d88a-4aba-9a80-53e2024ee719" />

<img width="916" height="203" alt="image" src="https://github.com/user-attachments/assets/abdb2b7e-33a1-42fa-831c-720983c261e6" />


---

### Verification

```bash
ping 200.0.0.2
```

---

### Observations

* Ping successful
* NAT table shows translation

---

### Result

```bash
192.168.1.2 → 200.0.0.1
```

---

### Final Answer

* Before NAT: 192.168.1.2
* After NAT: 200.0.0.1

---

### Conclusion

NAT allows private networks to access external networks using a public IP.

---
