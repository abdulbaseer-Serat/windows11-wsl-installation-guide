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
# Windows 11 WSL2 Installation Guide

A complete step-by-step guide for installing Windows Subsystem for Linux (WSL2) on Windows 11.

## What is WSL?

Windows Subsystem for Linux (WSL) allows you to run a Linux environment directly on Windows without using a traditional virtual machine.

## Prerequisites

- Windows 11
- Administrator Access
- Internet Connection
- Virtualization Enabled in BIOS

## Step 1: Open PowerShell as Administrator

1. Click Start
2. Search for PowerShell
3. Right-click PowerShell
4. Select Run as Administrator

## Step 2: Install WSL

Run:

```powershell
wsl --install
```

This command:

- Enables WSL
- Enables Virtual Machine Platform
- Downloads Linux Kernel
- Sets WSL2 as default
- Installs Ubuntu

## Step 3: Restart Windows

Restart your computer when prompted.

## Step 4: Configure Ubuntu

After reboot:

```text
Enter new UNIX username:
```

Example:

```text
basir
```

Set a password and confirm it.

## Step 5: Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

## Verify Installation

```powershell
wsl --status
```

```powershell
wsl --list --verbose
```

Expected Output:

```text
Default Version: 2
Ubuntu Running Version 2
```

## Useful Commands

Start WSL:

```powershell
wsl
```

Shutdown WSL:

```powershell
wsl --shutdown
```

Update WSL:

```powershell
wsl --update
```

List Distros:

```powershell
wsl --list --online
```

Install Debian:

```powershell
wsl --install -d Debian
```

Install Kali:

```powershell
wsl --install -d Kali-Linux
```

## Troubleshooting

### Error 0x80370102

Enable virtualization in BIOS:

- Intel VT-x
- AMD-V
- SVM Mode

Then restart the system.

## References

Microsoft WSL Documentation:
https://learn.microsoft.com/windows/wsl/install
