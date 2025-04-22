# SonicARP - Network Tool Demonstration by ibrahim

**Developer:** ibrahim ([Link do vašeg GitHub profila - ZAMENITE OVO!](https://github.com/vas_username))

**Technologies:** Python 3, Scapy, Tkinter (ttk, ttkthemes)

---

## 🚨🚨🚨 CRITICAL WARNING & USAGE ADVISORY 🚨🚨🚨

**This tool is intended STRICTLY for educational purposes and technical demonstration ONLY.**

**DO NOT use this software on any network without the explicit, PRIOR, WRITTEN PERMISSION of the network owner.** Unauthorized use of ARP spoofing tools is **ILLEGAL** in most jurisdictions and can cause significant network disruption. Such actions may lead to severe consequences, including **legal prosecution, financial penalties, and account suspension.**

**The developer (ibrahim) assumes ABSOLUTELY NO RESPONSIBILITY for any damage, disruption, or legal issues arising from the misuse of this software.** This code is shared "as-is" as a demonstration project. **USE ENTIRELY AT YOUR OWN RISK** and only within legally permitted and controlled environments.

---

## Description

SonicARP is a project showcasing the implementation of ARP spoofing using Python. It utilizes **Scapy** for low-level network packet crafting and manipulation, and **Tkinter** (with `ttk` and `ttkthemes`) for the graphical user interface.

The tool provides basic functionalities for:
*   Attempting automatic detection of local network parameters (IP, MAC, Gateway, Network Range).
*   Scanning the local network using ARP requests to discover active devices.
*   Performing an **automatic ARP spoofing attack** against **all** discovered devices (excluding the user's machine and the gateway).
*   Optionally poisoning the gateway's ARP cache as well (for potential Man-in-the-Middle setup analysis - actual interception requires separate tools).
*   Attempting to restore the ARP tables of targeted devices upon stopping the attack.
*   Logging activities within the GUI.

This project was developed primarily for learning purposes related to network programming, packet manipulation with Scapy, and GUI development with Tkinter. It is **not intended as a polished, production-ready utility** but rather as a functional demonstration of the concepts involved.

## Prerequisites

Before running SonicARP, ensure you have the following:

1.  **Python 3.x:** Recommended version 3.7 or higher.
2.  **pip:** The Python package installer (usually comes with Python).
3.  **Npcap:** **ESSENTIAL** packet capture library for Windows. Scapy relies on this for sending and receiving raw packets.
    *   Download from: [https://npcap.com/](https://npcap.com/)
    *   **During installation:** Make sure to check the option **"Support WinPcap API-compatible mode"**.
4.  **Administrator Privileges:** The script or the compiled `.exe` **MUST** be executed with administrator rights to allow Scapy access to raw sockets and network interfaces.

## Installation

1.  **Clone or Download:**
    *   Clone the repository: `git clone https://github.com/vas_username/SonicARP.git` (Zamenite URL pravim!)
    *   Or download the ZIP file from GitHub and extract it.
2.  **Navigate to Directory:**
    Open a terminal or command prompt and change to the project directory: `cd path/to/SonicARP`
3.  **Install Dependencies:**
    It's highly recommended to use a Python virtual environment (`venv`).
    ```bash
    # Create virtual environment (optional but recommended)
    python -m venv venv
    # Activate virtual environment
    # Windows:
    .\venv\Scripts\activate
    # Linux/macOS:
    source venv/bin/activate

    # Install required packages
    pip install scapy ttkthemes ipaddress
    ```
    *(Note: `ipaddress` is built-in with Python 3.3+ but listing it doesn't hurt).*
4.  **Install Npcap:** Make sure Npcap is installed as described in the Prerequisites section.

## Usage Guide

1.  **Run as Administrator:**
    *   **Windows:** Right-click on your terminal (Command Prompt, PowerShell) and select "Run as administrator".
    *   **Linux/macOS:** Use `sudo`.
2.  **Launch the Script:**
    From the administrator terminal within the project directory (and with the virtual environment activated, if used):
    ```bash
    python sonic_arp.py
    ```
    *(Replace `sonic_arp.py` with the actual name of your Python script if different).*
3.  **Interface Overview:**
    *   **Controls (Left Panel):** Buttons for scanning, starting/stopping the attack, and the gateway poisoning option. Also includes the critical warning.
    *   **Found Devices (Top Right):** Listbox where discovered devices will appear after a scan.
    *   **Activity Log (Bottom Right):** Shows status messages, errors, and attack progress.
    *   **Status Bar (Bottom):** Displays the current status and developer credit.
4.  **Workflow:**
    *   **Step 1: Scan Network:** Click `📡 Scan Network`. The tool will try to find devices on your local network using ARP. Wait for the scan to complete. Found devices (potential targets) will populate the list.
    *   **Step 2 (Optional): Poison Gateway:** If you intend to attempt a Man-in-the-Middle attack (requires separate tools for traffic analysis), check the `Poison Gateway (MitM)` box. By default, SonicARP only poisons the clients *about* the gateway.
    *   **Step 3: Start Attack:** Click `🚀 Start AUTO Attack`. **WARNING:** This will immediately begin sending ARP spoof packets to **ALL** devices listed in the "Found Devices" list.
    *   **Step 4: Stop Attack:** When finished, click `✅ Stop Attack`. The tool will cease sending spoof packets and attempt to send corrective ARP packets to restore the ARP tables of the targeted devices and the gateway (if poisoned).

## Building the .exe (Optional)

If you want a standalone executable (requires PyInstaller):

1.  **Install PyInstaller:** `pip install pyinstaller`
2.  **Prepare Icon:** Place an icon file (e.g., `sonic_icon.ico`) in the project directory.
3.  **Run PyInstaller:** From an **administrator** terminal in the project directory:
    ```bash
    pyinstaller --onefile --windowed --icon="sonic_icon.ico" --name="SonicARP_by_ibrahim" sonic_arp.py
    ```
    *(Adjust icon and script names as needed).*
4.  **Find Executable:** The `.exe` file will be located in the `dist` sub-directory.
5.  **IMPORTANT:** Even when using the `.exe`, the target computer **must still have Npcap installed correctly**, and the `.exe` **must be run as administrator**. Antivirus software might also flag the executable.

## Disclaimer

This software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.

## License

This project is licensed under the **MIT License**. See the `LICENSE` file for details.
*(Make sure you have a file named LICENSE containing the MIT license text in your repository if you select this)*.
