# Sonic ARP Spoofing by IBRAHIM [v4.1 - Fixes]

[![Download EXE (Windows)](https://img.shields.io/badge/⬇️%20DOWNLOAD%20EXE%20NOW-blue?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/ibrahim133744/Sonic-ARP-Spoofing/releases/tag/Sonic)

**Developer:** ibrahim ([GitHub Profile](https://github.com/ibrahim133744))

**Technologies:** Python 3, Scapy, Tkinter (ttk, ttkthemes), pystray, Pillow, WMI (Windows)

---

## 🚨🚨🚨 CRITICAL WARNING & USAGE ADVISORY 🚨🚨🚨

**This tool is intended STRICTLY for educational purposes and technical demonstration ONLY.**

**DO NOT use this software on any network without the explicit, PRIOR, WRITTEN PERMISSION of the network owner.** Unauthorized use of ARP spoofing tools is **ILLEGAL** in most jurisdictions and can cause significant network disruption. Such actions may lead to severe consequences, including **legal prosecution, financial penalties, and account suspension.**

**The developer (ibrahim) assumes ABSOLUTELY NO RESPONSIBILITY for any damage, disruption, or legal issues arising from the misuse of this software.** This code is shared "as-is" as a demonstration project. **USE ENTIRELY AT YOUR OWN RISK** and only within legally permitted and controlled environments.

---

## Disclaimer of Responsibility

**The developer (ibrahim) is NOT RESPONSIBLE for any damages, network disruptions, legal consequences, or any other negative outcome resulting from the use or misuse of this software.** This tool is provided solely for educational demonstration. By using this software, you acknowledge that you understand the risks and that you are solely responsible for your actions and for ensuring you have explicit permission to test on any given network. **If you misuse this tool, YOU ALONE BEAR THE CONSEQUENCES.**

---

## Description

SonicARP [v4.1 - Fixes] is a project demonstrating ARP spoofing using Python. It utilizes **Scapy** for network packet manipulation and **Tkinter** (with `ttkthemes`, `pystray`) for the graphical user interface and system tray integration.

**Functionality of this version:**
* GUI with theme selection (Light/Dark options) and basic multi-language support (EN/SR).
* Dropdown menu for selecting the active network interface.
* Automatic detection of network parameters (IP, MAC, Gateway, Network Range) for the selected interface.
* Network scanning using ARP requests to discover active devices on the selected interface's network.
* Option to attack **All Found Devices** or only **Selected Devices** from the list.
* Option to **Save** the discovered target list to a JSON file and **Load** targets from a file.
* Checkbox option to **Poison Gateway's ARP cache** (for potential MitM setup analysis).
* Starts the ARP spoofing attack based on selected mode and options.
* Attempts to **restore the ARP tables** of targeted devices and the gateway (if poisoned) upon stopping the attack.
* Logs activities and status updates within the GUI.
* Integrates with the **system tray**, allowing the application to be hidden.
* Includes a link to the developer's GitHub profile in the status bar.
* Checks for necessary Administrator privileges on startup.
* Includes configuration saving (theme, language) in `config.json`.
* Uses WMI on Windows for more user-friendly interface names.

This project was developed primarily for learning purposes. The source code is made visible for review and demonstration purposes.

---

## Prerequisites

To run SonicARP [v4.1 - Fixes], you need:

1. **Npcap Installation (Windows):** You **MUST** install the Npcap library first if you are on Windows. For Linux, ensure `libpcap-dev` (or equivalent) is installed.
   * Download Npcap from: [https://npcap.com/](https://npcap.com/)
   * **Crucial (Windows):** During installation, ensure **"Support WinPcap API-compatible mode"** is **checked**.
2. **Administrator/Root Privileges:** The executable or script **MUST** be run with administrator (Windows) or root (Linux) rights.
3. **(If running from source code):**
   * Python 3.x (e.g., 3.8+ recommended).
   * Required Python libraries. Install using pip:
     ```bash
     pip install scapy ttkthemes pystray pillow requests WMI
     ```
     * **Note:** `WMI` is only required and installable on Windows. Installation might fail on other OS, which is expected. `requests` is optional but recommended for potential future update checks.

---

## Running SonicARP [v4.1 - Fixes]

**Option 1: Using a Pre-compiled Executable (.exe - Windows)**

1. **Build or Download:** Obtain the executable file (e.g., `SonicARP_v4.1.exe`). *You typically need to build this yourself using PyInstaller with the provided source code and `icon.png`.*
2. **Ensure Npcap is installed** (see Prerequisites).
3. **Run:** Right-click the `.exe` file and select "**Run as administrator**".

**Option 2: Running from Source Code**

1. **Ensure Prerequisites are met** (Python, pip, Npcap/libpcap, Admin/Root rights).
2. **Download/Clone** the source code (`.py` file and `icon.png`).
3. **Install dependencies** (see Prerequisites):
   ```bash
   pip install scapy ttkthemes pystray pillow requests WMI
   ```
   *(Ignore WMI errors if not on Windows)*
4. **Run:** Open an **administrator** terminal (Windows) or use `sudo` (Linux), navigate to the code directory, and run the script:
   ```bash
   # Windows (Admin Terminal)
   python your_script_name.py

   # Linux
   sudo python3 your_script_name.py
   ```
   *(Replace `your_script_name.py` with the actual filename)*

---

## Usage Guide (v4.1 Interface)

1. **Select Interface:** Choose your active network interface from the dropdown menu at the top left. The application will attempt to gather network information (IP, Gateway, etc.). Wait for the status to indicate "Ready".
2. **Scan Network:** Click `📡 Scan Network` to discover devices on the selected network. Found devices will appear in the "Discovered Devices (Targets)" list on the right.
3. **(Optional) Load Targets:** Click `📂 Load` to load a previously saved list of targets from a JSON file. This will replace the currently displayed list.
4. **(Optional) Save Targets:** Click `💾 Save` to save the current list of discovered/loaded targets to a JSON file. (Enabled only when targets are present).
5. **Select Attack Mode:**
   * **All Found Devices:** Targets all devices currently shown in the list (excluding self/gateway).
   * **Selected Devices Only:** Targets only the devices you manually select (Ctrl+Click or Shift+Click) in the list. The Start button enables only when devices are selected.
6. **(Optional) Poison Gateway:** Check the `Poison Gateway (for MitM)` box if you want the tool to also send spoofed packets *to* the gateway, making it think your machine is the target device(s). (Needed for a full MitM).
7. **Start Attack:** Click `🚀 Start Attack`. The button is enabled only when prerequisites are met (interface info gathered, targets available/selected based on mode). The status bar and LED will indicate the attack is active.
8. **Stop Attack:** Click `✅ Stop Attack & Restore` to halt the spoofing packets and send ARP correction packets to restore the ARP tables of the targets (and gateway if poisoned).
9. **Hide/Show:** Use the system tray icon (usually bottom right) to hide the main window or bring it back. Right-clicking the tray icon provides options to Show/Hide or Exit.
10. **Exit:** Use the "File" -> "Exit" menu option or the "Exit" option in the system tray menu to properly close the application (this also triggers ARP restoration if an attack was running). Closing the window via the 'X' button will hide it to the tray instead.

---

## Copyright and Permissions

**Copyright (c) 2025 ibrahim. All Rights Reserved.**

The source code for SonicARP is made publicly visible for demonstration and educational review purposes only.

**You are granted permission to:**
* View and inspect the source code.
* Run the software **strictly** in accordance with the warnings and prerequisites mentioned above.

**You are explicitly NOT granted permission to:**
* Copy, modify, or distribute the source code or the executable file without attribution and maintaining the original license terms and warnings.
* Create derivative works based on this code without attribution and maintaining the original license terms and warnings.
* Use this software or parts of its code for commercial purposes.
* Re-license this software under any other terms.
* Remove or obscure any copyright notices, warnings, or disclaimers.

Any use beyond viewing and the limited execution permission described requires **explicit written consent** from the author (ibrahim).
