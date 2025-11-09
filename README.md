# 🕯️ Secret Santa Trustee — Encrypted Edition  
*Merry Christmas and keep your secrets safe!* 🎁

A simple, privacy-first Secret Santa helper for small groups — now with **optional encrypted backup** support.  
Every participant privately learns their recipient; the organizer can optionally generate an **AES-encrypted ZIP** containing all assignments, where **each person holds one piece of the password**.

---

## ✨ Highlights

- **Private reveal:** each participant only sees their own recipient.  
- **Encrypted backup (optional):** creates an AES-256 ZIP file; password is split across participants.  
- **Screen + scrollback clearing:** prevents snooping in terminal history.  
- **Temporary files only:** all intermediate data deleted on exit.  
- **Cross-platform:** works on Windows / macOS / Linux (Python 3.8+).  
- **Interactive or CLI-driven:** choose settings from a menu or command-line flags.

---

## 🎮 Quick Start

1. **Install dependencies**
   ```bash
   pip install pyzipper
Run the program

bash
Copy code
python3 "Trustee Encrypted V2.py"
Follow the on-screen menu
Choose between:

Manual mode (press Enter to clear)

Auto-clear after N seconds

Enable or disable encrypted backup

⚙️ Command-Line Options
Skip the configuration menu and control behavior directly:

Option	Description
--timeout N	Auto-clear after N seconds
--no-enter	Instant clear (no wait, no Enter)
--allow-repeat	Allow repeat viewing of results
--seed INT	Deterministic assignment generation
--no-backup	Disable encrypted backup
--skip-menu	Bypass the setup menu entirely

Example:

bash
Copy code
python3 "Trustee Encrypted V2.py" --timeout 5 --seed 42 --no-backup
🔐 Encrypted Backup Details
When encryption is enabled:

Creates a ZIP archive

python
Copy code
secret_santa_YYYYMMDD_HHMMSS.zip
in the same directory as the script.

Generates a random numeric password (4 digits × number of participants).

Each participant receives one password segment:

csharp
Copy code
[Part i] XXXX
Combine all parts in order to reconstruct the full password and unlock the archive.

Compatible with standard AES ZIP tools like 7-Zip or WinRAR.

🧭 Reveal Flow
Organizer enters all participant names (comma-separated).

Program builds a derangement (no self-gifting).

Each participant types their name to see their recipient.

Screen clears automatically or after pressing Enter.

Temporary files are removed on exit for complete privacy.

💡 Example Commands
bash
Copy code
# Default: manual Enter mode
python3 "Trustee Encrypted V2.py"

# 5-second auto-clear
python3 "Trustee Encrypted V2.py" --timeout 5

# Instant clear + deterministic seed
python3 "Trustee Encrypted V2.py" --no-enter --seed 123

# Disable backup and skip menu
python3 "Trustee Encrypted V2.py" --no-backup --skip-menu
🧹 Notes
Works best in a real terminal (some GUI shells may not clear scrollback).

All temporary files are stored in the OS temp directory and deleted automatically.

No internet or external storage required — 100 % local and private.



🎅 Credits
Developed with care to make your Secret Santa draws private, fair, and fun.
Wishing you a warm and joyful holiday season! 🎄
