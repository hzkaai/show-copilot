# Show Copilot ✨

English | [中文](README.zh.md)

Tiny Python helper that nudges Microsoft Edge into Copilot mode by patching your local profile data—no browser flags required.

## ⚡️ Quick Start (uv)
1. Install uv (once, PowerShell): `irm https://astral.sh/uv/install.ps1 | iex` (see uv docs for other shells).
2. Install deps (creates venv automatically): `uv sync`.
3. Run the script: `uv run main.py`.
4. Edge will close while patching; after it restarts, press Enter to finish.

## 🔧 What Happens
- Finds Edge user data for Stable/Canary/Dev/Beta on Windows, macOS, and Linux.
- Kills top-level Edge processes to avoid file locks, then brings them back.
- Sets `variations_country: "US"` in `Local State`.
- Sets `browser.chat_ip_eligibility_status: true` in every profile `Preferences` (`Default` and `Profile X` folders).
- Restarts any Edge builds that were running before the patch.

## 🛟 Notes
- The script writes to your existing Edge profile; back up `User Data` if you want a safety net.
- Run as the same OS user who owns the Edge profile to ensure write access.
- Not affiliated with Microsoft—use at your own risk.
