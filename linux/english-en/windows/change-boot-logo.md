---
icon: rectangle-vertical-history
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

# Change Boot Logo

{% hint style="danger" %}
**Important:**\
If you mess up the installation, your system may become unbootable! This software comes with no warranty. Use at your own risk.

* Make sure that your computer is booting with UEFI (Very likely that you do)
* Make sure that BitLocker is disabled, or find your recovery key.
* Create a full backup or a rescue disk before making any changes to the Windows boot logo. The backup or rescue disc helps you restore Windows if something goes wrong and you are unable to boot.
{% endhint %}

## # First Time Installation

### Step 1: Download "HackBGRT"

To change the boot logo, we will use an open-source application called HackBGRT. Here’s how to use it.

1. Go to the [HackBGRT GitHub](https://github.com/Metabolix/HackBGRT/releases)
2. Download the **latest release ZIP file**.
3. Extract it to desktop/folder of your choice

### Step 2: Using HackBGRT

1. Open the extracted folder, right-click on the **setup.exe** file, and select the **Run as administrator**\
   \
   <img src="../.gitbook/assets/image (9).png" alt="" data-size="original">&#x20;
2. It will open the app in command-line tool. \
   \- **Press the i key** on your keyboard to proceed with a first time installation\
   \- **Press the B key** to boot to UEFI setup where you can disable Secure Boot\
   \
   Additional:\
   If you've set the boot logo already, and want to modify it, p**ress the F key** on your keyboard to modify the installation \
   &#x20;\
   <img src="../.gitbook/assets/image (10).png" alt="" data-size="original">
3. After you press a key, it will open the paint app

### Step 3: Setting the logo

{% hint style="info" %}
**Note:**

* You **cannot** set GIFs or transparent images as the new boot logo.
* Keep the background of the logo black as transparency is not supported. Therefore, the new logo doesn’t look out of place on the black background of the boot screen.
* The image should not be bigger than 300 x 300 pixels. While the size is not a strict requirement, it ensures that you will not face problems while setting the new boot logo.
{% endhint %}

1. In Paint, click on the **File** > **Import from Canvas** > **From file** option. Now, find the image you want to set as the new Windows boot logo, select it, and click on the **Open** button.
2. If you want, you can resize the image by clicking on the **Resize** button.
3. Once you are done, click **File** > **Save** to save the file. After saving, close the Paint application.
4. Press a key to exit the cmd window.

### Step 4: Rebooting / Secure Boot Instructions

Since Secure Boot only accepts trusted files during boot, HackBGRT comes with the _shim_ boot loader, a tool which allows you to manually select HackBGRT as a trusted program.&#x20;

After installing HackBGRT and rebooting your computer, **follow the instructions below** to complete the process.



1. After rebooting, you will find this screen.\
   \
   Select `OK`,  _Enter_.\
   ![](<../.gitbook/assets/image (11).png>)\

2.  Next, press a key quickly

    ```
    Shim UEFI key management
    Press any key to perform MOK management
    Booting in 5 seconds
    ```


3.  Select `Enroll hash from disk`, _Enter_.&#x20;

    ```
    Perform MOK management

    Continue to boot
    Enroll key from disk
    Enroll hash from disk
    ```


4.  Select the first disk, _Enter_. (**Don't select "MyAsus"**)

    ```
    Select Binary

    The Selected Binary will have its hash Enrolled
    This means it will subsequently Boot with no prompting
    Remember to make sure it is a genuine binary before enrolling its hash

    +----------------+
    | YOUR DISK NAME |
    +----------------+
    ```


5.  Select `EFI/`, _Enter_.

    ```
    +---------------+
    |     EFI/      |
    |    loader/    |
    | vmlinuz-linux |
    +---------------+
    ```


6.  Select `HackBGRT/`, _Enter_.

    ```
    +------------+
    |    ../     |
    |   Boot/    |
    | HackBGRT/  |
    | Microsoft/ |
    +------------+
    ```


7.  Select `grubx64.efi`, _Enter_.

    ```
    +-----------------+
    |       ../       |
    |   grubx64.efi   |
    |   loader.efi    |
    |    mmx64.efi    |
    | certificate.cer |
    |   splash.bmp    |
    |   config.txt    |
    +-----------------+
    ```


8.  Select `Continue`, _Enter_.

    ```
    [Enroll MOK]

    +------------+
    | View key 0 |
    |  Continue  |
    +------------+
    ```


9.  Select `Yes`, _Enter_.

    ```
    Enroll the key(s)?

    +-----+
    | No  |
    | Yes |
    +-----+
    ```


10. Select `Reboot`, _Enter_.

    ```
    Perform MOK management

    +-----------------------+
    |        Reboot         |
    | Enroll key from disk  |
    | Enroll hash from disk |
    +-----------------------+
    ```



You are now ready to boot! Congrats!

## # Modifying Installation

If you want to change the logo, rerun **setup.exe** as administrator and **press the F key** on your keyboard to modify the installation.

Remember to save the file in paint!

{% hint style="info" %}
**For troubleshooting purposes,** [**please refer here**](https://github.com/Metabolix/HackBGRT/tree/v2.5.2?tab=readme-ov-file#troubleshooting)
{% endhint %}

\
