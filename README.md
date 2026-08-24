[https://img.shields.io/badge/Field-black%20Windows%20Subsystem-red](https://img.shields.io/badge/Field-black%20Windows%20Subsystem-red)


# windows 11 wsl installation guide.
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


## Prerequisites

Before installing WSL2, ensure:

- Windows 11 is installed
- Administrator access is available
- Internet connection is available
- CPU virtualization is enabled in BIOS/UEFI

---

## Step 1: Check Virtualization Status

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

## Step 2: Enable Virtual Machine Platform

Open PowerShell as Administrator:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -All
```


---

## Step 3: Enable Windows Subsystem for Linux

Open PowerShell as Administrator:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux -All
```

---

## Step 4: Install WSL2 Automatically

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

## Step 5: Configure Ubuntu or other lunix Operating system

After reboot, launch Ubuntu.

Linux will ask for:

```text
Enter new UNIX username:
Then enter a password.

```
---

## Step 6: Update Ubuntu

Update package repositories:

```bash
sudo apt update
```

Upgrade installed packages:

```bash
sudo apt upgrade -y
```

---

## Step 7: Verify WSL Installation

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

## Install Other Linux Distributions

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

## References
Microsoft WSL Documentation:https://learn.microsoft.com/windows/wsl/install.

## 🧑‍💻 Developer

Abdulbaseer Serat  
MS in Computer Sciences · Abasyn University · [GitHub](https://github.com/abdulbaseer-Serat) · [LinkedIn](https://linkedin.com/in/abdul-basir-serat-65b8201ab) · info.abdulbasir@gmail.com
