---
hidden: true
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

# What is Bloatware and Why You Should Remove It

Bloatware refers to pre-installed or unnecessary software that offers little value and often slows down your system. Manufacturers include these apps to promote services or generate revenue, but they usually consume memory, storage, and battery life.
  
  ## Why Remove Bloatware?
  1. Improves performance by reducing background processes.
  2. Frees up storage.
  3. Extends battery life.
  4. Reduces security risks from outdated or unused apps.



## Q: Don’t I Need an Antivirus?

No, not anymore.
In 2025, you don’t need third-party antivirus software, especially not McAfee or Norton. They’re known for slowing down systems, selling user data, and providing subpar protection.
Windows Security (Windows Defender) comes pre-installed with Windows. It's lightweight, effective, and more than enough for most users. As long as you avoid sketchy downloads and use common sense online, you're covered.

{% hint style="info" %}

Even though the tools used in this guide are safe and reputable, proceed with caution. We are not responsible for any changes you make to your system. All tools recommended below are open-source and well-maintained.

{% endhint %}


# How to Remove Bloatware
## 1) Clean Install (Recommended)

If possible, perform a clean installation of Windows. It’s the most effective way to remove pre-installed junk. It resets your system and wipes out all manufacturer bloat.

***For instructions on how to perform a clean install, refer to the Clean Install Guide.***

## 2) Removing Unnecessary Apps

We recommend using the Windows Debloat script by [Raphire](https://github.com/Raphire/Win11Debloat).

It automatically scans for and removes Microsoft’s pre installed bloatware.

**Steps:**

1. Open PowerShell or Terminal (preferably as Administrator).  

2. Paste and run the following command:


`& ([scriptblock]::Create((irm "https://debloat.raphi.re/")))`


3. Wait for the script to download **Win11Debloat**.  

4. Follow the on-screen instructions carefully.  

5. Select the default preset *`1`* and press Enter.  

6. It will show a list of changes it will make. To confirm, press Enter again and let it run.
  
![Win11Debloat](https://github.com/user-attachments/assets/010dd837-cc12-4b3e-953b-2be66e8dfd4c)



{% hint style="info" %}
The tool creates a system restore point by default, so if anything goes wrong, you can revert the changes.
{% endhint %}


Once it finishes:
- Go to ***Settings > Apps > Installed Apps***.

- Review the list and manually uninstall any remaining unwanted apps.

{% hint style="warning" %}

For antivirus software (McAfee, Norton) or tools like Armoury Crate, use official removal tools:
- McAfee MCPR Tool  
- Norton Removal Tool  
- Armoury Crate Uninstaller (For instructions on how to remove Armoury Crate and install G-Helper, refer to "Installing G-Helper.")
These apps are deeply integrated, and uninstalling them from Settings will leave behind files and services.

{% endhint %}

## 3) Disabling Unnecessary Services (Advanced Tweaks)

We’ll use the **CTT Tool** (Chris Titus Tech's Windows Utility), which provides a clean GUI for installing apps, disabling services, and applying tweaks.

**Steps:**

{% hint style="warning" %}

Warning: To avoid interference, the CTT tool temporarily disables Defender after all the tweaks have been successfully applied.  
**Make sure to turn Defender back on manually** by going to:  
**Defender > Virus & threat protection.**

{% endhint %}

1. Open PowerShell or Terminal as Administrator.  

2. Run this command:

`iwr -useb https://christitus.com/win | iex`

3. Wait for it to download and launch the tool.

**Features:**

- From the main screen, you can install apps using Winget.
- Click the apps you want and then select **"Install/Upgrade Applications"**.

![Ctt tool 1](https://github.com/user-attachments/assets/372c37a0-1958-4c65-b291-e7b6548f3d5f)

{% hint style="info" %}

Tweaks can only be applied after all app installations are completed.

{% endhint %}

4. Navigate to the **Tweaks** section. Select the same settings shown in the image below.
![Ctt tool 2](https://github.com/user-attachments/assets/43f3c35b-eff6-4d5b-a036-095601622aca)

  

5. Click **"Run Tweaks"** and wait for it to finish.  


6. Reboot your system when done.
