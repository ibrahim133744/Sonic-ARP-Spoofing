# Sonic ARP Spoofing by IBRAHIM [v1.3 - Auto Attack]

**Developer:** ibrahim ([GitHub Profile](https://github.com/ibrahim133744))

**Technologies:** Python 3, Scapy, Tkinter (ttk, ttkthemes)

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

SonicARP [v1.3] is a project demonstrating ARP spoofing using Python. It utilizes **Scapy** for network packet manipulation and **Tkinter** (with `ttkthemes`) for the graphical user interface.

**Functionality of this version:**
*   Attempts automatic detection of local network parameters.
*   Scans the local network using ARP requests to discover active devices.
*   Performs an **automatic ARP spoofing attack** against **ALL** discovered devices (excluding the user's machine and the gateway). **Note: This version attacks all found devices automatically, selective targeting is not implemented.**
*   Optionally poisons the gateway's ARP cache as well (for potential MitM setup analysis).
*   Attempts to restore the ARP tables of targeted devices upon stopping the attack.
*   Logs activities within the GUI.
*   Includes a link to the developer's GitHub profile in the status bar.

This project was developed primarily for learning purposes. The source code is made visible for review and demonstration purposes.

---

## Prerequisites

To run SonicARP [v1.3], you need:

1.  **Npcap Installation:** You **MUST** install the Npcap library first.
    *   Download from: [https://npcap.com/](https://npcap.com/)
    *   **Crucial:** During installation, ensure **"Support WinPcap API-compatible mode"** is **checked**.
2.  **Administrator Privileges:** The executable or script **MUST** be run with administrator rights.
3.  **(If running from source code):** Python 3.x (e.g., 3.7+) and the required libraries (`pip install scapy ttkthemes`).

---

## Running SonicARP [v1.3]

**Option 1: Using the Pre-compiled Executable (.exe)**

1.  **Download:** Get the `SonicARPSpoofing_by_IBRAHIM.exe` file (or similar name you used).
    *   *(You will need to build this yourself using PyInstaller and the corresponding v1.3 source code. Consider uploading it to GitHub Releases if sharing).*
2.  **Ensure Npcap is installed** (see Prerequisites).
3.  **Run:** Right-click `SonicARPSpoofing_by_IBRAHIM.exe` and select "**Run as administrator**".

**Option 2: Running from Source Code**

1.  **Ensure Prerequisites are met** (Python, pip, Npcap, Admin rights).
2.  **Download/Clone** the source code for this version.
3.  **Install dependencies:** `pip install scapy ttkthemes`
4.  **Run:** Open an **administrator** terminal, navigate to the code directory, and run `python your_script_name_v1.3.py` (replace with your actual filename).

---

## Usage Guide (v1.3 Interface)

1.  **Scan Network:** Click `📡 Scan Network` to find devices.
2.  **Review Devices:** Found devices (targets) appear in the list. **Remember, clicking Start will attack ALL of them.**
3.  **(Optional) Poison Gateway:** Check the box if desired.
4.  **Start Attack:** Click `🚀 Start AUTO Attack`. The attack on ALL devices begins immediately.
5.  **Stop Attack:** Click `✅ Stop Attack & Restore` to stop spoofing and attempt ARP table restoration.

---

## Copyright and Permissions

**Copyright (c) 2024 ibrahim. All Rights Reserved.** *(<- Zameni godinu ako treba)*

The source code for SonicARP is made publicly visible for demonstration and educational review purposes only.

**You are granted permission to:**
*   View and inspect the source code.
*   Run the software **strictly** in accordance with the warnings and prerequisites mentioned above.

**You are explicitly NOT granted permission to:**
*   Copy, modify, or distribute the source code or the executable file.
*   Create derivative works based on this code.
*   Use this software or parts of its code for commercial purposes.
*   Re-license this software under any other terms.

Any use beyond viewing and the limited execution permission described requires **explicit written consent** from the author (ibrahim).
