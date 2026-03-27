\# 🏫 **Smart Campus Network (CCNA Project)**



\## 📌 **Project Overview**



This project demonstrates the design and implementation of a \*\*Smart Campus Network\*\* using Cisco Packet Tracer. It integrates networking fundamentals, IoT device management, and security mechanisms to simulate a real-world campus infrastructure.



The network is designed to provide secure communication between multiple departments while enabling controlled access to IoT devices.



\---



\## 🚀 **Key Features**



\* 🌐 Dynamic Routing using RIP Version 2

\* 📡 DHCP Server for automatic IP allocation (IoT network)

\* 🔐 Standard Access Control List (ACL) for security

\* 📶 Secure Wireless Network with WPA2/AES encryption

\* 🏢 Multi-department network segmentation

\* 🤖 IoT device integration (Fan, Door, Air Conditioner)

\* 🖥️ Centralized server for administration

\* 🌍 Campus-wide connectivity through routers



\---



\## 🏗️ **Network Topology**



The network consists of multiple subnets representing different departments:



| Network        | Description         |

| -------------- | ------------------- |

| 192.168.1.0/24 | CEO Network         |

| 192.168.2.0/24 | HOD Faculty Network |

| 192.168.4.0/24 | Student Lab Network |

| 192.168.5.0/24 | Admin + IoT Network |

| 192.168.3.0/24 | Inter-router Link   |



📷 \*(Add your topology screenshot as `topology.png` here)\*



\---



\## 🌐 **Routing Configuration**



\* Routing Protocol: \*\*RIP Version 2\*\*

\* Enabled on all routers for dynamic route exchange

\* Configured with `no auto-summary` for classless routing



\### **Sample Configuration**



```

router rip

version 2

no auto-summary

network 192.168.1.0

network 192.168.2.0

network 192.168.3.0

network 192.168.4.0

network 192.168.5.0

```



\---



\## 📡 **DHCP Configuration (IoT Network)**



\* DHCP Server configured on \*\*Router1\*\*

\* Network: `192.168.5.0/24`



\### **Purpose**



\* Automatically assign IP addresses to IoT devices

\* Reduce manual configuration

\* Improve scalability



\### Sample Configuration



```

ip dhcp excluded-address 192.168.5.1 192.168.5.10



ip dhcp pool iot

network 192.168.5.0 255.255.255.0

default-router 192.168.5.1

dns-server 8.8.8.8

```



\---



\## 🔐 **Security Implementation (ACL)**



A \*\*Standard ACL\*\* is used to restrict access to IoT devices.



\### **Allowed Devices**



\* CEO Laptop → 192.168.1.10

\* HOD Laptop → 192.168.2.10



\### **Restricted**



\* All other devices are denied access to IoT network



\### **Configuration**



```

access-list 10 permit 192.168.1.10

access-list 10 permit 192.168.2.10

access-list 10 deny any



interface GigabitEthernet0/0

ip access-group allow-ceo-hod out

```



\### **Key Concept**



\* Standard ACL filters based on \*\*source IP address\*\*

\* Applied near the \*\*destination network (IoT network)\*\*



\---



\## 📶 **Wireless \& IoT Integration**



\* Wireless router configured for IoT connectivity

\* Devices connected:



&#x20; \* Fan

&#x20; \* Door

&#x20; \* Air Conditioner



\### **Features**



\* Secure communication using WPA2 personal/AES

\* Remote monitoring and control

\* Centralized management



\---



\## ⚙️ **Technologies Used**



\* Cisco Packet Tracer

\* Routing Protocols (RIP v2)

\* DHCP

\* Access Control Lists (ACL)

\* Wireless Networking

\* IoT Simulation



\---



\## 🎯 **Learning Outcomes**



\* Practical implementation of CCNA concepts

\* Understanding of routing and subnetting

\* Network security using ACLs

\* DHCP configuration and IP management

\* IoT integration in networking

\* Real-world network design approach



\---



\## 📂 **Project Files**



\* `smart-campus.pkt` → Packet Tracer simulation file

\* `topology.png` → Network diagram

\* `configs/` → Device configurations (optional)



\---



\## 🔮 **Future Improvements**



\* Replace RIP with \*\*OSPF (Open Shortest Path First)\*\*

\* Implement \*\*Extended ACLs\*\* for port-level control

\* Add \*\*NAT\*\* for internet access simulation

\* Integrate with \*\*cloud platforms (AWS VPC mapping)\*\*

\* VLAN segmentation for better network design



\---



\## 👨‍💻 Author



\*\*Your Name\*\*

DABLIKAR DURGA PRASAD



\---



\## ⭐ **Conclusion**



This project demonstrates how networking, security, and IoT can be combined to build a \*\*secure and scalable smart campus infrastructure\*\* using CCNA-level concepts.



\---



