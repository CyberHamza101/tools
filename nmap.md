# Nmap — Network Mapper

## 📌 Overview

Nmap (Network Mapper) is one of the most powerful and widely used network scanning tools in cybersecurity. It helps security professionals discover hosts, identify open ports, detect services, and fingerprint operating systems.

Nmap is used in:

* **Network enumeration**
* **Vulnerability assessment**
* **Penetration testing**
* **Asset discovery**
* **Firewall testing**

---

## ⚙️ Installation

Nmap comes pre-installed on most security‑focused Linux systems like Kali Linux. To install it manually:

### Debian/Ubuntu

```bash
sudo apt install nmap
```

### RedHat/CentOS

```bash
sudo yum install nmap
```

### macOS

```bash
brew install nmap
```

Verify installation:

```bash
nmap --version
```

---

## 🧩 Basic Scans

### 🔍 Scan a Single Host

```bash
nmap <target>
```

Example:

```bash
nmap 192.168.1.10
```

### 🔍 Scan Multiple Hosts

```bash
nmap 192.168.1.10 192.168.1.20
```

### 🔍 Scan a Range of IPs

```bash
nmap 192.168.1.1-254
```

### 🔍 Scan an Entire Subnet

```bash
nmap 192.168.1.0/24
```

---

## ⚡ Port Scanning

### Default Scan (Top 1000 Ports)

```bash
nmap <target>
```

### Scan Specific Ports

```bash
nmap -p 22,80,443 <target>
```

### Scan All Ports (0–65535)

```bash
nmap -p- <target>
```

---

## 🚀 Scan Types

### TCP SYN Scan (Stealth Scan)

Most common and fast:

```bash
nmap -sS <target>
```

### TCP Connect Scan

Full connection:

```bash
nmap -sT <target>
```

### UDP Scan

```bash
nmap -sU <target>
```

### Combined TCP + UDP Scan

```bash
nmap -sS -sU <target>
```

---

## 🧠 Service & Version Detection

Detect service versions running on open ports:

```bash
nmap -sV <target>
```

Aggressive version detection:

```bash
nmap -sV --version-intensity 9 <target>
```

---

## 🖥️ OS Detection

Basic OS detection:

```bash
nmap -O <target>
```

Combine OS + version + script scan:

```bash
nmap -A <target>
```

`-A` includes:

* OS detection
* Version detection
* Script scanning
* Traceroute

---

## 🔧 NSE — Nmap Scripting Engine

Nmap includes powerful scripts for enumeration and vulnerability scanning.

### Run Default Scripts

```bash
nmap -sC <target>
```

### Run a Specific Script

```bash
nmap --script http-title <target>
```

### Run Multiple Scripts

```bash
nmap --script http-title,ssh-auth-methods <target>
```

### Script Categories

* `auth`
* `broadcast`
* `brute`
* `default`
* `discovery`
* `exploit`
* `fuzzer`
* `intrusive`
* `malware`
* `safe`
* `version`

Example: brute force SSH

```bash
nmap --script ssh-brute -p 22 <target>
```

---

## ⚙️ Output Options

### Normal Output

```bash
nmap <target> -oN scan.txt
```

### XML Output

```bash
nmap <target> -oX scan.xml
```

### GREPable Output

```bash
nmap <target> -oG scan.grep
```

### Save All Output Types

```bash
nmap <target> -oA myscan
```

This creates:

* `myscan.nmap`
* `myscan.xml`
* `myscan.gnmap`

---

## 🛠️ Practical Examples

### Full Enumeration Scan

```bash
nmap -sC -sV -O -A -p- <target>
```

### Fast Scan

```bash
nmap -F <target>
```

### Evade Firewalls / IDS

```bash
nmap -Pn <target>
```

Disables host discovery (treats all hosts as online).

### Slow & Stealthy

```bash
nmap -T1 <target>
```

---

## ⚠️ Notes

* Always scan **only systems you are authorized to test**.
* Using aggressive scans (`-A`, `-T4`, `-T5`) may trigger IDS/IPS alerts.
* UDP scans are slow—expect long wait times.
