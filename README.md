# OPNsense Firewall Lab

## Overview
Designed and deployed a simulated SME network using OPNsense 
as the primary firewall. This lab covers core network security 
concepts including firewall rule management, DMZ architecture, 
DNS filtering, and VPN configuration.

## Network Topology
WAN (10.0.2.15)
    |
[OPNsense Firewall]
    |              |
  LAN            DMZ
192.168.1.0/24  192.168.2.0/24
    |               |
Ubuntu (client)  Kali (server)

## Technologies Used
- OPNsense 24.7.0
- VirtualBox
- Ubuntu 22.04
- Kali Linux

## What Was Implemented

### 1. Firewall Rules & Aliases
- Created named aliases for hosts and networks
- Implemented permit/deny rules with proper ordering
- Blocked specific destinations using IP aliases

### 2. DNS Filtering
- Forced all DNS traffic through internal resolver
- Blocked direct access to external DNS servers (port 53)
- Prevents DNS bypass attacks

### 3. DMZ Architecture
- Created isolated DMZ zone (192.168.2.0/24)
- Blocked DMZ → LAN traffic to prevent lateral movement
- Restricted LAN → DMZ access to admin host only

### 4. VPN (OpenVPN)
- Created internal PKI with custom CA
- Generated server and client certificates
- Configured OpenVPN server instance

## Key Concepts Demonstrated
- Stateful firewall inspection vs traditional ACLs
- Defense in depth through network segmentation
- Least privilege access control
- PKI and certificate based authentication
- DNS security and filtering

## Lessons Learned
- Importance of rule ordering (first match wins)
- Stateful inspection automatically handles return traffic
- DMZ isolation is critical to prevent lateral movement
- Always plan DNS exceptions before implementing filtering
