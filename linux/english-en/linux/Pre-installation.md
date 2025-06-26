---
description: Written by Zenith Zephyr
icon: arrows-rotate-reverse
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

Fedora Linux Installation Guide (Before Installing)

# Pre-installation Requirements:
- A USB drive with at least 8 GB of storage capacity.

- One of the following tools to create bootable media:

- ***Rufus, Ventoy, Balena Etcher, or Fedora Media Writer.***

- Secure Boot must be disabled in the BIOS. 

  ***WARNING: Secure Boot can prevent Fedora from booting if not disabled.***

- BitLocker must be turned off.

  ***WARNING: Failure to disable BitLocker may result in data loss or drive access issues.***

- GPU mode should be set to "Ultimate" or "Standard" in Windows before installation.

- Fast Boot should be disabled in Windows.( This is required only if you are planning to dual boot.)

# Asus Laptops and Linux Compatibility:

Asus laptops have excellent compatibility with Linux compared to many other brands.
Most of the software required to control features such as RGB lighting, CPU modes, and fan curves is readily available on Linux.
These functionalities can be managed similarly to how they are on Windows.

Additionally, you can verify game compatibility and anti-cheat support using:
- [Are We Anti-Cheat Yet](https://areweanticheatyet.com)
- [ProtonDB](https://www.protondb.com)

# Creating Bootable Media:

### 1. Download the latest Fedora ISO from the official website:
   https://fedoraproject.org/en/workstation/download

   Recommended edition: Fedora Workstation (GNOME)
   
   Alternative option: Fedora Workstation (KDE)

   Q: What do "GNOME" and "KDE" mean?
   
   A: These are desktop environments that define the look and feel of your system interface.
   
   - GNOME resembles macOS.
   
   - KDE is similar to Windows 10.

### 2. Once downloaded:
   - If using Rufus:
   - Open the tool, select the ISO, and write it to the USB drive.
   - If using Ventoy:
   - Simply copy the ISO to the USB drive if Ventoy is already installed.

# Dual Booting:

If you plan to dual boot Fedora with Windows, ensure that sufficient unallocated space is available on the disk. 

{% hint style="warning" %}
**Warning:**  
Do not create a new volume; leave the space empty for the installer to detect.
{% endhint %}

[Fedora Dual Boot Installation Video Tutorial](https://www.youtube.com/watch?v=eHQJMy8Q7Zk)

NOTE: To access BIOS, hold the F2 key and press the power button. In BIOS:
- Disable Secure Boot.
- Set the USB drive as the primary boot device by placing it above "Windows Boot Manager".
- Save and exit.

# Installing Fedora:

1. Boot from the USB drive.
   Restart your computer and boot from the USB drive containing the Fedora image.

2. Wait for the installer to load.
   Allow 1–2 minutes for the system to load properly.
   Once loaded, you should see the Anaconda installer.

   ***Note: If the installer doesn't appear immediately, wait 10–20 seconds.****

4. Select your language.
   On the Welcome screen, choose your preferred language and click Next.

5. Choose the installation method.
   On the Installation Destination screen, choose how you want Fedora to be installed:
   - For dual-boot systems: Select "Share disk with other operating system" and click Continue.
   - For standalone installations: Choose "Use entire disk".

   
   ***At the top of the screen, you’ll see the target drive for installation.
   If you have multiple drives, make sure to select the correct one to avoid data loss.***

6. Configure storage encryption (optional).
   On the Storage Configuration screen, it's recommended not to encrypt your data for simplicity, unless required.

7. Review and confirm settings.
   On the Summary screen, review all your selected options.
   If everything is correct, click Begin Installation.

8. Finish installation and reboot.
   After the installation completes:
   - Exit the Live Environment.
   - Remove the USB drive.
   - Reboot your system.
   You should now boot directly into Fedora.

# Uninstalling Fedora:
For dual boot setups: Follow the same video guide to remove Fedora safely.

For standalone Fedora installations:
1. Boot from Windows installation media.
2. Press Shift + F10 to open the Command Prompt.
3. Run the following commands:

   `diskpart`
      
   `select disk X   (Replace 'X' with the number of the drive where Fedora is installed)`
      
   `clean`
      
4. Continue with the Windows setup normally.

NOTE for Intel systems:

If the Windows installer does not detect your disk, disable VMD (Volume Management Device) in BIOS.
