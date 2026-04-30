# 🚀 WaterdogPE Pterodactyl Egg - Support x86/ARM64

A powerful **Pterodactyl Egg** for running **WaterdogPE**, Created by **@[ZORNER](https://zorner.men)**

---

## 📖 Overview

This egg allows you to easily deploy **WaterdogPE** on Pterodactyl Panel.
WaterdogPE is a Bedrock proxy similar to BungeeCord (Java Edition), enabling players to connect and switch between multiple Minecraft Bedrock servers using a single IP.

It is optimized for performance, stability, and multi-server network architecture.

---

## ⚡ Features

- 🔗 Multi-server proxy for Minecraft Bedrock Edition
- 🌐 Seamless server switching (hub system support)
- ⚙️ Lightweight and fast Java-based proxy
- 🧩 Fully compatible with Pterodactyl Panel
- ☕ Supports multiple Java versions (8 – 21)
- 📦 Automatic WaterdogPE downloader (latest or specific version)
- 🛠️ Auto-configured `config.yml`
- 🧠 Works on x86/x64 and ARM64 architectures

---

## 🖥️ Supported Docker Images

| Java Version      | Docker Image                         |
| :---------------- | :----------------------------------- |
| **Java 21** | `ghcr.io/ptero-eggs/yolks:java_21` |
| **Java 17** | `ghcr.io/ptero-eggs/yolks:java_17` |
| **Java 16** | `ghcr.io/ptero-eggs/yolks:java_16` |
| **Java 11** | `ghcr.io/ptero-eggs/yolks:java_11` |
| **Java 8**  | `ghcr.io/ptero-eggs/yolks:java_8`  |

---

## 🔧 Important Setup Notes

### 1. Disable Online Mode

All Minecraft Bedrock servers that you want to connect to WaterdogPE as backend servers MUST have their online mode disabled.

In your backend server's `server.properties`:

```
online-mode=false
```

> **⚠️ Security Note:**
> Make sure your backend servers are not directly exposed to the internet (only accessible via WaterdogPE proxy) to prevent unauthorized connections.

---



## ➕ How to Add a New Backend Server to WaterdogPE

1. **Prepare the backend server**

* Install a standard Minecraft Bedrock server (e.g., BDS, PocketMine-MP, Nukkit, etc.)
* Set `online-mode=false` in its `server.properties`
* Note its **IP address** and port (default: 19132)

2. **Open WaterdogPE’s configuration file**
   Navigate to the WaterdogPE directory inside your Pterodactyl Egg instance:

   ```
   config.yml
   ```
3. **Locate the `priorities `section**
   Example:

   ```
   priorities:
       - lobby
   ```

   and

   ```
    servers:
        lobby:
            address: 0.0.0.0:19132
            public_address: 0.0.0.00:19132
            server_type: bedrock
   ```



    **Add your new server**
    
    ```
    priorities:
            - lobby
            - survival
    ```
    
    and 
    
    ```
    servers:
        lobby:
            address: 0.0.0.0:19132
            public_address: 0.0.0.0:19132
            server_type: bedrock
       survival:
            address: 0.0.0.0:19133
            public_address: 0.0.0.0:19133
            server_type: bedrock
    ```

> Save the file and restart WaterdogPE (restart the Egg from Pterodactyl panel)

---


## ✅ Verification Steps


After adding a new server:

* Join your WaterdogPE proxy IP (single entry point)
* Use the server switching command (default:` /server <server_name>`)

If the backend server shows "`Connection refused`" or "`Not authenticated`", double-check that `online-mode=false` is applied and the server was restarted.

**⚠️TIP :**
Troubleshooting: If a warning appears to enable cheats when using the` /server` command, it is recommended to use an additional **[plugins](https://github.com/TegarPriyadi/WaterdogPE-Plugins)** as an alternative to the server switching system for more stability.


**<3 DONASI**

Please help me to buy Minecraft Badrock Original for PC

**[KLIK ME](https://nowpayments.io/donation/zorner)!!**

