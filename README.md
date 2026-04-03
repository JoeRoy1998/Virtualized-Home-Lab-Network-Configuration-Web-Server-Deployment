# Virtualized Home Lab: Network Configuration & Web Server Deployment

## Overview
This project demonstrates the creation of a virtualized home lab environment using Oracle VM VirtualBox. The lab simulates a small network with a server and client system to practice networking, system administration, and basic cybersecurity concepts.

The environment includes static IP configuration, SSH remote access, a deployed web server, and firewall rule implementation.

## Lab Architecture
Host Machine
│
├── Ubuntu Server (192.168.56.10)
│     - Apache Web Server
│     - SSH Enabled
│     - UFW Firewall
│
└── Ubuntu Client (192.168.56.20)
      - Used for testing and administration

## Technologies Used
- Oracle VM VirtualBox
- Ubuntu Server
- Ubuntu Desktop
- Apache HTTP Server
- OpenSSH
- UFW (Uncomplicated Firewall)

## Key Skills Demonstrated
- Virtualization and lab environment setup
- Network configuration (static IP addressing)
- Linux system administration
- Secure remote access using SSH
-  Web server deployment and management
- Firewall configuration and traffic control
- Troubleshooting network and service issues

- ## Setup & Configuration

### 1. Virtual Environment Setup
- Created two virtual machines using VirtualBox:
  - Ubuntu Server
  - Ubuntu Client
- Configured dual network adapters:
  - NAT (internet access)
  - Host-only (internal communication)

### 2. Network Configuration
- Assigned static IP addresses using Netplan:
  - Server: 192.168.56.10
  - Client: 192.168.56.20

### 3. SSH Configuration
- Installed and enabled OpenSSH on the server
- Verified remote access from client to server

### 4. Web Server Deployment
- Installed Apache HTTP Server on the server
- Verified web access from the client browser

### 5. Firewall Configuration
- Enabled UFW firewall
- Allowed:
  - SSH (port 22)
  - HTTP (port 80)

## Troubleshooting Scenario: Web Server Not Accessible

### Problem
The client machine was unable to access the web server hosted on the server VM.

### Diagnosis
- Verified network connectivity using ping (successful)
- Confirmed SSH access to the server (successful)
- Checked Apache service status (running)
- Reviewed firewall rules using UFW

### Root Cause
Port 80 (HTTP) was blocked by the firewall.

### Resolution
- Updated UFW rules to allow HTTP traffic on port 80
- Verified successful access to the web server from the client

### Outcome
The issue was resolved by correctly identifying and modifying firewall rules, restoring web server accessibility.

## Screenshots

### Client VM

#### Ping Test
![Ping Test](screenshots/client-ping.png)

#### SSH Connection
![SSH Connection](screenshots/ssh-connection.png)

#### Web Server Access
![Web Access](screenshots/web-access.png)

---

### Server VM

#### Static IP Configuration
![Server IP](screenshots/server-ip.png)

#### Apache Service Status
![Apache Status](screenshots/apache-status.png)

#### Firewall Rules
![UFW Status](screenshots/ufw-status.png)


## Future Improvements

- Add a penetration testing machine (Kali Linux)
- Perform network scanning and vulnerability assessments
- Implement centralized logging and monitoring
- Expand to Active Directory environment
- Simulate real-world attack and defense scenarios
