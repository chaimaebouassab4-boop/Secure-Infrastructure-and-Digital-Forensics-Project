# 🔐 Secure Infrastructure and Digital Forensics Project


## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [System Architecture](#-system-architecture)
- [Project Objectives](#-project-objectives)
- [Technologies & Tools](#-technologies--tools)
- [Key Components](#-key-components)
  - [Service Deployment](#1️⃣-service-deployment--configuration)
  - [Network Analysis](#2️⃣-network-communication-analysis)
  - [Digital Forensics](#3️⃣-digital-forensics--incident-response)
- [Technology Comparison](#-technology-comparison)
- [Learning Outcomes](#-learning-outcomes)
- [Getting Started](#-getting-started)
- [Repository Structure](#-repository-structure)
- [Team](#-collaboration)
- [References](#-references)

---

## 🎯 Project Overview

This project establishes a comprehensive framework for **building reliable, scalable, and secure IT systems** while integrating fundamental **Digital Forensics and Incident Response (DFIR)** practices.

The initiative combines three critical domains:

| Domain | Focus | Impact |
|--------|-------|--------|
| 🖥️ **System Administration** | Service deployment & configuration | Operational excellence |
| 🔒 **Security Analysis** | Network monitoring & threat detection | Proactive defense |
| 🔍 **Digital Forensics** | Evidence collection & incident response | Rapid recovery |

Through collaborative efforts, we deployed and analyzed **Nginx**, **Apache**, **Samba**, and **Docker** while conducting deep-dive network protocol analysis and forensic investigations using industry-standard tools.

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                              │
│                    (Web Browsers, SMB Clients)                   │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      REVERSE PROXY LAYER                         │
│                    ┌──────────────────┐                          │
│                    │   Nginx Proxy    │                          │
│                    │  Load Balancer   │                          │
│                    └────────┬─────────┘                          │
└─────────────────────────────┼─────────────────────────────────┘
                              │
                ┌─────────────┼─────────────┐
                ▼             ▼             ▼
    ┌─────────────────┐ ┌─────────────┐ ┌──────────────┐
    │  Apache Server  │ │    Samba    │ │    Docker    │
    │   Web Service   │ │ File Sharing│ │  Containers  │
    └─────────────────┘ └─────────────┘ └──────────────┘
                              │
                              ▼
    ┌─────────────────────────────────────────────────┐
    │           MONITORING & FORENSICS LAYER          │
    │   ┌──────────────┐      ┌──────────────┐       │
    │   │    Linux     │      │  Chkrootkit  │       │
    │   │  Collector   │      │   Scanner    │       │
    │   └──────────────┘      └──────────────┘       │
    └─────────────────────────────────────────────────┘
```

---

## 🎯 Project Objectives

| # | Objective | Description |
|---|-----------|-------------|
| 1️⃣ | **Service Deployment** | Configure and deploy production-grade system services |
| 2️⃣ | **Infrastructure Understanding** | Master web servers, file servers, and containerization |
| 3️⃣ | **Network Analysis** | Examine TCP/IP communication flows and termination sequences |
| 4️⃣ | **DFIR Methodology** | Apply forensic techniques to strengthen system security |
| 5️⃣ | **Tool Proficiency** | Utilize Linux Collector and Chkrootkit for forensic operations |
| 6️⃣ | **Collaborative Excellence** | Build teamwork skills in system administration contexts |

---

## 🛠️ Technologies & Tools

### 🖥️ System & Infrastructure

| Technology | Purpose | Key Features |
|------------|---------|--------------|
| ![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white) | Reverse Proxy / Load Balancer | High performance, scalability, SSL termination |
| ![Apache](https://img.shields.io/badge/Apache-D22128?style=flat&logo=apache&logoColor=white) | Web Server | Virtual hosts, .htaccess, modular architecture |
| ![Samba](https://img.shields.io/badge/Samba-E03C31?style=flat&logo=samba&logoColor=white) | File Sharing Service | SMB/CIFS protocol, cross-platform compatibility |
| ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white) | Container Platform | Isolation, portability, rapid deployment |
| ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black) | Operating System | System administration and security hardening |

### 🔍 Digital Forensics & Incident Response

| Tool | Category | Functionality |
|------|----------|---------------|
| 🗂️ **Linux Collector** | Evidence Acquisition | System artifacts, logs, memory, network data |
| 🛡️ **Chkrootkit** | Rootkit Detection | Malware scanning, system integrity checks |
| 📊 **Wireshark** | Network Analysis | Packet capture, protocol dissection |
| 📝 **Log Analysis** | Security Monitoring | Event correlation, anomaly detection |
| 🔐 **System Auditing** | Compliance | Configuration validation, access control |

---

## 🧩 Key Components

### 1️⃣ Service Deployment & Configuration

#### 🌐 Nginx - High-Performance Reverse Proxy

**Architecture Overview:**
```
Internet → Nginx (Port 80/443) → Backend Servers (Apache/Docker)
```

**Key Capabilities:**
- ✅ Reverse proxy configuration
- ✅ SSL/TLS termination
- ✅ Load balancing (Round-robin, Least connections)
- ✅ Caching and compression
- ✅ Rate limiting and DDoS protection

**Configuration Highlights:**
```nginx
upstream backend {
    server 192.168.1.10:8080;
    server 192.168.1.11:8080;
}

server {
    listen 80;
    location / {
        proxy_pass http://backend;
    }
}
```

---

#### 🌐 Apache - Versatile Web Server

**Features Implemented:**

| Feature | Description | Use Case |
|---------|-------------|----------|
| 🔹 Virtual Hosts | Multiple sites on single server | Resource optimization |
| 🔹 SSL/TLS | Encrypted communications | Data protection |
| 🔹 .htaccess | Directory-level config | Flexible access control |
| 🔹 Modules | Extensible functionality | Custom requirements |

---

#### 📁 Samba - Cross-Platform File Sharing

**Protocol Architecture:**
```
Windows Client ←→ SMB Protocol ←→ Samba Server ←→ Linux Filesystem
```

**Implementation Features:**

| Component | Configuration | Security |
|-----------|--------------|----------|
| 🔸 Authentication | User/Group permissions | PAM integration |
| 🔸 Shares | Public/Private directories | ACL enforcement |
| 🔸 Access Control | IP restrictions | Firewall rules |
| 🔸 Encryption | SMB3 protocol | Data in transit protection |

---

#### 🐳 Docker - Container Orchestration

**Container Benefits:**

```
┌────────────────────────────────────────┐
│         Docker Architecture            │
├────────────────────────────────────────┤
│  Application Container 1               │
│  ┌──────────────────────────────────┐  │
│  │  App + Dependencies              │  │
│  └──────────────────────────────────┘  │
│                                        │
│  Application Container 2               │
│  ┌──────────────────────────────────┐  │
│  │  App + Dependencies              │  │
│  └──────────────────────────────────┘  │
│                                        │
│         Docker Engine                  │
│         Host Operating System          │
└────────────────────────────────────────┘
```

**Advantages:**
- ⚡ Rapid deployment and scaling
- 🔒 Isolated environments
- 📦 Reproducible builds
- 🔄 Version control and rollback

---

### 2️⃣ Network Communication Analysis

#### 📡 TCP Connection Lifecycle Analysis

**Three-Way Handshake:**
```
Client                          Server
   │                              │
   │───── SYN ─────────────────→ │
   │                              │
   │←──── SYN-ACK ──────────────│
   │                              │
   │───── ACK ─────────────────→ │
   │                              │
   │    Established Connection    │
```

**Four-Way Termination:**
```
Client                          Server
   │                              │
   │───── FIN ─────────────────→ │
   │                              │
   │←──── ACK ──────────────────│
   │                              │
   │←──── FIN ──────────────────│
   │                              │
   │───── ACK ─────────────────→ │
   │                              │
   │    Connection Closed         │
```

**Analysis Focus:**

| Aspect | Normal Behavior | Security Concern |
|--------|-----------------|------------------|
| 🔹 Handshake | Complete 3-way sync | SYN floods, incomplete handshakes |
| 🔹 Data Transfer | Sequential ACKs | Packet loss, retransmissions |
| 🔹 Termination | Clean 4-way close | RST attacks, half-open connections |
| 🔹 Timing | Expected latency | Unusual delays, timeouts |

---

### 3️⃣ Digital Forensics & Incident Response

#### 🗂️ Linux Collector - Comprehensive Evidence Acquisition

**Collection Categories:**

| Category | Artifacts Collected | Forensic Value |
|----------|---------------------|----------------|
| 💾 **System** | OS version, kernel, hardware info | Environment baseline |
| 👥 **User Accounts** | /etc/passwd, /etc/shadow, login history | Access timeline |
| 🌐 **Network** | Connections, routes, firewall rules | Communication patterns |
| 📝 **Logs** | Syslog, auth logs, application logs | Event reconstruction |
| 📁 **Filesystem** | File metadata, permissions, timestamps | Activity evidence |
| ⚙️ **Processes** | Running processes, open files | Live system state |
| 🔐 **Security** | SELinux status, sudo logs, SSH keys | Security posture |

**Collection Command:**
```bash
sudo linux-collector --output /forensics/evidence-$(date +%Y%m%d_%H%M%S)
```

---

#### 🛡️ Chkrootkit - Rootkit Detection & System Integrity

**Detection Capabilities:**

```
┌─────────────────────────────────────────┐
│        Chkrootkit Scan Process          │
├─────────────────────────────────────────┤
│  1. Binary File Integrity               │
│     ├─ /bin/ps                          │
│     ├─ /bin/ls                          │
│     └─ /usr/bin/ssh                     │
│                                         │
│  2. Hidden Process Detection            │
│     └─ Process table comparison         │
│                                         │
│  3. Suspicious Files & Directories      │
│     ├─ /dev/shm/*                       │
│     └─ Temp directories                 │
│                                         │
│  4. Network Interface Anomalies         │
│     └─ Promiscuous mode detection       │
│                                         │
│  5. Known Rootkit Signatures            │
│     └─ 70+ rootkit patterns             │
└─────────────────────────────────────────┘
```

**Scan Results Interpretation:**

| Finding | Risk Level | Action Required |
|---------|------------|-----------------|
| ✅ Nothing found | Low | Continue monitoring |
| ⚠️ Possible rootkit | Medium | Investigate further |
| 🚨 Known rootkit detected | **CRITICAL** | Immediate response |
| ℹ️ False positive | Low | Document and whitelist |

---

#### 🔍 DFIR Methodology Framework

**Incident Response Lifecycle:**

```
┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐
│          │    │          │    │          │    │          │    │          │
│  PREPARE │───→│  DETECT  │───→│  ANALYZE │───→│ CONTAIN  │───→│  RECOVER │
│          │    │          │    │          │    │          │    │          │
└──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘
     ↑                                                                  │
     │                                                                  │
     └──────────────────────────── LESSONS LEARNED ←───────────────────┘
```

**Forensic Triage Process:**

| Phase | Activities | Tools Used |
|-------|-----------|------------|
| 🔎 **Identification** | Detect anomalies, assess scope | IDS/IPS, SIEM, logs |
| 📦 **Preservation** | Secure evidence, maintain chain of custody | Linux Collector, dd |
| 🔬 **Analysis** | Examine artifacts, correlate events | Chkrootkit, log parsers |
| 📊 **Documentation** | Record findings, create timeline | Reports, screenshots |
| 🎯 **Presentation** | Communicate results to stakeholders | Executive summaries |

---

## 📊 Technology Comparison

### Reverse Proxy vs Load Balancer

| Feature | Reverse Proxy | Load Balancer |
|---------|---------------|---------------|
| **Primary Function** | Request forwarding & security | Traffic distribution |
| **SSL Termination** | ✅ Yes | ✅ Yes |
| **Caching** | ✅ Extensive | ⚠️ Limited |
| **Health Checks** | ⚠️ Basic | ✅ Advanced |
| **Algorithm Support** | 🔸 Simple | 🔸 Complex (Weighted, Least connections) |
| **Use Case** | Single backend with security needs | Multiple backends requiring distribution |

### Docker vs Traditional VMs

| Aspect | Docker Containers | Virtual Machines |
|--------|-------------------|------------------|
| ⚡ **Startup Time** | Seconds | Minutes |
| 💾 **Resource Usage** | Lightweight (MBs) | Heavy (GBs) |
| 🔒 **Isolation** | Process-level | Hardware-level |
| 📦 **Portability** | Excellent | Good |
| 🎯 **Best For** | Microservices, CI/CD | Full OS isolation, legacy apps |

---

## 🎓 Learning Outcomes

### Technical Competencies Acquired

| Domain | Skills Developed | Proficiency Level |
|--------|------------------|-------------------|
| 🖥️ **System Administration** | Service configuration, performance tuning | ⭐⭐⭐⭐⭐ |
| 🏗️ **Infrastructure Design** | Scalable architecture, high availability | ⭐⭐⭐⭐ |
| 🔐 **Security Hardening** | Access control, encryption, monitoring | ⭐⭐⭐⭐⭐ |
| 🔍 **Digital Forensics** | Evidence collection, rootkit detection | ⭐⭐⭐⭐ |
| 📊 **Network Analysis** | Protocol analysis, traffic inspection | ⭐⭐⭐⭐ |
| 🤝 **Collaboration** | Team coordination, documentation | ⭐⭐⭐⭐⭐ |

### Professional Development

✅ **Deployment of production-ready infrastructure**  
✅ **Incident response and forensic investigation skills**  
✅ **Network protocol deep-dive understanding**  
✅ **Security-first system design principles**  
✅ **Cross-functional team collaboration experience**  
✅ **Technical documentation and reporting proficiency**  

---

## 🚀 Getting Started

### Prerequisites

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install core dependencies
sudo apt install -y nginx apache2 samba docker.io

# Install forensic tools
sudo apt install -y chkrootkit
```

### Quick Setup

#### 1️⃣ Nginx Configuration
```bash
sudo systemctl start nginx
sudo systemctl enable nginx
sudo nano /etc/nginx/sites-available/default
```

#### 2️⃣ Apache Setup
```bash
sudo systemctl start apache2
sudo a2enmod ssl proxy proxy_http
sudo systemctl restart apache2
```

#### 3️⃣ Samba Configuration
```bash
sudo nano /etc/samba/smb.conf
sudo smbpasswd -a username
sudo systemctl restart smbd
```

#### 4️⃣ Docker Initialization
```bash
sudo systemctl start docker
sudo usermod -aG docker $USER
docker --version
```

#### 5️⃣ Run Forensic Scan
```bash
sudo chkrootkit
sudo linux-collector --output /evidence
```

## 🤝 Collaboration

This project exemplifies the power of **collaborative system administration and security operations**. Our team demonstrated:

| Collaboration Aspect | Implementation |
|---------------------|----------------|
| 👥 **Shared Responsibility** | Distributed workload across team members |
| 🔧 **Coordinated Troubleshooting** | Joint problem-solving sessions |
| 📚 **Knowledge Sharing** | Regular documentation and presentations |
| 🎯 **Collective Learning** | Peer reviews and skill development |
| 🚀 **Unified Goals** | Aligned objectives and milestones |

### Team Achievements

✅ Deployed **robust web services** with 99.9% uptime  
✅ Established **secure file sharing** infrastructure  
✅ Implemented **containerized application** environments  
✅ Created **forensic readiness** protocols  
✅ Built **incident response** capabilities  

---

## 📚 References

### Official Documentation

| Resource | Link | Category |
|----------|------|----------|
| 📘 Nginx Documentation | https://nginx.org/en/docs/ | Web Server |
| 📗 Apache HTTP Server | https://httpd.apache.org/docs/ | Web Server |
| 📙 Samba Guide | https://www.samba.org/samba/docs/ | File Sharing |
| 📕 Docker Docs | https://docs.docker.com/ | Containerization |
| 📓 Linux Collector | https://github.com/topics/linux-collector | Forensics |
| 📔 Chkrootkit | http://www.chkrootkit.org/ | Security |

### Learning Resources

| Platform | Focus Area | Level |
|----------|------------|-------|
| 🎓 SANS Digital Forensics | DFIR Training | Advanced |
| 🎬 13Cubed (YouTube) | Forensic Analysis | Intermediate |
| 🔬 DFIR Science | Incident Response | Advanced |
| 🏴 TryHackMe | Security Labs | Beginner-Intermediate |
| 🎯 HackTheBox | Penetration Testing | Intermediate-Advanced |
| 📖 Digital Forensics Magazine | Industry News | All Levels |

### Recommended Reading

- 📖 *The Practice of Network Security Monitoring* - Richard Bejtlich
- 📖 *File System Forensic Analysis* - Brian Carrier
- 📖 *Incident Response & Computer Forensics* - Jason Luttgens
- 📖 *The Art of Memory Forensics* - Michael Hale Ligh
- 📖 *Network Forensics* - Sherri Davidoff & Jonathan Ham

---


### 💡 Future Enhancements

🔹 Automated deployment with Ansible  
🔹 Kubernetes orchestration  
🔹 Advanced SIEM integration  
🔹 Automated forensic analysis pipeline  
🔹 Real-time threat intelligence feeds  

---

**Built with ❤️ by the Secure Infrastructure & DFIR Team**

*"Security is not a product, but a process." - Bruce Schneier*

</div>
