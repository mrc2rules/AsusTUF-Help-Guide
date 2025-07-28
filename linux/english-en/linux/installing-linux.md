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
# Fedora Post-Installation Guide

This guide walks you through setting up your Fedora system with Nvidia drivers, Asus tools, and power management tweaks.

{% stepper %} {% step %}

## Step 1: Post-Install Configuration

 If you're using an Nvidia dGPU, you'll need to install Nvidia's proprietary drivers manually.

AMD users can skip this, as Mesa drivers are built into the kernel and work out of the box.

{% hint style="info" %} Note: Unlike Windows, most drivers are included in the kernel, so you don't usually need to install them manually. 

{% endhint %} {% endstep %}


{% step %}

## Step 2: GPU Driver Installation and Asus Software Setup

### 2.1 Nvidia Driver Installation (Fedora)

{% hint style="warning" %} Important: Make sure Secure Boot is turned off or the Nvidia driver won’t load. {% endhint %}

Start by updating the system:

```bash
sudo dnf update
```

Enable RPM Fusion:

```bash
sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm \
https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```

Install Nvidia packages:

```bash
sudo dnf install akmod-nvidia
sudo dnf install xorg-x11-drv-nvidia-cuda
```

{% hint style="info" %} After installing, wait 5–8 minutes for the kernel module to build in the background. {% endhint %}

Enable Nvidia power management:

```bash
sudo systemctl enable nvidia-hibernate.service nvidia-suspend.service nvidia-resume.service nvidia-powerd.service
```

Blacklist Nouveau and enable Nvidia DRM:

```bash
sudo nano /etc/default/grub

# Verify that the following parameters are present:
GRUB_CMDLINE_LINUX="rd.driver.blacklist=nouveau modprobe.blacklist=nouveau nvidia-drm.modeset=1 rhgb quiet"
```

### 2.2 Asus Software Installation

Add the COPR repo:

```bash
sudo dnf copr enable lukenukem/asus-linux
```

Install tools:

```bash
sudo dnf install asusctl supergfxctl rog-control-center
```

Enable GPU switching:

```bash
sudo systemctl enable supergfxd.service
sudo systemctl start supergfxd.service
```

{% hint style="info" %} Ignore the "Asus kernel isn't loaded" message in rog-control-center. It’s safe. {% endhint %}

### 2.3 Switching GPU Modes with a GUI

GNOME: Use the [supergfxctl-gex](https://extensions.gnome.org/extension/5344/supergfxctl-gex/) extension.

KDE: Use the supergfxctl-plasmoid:

```bash
sudo dnf copr enable jhyub/supergfxctl-plasmoid
sudo dnf install supergfxctl-plasmoid
```

Reload Plasma:

```bash
plasmashell --replace &
```

Set Hybrid GPU mode:

```bash
supergfxctl --mode Hybrid
```

{% hint style="info" %} Note: Switching to/from Hybrid mode needs logout. Ultimate mode requires a reboot. {% endhint %}

{% endstep %}
{% step %} 

## Step 3: Fixing Hotkeys

Some hotkeys are BIOS-level and can’t be remapped.

{% hint style="info" %} To test remap capability: press the key while adding a shortcut. If nothing registers, it can't be reassigned. {% endhint %}

### GNOME

- Settings → Keyboard → Shortcuts → “+”

### KDE

- System Settings → Shortcuts → Custom Shortcuts → New Global Shortcut → Command/URL

**Commands:**

- `rog-control-center`: Launch GUI
- `asusctl aura -n`: Toggle Aura lighting
- `asusctl profile -n`: Change power profile

{% endstep %}

{% step %} 

## Step 4: Power Management

If battery life on Linux feels worse than on Windows, you might want to try out some power management tools. These tools automatically handle system power, whether you're on battery or plugged in, by adjusting CPU frequencies and other power settings.

Two of the best tools for this are TLP and CPU AutoFreq. Personally, I’ve found CPU AutoFreq to work better, but this can vary depending on your laptop and how you use it. You can try either one to see which gives better results for your setup.

{% hint style="warning" %}
Important: Only install one of these tools. Running both simultaneously can cause conflicts and lead to unexpected behavior.
{% endhint %}

### 4.1 TLP

TLP is a feature-rich command-line utility for Linux that helps extend battery life without requiring manual tuning. Its default configuration is already optimized and implements many of Powertop’s recommendations.

**Install TLP:**

```bash
sudo dnf install tlp
```

**Enable TLP:**

```bash
sudo systemctl enable tlp
sudo systemctl start tlp
```

{% hint style="info" %} TLP conflicts with power-profiles-daemon. Remove it or mask its service:

```bash
# To remove it:
sudo dnf remove  power-profiles-daemon

#To mask it:
systemctl mask power-profiles-daemon.service
```

{% endhint %}

### 4.2 CPU AutoFreq

CPU AutoFreq is a real-time CPU frequency and power optimizer. It monitors your system load, battery level, and temperature to dynamically manage CPU scaling for better battery life.

**Installation:**

```bash
git clone https://github.com/AdnanHodzic/auto-cpufreq.git && cd auto-cpufreq && sudo ./auto-cpufreq-installer
```

{% hint style="info" %} If power-profiles-daemon is installed, disable it:

```bash
systemctl mask power-profiles-daemon.service
```

{% endhint %}

{% hint style="info" %} After installation, open the cpu-auto-freq app and verify if it’s working properly. {% endhint %}

{% endstep %}

{% step %}


## Step 5: Enable Flatpak Support

By default, Fedora restricts the set of available Flatpak apps. You can unlock full Flatpak support by enabling third-party repos during the initial setup, or manually with the following command:

```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

{% endstep %}

{% step %}


## Step 6: Enable Multimedia Codecs

To add support for common multimedia formats, run:

```bash
sudo dnf install libavcodec-freeworld
```

{% endstep %}

{% step %}

## Step 7: DNF Configuration

You can configure DNF to increase download speeds by enabling parallel downloads and selecting the fastest mirror.

**Edit the config file:**

```bash
sudo nano /etc/dnf/dnf.conf
```

**Add these lines at the end:**

```bash
max_parallel_downloads=10
fastestmirror=1
```

{% endstep %}
{% endstepper %}
