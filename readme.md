# 🛡️ BenX Anti-Backdoor - Hardened Edition v1.1.0

> *The ultimate security solution for FiveM (Qbox/FXServer). Stop backdoors before they stop your server.*

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

## 🛠 Features
🧬 **Structural Code Analysis**: Scans for `PerformHttpRequest` + `load` combos.

🔓 **De-Obfuscation Engine**: Automatically decodes Base64 and Hex strings to reveal hidden code.

📊 **Deep Entropy Scanning**: Detects "binary-looking" Lua code (strong indicator of malware).

⏰ **Scheduled Scans**: Set automatic full-server scans at specific times (UTC/Local).

💾 **Atomic Persistence**: Crash-proof whitelist database system.

🔎 **Signature Checks**: `/checkscan` to find known malicious fingerprints instantly.

## 📋 Commands (Console/RCON Only)
| Command | Description |
|---------|-------------|
| `/scan` | Full server behavioral scan |
| `/scan <name>` | Scan a specific resource |
| `/checkscan` | Signature-based check for known malware |
| `/whitelist <name>` | Exclude a safe resource from scans |
| `/whitelist remove <name>` | Remove from whitelist |
| `/benxstatus` | Show scan history and system status |
| `/benxhelp` | List all commands |

## 🔄 Recent Updates (v1.1.0)
- **Webhook Security**: Moved Discord Webhook to Convar storage.
- **De-obfuscation**: Added Base64 and Hex decoders to scanning engine.
- **Performance**: Optimized entropy sampling for large files.
- **Namespace Safety**: Prefixed globals to prevent conflicts.

<p align="center">
  <strong>📦 Ready to secure your server?</strong><br>
  <a href="https://benx.tebex.io/category/scripts">
    <img src="https://img.shields.io/badge/Buy%20Now%20on%20Tebex-%2420.00-important?style=for-the-badge&logo=tebex" alt="Buy on Tebex">
  </a>
</p>

*© 2026 Benjamin Krishan - BenX Development. All rights reserved.*
