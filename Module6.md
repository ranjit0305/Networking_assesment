#  Layer 3 Networking Assignment (Module 06)

---

##  1. ARP Packet Analysis using Wireshark

### Objective

To capture and analyze ARP packets and understand how devices resolve IP addresses to MAC addresses.

---

### Procedure

* Opened Wireshark and started capture
* Applied filter: `arp`
* Performed ping between devices

---

### 📸 Screenshot: ARP Capture

<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/0c60b91e-0ee3-4553-bcce-7bbb46c20a02" />


---

### Observations

* ARP Request: Broadcast asking “Who has IP?”
* ARP Reply: Unicast response with MAC address

---

### Conclusion

ARP maps IP addresses to MAC addresses within a LAN.

---

##  2. Static Routing Configuration

### Objective

To configure static routes between networks.

---

### 📸 Screenshot: Topology

<img width="675" height="231" alt="image" src="https://github.com/user-attachments/assets/48647507-5da8-4744-ab82-e5fd9a898275" />

---

### Configuration

#### Router0

```bash
interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

interface g0/1
ip address 10.0.0.1 255.255.255.0
no shutdown

ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

#### Router1

```bash
interface g0/0
ip address 10.0.0.2 255.255.255.0
no shutdown

interface g0/1
ip address 192.168.2.1 255.255.255.0
no shutdown

ip route 192.168.1.0 255.255.255.0 10.0.0.1
```

---

### 📸 Screenshot: Ping Output
<img width="805" height="459" alt="image" src="https://github.com/user-attachments/assets/c74c7351-0835-4ef8-92b1-67976632a8d0" />
![Ping](images/static_ping.png)

---

### Conclusion

Static routing enables communication between different networks.

---

##  3. Subnetting (10.0.0.0/24 → 4 Subnets)

### Objective

To divide network into equal subnets.

---

### Subnet Mask

`255.255.255.192 (/26)`

---

### Subnets

| Subnet | Range                   |
| ------ | ----------------------- |
| 1      | 10.0.0.1 – 10.0.0.62    |
| 2      | 10.0.0.65 – 10.0.0.126  |
| 3      | 10.0.0.129 – 10.0.0.190 |
| 4      | 10.0.0.193 – 10.0.0.254 |

---

### 📸 Screenshot

<img width="486" height="202" alt="image" src="https://github.com/user-attachments/assets/401fc055-45d7-41e0-9e34-132a32bd22d7" />


---

### 📸 Screenshot: Ping Test

![Subnet Ping]<img width="722" height="314" alt="image" src="https://github.com/user-attachments/assets/62f52ec8-e049-48e5-a287-bf2fff2e594b" />


---

### Conclusion

Subnetting improves network efficiency.

---

## 🔹 4. IP Address Classification

### Given IPs

* 192.168.10.5
* 172.20.15.1
* 8.8.8.8

---

### Table

| IP           | Class | Type    |
| ------------ | ----- | ------- |
| 192.168.10.5 | C     | Private |
| 172.20.15.1  | B     | Private |
| 8.8.8.8      | A     | Public  |

---

### Explanation

Private IPs are used inside networks, public IPs are used on the internet.

---

## 🔹 5. NAT Configuration

### Objective

To configure NAT and verify connectivity.

---

### 📸 Screenshot: Topology

<img width="753" height="333" alt="image" src="https://github.com/user-attachments/assets/2394cab5-25cb-4d0d-9fa0-f3794ac9ba56" />

---

### Configuration

#### Router0

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
```

---

#### Router1

```bash
interface g0/0
ip address 200.0.0.2 255.255.255.0
no shutdown

ip route 192.168.1.0 255.255.255.0 200.0.0.1
```

---

### 📸 Screenshot: Ping Result
<img width="844" height="281" alt="image" src="https://github.com/user-attachments/assets/0a4ac136-df7c-414f-81d3-75d7410318da" />


---

### 📸 Screenshot: NAT Table

<img width="916" height="203" alt="image" src="https://github.com/user-attachments/assets/160717c9-6afe-4742-bc13-db13d9d03f14" />


---

### Observations

* Private IP translated to public IP
* NAT table confirms translation

---

### Result

`192.168.1.2 → 200.0.0.1`

---

### Final Answer

* Before NAT: 192.168.1.2
* After NAT: 200.0.0.1

---

### Conclusion

NAT allows multiple private devices to access external networks using a single public IP.

---
