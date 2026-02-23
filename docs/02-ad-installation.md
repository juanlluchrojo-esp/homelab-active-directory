# Active Directory Deployment

## 1. Objective

Deploy a new Active Directory forest and domain using Windows Server 2025,
including DNS integration and Global Catalog configuration.

---

## 2. Server Preparation

### 2.1 Static IP Configuration

The Domain Controller was configured with a static IP address to ensure
stable domain services.

- IP Address: 192.168.122.10
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.122.1
- Preferred DNS: 127.0.0.1

Static configuration is critical for Active Directory stability.

---

## 3. Role Installation

### 3.1 AD DS Role

Installed the following server role:

- Active Directory Domain Services (AD DS)

Using:
- Server Manager
- Add Roles and Features Wizard

The DNS Server role was selected during AD DS installation.

---

## 4. Domain Controller Promotion

The server was promoted to a Domain Controller with the following configuration:

### Forest Configuration
- Deployment Operation: Add new forest
- Root Domain Name: empresa.local
- Forest Functional Level: Windows Server 2025
- Domain Functional Level: Windows Server 2025

### Domain Controller Options
- DNS Server: Enabled
- Global Catalog: Enabled
- Read Only Domain Controller (RODC): Disabled

### DSRM Password
A Directory Services Restore Mode password was defined
for recovery scenarios.

---

## 5. DNS Configuration

DNS was integrated into Active Directory.

- Forward Lookup Zone automatically created: empresa.local
- Dynamic updates enabled
- Domain Controller registered automatically in DNS

This ensures proper name resolution for domain clients.

---

## 6. Post-Installation Validation

After reboot, the following validations were performed:

### 6.1 Service Verification

- Active Directory Users and Computers
- DNS Manager
- Group Policy Management Console

All services loaded correctly.

### 6.2 Command Line Validation

Verified domain controller status:

```
whoami
```

Expected output:
```
EMPRESA\administrator
```

---

## 7. Security Considerations

- Administrator account secured
- Static IP enforced
- Domain functional levels set to latest available version

---

## 8. Lessons Learned

- Static IP configuration must be set before domain promotion
- DNS integration simplifies domain resolution
- Proper functional level selection ensures feature compatibility
