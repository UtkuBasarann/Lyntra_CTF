# Lyntra Cyber Academy — Vulnerable Lab VM (`.ova`)
Official pre-configured vulnerable virtual machine (.ova) for [Lyntra Cyber Academy](https://lyntracyberacademy.com) hands-on CTF scenarios and security labs.

![Format](https://img.shields.io/badge/Format-.OVA-orange?style=for-the-badge)
![Size](https://img.shields.io/badge/Size-2.9%20GB-brightgreen?style=for-the-badge)
![Platform](https://img.shields.io/badge/Virtualization-VirtualBox%20%7C%20VMware-purple?style=for-the-badge)

This repository hosts the official setup documentation and direct download access for the **Lyntra Cyber Academy** vulnerable virtual machine. 

The pre-configured appliance (`.ova`) contains hands-on CTF challenges, vulnerable web services, and local privilege escalation targets built specifically for practical penetration testing and cybersecurity training.

---

## Direct Download & Appliance Details

### File Specifications
- **Filename:** `LyntraCTF_Lab.ova`
- **File Size:** `2.9 GB`
- **Format:** Open Virtual Appliance (`.ova`)

**[Click Here to Download LyntraCTF_Lab.ova (2.9 GB)](https://lab.lyntracyberacademy.com/downloads/LyntraCTF_Lab.ova)**

*Terminal Direct Download (`wget`):*
```bash
wget https://lab.lyntracyberacademy.com/downloads/LyntraCTF_Lab.ova
```

## Installation & Setup Guide

### Prerequisites
* **Virtualization Software:** Oracle VM VirtualBox (v6.x / v7.x) or VMware Workstation / Player
* **System Requirements:** Minimum 2 CPU cores, 2–4 GB RAM, 10 GB free disk space

---

### Important Note on Network Configuration
To safely test this machine without exposing your physical local network to vulnerabilities—while still allowing your attacker machine (e.g., Kali Linux) to scan, exploit, and SSH into the target VM:
* **Host-Only Mode (Recommended):** Keeps both Kali Linux and the target VM on an isolated virtual network (`vboxnet0`). They can freely communicate via SSH, HTTP, and Nmap, while remaining completely isolated from your home network and the internet.
* **NAT Network Mode:** Creates an isolated internal subnet shared between your virtual machines.

---

### Option 1: Oracle VM VirtualBox

1. **Download File:** Download the `LyntraCTF_Lab.ova` appliance file.
2. **Open VirtualBox:** Navigate to `File` ➔ `Import Appliance...` (or press `Ctrl + I`).
3. **Select File:** Browse and select the downloaded `LyntraCTF_Lab.ova` file, then click **Next**.
4. **Configure Resources:** Adjust RAM (e.g., 2048 MB or 4096 MB) and CPU allocation based on your system capacity.
5. **Network Settings:** Change the **Network Adapter** to **Host-Only Adapter** (or **NAT Network**) for safe isolation.
6. **Import:** Click **Import** and wait for the deployment process to complete.
7. **Start:** Select the VM and click **Start**.

---

### Option 2: VMware Workstation / Player

1. **Open VMware:** Navigate to `File` ➔ `Open...`.
2. **Select File:** Choose the downloaded `LyntraCTF_Lab.ova` file.
3. **Set Destination:** Specify the target folder path for the imported virtual machine and click **Import**.
4. **Network Settings:** Go to `VM Settings` and ensure the **Network Adapter** is set to **Host-Only** (or a Custom Private Network).
5. **Start:** Click **Power on this virtual machine**.

---

### Post-Installation & Initial Access

1. Once booted, discover the target VM's IP address from your attacker machine (e.g., Kali Linux) on the same virtual network:
   ```bash
   sudo netdiscover -i eth0
   # or
   nmap -sn 192.168.56.0/24
   ```
2. Perform enumeration, exploit vulnerabilities, and establish SSH or HTTP connections:
    ```bash
    ssh username@192.168.56.X
    ```
3. Capture hidden flags (`flag{...}`) and submit them on [lyntracyberacademy.com](https://lyntracyberacademy.com) to earn your points and climb the leaderboard!
