# OSPF Routing Lab (Cisco Packet Tracer)

## Project Overview

This project demonstrates how to configure **OSPF (Open Shortest Path First)** routing in a multi-router network using Cisco Packet Tracer.

## Network Topology

   PC1 (192.168.1.2)
         │
       [SW1]
         │
        R1 (192.168.1.1 / 192.168.2.1)
         │
        R2 (192.168.2.2 / 192.168.3.1)
         │
        R3 (192.168.3.2 / 192.168.4.1)
         │
       [SW2]
         │
    PC2 (192.168.4.2)

- **SW1, SW2** → Layer 2 switches  
- **R1, R2, R3** → Routers running OSPF  
- **All routers in OSPF Area 0**


- **SW1, SW2** → Layer 2 switches  
- **R1, R2, R3** → Routers running OSPF  
- **All routers in OSPF Area 0**  

*Screenshot of topology is included in `/topology/ospf-topology.png`*

##  Router Configuration Summary

| Router | Interfaces & IPs                | Router ID | OSPF Area |
|--------|--------------------------------|-----------|-----------|
| R1     | g0/0: 192.168.1.1/24           | 1.1.1.1   | 0         |
|        | g0/1: 192.168.2.1/24           |           |           |
| R2     | g0/0: 192.168.2.2/24           | 2.2.2.2   | 0         |
|        | g0/1: 192.168.3.1/24           |           |           |
| R3     | g0/0: 192.168.3.2/24           | 3.3.3.3   | 0         |
|        | g0/1: 192.168.4.1/24           |           |           |

> Full router configuration files are included in the `configs/` folder:
> - `R1.txt`  
> - `R2.txt`  
> - `R3.txt`  

## Key Concepts

- **OSPF**: Dynamic routing protocol that automatically learns routes.  
- **Router ID**: Unique ID for each router in OSPF network.  
- **Area 0**: Backbone area where all routers must connect.  
- **Neighbor Relationship**: Routers automatically discover each other.  
- **Cost**: OSPF chooses the best path (lower cost = preferred path).  

## Verification Commands

- On Routers:
show ip ospf neighbor
show ip route

# Networks:

* 192.168.1.0/24 (PC1 side)
* 192.168.2.0/24 (between R1-R2)
* 192.168.3.0/24 (between R2-R3)
* 192.168.4.0/24 (PC2 side)

## OSPF Configuration

## Router-1
router ospf 1
router-id 1.1.1.1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.2.0 0.0.0.255 area 0

### Router-2
router ospf 1
router-id 2.2.2.2
network 192.168.2.0 0.0.0.255 area 0
network 192.168.3.0 0.0.0.255 area 0

### Router-2

router ospf 1
router-id 3.3.3.3
network 192.168.3.0 0.0.0.255 area 0
network 192.168.4.0 0.0.0.255 area 

### OSPF

Dynamic routing protocol that automatically learns routes.

### Router ID

Unique ID for each router in OSPF network.

###  Area 0

Backbone area (সব router connect থাকতে হবে এখানে)

###  Neighbor Relationship

Routers automatically discover each other.

### Cost

Used to Best path  (lower cost = better path)

## Verification Commands

show ip ospf neighbor
show ip route

##  Testing

✔ PC1 থেকে PC2 ping successful
✔ All routers learned routes via OSPF

##  Real-World Scenario

Suppose

* R1 = Head Office
* R2 = ISP / Core Network
* R3 = Branch Office

OSPF automatically  exchange route  No need manual configuration ল

## Files Included

* Packet Tracer file (.pkt)
* Router configurations
* Network topology diagram

##  Future Improvements

* Multi-Area OSPF (Area 0, Area 1)
* OSPF vs Static Routing comparison
* Failover testing

## Author

Created for learning and networking practice.
