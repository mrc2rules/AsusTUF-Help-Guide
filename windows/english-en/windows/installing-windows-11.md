---
description: 'Note: This is a clean-install'
icon: arrows-rotate-reverse
cover: ../.gitbook/assets/9.png
coverY: 0
---

# Installing Windows 11

{% hint style="danger" %}
**Caution**

All files on the drive you plan to install Windows to will be **deleted** if you follow this guide - this is intended. Please ensure you have an adequate [backup policy](https://rtech.support/backups) in place before proceeding if you have files of value.
{% endhint %}

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

* An internet connection.
* A working computer to run the Windows Media Creation Tool.
* A USB flash drive that is at least 8GB or greater.

## # Steps

{% stepper %}
{% step %}
### Creating installation media <a href="#creating-installation-media" id="creating-installation-media"></a>

There are two ways you can use to create an installation media. If you're new to this, you should probably use MCT (Media Creation Tool).&#x20;

Rufus is another choice for advanced users with a lot more configurable options for your installation.

Ventoy is also a choice for advanced users who want to manage all their ISOs into one singular drive.

{% tabs %}
{% tab title="Microsoft Media Creation Tool" %}
1. Create a bootable USB flash drive using the [Create Windows 11 Installation Media download](https://www.microsoft.com/en-us/software-download/windows11) from Microsoft. It can be found under the headline “Create Windows 11 Installation Media”

{% hint style="warning" %}
**Warning**

Save MCT to Desktop or Downloads folder. MCT must be saved and run from outside the USB flash drive. Just moving an ISO file to the USB flash drive will not make it bootable.
{% endhint %}

2. Run MCT by double clicking it. You will be greeted with Windows Terms Of Service. Press Accept.
3. Keep this as default, press next.

<div align="left"><figure><img src="../.gitbook/assets/image (28).png" alt="" width="375"><figcaption></figcaption></figure></div>

4. Select create installation media for another PC, and then click next.

<div align="left"><figure><img src="../.gitbook/assets/image (33).png" alt="" width="375"><figcaption></figcaption></figure></div>

4. Select USB flash drive, then press next.

<div align="left"><figure><img src="../.gitbook/assets/image (29).png" alt="" width="375"><figcaption></figcaption></figure></div>

6\. Select the USB you want to use, press next.

{% hint style="danger" %}
**Caution**


This step will wipe the selected USB Flash drive, so ensure you have nothing important on the USB drive, and back up all important documents.
{% endhint %}

<div align="left"><figure><img src="../.gitbook/assets/image (30).png" alt="" width="375"><figcaption></figcaption></figure></div>

7\. Wait until MCT finish its job. this may take some time.

<div align="left"><figure><img src="../.gitbook/assets/image (32).png" alt="" width="375"><figcaption></figcaption></figure></div>

8. After MCT finishes, shutdown your PC.
{% endtab %}

{% tab title=" Rufus" %}
1. Download the [Windows Multi Edition ISO from here](https://www.microsoft.com/en-us/software-download/windows11)
2. Download and run [Rufus](https://rufus.ie/).
3. If you have multiple drives inserted, select the one you desire.
3. Select `ISO Image` and then browse for the Windows ISO image. It should then look like this:
<div align="left"><figure><img src="../.gitbook/assets/rufus_win_main.png" alt="" width="375"><figcaption></figcaption></figure></div>
5. Select the Partition scheme (GPT/MBR) depending on your motherboard’s capabilities.
6. Click `Start`. You will now see a couple of options. If you don't know what they do, leave them as is.
<div align="left"><figure><img src="../.gitbook/assets/rufus_win_options.png" alt="" width="375"><figcaption></figcaption></figure></div>
7. Eject the USB flash drive and then restart. You should now be able to boot into your newly flashed drive!
{% endtab %}

{% tab title=" Ventoy" %}

{% hint style="danger" %}
**Caution**

While Ventoy does support secure boot, there is a chance that it wont work for other ISOs. For this, you will have to refer to their [troubleshooting guide](https://www.ventoy.net/en/doc_secure.html). If you don't want to enroll the MOK keys, simply turn off Secure Boot.

{% endhint %}

1. Download the [Windows Multi Edition ISO from here](https://www.microsoft.com/en-us/software-download/windows11)
2. Download the .zip of [Ventoy](https://www.ventoy.net/en/download.html) and extract it
3. Run the `Ventoy2Disk.exe` program
3. Select your drive and press `Install`. It should look like this.
<div align="left"><figure><img src="../.gitbook/assets/ventoy_before_flash.png" alt="" width="337"><figcaption></figcaption></figure></div>
4. After flash, the right box should have the same numbers as the one in the left.
<div align="left"><figure><img src="../.gitbook/assets/ventoy_after_flash.png" alt="" width="337"><figcaption></figcaption></figure></div>
5. Then copy the Windows ISO to the root of VENTOY, not VTOYEFI!
<div align="left"><figure><img src="../.gitbook/assets/ventoy_drives.png" alt="" width="437"><figcaption></figcaption></figure></div>
6. Restart your computer and boot into Ventoy. If successful, Windows (and other ISOs you have copied to) should appear here!
<div align="left"><figure><img src="../.gitbook/assets/ventoy_uefi.png" alt="" width="475"><figcaption></figcaption></figure></div>

{% endtab %}
{% endtabs %}
{% endstep %}

{% step %}
### Boot into your USB <a href="#creating-installation-media" id="creating-installation-media"></a>

Plug in the Windows USB installer and spam `Esc` when booting the laptop.&#x20;

Change the BIOS boot order to have USB media as the first priority (this can usually be found under the boot tab) or simply look for the words “boot menu” when you see your BIOS boot screen. Press the corresponding function key and choose the USB flash drive to boot from it.
{% endstep %}

{% step %}
### Installing Windows <a href="#creating-installation-media" id="creating-installation-media"></a>

1. Click “Install now”

{% hint style="warning" %}
**Warning**

If you do not see an installer like the below screenshot, click next twice, then click “Previous version of Setup” near the bottom left corner of the installer window.
{% endhint %}

<div align="left"><figure><img src="../.gitbook/assets/image (34).png" alt="" width="375"><figcaption></figcaption></figure></div>

2. Continue on until you hit the license key screen. Here you can either enter your license code, or if Windows has been installed to this computer before, click on the `I don't have a product key` link.

<div align="left"><figure><img src="../.gitbook/assets/image (35).png" alt="" width="375"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (36).png" alt="" width="375"><figcaption></figcaption></figure></div>

3. Continue on until you reach the “Which type of installation do you want?” screen. Click “Custom”.

<div align="left"><figure><img src="../.gitbook/assets/image (37).png" alt="" width="375"><figcaption></figcaption></figure></div>

4. Select the largest "primary" partition (should be at least 500GB). Click format. _**Make sure you have the right one selected.**_ At this point click `Next`&#x20;

{% hint style="danger" %}
**Caution**
\
Do not delete any partitions, especially the smaller ones. They contain OEM image
{% endhint %}



5. After formatting completes, click on the same "primary partition" again, then continue.&#x20;
6. Windows will now install. When it finishes it will automatically restart your machine, when your screen goes black pull out your installation USB drive.

{% hint style="success" %}
**Congratulations!**

You have successfully installed Windows 11. Once the computer has rebooted, you will be greeted with the Out-of-the-Box Experience and you can start setting up your new installation of Windows.
{% endhint %}
{% endstep %}

{% step %}
### Windows OOBE (Out Of the Box Experience)

The laptop will boot into the OOBE setup. Please proceed according to the steps.&#x20;

You may or may not have WiFi at this stage. If so, please use an ethernet cable
{% endstep %}

{% step %}
### Base Windows Setup

* **Windows Updates**\
  Open Windows Updates and update everything. Reboot when needed. Repeat until updates are gone.\
  \
  If updates are "stuck," click `pause updates` then `resume updates` and repeat above steps.\

* **Graphics Driver Updates**\
  Open the '[NVIDIA](https://www.nvidia.com/en-us/software/nvidia-app/)' and '[AMD Adrenalin](https://www.amd.com/en/products/software/adrenalin.html)' app to update your graphics drivers. This is crucial for optimal performance. Avoid updating **graphics drivers** from Windows Update/GHelper as they can be pretty old.\
  \
  Additionally, install GHelper and make sure Armoury Crate is not installed. Don't know what GHelper is or how to install?\
  [Click here for the tutorial](../getting-started/installing-ghelper.md) - [installing-ghelper.md](../getting-started/installing-ghelper.md "mention")



* **Windows Store Updates**\
  Open Microsoft Store -> click library on bottom left -> update everything.\
  Uninstall any apps you don't want. _**Don't uninstall Realtek Audio Console or Dolby Access**_
{% endstep %}
{% endstepper %}
