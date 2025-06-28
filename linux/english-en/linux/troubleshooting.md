---
icon: screwdriver-wrench
---

# Troubleshooting

### <mark style="color:orange;">1.</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**Brightness not working in Hybrid or Eco mode**</mark> <mark style="color:orange;">**(But works in Ultimate / dGPU-only mode)**</mark>

<mark style="color:green;">**Fix:**</mark> You need to modify the GRUB settings.\
Open a terminal and run:

```
sudo nano /etc/default/grub
```

\
Find this line:

```
GRUB_CMDLINE_LINUX="rhgb quiet"
```

\
Replace it with:

```
GRUB_CMDLINE_LINUX="rhgb quiet pcie_aspm=force acpi_backlight=native"
```

\
Then update GRUB by running:

```
grub2-mkconfig -o /boot/grub2/grub.cfg
```

\
Finally, reboot your system.

{% hint style="info" %}
**Note:**&#x20;

This method works on other distributions as well. On those, you may need to add the parameters to the line starting with GRUB\_CMDLINE\_LINUX\_DEFAULT instead.
{% endhint %}

### <mark style="color:orange;">2. Apps are not using dGPU While Set to Hybrid Mode</mark> <mark style="color:orange;">(Mostly occurs on Arch-based distros; not for Fedora)</mark>

<mark style="color:green;">**Fix:**</mark> Install and enable switcheroo-control.

Run:

{% code lineNumbers="true" %}
```bash
yay -S switcheroo-control
```
{% endcode %}

Then enable and start the service:

{% code lineNumbers="true" %}
```bash
sudo systemctl enable switcheroo-control
sudo systemctl start switcheroo-control
```
{% endcode %}

After that, right-click on the application. If you see an option to run it with the dedicated GPU, it means Switcheroo is installed and enabled

{% hint style="info" %}
**Note:**&#x20;

This service manages GPU switching, allowing apps to use the dedicated GPU on demand.
{% endhint %}

### <mark style="color:orange;">3. Battery Drains Fast</mark>

<mark style="color:green;">**Fix:**</mark> Install auto-cpufreq to manage CPU frequency and boost automatically.

Run these commands:

{% code lineNumbers="true" %}
```bash
git clone https://github.com/AdnanHodzic/auto-cpufreq.git
cd auto-cpufreq
sudo ./auto-cpufreq
```
{% endcode %}

Follow the prompts and select Install to enable the daemon.

Then enable and start the service:

{% code lineNumbers="true" %}
```bash
sudo systemctl enable auto-cpufreq
sudo systemctl start auto-cpufreq
```
{% endcode %}

{% hint style="info" %}
**Note:**&#x20;

This tool automatically manages CPU performance and power saving, so you don't need to tweak CPU settings manually.
{% endhint %}

### <mark style="color:orange;">4. Some Keys Like Fn+F5, Fn+F4, or Armoury Crate Key Don’t Work</mark>

This is expected behavior as these keys are not fully supported yet.\
Check the post-install guide for steps to enable these keys.

### <mark style="color:orange;">5. How to Change GRUB Timeout</mark>

Open the GRUB configuration file:

{% code lineNumbers="true" %}
```basic
sudo nano /etc/default/grub
```
{% endcode %}

Find the line:\
`GRUB_TIMEOUT=5`

Change the number to your preferred timeout in seconds (try to keep it below 60).

Then update GRUB:

{% code lineNumbers="true" %}
```purebasic
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```
{% endcode %}

{% hint style="info" %}
**Note:**&#x20;

Your system will wait for the entire countdown before booting the default entry.
{% endhint %}

### <mark style="color:orange;">6. Black Screen or System Doesn’t Boot After Installing NVIDIA Drivers</mark>

This usually happens if the NVIDIA drivers are not installed correctly.

<mark style="color:green;">**Fix:**</mark>

* Disable Secure Boot in BIOS, as it blocks unsigned NVIDIA drivers from loading.
* After disabling Secure Boot, your system should boot normally.
* Remove the existing NVIDIA drivers and reinstall them correctly.

## Need Additional Help with Linux?

You can get help from these communities:

* Fedora Forums
* r/Linux4Noobs
* r/LinuxGaming
* r/Fedora
* [Asus Linux Discord](https://discord.gg/B8GftRW2Hd)
