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

# Post-installation

## Installing Linux

{% stepper %}
{% step %}
## Post Install Configuration

* If you have an Nvidia dGPU, you’ll need to install the Nvidia drivers on Linux.
* If you have an AMD dGPU, you don’t need to install any extra drivers because the open source Mesa drivers are already included in the Linux kernel.

{% hint style="info" %}
**Note:**\
Unlike Windows, you generally don’t need to install additional drivers for most hardware. Linux usually handles that automatically.
{% endhint %}
{% endstep %}

{% step %}
## Asus Software Setup and GPU Driver Installation

The instructions you need are on the [Asus Linux website](https://asus-linux.org/guides/fedora-guide/). You can skip the installation steps there and start from the Setup section. Just follow these parts:

1. Update Fedora
2. Install Nvidia graphics drivers (skip if you have AMD gpu)
3. Install **asusctl** and **supergfxctl**

After installing **supergfxctl**, open your terminal and run:

{% code lineNumbers="true" %}
```bash
sudo systemctl enable supergfxd.service
sudo systemctl start supergfxd.service
```
{% endcode %}

You can ignore the “Asus kernel isn’t loaded” warning in _**rog-control-center**_.

### Switching GPU Modes with a GUI

* If you are using GNOME, install the [supergfxctl-gex extension.](https://extensions.gnome.org/extension/5344/supergfxctl-gex)
* If you are using KDE, you’ll need to install [supergfxctl-plasmoid.](https://gitlab.com/Jhyub/supergfxctl-plasmoid)



1. Run the following commands to install it:

{% code lineNumbers="true" %}
```bash
sudo dnf copr enable jhyub/supergfxctl-plasmoid
sudo dnf install supergfxctl-plasmoid
```
{% endcode %}

2. Then, reload Plasma for the changes to take effect.

{% code lineNumbers="true" %}
```bash
plasmashell --replace &
```
{% endcode %}

3. Finally, in the terminal, set the GPU mode to Hybrid:

{% code lineNumbers="true" %}
```bash
supergfxctl --mode Hybrid
```
{% endcode %}

After reloading the shell, a chip icon should appear on the taskbar. You can use this icon to switch GPU modes through a graphical interface without needing the terminal.\
\
After rebooting your system the GPU modes should be working perfectly.

{% hint style="info" %}
**Note:**\
Switching the GPU mode to or from _Hybrid_ requires you to log out and log back in. _Ultimate_ mode functions similarly to Windows and requires a full system reboot.
{% endhint %}
{% endstep %}

{% step %}
## Fixing hotkeys:

{% hint style="info" %}
Some hotkey actions are managed directly by the BIOS, meaning their input does not reach the operating system and therefore cannot be remapped.

\
To verify whether a hotkey can be remapped, press the keys while creating the shortcut.\
If the input registers, remapping is possible; if not, you will need to assign a different key combination.
{% endhint %}

* In **GNOME**, go to Settings > Keyboard > Keyboard Shortcuts, then click “+” to add a new shortcut.
* In **KDE**, go to System Settings > Shortcuts > Custom Shortcuts, then create a new Global Shortcut → Command/URL.

Set any name, press the key you want (e.g., Fn+F4), and enter the command:

1. For Armoury Crate: `rog-control-center`
2. For Aura Mode: `asusctl aura -n`
3. For Performance Mode: `asusctl profile -n`


{% endstep %}
{% endstepper %}
