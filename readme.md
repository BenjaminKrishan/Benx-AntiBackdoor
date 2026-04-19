# 🛡️ BenX Anti-Backdoor - Hardened Edition v1.1.0

> *The ultimate security solution for FiveM (FXServer). Stop backdoors before they stop your server.*

<p align="center">
  <a href="https://benx.tebex.io/category/scripts">
    <img src="https://img.shields.io/badge/Buy%20Now-Tebex-blue?style=for-the-badge&logo=checkmarx" alt="Purchase on Tebex">
  </a>
  <a href="#-features">
    <img src="https://img.shields.io/badge/Version-1.1.0-green?style=for-the-badge" alt="Version">
  </a>
</p>

---

### 🔥 **Don't Risk Your Server Data**
Many free or leaked scripts contain hidden **PerformHttpRequest** backdoors and obfuscated loaders. **BenX Anti-Backdoor** is a comprehensive, high-performance security solution that monitors resource starts, decodes hidden payloads (Base64/Hex), and shuts down threats automatically.

👉 **Get it now:** [https://benx.tebex.io/category/scripts](https://benx.tebex.io/category/scripts)

---

## 🚀 Installation

1. **Download and Extract**: Place the `benx-antibackdoor` folder into your `resources` directory (e.g., `resources/[scripts]/benx-antibackdoor`).
2. **Configure Webhook**: Set your Discord Webhook via Convar in `server.cfg`:
   ```bash
   set benx_webhook "https://discord.com/api/webhooks/YOUR_WEBHOOK_URL"
   ```
3. **Add to Server Config**:
   ```bash
   ensure benx-antibackdoor
   ```
4. **Permissions**: Ensure the resource can stop other resources if `AutoStopInfected` is enabled in `config.lua`.

---

## 🛠 Features

### 🧬 Structural Code Analysis
The engine scans for dangerous patterns like `PerformHttpRequest` linked to `load` or `assert` commands. It checks for common RCE (Remote Code Execution) vectors and data theft patterns (RCON passwords, License Keys).

### 🔓 De-Obfuscation Engine
Malicious code is often hidden in **Base64** or **Hex**. Our scanner identifies these strings and decodes them in memory to analyze the *actual* intent of the code.

### 📊 Deep Entropy Scanning
By calculating Shannon Entropy, the script detects "random" or "binary-looking" Lua code. High entropy is a primary indicator of obfuscated malware that traditional regex-based scanners miss.

### 💾 Atomic Persistence
The whitelist system uses a multi-stage saving process (Atomic Write) with backups to ensure your whitelist database never corrupts during a server crash.

---

## 📋 Comprehensive Command List
*All commands must be executed from the Server Console or RCON.*

| Command | Sub-arguments | Description |
|---------|---------------|-------------|
| `/scan` | `[resource]` | Runs a full system scan. If a resource name is provided, only that resource is scanned. |
| `/checkscan` | - | Performs a signature-based check for known bad file fingerprints in active memory. |
| `/whitelist` | `all` | Whitelists all currently started resources (useful for initial setup). |
| `/whitelist` | `<name>` | Manually whitelists a specific resource by its folder name. |
| `/whitelist` | `remove <name>` | Removes a resource from the whitelist. |
| `/whitelist` | `update <name>` | Re-calculates fingerprints for a whitelisted resource (use after updating a script). |
| `/whitelist` | `clear confirm`| Completely resets the whitelist database. |
| `/benxstatus` | - | Displays the overall health of the security system, active threats, and last scan time. |
| `/listbackdoors`| - | Shows detailed technical descriptions for all currently detected threats. |
| `/benxhelp` | - | Lists all available commands with brief descriptions. |

---

## ⚙️ Configuration Guide (`config.lua`)

| Key | Default | Description |
|-----|---------|-------------|
| `Config.ScanOnStart` | `true` | Runs a full scan immediately when the server starts. |
| `Config.ScanOnResourceStart` | `true` | Automatically scans any new resource when it is started. |
| `Config.AutoStopInfected` | `true` | If a **CRITICAL** threat is found, the resource is stopped instantly. |
| `Config.MonitorIntervalMin` | `5` | How often (in minutes) the script monitors files for changes after the server is up. |
| `Config.EntropyThreshold` | `7.2` | Sensitivity of the entropy scanner. Higher = less sensitive, lower = more sensitive. |
| `Config.UseUTC` | `true` | Use UTC for scheduled scans. Set to `false` for local server time. |
| `Config.ScheduledScans` | - | Configure automatic scans at specific times (e.g., `{"03:00", "15:00"}`). |

---

## 🔄 Recent Updates (v1.1.0)
- **Webhook Security**: Moved Discord Webhook to Convar storage.
- **De-obfuscation**: Added Base64 and Hex decoders to scanning engine.
- **Performance**: Optimized entropy sampling for large files and added thread yielding to prevent server lag.
- **Namespace Safety**: Prefixed globals and localized core functions.

<p align="center">
  <strong>📦 Ready to secure your server?</strong><br>
  <a href="https://benx.tebex.io/category/scripts">
    <img src="https://img.shields.io/badge/Buy%20Now%20on%20Tebex-%2414.49-important?style=for-the-badge&logo=tebex" alt="Buy on Tebex">
  </a>
</p>

*© 2026 Benjamin Krishan - BenX Development. All rights reserved.*
