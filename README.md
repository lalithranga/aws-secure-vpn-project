# 🔐 SecureBank Multi-Region AWS VPC Architecture

A secure multi-region AWS network architecture project designed for a simulated financial institution (**SecureBank**).

This project demonstrates enterprise cloud security practices including VPC isolation, network segmentation, encrypted Site-to-Site VPN connectivity, Linux administration, and AWS security controls.

---

## 🚀 Skills Demonstrated

- AWS Cloud Infrastructure
- Secure VPC Architecture
- Multi-Region Networking
- Linux Server Administration
- IPsec VPN Configuration
- Network Security
- Security Groups
- Route Tables
- CIDR Planning
- Cloud Security Best Practices

---

## 🛠️ Technologies Used

- AWS VPC
- Amazon EC2
- Security Groups
- Internet Gateway
- Elastic IP
- Virtual Private Gateway (VGW)
- Customer Gateway (CGW)
- AWS Site-to-Site VPN
- Linux
- Libreswan IPsec
- AES-256 Encryption
- IKEv2

---

# 🏗️ Architecture Overview

The solution contains two isolated AWS environments:

## 🇦🇺 Sydney Region (Head Office)

**VPC:** SecureBank-Sydney-VPC

```
CIDR: 10.0.0.0/16
Subnet: 10.0.1.0/24
```

Components:

- Linux EC2 Server
- Security Group Firewall
- Virtual Private Gateway
- Route Tables


---

## 🇸🇬 Singapore Region (Branch Office)

**VPC:** SecureBank-Singapore-VPC

```
CIDR: 172.16.0.0/16
Subnet: 172.16.1.0/24
```

Components:

- Linux EC2 Server
- Elastic IP
- Customer Gateway
- Libreswan VPN Configuration


---

# 🔒 Security Implementation

## Network Segmentation

Two separate VPC environments were created to isolate business locations.

Benefits:

- Reduces attack impact
- Prevents unnecessary network access
- Limits lateral movement during security incidents


## Least Privilege Access

Security Groups were configured using a default deny approach.

Controls include:

- Restricted SSH access
- Limited ICMP traffic
- Controlled administrative access
- No unrestricted internet exposure


## Encrypted VPN Communication

A secure Site-to-Site VPN tunnel was implemented using:

- IPsec
- IKEv2
- AES-256 encryption
- SHA-256 integrity verification


This protects communication between Sydney and Singapore over the public internet.


---

# 🌐 VPN Architecture

Traffic flow:

```
Sydney EC2
    |
Route Table
    |
Virtual Private Gateway
    |
Encrypted IPsec VPN Tunnel
    |
Customer Gateway
    |
Singapore EC2
```

---

# 🐧 Linux Administration

Configured VPN services on Linux using:

- Libreswan IPsec
- ipsec.conf
- aws-vpn.secrets
- VPN status monitoring commands


Verified:

- VPN tunnel status
- Encryption parameters
- Private IP communication
- Secure SSH connectivity


---

# 📊 Security Concepts Applied

This project follows:

- AWS Well-Architected Security Pillar
- NIST Cybersecurity Framework principles
- Zero Trust networking concepts
- Defense-in-depth security model
- Principle of Least Privilege


---

# 📂 Repository Contents

```
SecureBank-Multi-Region-VPC/

├── README.md
├── architecture-diagram.png
├── SCS-C02-Assessment-Report.pdf
```

---

# 📚 Learning Outcomes

Through this project I gained hands-on experience with:

- Designing secure AWS networks
- Deploying multi-region cloud infrastructure
- Configuring VPN connectivity
- Managing Linux cloud servers
- Applying cloud security principles
- Troubleshooting network connectivity issues


---

# 🚀 Future Improvements

- Automate infrastructure using Terraform
- Add AWS CloudWatch monitoring
- Implement AWS Secrets Manager
- Add AWS IAM least privilege policies
- Create CI/CD deployment pipeline

---

## 📄 Documentation

Detailed implementation steps and screenshots are available in:

**aws-secure-vpn-project.pdf**