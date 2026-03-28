# Networks assignment 
---

## 🧪 1. Connectivity Test and DNS Lookup

🎯 Objective  
To test network connectivity and resolve domain names using command-line tools.

🌐 Network Setup  
- PC connected to internet

⚙️ Steps Performed  
1. Opened Command Prompt  
2. Executed `ping` command  
3. Used `nslookup` for DNS resolution  

💻 Commands  

ping www.google.com

nslookup www.google.com


📸 Screenshots  
<img width="934" height="400" alt="image" src="https://github.com/user-attachments/assets/27af1c8b-2922-4f67-9cf3-dae50cee7909" />
<img width="940" height="358" alt="image" src="https://github.com/user-attachments/assets/f7178f13-10ff-4b81-b508-de6715a15e50" />
<img width="940" height="624" alt="image" src="https://github.com/user-attachments/assets/ecc0a729-1922-4ae2-86a3-af79ed1440ea" />

<img width="940" height="663" alt="image" src="https://github.com/user-attachments/assets/ff841671-c4f0-4cb5-892e-3a1d979dfc74" />

🔍 Observations  
- ping verifies connectivity  
- nslookup resolves domain to IP  

✅ Result  
Successfully tested connectivity and DNS resolution.

🧾 Conclusion  
Network connectivity and DNS services are functioning properly.

---

## 🧪 2. Wireshark Packet Analysis

🎯 Objective  
To capture and analyze DNS, TCP, and UDP packets.

🌐 Network Setup  
- Wireshark installed on PC  

⚙️ Steps Performed  
- Opened Wireshark  
- Selected active interface  
- Started packet capture  
- Applied filters  

🔎 Filters Used  
```
dns
tcp
udp
```

📸 Screenshots  
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/f3099716-75c3-4619-abd6-41346cb6ae70" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/96f55973-861d-4710-9cf7-df16cc7477fc" />
<img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/f2879d03-8d9f-4ed1-a2f4-a1d0b6a729a3" />
<img width="933" height="753" alt="image" src="https://github.com/user-attachments/assets/bbb25a71-8c07-43f2-86bc-5921d12668b7" />


🔍 Observations  
- DNS resolves domain names  
- TCP ensures reliable communication  
- UDP provides faster transmission  

✅ Result  
Successfully analyzed network packets.

🧾 Conclusion  
Different protocols serve different networking purposes.

---

## 🧪 3. Traceroute Analysis

🎯 Objective  
To analyze network path using traceroute.

⚙️ Steps Performed  
- Executed traceroute command  
- Observed hops and delays  

💻 Command  
```
tracert google.com
```

📸 Screenshots  
<img width="940" height="317" alt="image" src="https://github.com/user-attachments/assets/63e818a5-8083-4fc5-8b3d-58074d023f0c" />


🔍 Observations  
- Shows intermediate routers (hops)  
- Displays latency  

✅ Result  
Route path successfully analyzed.

🧾 Conclusion  
Traceroute helps understand network path and delays.

---

## 🧪 4. Cisco Packet Tracer Setup

🎯 Objective  
To create and simulate a basic network.

⚙️ Steps Performed  
- Added PCs, switch, router  
- Connected devices  
- Assigned IP addresses  

✅ Result  
Network topology created.

🧾 Conclusion  
Packet Tracer helps simulate real networks.

---

## 🧪 5. VLAN and Trunk Ports

🎯 Objective  
To configure VLANs and test communication.

⚙️ Steps Performed  
- Created VLANs  
- Configured trunk ports  
- Tested ping between VLANs  

💻 Commands  
```
Both switches:

vlan 10
vlan 20

interface fa0/1
switchport mode access
switchport access vlan 10

interface fa0/2
switchport mode access
switchport access vlan 20

interface fa0/24
switchport mode trunk
```

📸 Screenshots  
<img width="577" height="203" alt="image" src="https://github.com/user-attachments/assets/9110f37d-f1a9-4a75-adee-0b7907134f4a" />
<img width="940" height="956" alt="image" src="https://github.com/user-attachments/assets/2d8645dc-e101-4b92-a485-67bc4edf6996" />
<img width="628" height="286" alt="image" src="https://github.com/user-attachments/assets/ea17f6bf-f24a-422f-b47c-9ba62e6035ed" />

✅ Result  
VLAN communication verified.

🧾 Conclusion  
Trunk ports allow VLAN communication.
Data will be tagged along with the VLAN name.
---

## 🧪 6. Native VLAN Configuration

🎯 Objective  
To configure native VLAN and troubleshoot mismatches.

⚙️ Steps Performed  
- Changed native VLAN
```
enable
configure terminal

interface fa0/24
switchport mode trunk
switchport trunk native vlan 99
```
- Now VLAN 99 will be untagged and other vlans will be tagged
- Tested connectivity  
- Checked mismatch issues  

✅ Result  
Mismatch issues identified and resolved.

🧾 Conclusion  
Native VLAN mismatch can disrupt communication.


## 🧪 7. Management VLAN Configuration

🎯 Objective  
To configure management VLAN for remote access.

⚙️ Steps Performed  
- Created VLAN  
- Assigned IP address  
- Enabled SSH/Telnet  

📸 Screenshots  
<img width="373" height="183" alt="image" src="https://github.com/user-attachments/assets/ad158a09-d832-47bd-8593-191064a69363" />
<img width="940" height="856" alt="image" src="https://github.com/user-attachments/assets/2466b123-d9d4-4242-940d-7d325ea28524" />
<img width="652" height="314" alt="image" src="https://github.com/user-attachments/assets/c548bdf7-8a2c-4e1a-a8c7-448a2b4afead" />


✅ Result  
Remote access successful.

🧾 Conclusion  
Management VLAN allows secure remote access.

---

## 🧪 8. Voice VLAN Configuration

🎯 Objective  
To configure voice VLAN for VoIP.

⚙️ Steps Performed  
- Created VLAN 20 for voice  
- Assigned VLAN 10 for data  
- Configured switch port  

💻 Command  
```
enable
configure terminal

vlan 10
name DATA

vlan 20
name VOICE

interface fa0/1
switchport mode access
switchport access vlan 10
switchport voice vlan 20


```

📸 Screenshots  
<img width="385" height="151" alt="image" src="https://github.com/user-attachments/assets/0ede3434-dd39-4420-934f-8b75994b7869" />
<img width="607" height="241" alt="image" src="https://github.com/user-attachments/assets/bc28e2ff-d691-46ce-bcdf-c8da48142648" />


✅ Result  
Voice and data traffic separated.

🧾 Conclusion  
Voice VLAN improves call quality.

## 🧪 9. VLAN Troubleshooting

🎯 Objective  
To resolve communication issues between VLANs.

⚙️ Steps Performed  
- Checked VLAN assignment  
- Verified trunk  
- Fixed configuration  

📸 Screenshots  
<img width="486" height="209" alt="image" src="https://github.com/user-attachments/assets/21328b6d-15ed-46e0-8617-f94463ddf486" />
<img width="700" height="250" alt="image" src="https://github.com/user-attachments/assets/9e164780-f597-4501-947a-e61bf97427d4" />
<img width="469" height="341" alt="image" src="https://github.com/user-attachments/assets/813a4fce-476b-4c76-b85f-a2ec48f17048" />
<img width="691" height="289" alt="image" src="https://github.com/user-attachments/assets/8cc383c9-a5ed-4aaa-bb76-0959ff04209c" />


✅ Result  
Connectivity restored.

🧾 Conclusion  
Proper VLAN setup is essential.

---

## 🧪 10. Inter-VLAN Routing

🎯 Objective  
To enable communication between VLANs using router.

⚙️ Steps Performed  
- Created subinterfaces  
- Assigned VLAN IDs  

💻 Commands  

interface g0/0.10
encapsulation dot1Q 10

interface g0/0.20
encapsulation dot1Q 20


📸 Screenshots  
<img width="469" height="341" alt="image" src="https://github.com/user-attachments/assets/4424b29d-ce93-43da-8cf3-e3bd8f3e9205" />
Switch:
<img width="349" height="251" alt="image" src="https://github.com/user-attachments/assets/2072eae3-09cf-43b2-8cae-93bfb367e28f" />
Router:
<img width="611" height="425" alt="image" src="https://github.com/user-attachments/assets/61e221b8-6288-4a34-9200-23b3f7586398" />
<img width="459" height="184" alt="image" src="https://github.com/user-attachments/assets/f4b3cc67-053d-4d44-a9c3-eeca75466dd1" />




✅ Result  
Inter-VLAN communication successful.

🧾 Conclusion  
Router enables communication between VLANs.

---

## 🧪 11. ACL Implementation

🎯 Objective  
To restrict traffic using ACL.

⚙️ Steps Performed  
- Configured ACL rules  
- Tested allowed/blocked traffic  

📸 Screenshots  
<img width="447" height="211" alt="image" src="https://github.com/user-attachments/assets/e8469660-0207-40d9-869c-46ec0450e2cc" />
<img width="775" height="325" alt="image" src="https://github.com/user-attachments/assets/be3d6a84-5b38-49e1-8dab-9b1bdba03c4c" />
<img width="603" height="108" alt="image" src="https://github.com/user-attachments/assets/b99bf030-84c8-48a6-b8d4-60cef0f5193f" />
<img width="686" height="244" alt="image" src="https://github.com/user-attachments/assets/3ea285fc-77e8-4293-bf53-0e7012baa8d1" />


✅ Result  
Traffic filtered successfully.

🧾 Conclusion  
ACL enhances network security.

---

## 🧪 12. Standard ACL

🎯 Objective  
To allow traffic from specific IP range.

💻 Commands  
```
access-list 10 permit 192.168.1.0 0.0.0.255
```

📸 Screenshots  
<img width="431" height="173" alt="image" src="https://github.com/user-attachments/assets/9f22b026-dda5-4dc1-8dcd-13126ad50be7" />
<img width="728" height="81" alt="image" src="https://github.com/user-attachments/assets/5187a6c7-811f-4fa3-b0ce-1062df55f086" />
<img width="702" height="286" alt="image" src="https://github.com/user-attachments/assets/62fd5db1-5e05-422a-9f61-d657386a848a" />


✅ Result  
Selective access allowed.

🧾 Conclusion  
Standard ACL filters based on source IP.

---

## 🧪 13. Extended ACL

🎯 Objective  
To block HTTP and FTP traffic.

💻 Commands  
```
access-list 100 deny tcp any any eq 80
access-list 100 deny tcp any any eq 21
access-list 100 permit ip any any
```

📸 Screenshots  
<img width="489" height="205" alt="image" src="https://github.com/user-attachments/assets/7c445be7-f71c-4a6a-b7f0-308d0657e9dc" />
<img width="661" height="286" alt="image" src="https://github.com/user-attachments/assets/8993291b-c33e-456d-850f-8aa6794f7fc9" />
<img width="627" height="216" alt="image" src="https://github.com/user-attachments/assets/a6c17620-dfb7-4943-8d22-8fcd4da09676" />
<img width="894" height="298" alt="image" src="https://github.com/user-attachments/assets/f534c29f-cf5a-413b-af6e-84f6e3be5e94" />


✅ Result  
Application traffic blocked.

🧾 Conclusion  
Extended ACL provides detailed filtering.

---

## 🧪 14. NAT (Static, Dynamic, PAT)

🎯 Objective  
To configure NAT techniques.

💻 Commands  
```
ip nat inside source list 1 interface g0/1 overload
```

📸 Screenshots  
<img width="630" height="205" alt="image" src="https://github.com/user-attachments/assets/92538377-7f28-4127-90db-c51b405b69b5" />
<img width="727" height="286" alt="image" src="https://github.com/user-attachments/assets/74da1947-9d25-494d-98cb-200300d86239" />
<img width="830" height="100" alt="image" src="https://github.com/user-attachments/assets/8fd22c1c-b264-4490-8abc-b60d3bee80a5" />
<img width="924" height="175" alt="image" src="https://github.com/user-attachments/assets/f61ca083-232c-43ea-8273-3965f609a60c" />


✅ Result  
NAT translation successful.

🧾 Conclusion  
NAT enables private-to-public communication.

---

## 🧪 15. iPerf Network Testing

🎯 Objective  
To test network performance using iPerf.

⚙️ Steps Performed  
- Installed iPerf  
- Connected devices in same network  
- Tested TCP and UDP  

💻 Commands  

iperf -s
iperf -c <server-ip>
iperf -u
iperf -bidir


📸 Screenshots  
(Add here)

✅ Result  
Network performance measured.

🧾 Conclusion  
iPerf helps analyze bandwidth and throughput.

---
🧾 Conclusion  
NAT enables communication between private and public networks.
