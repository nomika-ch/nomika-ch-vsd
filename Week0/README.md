# Week 0 Documentation – VSD RISC-V SoC Tapeout Program
### Task: Environment Setup (Ubuntu, Terminal, Yosys, Icarus Verilog, GTKWave)

---
## Tools Installation

#### <ins>All the instructions for installation of required tools can be found here:</ins>

### **System Requirements**
- 4 GB RAM
- 50 GB HDD
- Ubuntu 20.04 or higher
- 4 vCPU
## 1. Ubuntu Installation
- Downloaded and installed **Ubuntu** as the Linux environment inside **VirtualBox**.  
- Faced an issue:  
  - **Error**: `sudoers not found` while running commands with `sudo`.  
  - **Fix**: Added the user to the `sudoers` file by editing it and appending:  
    ```
    user_name ALL=(ALL:ALL) ALL
    ```
  - After this, `sudo` worked properly.

---

## 2. Resizing the Terminal (VirtualBox Guest Additions)
- To enable terminal resizing and better screen integration, installed **VirtualBox Guest Additions**.  
- Steps followed:  
  1. From VirtualBox menu → **Devices → Insert Guest Additions CD Image…**  
  2. Mounted under:  
     ```
     /media/openboxuser/VBox_GAs_7.1.8/
     ```  
  3. Installed prerequisites:  
     ```bash
     sudo apt update
     sudo apt install build-essential dkms linux-headers-$(uname -r)
     ```
  4. Ran the installer:  
     ```bash
     cd /media/openboxuser/VBox_GAs_7.1.8/
     ./autorun.sh
     ```

- After reboot, terminal resizing worked correctly.

---

# 3. Yosys Installation Procedure

```bash
# 1. Update the package index
sudo apt-get update

# 2. Clone the Yosys repository from GitHub
git clone https://github.com/YosysHQ/yosys.git

# 3. Change directory into the cloned repository
cd yosys

# 4. Install 'make' if it is not already installed
sudo apt install make

# 5. Install required build dependencies
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev

# 6. (Optional) configure for GCC compiler
make config-gcc

# 7. Initialize Git submodules (Yosys build depends on 'abc' submodule)
git submodule update --init --recursive

# 8. Build Yosys
make

# 9. Install Yosys system-wide
sudo make install
```

Yosys check


<img width="848" height="374" alt="Screenshot from 2025-09-19 23-48-17" src="https://github.com/user-attachments/assets/1e0689d8-83bb-406e-84aa-9f326c773fbe" />

---

# 4. Installing Icarus Verilog (Simulator)
```bash
sudo apt update
sudo apt install iverilog

  ```
iVerilog check

<img width="855" height="243" alt="Screenshot from 2025-09-19 23-51-26" src="https://github.com/user-attachments/assets/633793b9-ffda-487c-adc9-4a8079290f0e" />

---

# 5. Installing GTKWave (Waveform Viewer)
```bash
sudo apt update
sudo apt install gtkwave

  ```
GTKWave check

<img width="860" height="618" alt="Screenshot from 2025-09-19 23-59-29" src="https://github.com/user-attachments/assets/439445e1-69db-42b0-b5d3-13a5f3d9b269" />

**ISSUE FACED** : On running gtkwave, got the warning:
```bash
Failed to load module "canberra-gtk-module"
```

**Fix applied:**
```bash
sudo apt-get install libcanberra-gtk-module libcanberra-gtk3-module
```
- After installing these modules, GTKWave launched successfully without warnings.

## Final Setup Status

- Ubuntu installed successfully.
- Terminal resizing enabled via VirtualBox Guest Additions.
- Yosys, Icarus Verilog, and GTKWave installed and verified.
- All Week-0 environment setup tasks completed.
