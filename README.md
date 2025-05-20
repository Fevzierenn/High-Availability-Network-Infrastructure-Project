# High Availability VLAN-Based Network Design Project

This project demonstrates the design and implementation of a **high availability Layer 2/3 network architecture** using **Cisco Packet Tracer**. It features VLAN segmentation, subnetting, redundant connections, and key network protocols like **EtherChannel**, **Spanning Tree Protocol (STP)**, and **Hot Standby Router Protocol (HSRP)**.

---

## 📌 Project Overview

- **Type:** Enterprise Network Design (Simulation)
- **Tool Used:** Cisco Packet Tracer
- **Topology:** 2 internal networks (Sales & Production)
- **Key Technologies:** VLAN, Subnetting, EtherChannel, STP, HSRP
- **Purpose:** Simulate a fault-tolerant, high-performance enterprise network infrastructure suitable for real-world business operations

---

## 🧱 Network Architecture

### 🖥 Internal Networks
| Department   | Host Requirement | VLAN ID | Subnet Size     |
|--------------|------------------|---------|-----------------|
| Sales        | 100 hosts        | 10      | /25 or larger   |
| Production   | 300 hosts        | 20      | /23 or larger   |

- Each department is logically separated using **VLANs**.
- IP addressing is uniquely assigned per department based on subnet size.

### 🧩 Equipment Used
- **Routers:** 2 Cisco routers (HSRP configuration)
- **Switches:** 3 Cisco Layer 2 switches
- **Application Server:** Hosting **SAP Business One**
- **Database Server:** Running **Microsoft SQL Server**
- **End Devices:** PCs/Clients assigned to respective VLANs

---

## 🔗 Network Design and Protocols

### 🔁 Redundancy
- **Redundant physical links** are implemented between switches and routers.
- These links are aggregated using **EtherChannel**, ensuring load balancing and link redundancy.

### 🧬 EtherChannel
- Used between switches and between switch-router connections.
- Configured using **PAgP (Port Aggregation Protocol)** or **LACP**.
- Ensures bandwidth optimization and failover capabilities.

### 🌲 Spanning Tree Protocol (STP)
- **STP** is configured to prevent Layer 2 loops in the network.
- One switch is set as **Root Bridge**, others as alternatives.
- STP ensures a loop-free topology and automatically recalculates paths during link failures.

### 🔥 HSRP (Hot Standby Router Protocol)
- **2 routers** are configured in **HSRP group** to provide **gateway redundancy**.
- One router acts as **Active**, and the other as **Standby**.
- In case of active router failure, standby takes over instantly.
- Clients use a **virtual IP address** as their default gateway.

---

## 🧪 Services Integration

- **SAP Business One** server is placed in the Production VLAN and provides enterprise application services.
- **MS SQL Server** is deployed in a secure zone and communicates with the SAP server for database operations.
- End devices can access the SAP and MSSQL services via routed VLANs and default gateways handled by HSRP.

---

## 🌐 IP Addressing Plan (Example)

| VLAN | Subnet            | Default Gateway | Description       |
|------|--------------------|------------------|--------------------|
| 10   | 192.168.10.0/25    | 192.168.10.1     | Sales Department   |
| 20   | 192.168.20.0/23    | 192.168.20.1     | Production Dept    |

> Gateways are handled through HSRP’s virtual IP address.

---

## 📁 Project Files

- `.pkt` file: Cisco Packet Tracer network topology


## 🚀 Learning Objectives & Skills Demonstrated

- Network segmentation using VLANs
- Subnetting for efficient IP usage
- Implementation of high availability protocols (HSRP, STP)
- Load balancing and redundancy via EtherChannel
- Layer 2/3 design best practices
- Enterprise application integration in network design (SAP, MSSQL)


## 📌 Notes

This project was part of a hands-on networking course focused on **High Availability Systems**. It showcases practical understanding and implementation of fault-tolerant network architectures suitable for real-world enterprise environments.




