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

 Post Install Configuration

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
 
 
 
 
 ##Gaming on Linux(https://youtu.be/BYIDoD8VdAw)
If you have most games on Steam, then congrats, you’ve saved yourself from some hassle. Just go to Steam settings and enable Proton. After that, your games should run normally, just like they did on Windows.
If you use any launcher other than Steam, you’ll need to install Lutris to play games from different launchers such as Epic Games, GOG, or any other emulators.

To install Lutris, type this in the terminal to install Lutris and Wine:

`sudo dnf install lutris && sudo dnf install wine`

[Video tutorial on how to add game executables manually: Installation Guide](https://www.youtube.com/watch?v=hDg4rJj8jhk)

***And just so you know, I use Arch, btw!***

