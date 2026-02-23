# Architecture Design

## 1. Overview

This homelab simulates a basic enterprise Active Directory environment
deployed on a virtualized infraestructure using KVM on Ubuntu.

The goal is to replicate a small corporate network with centralized
authentication, DNS services and Group Policy management.

---

## 2. Host Environment

- Host OS: Ubuntu 24.04.4 LTS.
- Hypervisor: KVM / QEMU.
- Virtualization management: Virt-Manager.
- Network Mode: NAT (libvirt default network).

--

## 3. Virtual Machines

### 3.1 Domain Controller

- Hostname: DC01.
- OS: Windows Server 2025 Standard Edition.
- Roles:
	- Active Directory Domain Services (AD DS).
	- DNS Server.
	- Global Catalog.
- Domain: empresa.local.
- IP Address: 192.168.122.10
- DNS: Self (127.0.0.1 / 192.168.122.10)

---

### 3.2 Client Machine

- Hostname: WIN11CLIENT
- OS: Windows 11 Pro.
- Joined to: empresa.local
- IP Address: 192.168.122.20
- DNS Server: 192.168.122.10 (DC01)

---

## 4. Network Topology

- Ubuntu Host (KVM)

	- DC01 (192.168.122.10)
		- AD DS
		- DNS
		- Global Catalog

	- WIN11CLIENT (192.168.122.20)
		- Domain joined to empresa.local

---

## 5. Logical Design

- Single Forest
- Single Domail (empresa.local)
- Centralized Authentication
- DNS integrated with Active Directory
- Structured Organizational Units (OU)
- Security Groups for role-based access control
- Corporate GPO applied to user OU

---

# 6. Design Decisions

- NAT Network used for lab isolation
- Single Domain Controller for simplicity
- DNS integrated into Active Directory to simplify name resolution
- Static IP configuration to ensure domain stability

---

## 7. Future Improvements

- Add secondary Domain Controller
- Implement DHCP Server role
- Deploy File Server with NTFS permissions
- Introduce Linux client integration
- Hybrid integration with Azure AD

---
