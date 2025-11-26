# Netdiscover — ARP Network Scanner

## 📌 Overview

Netdiscover is a lightweight ARP-based network scanning tool used to quickly identify active hosts on a local network. It is extremely useful in situations where:

* DNS is not working
* No DHCP server is present
* Network is unfamiliar or unknown
* You need fast host discovery without noisy probes

Netdiscover is commonly used in:

* Penetration testing
* Network reconnaissance
* Home/office network mapping
* Device discovery

It is ideal for quick scans in LAN environments.

---

## ⚙️ Installation

Most pentesting distros (Kali, Parrot OS) include Netdiscover by default.

### Debian/Ubuntu

```bash
sudo apt install netdiscover
```

### Verify Installation

```bash
netdiscover -h
```

---

## 🧪 How Netdiscover Works

Netdiscover uses **ARP (Address Resolution Protocol)** requests to identify:

* IP addresses
* MAC addresses
* Hardware vendors

It does not require ping or DNS — making it stealthy and highly reliable in LANs.

---

## 🔍 Basic Usage

### Scan a Network Automatically

```bash
sudo netdiscover
```

This performs a passive scan and listens for ARP traffic.

---

## 🚀 Active Scanning

Active mode sends ARP requests to identify all hosts.

### Scan a Specific Network Range

```bash
sudo netdiscover -r 192.168.1.0/24
```

### Scan with Specified Interface

```bash
sudo netdiscover -i eth0 -r 10.0.0.0/24
```

### Set Scan Speed (1–5)

Speed 1 = slow & stealthy, 5 = fast

```bash
sudo netdiscover -r 192.168.1.0/24 -s 5
```

---

## 🖥️ Display Options

### Show Only Active Hosts

```bash
sudo netdiscover -r 192.168.1.0/24 -N
```

### Output in Simple Format

```bash
sudo netdiscover -r 192.168.1.0/24 -P
```

(Useful for scripts.)

---

## 🛠️ Practical Examples

### Identify All Devices on Your Local Network

```bash
sudo netdiscover -r 192.168.0.0/24
```

### Scan a Corporate VLAN

```bash
sudo netdiscover -i eth1 -r 10.10.10.0/24
```

### Passive Listening Mode (Stealth)

```bash
sudo netdiscover -p
```

(No ARP packets are sent.)

---

## 🧠 When to Use Netdiscover

Use Netdiscover when:

* You need fast live host discovery
* You're connected to a new or unknown network
* You're performing WiFi penetration testing
* Nmap ping scans are blocked
* The network uses ARP extensively (most LANs do)

Not ideal for:

* Remote networks (outside LAN)
* Large enterprise networks with ARP filtering

---

## ⚠️ Notes

* Active ARP scans may appear in router logs
* Use only on networks you are authorized to test
* Some devices may not respond to ARP broadcasts

---
