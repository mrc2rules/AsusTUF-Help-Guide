# Asus TUF Linux Fixes & FAQ

1. Brightness Not Working in Hybrid or Eco Mode
(Works in Ultimate / dGPU-only mode)

Fix: You need to modify the GRUB settings.

Open a terminal and run:

`sudo nano /etc/default/grub`

Find this line:
GRUB_CMDLINE_LINUX="`rhgb quiet`"

Replace it with:
GRUB_CMDLINE_LINUX="`rhgb quiet pcie_aspm=force acpi_backlight=native`"

Then update GRUB by running:

`grub2-mkconfig -o /boot/grub2/grub.cfg`

Finally, reboot your system.

*Note: This method works on other distributions as well. On those, you may need to add the parameters to the line starting with GRUB_CMDLINE_LINUX_DEFAULT instead.*



2. Apps Not Using Dedicated GPU (dGPU) While Set to Hybrid Mode
(Mostly occurs on Arch-based distros; not for Fedora)

Fix: Install and enable switcheroo-control.

Run:

`yay -S switcheroo-control`

Then enable and start the service:

`sudo systemctl enable switcheroo-control`

`sudo systemctl start switcheroo-control`

After that, right-click on the application. If you see an option to run it with the dedicated GPU, it means Switcheroo is installed and enabled

{% hint style="info" %}
Note: This service manages GPU switching, allowing apps to use the dedicated GPU on demand.
{% endhint %}

3. Battery Drains Fast

Fix: Install auto-cpufreq to manage CPU frequency and boost automatically.

Run these commands:

`git clone https://github.com/AdnanHodzic/auto-cpufreq.git`

`cd auto-cpufreq`

`sudo ./auto-cpufreq`

Follow the prompts and select Install to enable the daemon.

Then enable and start the service:

`sudo systemctl enable auto-cpufreq`

`sudo systemctl start auto-cpufreq`


{% hint style="info" %}
Note: This tool automatically manages CPU performance and power saving, so you don't need to tweak CPU settings manually.
{% endhint %}


4. Some Keys Like Fn+F5, Fn+F4, or Armoury Crate Key Don’t Work

This is expected behavior as these keys are not fully supported yet.
Check the post-install guide for steps to enable these keys.

5. How to Change GRUB Timeout

Open the GRUB configuration file:

`sudo nano /etc/default/grub`

Find the line:
GRUB_TIMEOUT=`5`

Change the number to your preferred timeout in seconds (try to keep it below 60).

Then update GRUB:

`sudo grub2-mkconfig -o /boot/grub2/grub.cfg`

{% hint style="info" %}
Note: Your system will wait for the entire countdown before booting the default entry.
{% endhint %}


6. Black Screen or System Doesn’t Boot After Installing NVIDIA Drivers

This usually happens if the NVIDIA drivers are not installed correctly.

Fix:
- Disable Secure Boot in BIOS, as it blocks unsigned NVIDIA drivers from loading.
- After disabling Secure Boot, your system should boot normally.
- Remove the existing NVIDIA drivers and reinstall them correctly.


7. Need Help with Linux?

You can get help from these communities:
- Fedora Forums
- r/Linux4Noobs
- r/LinuxGaming
- r/Fedora
- [Asus Linux Discord](https://discord.gg/B8GftRW2Hd)


