---
icon: broom-wide
cover: ../.gitbook/assets/10.png
coverY: 0
---

# Debloating Windows

## What is bloatware?

Bloatware refers to pre-installed or unnecessary software that offers little value and often slows down your system.&#x20;

Manufacturers include these apps to promote their services or generate revenue, but they usually consume memory, storage, and battery life.

## Why Remove Bloatware?

1. Improves performance by reducing background processes.
2. Frees up storage.
3. Extends battery life.
4. Reduces security risks from outdated or unused apps.

## Steps

{% stepper %}
{% step %}
### Clean Install (Alternative Option)

If possible, perform a clean installation of Windows. It’s the most effective way to remove pre-installed junk. It resets your system and wipes out all manufacturer bloat.

**For instructions on how to perform a clean install, refer to the** [installing-windows-11.md](installing-windows-11.md "mention") **guide.**
{% endstep %}

{% step %}
### Remove pre-installed applications

This guide will be using the Windows debloat script by [Win11Debloat by Raphire](https://github.com/Raphire/Win11Debloat).

It can remove pre-installed bloatware apps, disable telemetry, remove intrusive interface elements and much more. To see a list of what's removed by default, [click here](https://github.com/Raphire/Win11Debloat#default-settings).\


1. Open PowerShell as Administrator.
2.  Paste and run the following command:

    ```powershell
    & ([scriptblock]::Create((irm "https://debloat.raphi.re/")))
    ```
3. Wait for the script to download **Win11Debloat**.
4. Follow the on-screen instructions carefully.
5. Select the default preset _`1`_ and press `Enter`.
6. It will show a list of changes it will make. To confirm, press `Enter` again and let it run.

![Win11Debloat](https://github.com/user-attachments/assets/010dd837-cc12-4b3e-953b-2be66e8dfd4c)

{% hint style="info" %}
The tool creates a system restore point by default, so if anything goes wrong, you can revert the changes.
{% endhint %}

Once it finishes:

* Go to _**Settings > Apps > Installed Apps**_.
* Review the list and manually uninstall any remaining unwanted apps.
{% endstep %}

{% step %}
### Uninstall 3rd-party antivirus software

_**But wait, don’t I need an antivirus?**_\
No, not anymore. \
In 2025, you don’t need 3rd-party antivirus software, especially not McAfee or Norton. They slow down systems, sell user data, and provide subpar protection.\
\
**Windows Security (Windows Defender)** comes pre-installed with Windows. It's lightweight, effective, and more than enough for most users. As long as you avoid sketchy downloads and use common sense online, you're covered.

To remove them, use these official removal tools:

* [McAfee MCPR Tool](https://download.mcafee.com/molbin/iss-loc/SupportTools/MCPR/MCPR.exe)
* [Norton Removal Tool](https://norton.com/nrnr)
{% endstep %}

{% step %}
### Disabling Unnecessary Services (Advanced Tweaks)

We’ll use the **CTT Tool** ([Chris Titus Tech's Windows Utility](https://github.com/ChrisTitusTech/winutil)), which provides a clean GUI for installing apps, disabling services, and applying tweaks.

{% hint style="warning" %}
**Warning:**&#x20;

To avoid interference, the CTT tool temporarily disables Defender after all the tweaks have been successfully applied.\
**Make sure to turn Defender back on manually** by going to:\
**Defender > Virus & threat protection.**
{% endhint %}

**Steps:**

1. Open PowerShell or Terminal as Administrator.
2.  Paste and run the following command:

    ```powershell
    iwr -useb https://christitus.com/win | iex
    ```
3. Wait for it to download and launch the tool.&#x20;
4. **Open Tweaks Tab**: Navigate to the ‘Tweaks’ tab in the application.

<figure><img src="https://github.com/user-attachments/assets/43f3c35b-eff6-4d5b-a036-095601622aca" alt=""><figcaption></figcaption></figure>

4. **Select Tweaks**: Choose the tweaks you want to apply. You can use the presets available at the top for convenience.
5. **Run Tweaks**: After selecting the desired tweaks, click the ‘Run Tweaks’ button at the bottom of the screen.
6. Reboot your system when done.
{% endstep %}
{% endstepper %}
