---
description: ''
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

Installation Guide (Before Installing)

Pre-installation Requirements
- Usb drive 8GB or higher
- Rufus,Ventoy,Balena Etcher or Fedora Media Writer
- Secure Boot is disabled in Bios.
- BitLocker is turned off (May cause data loss if ignored)
- Gpu modes should be set to Ultimate or Standard in Windows before the installtion
- Fast Boot should be disabled in Windows(For dual boot only)

# Asus Laptops and Linux Compatibility
Asus laptops have excellent compatibility with Linux compared to many other laptop brands. Most of the software you need to control features (like RGB, CPU modes, and fan curves) is readily available on Linux. You can pretty much manage everything just like you would on Windows.
Additionally, you can check the list of supported games on "Are We Anti-Cheat Yet" or proton db to see if your games work well on Linux.

Creating a Bootable Media:

First, download the latest ISO from the [Fedora website](https://fedoraproject.org/en/workstation/download).
The recommended one is Fedora Workstation (GNOME). You can also use Fedora Workstation (KDE).

Q: What do "GNOME" and "KDE" at the end mean?
A: GNOME and KDE are desktop environments. They basically handle how your desktop looks. GNOME is similar to macOS, and KDE is similar to Windows 10. You can use either one, but GNOME is recommended.

After you've downloaded the ISO, just run Rufus and burn the ISO to the USB drive. If you have Ventoy installed on the USB drive, just copy the ISO to the drive.

# Dual Booting
If you plan on dual booting (i.e., using both Linux and Windows at the same time), you need to create space for Fedora to be installed on.Dont create a new voume just leave it blank so the installer pickups up the mepty space.

[Follow this guide](https://www.youtube.com/watch?v=eHQJMy8Q7Zk)

***Note: To go into the Bios, just hold the F2 key and press the power button. It should take you to the Bios. In the Bios, disable Secure Boot and drag the "Windows Boot Manager" below the USB drive, then save changes and exit.***

# Installing Fedora
If you just plan on using Linux, then select "Use entire disk" during the setup and continue.

# Uninstalling Fedora

If you dual booted Fedora, then just follow the instructions in the video to remove it.

If you just installed Fedora, then boot from the Windows installation media.

Press Shift + F10

Type:
*diskpart*

*Select disk X (X is wherever Linux is installed)*

*Clean disk*

After that, just continue with the setup normally.

Note: Intel systems
If it asks for drivers for the disk, just disable VMD in Bios.
