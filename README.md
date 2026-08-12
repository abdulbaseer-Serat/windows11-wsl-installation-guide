# windows11 wsl installation guide
A complete step-by-step guide for installing Windows Subsystem for Linux (WSL2) on Windows 11.
## What is WSL?

WSL (Windows Subsystem for Linux) is a Microsoft feature that allows you to run a real Linux environment directly inside Windows without creating a separate virtual machine or dual-boot setup. It lets you use Linux commands, tools, scripts, package managers, and applications alongside Windows.
```text
Examples:

- Run Ubuntu on Windows
- Use Bash shell
- Install Python, Java, Node.js
- Run Docker containers
- Use Linux development tools
- Access Linux files from Windows Explorer
```


# Prerequisites

Before installing WSL2, ensure:

- Windows 11 is installed
- Administrator access is available
- Internet connection is available
- CPU virtualization is enabled in BIOS/UEFI

---

# Step 1: Check Virtualization Status

1. Press:

```text
Ctrl + Shift + Esc
```

2. Open **Task Manager**
3. Select **Performance**
4. Click **CPU**

Verify:

```text
Virtualization: Enabled
```

If it shows Disabled, enable virtualization in BIOS.

---

# Step 2: Enable Virtualization in BIOS

## Intel Systems

Enable:

```text
Intel Virtualization Technology (VT-x)
```

## AMD Systems

Enable:

```text
AMD-V
```

or

```text
SVM Mode
```

Save changes and restart Windows.

---

# Step 3: Enable Virtual Machine Platform

Open PowerShell as Administrator:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -All
```

Restart Windows when prompted.

---

# Step 4: Enable Windows Subsystem for Linux

Open PowerShell as Administrator:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux -All
```

Restart Windows.

---

# Step 5: Install WSL2 Automatically

Open PowerShell as Administrator:

```powershell
wsl --install
```

This command automatically:

- Enables Windows Subsystem for Linux
- Enables Virtual Machine Platform
- Downloads Linux Kernel
- Sets WSL2 as Default
- Installs Ubuntu

Restart the computer after installation.

---

# Step 6: Configure Ubuntu

After reboot, launch Ubuntu.

Linux will ask for:

```text
Enter new UNIX username:
```

Example:

```text
basir
```

Then enter a password.

Example:

```text
New password:
Retype new password:
```

You will now enter the Ubuntu terminal.

---

# Step 7: Update Ubuntu

Update package repositories:

```bash
sudo apt update
```

Upgrade installed packages:

```bash
sudo apt upgrade -y
```

---

# Step 8: Verify WSL Installation

Check WSL status:

```powershell
wsl --status
```

Expected output:

```text
Default Version: 2
```

Check installed distributions:

```powershell
wsl --list --verbose
```

Example:

```text
NAME      STATE     VERSION
Ubuntu    Running   2
```

---

# Install Other Linux Distributions

Show available distributions:

```powershell
wsl --list --online
```

Install Debian:

```powershell
wsl --install -d Debian
```

Install Kali Linux:

```powershell
wsl --install -d Kali-Linux
```

Install openSUSE:

```powershell
wsl --install -d openSUSE-Leap-15.6
```

---

# Useful WSL Commands

## Start WSL

```powershell
wsl
```

## Shutdown WSL

```powershell
wsl --shutdown
```

## Update WSL

```powershell
wsl --update
```

## Check Status

```powershell
wsl --status
```

## List Installed Distributions

```powershell
wsl --list --verbose
```

## Set Default WSL Version

```powershell
wsl --set-default-version 2
```

---

# Access Linux Files from Windows

Inside Ubuntu:

```bash
explorer.exe .
```

This opens the current Linux directory in Windows File Explorer.

---

# Troubleshooting

## Error 0x80370102

### Cause

Virtualization is disabled in BIOS.

### Solution

Enable one of the following:

Intel:

```text
Intel Virtualization Technology (VT-x)
```

AMD:

```text
AMD-V
SVM Mode
```

Restart and try again.

---

## WSL Not Starting

Restart WSL:

```powershell
wsl --shutdown
```

Then:

```powershell
wsl
```

---

## Ubuntu Missing

Install Ubuntu manually:

```powershell
wsl --install -d Ubuntu
```

---

# One-Command Installation

For most Windows 11 systems:

```powershell
wsl --install
```

After restarting:

```powershell
wsl --status
```

If the output shows:

```text
Default Version: 2
```

your WSL2 installation is successful.

---

# Author

Abdul BASIR-SERAT

## Technologies

- Windows 11
- WSL2
- Ubuntu
- PowerShell
- Linux
- Virtual Machine Platform

## License

MIT License
