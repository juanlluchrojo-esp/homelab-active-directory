# Active Directory Homelab - Windows Server 2025

Enterprise-style Active Directory homelab built on Ubuntu + KVM,
including DNS integration, OU structure and Group Policy implementation.

![Windows Server](https://img.shields.io/badge/Windows_Server-2025-blue)
![AD DS](https://img.shields.io/badge/Active_Directory-Configured-green)
![Virtualization](https://img.shields.io/badge/KVM-Ubuntu-orange)

## Project Structure

- docs/
	- 01-architecture.md
	- 02-ad-installation.md
	- 03-organizational-structure.md

## Architecture

- Hypervisor: Ubuntu + KVM.
- Domain Controller: Windows Server 2025 Standard Edition.
- Client: Windows 11 Pro.
- Domain: empresa.local

## Configured Components

- Active Directory Domain Services.
- Integrated DNS Server.
- Creation of structured Organizative Units (OU).
- Creation of Security Groups.
- Implementation of corporative Group Policy.
- Client to Domain union.
- Validation with gpresult.

## Objective

Simulate basic corporative environment for learning of Systems Administration.

## Skills Demonstrated

- Active Directory deployment
- DNS configuration
- Domain controller promotion
- Group Policy implementation
- Windows Server administration
- Virtualization with KVM
- Technical documentation in English
- Version control with Git
