### Asus Tuf Linux Fixes & FAQ

1. Brightness not working in Hybrid or Eco mode.(But,works in ultimate/dgpu only mode)
Fix: You need to change Grub settings.

Open terminal and type:
`sudo nano /etc/default/grub`

Find this line:
`GRUB_CMDLINE_LINUX="rhgb quiet"`

Replace it with:
`GRUB_CMDLINE_LINUX="rhgb quiet pcie_aspm=force acpi_backlight=native"`

Then update GRUB with:
`grub2-mkconfig -o /boot/grub2/grub.cfg`

Now reboot your system.

**Note:This works on other distros as well, but on those distros you need to add the line to GRUB_CMDLINE_LINUX_DEFAULT instead.**


## 2. Apps not using dgpu while the gpu is set to hybrid.
(This mostly happens on Arch-based distros) **(Not for fedora)**

Fix: Install `switcheroo-control`.

Run:
`yay -S switcheroo-control`

Then enable and start it:
`sudo systemctl enable switcheroo-control`
`sudo systemctl start switcheroo-control`

After that, right-click on an app. If you see an option to run it with dedicated graphics, it should work fine.


## 3. Battery drains fast.
Fix: Install `auto-cpufreq`.

Run these commands:
`git clone https://github.com/AdnanHodzic/auto-cpufreq.git`
`cd auto-cpufreq`
`sudo ./auto-cpufreq`

Follow the prompts and install the daemon by clicking "Install" in the app.

Then run:
`sudo systemctl enable auto-cpufreq`
`sudo systemctl start auto-cpufreq`

***It manages CPU boost automatically, so you don’t need to do it manually.***


## 4. Some keys like Fn+F5, Fn+F4, or Armory Crate key don’t work
This is normal and expected behavior. These keys aren’t fully supported.
Check the post-install guide,it contains the steps to get them working again.


## 5.Steps to Change Grub timeout
Open the Grub config:
`sudo nano /etc/default/grub`

Look for this line:
`GRUB_TIMEOUT=5`

Change the number to how many seconds you want the menu to show. (Try to keep it under 60.)

Then update Grub:
`sudo grub2-mkconfig -o /boot/grub2/grub.cfg`

***Note: Your system will wait for the full countdown before booting.***


## 6.Black screen or system doesn’t boot after installing NVIDIA drivers

This can happens if the Nvidia drivers aren’t installed properly.
You can try disabling Secure Boot in the Bios. Secure Boot prevents unsigned Nvidia drivers from loading.
After disabling it, the system should boot normally.
Then, remove the drivers and reinstall them correctly.


## 7. Need help with Linux?
You can ask for help on these places:
- Fedora Forums
- r/Linux4Noobs
- r/LinuxGaming
- r/Fedora
- [Asus Linux Discord:](https://discord.gg/B8GftRW2Hd)
