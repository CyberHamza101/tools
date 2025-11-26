# Man-in-the-Middle (MITM) Attack  
A practical guide for cybersecurity learners

## 📌 Overview  
A **Man-in-the-Middle (MITM)** attack happens when an attacker secretly intercepts, relays, or modifies communication between two parties who believe they are communicating directly.  
The attacker places themselves **between the victim and the router/server**, acting as an invisible proxy.

MITM attacks are common in:
- Public Wi-Fi networks  
- Insecure home networks  
- Networks using weak or outdated encryption  
- Unsecured HTTP websites  

---

## 🧠 How MITM Works  
Simple representation:

Victim → Attacker → Router / Server

The attacker can:
- Monitor traffic  
- Steal passwords and session tokens  
- Modify or inject malicious data  
- Redirect users to fake websites  
- Take over accounts (session hijacking)  

---

## 🧪 Common MITM Techniques

### **1. ARP Spoofing / ARP Poisoning**
The attacker sends fake ARP replies to victims, making them think the attacker is the router.  
This allows full traffic interception.

**Tools:** `arpspoof`, `ettercap`, `bettercap`

---

### **2. DNS Spoofing**
The attacker alters DNS responses to redirect victims to malicious websites.

Example:
facebook.com → attacker's server

---

### **3. Rogue Access Point (Fake Wi-Fi)**
The attacker creates a Wi-Fi network with a similar or attractive name.  
Victims connect without noticing.

Examples:
- Real: `CoffeeShop_WiFi`
- Fake: `CoffeeShop_WiFi_Free`

---

### **4. HTTPS Downgrade (SSL Stripping)**
The attacker forces communication to use **HTTP instead of HTTPS**, exposing sensitive data.

**Tool:** `sslstrip`

---

### **5. Evil Twin Attack**
The attacker clones a legitimate access point (same name, same MAC, stronger signal).  
Victims automatically connect.

---

## 🔥 What Attackers Can Steal
MITM gives attackers access to:

- Login credentials  
- Credit card information  
- Session cookies (account takeover)  
- Emails, messages, chats  
- Authentication tokens  
- Business or personal data  
- Entire plaintext network traffic  

---

## 🧰 Tools Commonly Used in MITM Attacks

| Tool | Description |
|------|-------------|
| **Wireshark** | Packet capture and analysis |
| **Ettercap** | MITM + ARP poisoning |
| **Bettercap** | Modern MITM framework |
| **arpspoof** | ARP poisoning |
| **dsniff** | Password sniffing |
| **mitmproxy** | HTTPS interception |

---

## 🛡 How to Protect Against MITM Attacks

### **1. Use HTTPS Everywhere**
Check for the 🔒 lock icon in browsers.  
Avoid sites that use HTTP.

---

### **2. Avoid Public Wi-Fi (or Use a VPN)**
Public Wi-Fi is highly vulnerable.  
A **VPN encrypts your entire connection**, making MITM attacks ineffective.

---

### **3. Secure Home/Office Wi-Fi**
- Enable **WPA3** (or at least WPA2)  
- Disable **WPS**  
- Change default router password  
- Update firmware regularly  
- Enable **client isolation**  

---

### **4. Defend Against ARP Spoofing**
- Use static ARP entries  
- Enable Dynamic ARP Inspection (DAI) on switches  

---

### **5. Use Multi-Factor Authentication (MFA/2FA)**
Even if attackers intercept your credentials, they cannot log in.

---

### **6. Respect Browser Certificate Warnings**
If you see:  
> “Your connection is not private.”  
Do **not** proceed — it may be a MITM attack.

---

  

---


