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

# Installing Linux

## Asus Laptops and Linux Compatibility

Asus laptops have excellent compatibility with Linux compared to many other laptops brands. Most of the software you need to control features (like RGB, CPU modes, and fan curves) are readily available on Linux. You can pretty much manage everything just like you would on Windows.

Additionally, you can check the list of supported games on [Are We Anti-Cheat Yet](https://areweanticheatyet.com/) to see if your games work well on Linux.

## Choosing The Right Distro

Picking a Linux distro can be annoying, but I’ve found that Fedora is the best all around choice.

The software support for Debian based distros is pretty limited - you’ll end up having to compile a lot of things from source. So, I’d recommend avoiding distros like Ubuntu or Mint. Not that they’re bad, just not ideal when it comes to software compatibility out of the box.

You can go with Fedora Workstation if you like a macOS like look, or Fedora KDE if you prefer something closer to Windows 10. Both work great.

## Step 1: Installing Linux

{% hint style="warning" %}
**Note:**

Set your GPU mode to “Ultimate” or “Standard” beforehand in Windows via GHelper/Armory Crate
{% endhint %}

* If you want to install **Linux only**,  just erase your disk during setup and tell the installer to install Fedora only.
* If you want to **dual boot Fedora with Windows**, just follow this following linked YouTube guide step by step. -> [How to Dual Boot Fedora](https://youtu.be/kvnfccdTYQU)

## Step 2: Post Install Configuration

If you have an Nvidia dGPU, you’ll need to install the Nvidia drivers on Linux.&#x20;

If you have an AMD dGPU, you don’t need to install any extra drivers because the open source Mesa drivers are already included in the Linux kernel.&#x20;

{% hint style="info" %}
**Note:**

**U**nlike Windows, you generally don’t need to install additional drivers for other hardware. Linux usually handles that automatically.
{% endhint %}

## Step 3: Setting Up Asus Software

The instructions you need are on the \[Asus Linux website]\(https://asus-linux.org/guides/fedora-guide/). You can skip the installation steps there and start from the Setup section. Just follow these parts:

1. Update Fedora
2. Install nvidia graphics drivers (skip if you have amd gpu)
3. Install asusctl and supergfxctl

After installing supergfxctl, open your terminal and run:

`sudo systemctl enable supergfxd.service`

`sudo systemctl start supergfxd.service`

You can ignore the “Asus kernel isn’t loaded” warning in _**rog-control-center**_.

If you’re using gnome, install the supergfxctl-gex extension.

If you’re on KDE, run these commands:

`sudo dnf copr enable jhyub/supergfxctl-plasmoid`

`sudo dnf install supergfxctl-plasmoid`

Then, in the terminal, type:

`supergfxctl --mode Hybrid`

Reboot your system, and voila, GPU modes should be working perfectly, and you can control them via the GUI.

## Step 4: Fixing hotkeys:

Some keys like the AC (Armoury Crate) key, Fn+F4, and Fn+F5 may not work by default in Linux. You can manually remap them in GNOME or KDE settings.

In GNOME, go to Settings > Keyboard > Keyboard Shortcuts, then click “+” to add a new shortcut.

In KDE, go to System Settings > Shortcuts > Custom Shortcuts, then create a new Global Shortcut → Command/URL.

Set any name, press the key you want (e.g., Fn+F4), and enter the command:

1.For Armoury Crate: `rog-control-center`

2.For Aura Mode: `asusctl aura -n`

3.For Performance Mode: `asusctl profile -n`

Note: Fn+F5 may not be detected due to ACPI issues. If it doesn't register it, choose another key.

## Additional Links & Support:

Since most of us here on the subreddit are more familiar with Windows, support for Linux is pretty limited. For faster help, I recommend visiting communities like:

1. [r/linux4noobs](https://www.reddit.com/r/linux4noobs/)
2. [r/fedora](https://www.reddit.com/r/fedora/)
3. Fedora Forums
4. [Asus Linux Discord server](https://discord.gg/B8GftRW2Hd)
5. [Gaming on Linux](https://youtu.be/BYIDoD8VdAw)

And just so you know, I use Arch, btw!

