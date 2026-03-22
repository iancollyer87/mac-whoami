<h1 align="center">
  <br>
  🔒 mac-whoami
  <br>
</h1>

<h4 align="center">
  macOS Privacy & Anonymity Tool — inspired by <a href="https://github.com/owerdogan/whoami-project">kali-whoami</a>
</h4>

<p align="center">
  <img src="https://img.shields.io/badge/platform-macOS-black?style=for-the-badge&logo=apple" />
  <img src="https://img.shields.io/badge/shell-zsh-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/license-GPL%20v3-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/version-1.0.0-black?style=for-the-badge" />
  <img src="https://img.shields.io/github/stars/iancollyer87/mac-whoami?style=for-the-badge&color=black" />
  <img src="https://img.shields.io/github/forks/iancollyer87/mac-whoami?style=for-the-badge&color=black" />
  <img src="https://img.shields.io/github/issues/iancollyer87/mac-whoami?style=for-the-badge&color=black" />
</p>

---

## About

**mac-whoami** is a macOS privacy and anonymity tool modeled after the popular [kali-whoami](https://github.com/owerdogan/whoami-project) project for Linux. Since kali-whoami is built exclusively for Debian and Arch-based Linux distributions, this tool brings similar functionality natively to macOS (Apple Silicon & Intel).

> ⚠️ **Note:** No tool can guarantee 100% anonymity. mac-whoami reduces your attack surface and digital footprint — use it responsibly.

---

## Modules

| Module | Description |
|---|---|
| 🔀 **MAC Changer** | Randomizes your MAC address on `en0` using a locally-administered prefix |
| 🌐 **DNS Changer** | Switches DNS to Cloudflare `1.1.1.1` + Quad9 `9.9.9.9` |
| 🖥️ **Hostname Changer** | Sets a randomized hostname (e.g. `phantom-4821`) |
| 🕐 **Timezone Changer** | Sets system timezone to UTC to prevent location leakage |
| 🗑️ **Log Killer** | Wipes system logs, user logs, and shell history |
| 🔥 **Firewall** | Enables macOS firewall + stealth mode |
| 🔇 **Diagnostics** | Disables crash reporter and Apple diagnostics |
| 🧹 **Cache Cleaner** | Clears user caches and temp files |

---

## Installation

```bash
# Clone the repo
git clone https://github.com/iancollyer87/mac-whoami.git
cd mac-whoami

# Install system-wide
sudo cp mac-whoami /usr/local/bin/mac-whoami
sudo chmod +x /usr/local/bin/mac-whoami
```

---

## Usage

```bash
sudo mac-whoami --start    # Backup settings and activate all privacy modules
sudo mac-whoami --stop     # Deactivate all modules and restore original settings
sudo mac-whoami --status   # Show current privacy status
sudo mac-whoami --logs     # Clear system logs only
sudo mac-whoami --mac      # Randomize MAC address only
sudo mac-whoami --fix      # Emergency restore of all original settings
sudo mac-whoami --help     # Show help menu
```

---

## How It Works

When you run `--start`, mac-whoami:
1. **Backs up** your current MAC address, hostname, DNS settings, and timezone to `~/.mac-whoami/backups/`
2. **Applies** all privacy modules in sequence
3. **Logs** every action to `/var/log/mac-whoami.log`

When you run `--stop`, everything is **restored exactly** to what it was before.

---

## Requirements

- macOS 12 Monterey or later
- Apple Silicon (M1/M2/M3/M4) or Intel Mac
- `zsh` (default on macOS Catalina+)
- Run with `sudo` for full functionality

---

## Uninstall

```bash
sudo rm /usr/local/bin/mac-whoami
rm -rf ~/.mac-whoami
```

---

## Credits

Inspired by [kali-whoami](https://github.com/owerdogan/whoami-project) by [@owerdogan](https://github.com/owerdogan).

---

## License

Distributed under the **GPL v3 License**. See [LICENSE](LICENSE) for details.
