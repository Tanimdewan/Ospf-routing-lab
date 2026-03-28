# 🔥 OSPF Routing Lab (Cisco Packet Tracer)

## 📌 Project Overview

This project demonstrates how to configure **OSPF (Open Shortest Path First)** routing in a multi-router network using Cisco Packet Tracer.

এই প্রজেক্টে আমরা দেখিয়েছি কিভাবে OSPF ব্যবহার করে বিভিন্ন network connect করা যায়।

---

## 🌐 Network Topology

```
PC1 --- R1 --- R2 --- R3 --- PC2
```

### 📍 Networks:

* 192.168.1.0/24 (PC1 side)
* 192.168.2.0/24 (between R1-R2)
* 192.168.3.0/24 (between R2-R3)
* 192.168.4.0/24 (PC2 side)

---

## ⚙️ OSPF Configuration

### 🔹 R1

```
router ospf 1
router-id 1.1.1.1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.2.0 0.0.0.255 area 0
```

### 🔹 R2

```
router ospf 1
router-id 2.2.2.2
network 192.168.2.0 0.0.0.255 area 0
network 192.168.3.0 0.0.0.255 area 0
```

### 🔹 R3

```
router ospf 1
router-id 3.3.3.3
network 192.168.3.0 0.0.0.255 area 0
network 192.168.4.0 0.0.0.255 area 0
```

---

## 🧠 Key Concepts

### 🔸 OSPF

Dynamic routing protocol that automatically learns routes.

### 🔸 Router ID

Unique ID for each router in OSPF network.

### 🔸 Area 0

Backbone area (সব router connect থাকতে হবে এখানে)

### 🔸 Neighbor Relationship

Routers automatically discover each other.

### 🔸 Cost

Best path select করতে use হয় (lower cost = better path)

---

## 🔍 Verification Commands

```
show ip ospf neighbor
show ip route
```

---

## 📡 Testing

✔ PC1 থেকে PC2 ping successful
✔ All routers learned routes via OSPF

---

## 🏢 Real-World Scenario

ধরো:

* R1 = Head Office
* R2 = ISP / Core Network
* R3 = Branch Office

OSPF automatically route exchange করে → manual configuration লাগে না।

---

## 📁 Files Included

* Packet Tracer file (.pkt)
* Router configurations
* Network topology diagram

---

## 🚀 Future Improvements

* Multi-Area OSPF (Area 0, Area 1)
* OSPF vs Static Routing comparison
* Failover testing

---

## 🙌 Author

Created for learning and networking practice.
