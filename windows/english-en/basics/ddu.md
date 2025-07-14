---
icon: microchip
cover: ../.gitbook/assets/7.png
coverY: 0
---

# Display Driver Uninstaller Guide (DDU)

This guide shows you how to completely remove your GPU drivers and reinstall it. Reinstalling GPU drivers will ensure a clean driver install and resolve any potential issues.

**Reasons why you might need to do this:**

* If you're having crashes/black-screen or artifacts/glitches on your screen.\
  \
  These issues could be caused by a faulty/corrupted GPU driver. Your laptop has 2 GPUs.\
  — An **iGPU** (integrated in the processor) _<mark style="color:blue;">eg: Intel UHD/Iris graphics, AMD Radeon xxxM graphics</mark>_\
  — A **dGPU** (dedicated graphics card) _<mark style="color:green;">eg: Nvidia RTX/GTX series, AMD Radeon RX series</mark>_\

* If you're having issues in **Standard/Eco/Optimized** modes, <mark style="color:yellow;">reinstall the iGPU driver</mark>.\
  If you're having issues in **Ultimate** mode or **while playing games**, <mark style="color:yellow;">reinstall the dGPU driver</mark>.\


{% hint style="danger" %}
**BEFORE YOU START**

If you are reinstalling **dGPU drivers, switch to standard mode on GHelper/Armoury Crate**\
If you are reinstalling **iGPU drivers, switch to ultimate mode on GHelper/Armoury Crate**,

If you don't do this, you'll get a black screen after deleting the driver, requiring you to connect an external display to your laptop via the port that connects to your other functioning GPU.
{% endhint %}

## # Steps

{% stepper %}
{% step %}
### Download official drivers

Download the newest drivers for your GPU from the manufacturer's website.&#x20;

{% hint style="warning" %}
**DO NOT install or run them yet**
{% endhint %}

Nvidia: [https://www.nvidia.com/en-us/drivers/](https://www.nvidia.com/en-us/drivers/) \
AMD: [https://www.amd.com/en/support/download/drivers.html](https://www.amd.com/en/support/download/drivers.html)&#x20;

Save the driver installer on your desktop for easier access later. Preferably you'd want to have the latest driver because it will work best, especially with newer games as manufacturers often release bug fixes for them.
{% endstep %}

{% step %}
### Install DDU

This software will completely uninstall everything related to your driver without leaving any trace of it, allowing you to fresh install new drivers.

&#x20;[https://www.wagnardsoft.com/forums/viewtopic.php?t=5092](https://www.wagnardsoft.com/forums/viewtopic.php?t=5092)&#x20;

Portable mode is easier,  just extract it to an empty folder on your desktop.
{% endstep %}

{% step %}
### Preparing for DDU

1. Remove your internet connection completely (WiFi or ethernet). This prevents Windows from auto installing a GPU driver by itself through Windows Updates.
2. Open DDU, then on the top left open the `Options` menu,&#x20;
3. Tick the `Enable Safe Mode dialog` option, it is the second to last option.&#x20;
4. Reopen DDU, it should give you a `launch option` menu. Click the launch option drop-down box menu and select `Safe mode`
5. Your laptop will now restart and boot into safe mode. This is necessary to isolate any potential conflicts
6. DDU should open automatically after the restart, if it doesn't, run it manually.
{% endstep %}

{% step %}
### Using DDU

1. Once you're in DDU, there should be 2 drop-down menus on the right side, \
   `-Select device type-` and `-Select device-`\
   \
   Under the first menu, **select the GPU option**\
   Under the second one, **select the GPU driver you want to uninstall.**&#x20;
2. Then press `clean and restart`, wait until it automatically restarts.&#x20;
3. Once it restarts, install the GPU driver you downloaded earlier, after it finishes the installation, restart your laptop and re enable the internet.
{% endstep %}
{% endstepper %}

_Adapted from @yamen76 's guide on AsusTUF discord_



