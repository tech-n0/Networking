
### **Why is Backup Important?**

Backups are **crucial** in networking because they help restore configurations after:

- **Hardware failures** (e.g., a router or switch crashes).
- **Misconfigurations** (e.g., a bad change causes loss of network access).
- **Firmware updates** (which might wipe the current settings).
- **Security incidents** (malware, unauthorized changes).

By backing up device configurations, you can quickly **restore settings** instead of reconfiguring everything manually.

---

### **Cisco Backup Components**

When backing up Cisco router/switch configurations, you need to understand these components:

#### **1. Flash Memory**

- **Stores the operating system (IOS)** and sometimes config files.
- **Non-volatile** (data is retained after reboot).
- The `show flash:` command lists files stored in flash.

#### **2. Running-Config**

- **Active configuration** that is currently running on the device.
- **Stored in RAM (volatile memory)** → Lost after a reboot unless saved.
- Use `show running-config` to view it.

#### **3. Startup-Config**

- **Saved configuration** that loads when the device reboots.
- **Stored in NVRAM (non-volatile memory)** → **Retained after reboot**.
- Use `show startup-config` to view it.
- To save the running config to startup-config, use:

```
copy running-config startup-config
```

#### **4. TFTP (Trivial File Transfer Protocol)**

- A simple protocol used to **transfer files over the network** (backup & restore).
- Used for saving/restoring configurations **remotely** instead of storing them locally.


```
# To back up to a TFTP server:
copy running-config tftp

# To restore from a TFTP server:
copy tftp running-config
```