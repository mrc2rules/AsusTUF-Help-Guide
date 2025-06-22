### Asus Tuf Linux Fixes & FAQ

## 1. Brightness not working in Hybrid or Eco mode (But works in ultimate mode)

Fix: Adjust Grub configurations

Open terminal and type:
`sudo nano /etc/default/grub`

Find this line:
`GRUB_CMDLINE_LINUX="rhgb quiet"`

Replace it with:
`GRUB_CMDLINE_LINUX="rhgb quiet pcie_aspm=force acpi_backlight=native"`

Then update GRUB with:
`grub2-mkconfig -o /boot/grub2/grub.cfg`

Now reboot your system.

**Note: You may need to add the line to GRUB_CMDLINE_LINUX_DEFAULT instead for certain distros.**

## 2. Apps are not using dGPU while the GPU mode is set to hybrid

Note: This mostly happens on Arch-based distros **(Not for fedora)**

Fix: Install `switcheroo-control`

Run:
`yay -S switcheroo-control`

Then enable and start it:
`sudo systemctl enable switcheroo-control`
`sudo systemctl start switcheroo-control`

After that, right-click on an app. The app should now run on dGPU if the option to run it with dedicated graphics was selected.

## 3. Fast battery drainage

Fix: Install `auto-cpufreq`

Run these commands:
`git clone https://github.com/AdnanHodzic/auto-cpufreq.git`
`cd auto-cpufreq`
`sudo ./auto-cpufreq`

Follow the prompts and install the daemon by clicking "Install" in the app.

Then run:
`sudo systemctl enable auto-cpufreq`
`sudo systemctl start auto-cpufreq`

***Note: `auto-cpufreq` manages CPU boost automatically.***

## 4. Some keys like Fn+F5, Fn+F4, or Armoury Crate key (M4) don’t work

This is normal and expected behavior. Certain keys aren’t fully supported.
Check the post-install guide, it contains the steps to get them working again.

## 5. Steps to change Grub timeout

Open the Grub config:
`sudo nano /etc/default/grub`

Look for this line:
`GRUB_TIMEOUT=5`

Change the number to how long in seconds you want the menu to show (It's suggested to keep the value under 60 seconds).

Then update Grub:
`sudo grub2-mkconfig -o /boot/grub2/grub.cfg`

***Note: Your system will wait for the full countdown before booting.***

## 6. Black screen or system doesn’t boot after installing NVIDIA drivers

This can happen if NVIDIA drivers aren’t installed properly.
You can try disabling Secure Boot in the BIOS. Secure Boot prevents unsigned NVIDIA drivers from loading.
After disabling it, the system should boot normally.
Then, remove the drivers and reinstall them correctly.

## 7. Need some more help with Linux?

You can ask for more help here:
- Fedora Forums
- r/Linux4Noobs
- r/LinuxGaming
- r/Fedora
- [Asus Linux Discord](https://discord.gg/B8GftRW2Hd)
