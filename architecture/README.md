# Azure Infrastructure Architecture

## Components

- Azure Virtual Network (VNet)
- Subnet configuration
- Azure Load Balancer
- Backend pool
- Health probes
- Network Security Groups
- Ubuntu Linux virtual machines
- Nginx web servers

---

## Traffic Flow

Internet
↓
Azure Load Balancer (Public IP)
↓
Backend Pool
↓
vm-web-01
vm-web-02

---

## Design Goals

- High availability web infrastructure
- Traffic distribution using Azure Load Balancer
- Secure backend Linux servers
- NSG-based traffic filtering
- HTTPS-enabled web hosting
- Linux administration and troubleshooting practice
