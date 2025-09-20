# Small Business Windows Server 2022 Setup

This project documents how to repurpose an **old SFF PC with an Intel Xeon E3-1270 v2** into a **Windows Server 2022** box for small business workloads.

---

## ⚙️ Hardware Requirements

* **CPU**: Intel Xeon E3-1270 v2 (Ivy Bridge, 4C/8T)
* **RAM**: 16–32GB DDR3 (ECC if supported)
* **Storage**: SSD (≥250GB for OS), optional HDD/SSD for data
* **NIC**: Intel Gigabit Ethernet adapter with Server 2022 drivers
* **Chassis**: Small Form Factor PC with sufficient airflow and stable PSU

---

## 📌 Supported Server Roles

Choose based on small business needs:

* ✅ File & Print Server
* ✅ Active Directory Domain Controller
* ✅ DNS / DHCP
* ✅ Web Server (IIS)
* ✅ Backup Storage
* ⚠️ Hyper-V (limited by CPU generation)

---

## 🚀 Installation Steps

### 1. Preparation

1. Download **Windows Server 2022 ISO** from Microsoft.
2. Create bootable USB with [Rufus](https://rufus.ie/).
3. Backup all data on the machine.
4. Configure BIOS:

   * Enable **AHCI mode**
   * Disable unused devices (optional)
   * Set boot priority → USB first

### 2. Install Windows Server 2022

1. Boot from USB.
2. Choose **Standard (Desktop Experience)**.
3. Partition SSD (≥80GB for OS).
4. Install and set Admin password.
5. After first boot, install **chipset/NIC drivers**.

### 3. Post-Install Configuration

* Rename server (e.g., `SBSERVER01`).
* Assign **static IP**.
* Run **Windows Update**.
* Install server **roles/features** via **Server Manager**.
* Create non-admin **user accounts**.

---

## 🔒 Security & Maintenance

* Enable and configure **Windows Firewall**.
* Use built-in **Windows Defender Antivirus**.
* Schedule **regular OS updates**.
* Setup **backup strategy** (external HDD or cloud).

---

## 🛠️ Alternatives

If Server 2022 is too heavy for your workload:

* Run **Proxmox or VMware ESXi** → host Windows Server VM(s).
* Use **Linux (Ubuntu/Debian)** with Samba, Nextcloud, etc., for SMB services.

---

## 📂 Project Structure

```
.
├── docs/                  # Setup guides and screenshots
├── config/                # Example server role configurations
├── scripts/               # PowerShell automation scripts
└── README.md              # Main project documentation
```

---

## 📖 License

MIT License — free to use, modify, and share.
