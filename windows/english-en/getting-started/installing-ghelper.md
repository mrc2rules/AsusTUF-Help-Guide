---
icon: g
cover: ../.gitbook/assets/241183841-4d98465a-63a5-4498-ae14-afb3e67e7e82.png
coverY: 0
---

# Installing GHelper

## **What is GHelper?**

GHelper is an open-source, minimalistic and lightweight alternative to Armoury Crate for managing performance, fan curves, power&#x20;settings and more, on your TUF laptop.

Unlike AC, which is buggy, bloated and RAM-heavy, GHelper runs with minimal impact on system performance. It has&#x20;all the features of Armoury Crate, BUT with a much cleaner UI. It's completely safe, free to&#x20;use and supports all major Asus models.

For more information, [click to visit the website.](https://g-helper.com/)

## **Steps + How do I uninstall AC?**

1\. [Click this link](https://dlcdnets.asus.com/pub/ASUS/mb/14Utilities/Armoury_Crate_Uninstall_Tool.zip?model=Armoury%20Crate) to&#x20;download the Armoury Crate uninstaller.\
2\. Run it and proceed.\
3\. Then [download GHelper from this link](https://github.com/seerge/g-helper/releases/latest). Extract the `.zip` file and run it.\
5\. Inside GHelper, at the very bottom left, check the box _<mark style="color:yellow;">**Run at startup**</mark>_\
6\. Inside GHelper, go to _<mark style="color:yellow;">**Extra -> Other -> Stop Asus Services**</mark>_\
&#x37;_**.**_ Finally, open <mark style="color:yellow;">**Task manager -> Startup Apps**</mark> and disable `ASUS Smart Display Control`

{% hint style="info" %}
Note:&#x20;

Make sure to extract GHelper/AC uninstaller from the zip file before running it. If the uninstaller fails, rerun it.
{% endhint %}

<details>

<summary>GHelper Frequently Asked Questions</summary>

### How do I stop the Armoury Crate install popup appearing every time I press the M4 / ROG key?

Stop all asus services from `Extra` -> `Stop services`. Or stop `ArmouryCrateControlInterface` under windows Services app

### How does GHelper control my fan speeds?

**It doesn't and can't control your fans**. Firmware / BIOS controls them in real-time. Armoury also doesn't control fans in real time anyhow.

What G-helper can do - is (optionally) set a custom fan profile to the current performance mode via the same endpoint Armoury uses in Manual mode.

How it will be interpreted - is still up to the firmware. If you don't like how firmware controls fans, you can try [Experimental build with a manual fan control](https://github.com/seerge/g-helper/discussions/2272)

### Backlight doesn't change color or stays blue

In newest models Windows itself can also control lightning. Make sure to go to `Windows Settings` -> `Personalization` -> `Dynamic Lightning` and turn it off there.

If you have white-only backlight and you can't change backlight mode, try to set color to pure RED

### Battery charge limiter is not working

It could be that Asus services are overwriting this limit after. You can stop them from `Extra` settings by clicking `Stop` button. Some models support only 80% limit, so try to set exactly **80%** to be sure.

After restart, BIOS resets all settings to defaults, including charge limit. As soon as you log in and G-Helper starts it would apply charge limit again. Before app starting - your laptop may keep charging. This is normal and this is how things are.

### How do Visual Modes and Color Gamuts work

Visual Modes and Color Gamuts are handled by `AsusSplendid.exe` (part of Asus System Control Interface package) that G-Helper runs under the hood. If Visual Modes or Color Gamuts don't seem to work - you can try to manually delete `C:\ProgramData\ASUS\GameVisual` folder containing color profiles. Then restart G-Helper so it can spot missing profiles and offer you to download them again.

### I have problems turning on Eco mode or adjusting brightness

There is a known issue with Nvidia drivers, that don't act correctly if you shutdown/restart your laptop with GPU being disable (i.e in Eco or Optimized mode on battery). To [prevent this from happening](https://github.com/seerge/g-helper/discussions/1042) you can select `Enable GPU on shutdown` under `Extra` settings.

### Why is Ultimate GPU mode not available on my laptop?

Ultimate mode is supported (by hardware) only on 2022+ models

### Should I apply custom power limits (PPT) and fan curves?

You don't have to, it's purely optional. From my experience built in (in BIOS) performance modes work well. Limit your power or apply custom fan curves only if you have issues. As soon as you click Apply in the `Fans + Power` section BIOS will consider your fan curve as "custom"! (no matter if you modified it or not)

### How do I change fan % to fan RPM?

Click on them

### When I try to apply a custom fan curve I get "BIOS rejected fan curve"

TUF models from 2021 and older don't support custom fan curves at all. Most probably you didn't have them in the Armoury as well?

### I don't see a GPU temperature in G-helper

Most probably either you are using Eco / Optimized mode and your dGPU is simply off, or your windows has put the dGPU into sleep to preserve power.

### I don't see app after starting it

Please check the system tray for a `(G)` icon. By default Windows is keen to hide all icons, so you may need to click `^` to see them all. I would advise to right click on Taskbar select TaskBar Settings -> Other System Tray icons -> Mark G-Helper to be always ON.

### App crashes or doesn't work properly

Open "Event Viewer" from the start menu, go to Windows Logs -> Application and check for recent Errors mentioning G-Helper. If you see one - please post a [new issue](https://github.com/seerge/g-helper/issues) with all details from this error.

### Can I use the MyASUS app along with G-Helper?

You can, the only problem is that MyASUS may override the battery charge limit that you set before. My advice in such a situation would be to set the same limit (i.e. 80%) in both MyASUS and G-Helper.

### What services can be stopped from the Extra settings?

* ArmouryCrateControlInterface
* AsHidService
* ASUSOptimization
* AsusAppService
* ASUSLinkNear
* ASUSLinkRemote
* ASUSSoftwareManager
* ASUSLiveUpdateAgent
* ASUSSwitch
* ASUSSystemAnalysis
* ASUSSystemDiagnosis
* AsusCertService

### How do I set Mute Microphone to M3?

If you have the Asus Optimization Service running, it's controlled by that service (therefore G-helper doesn't interfere and doesn't touch this function). Alternatively you can stop that service - and you can bind M3 to anything you want.

### How do I disable Win key?

Press `FN + WIN`

### My display colors seem OFF even if I set Visual Mode to `Default`

Make sure to turn off windows setting `System -> Display -> Advanced Display -> Automatically Manage Color for Apps`

### Windows Defender or any other antivirus marks app as malware / virus

False positives from Windows Defender (or any other similar system that uses machine learning for detection) is possible as the application is not digitally signed with a certificate. You can always download a version below or compile the app by yourself.

All application sources are open and can be monitored from A to Z. Application is assembled directly on GitHub from this sources using GitHub actions.

### Where can I find app settings or logs ?

You can find them under the `%AppData%\GHelper` folder. Please include them when posting a new bug-report or issue.

### App refuses to run on startup or runs without any icon in tray on startup

Open the app, and uncheck and check again "run on startup". If it still doesn't help (for some reason), you can try to manually edit the "GHelper" task in Windows Task Scheduler, and add a couple of seconds delay to start.

### How do I uninstall G-helper?

G-helper is a single exe, and it doesn't install anything in the system. To remove it - you can simply delete exe :) If you have applied any custom fan profiles or PPTs - before removing I would recommend selecting your favorite performance mode (for example balanced) and clicking "Factory defaults" under Fans + Power.

### Can I undervolt my CPU ?

Currently you can undervolt AMD CPUs. If your model supports that - you will see an undervolting slider under `Fans+Power -> Advanced`. If you don't see a slider there, it means your CPU doesn't support undervolting. Full list of models that support that [can be found here](https://github.com/seerge/g-helper/discussions/736)

### I have uninstalled Armoury and my GPU performance is lower than it was

Check your NVidia Experience settings and make sure that you have **Whisper Mode** set to `OFF`. Also you can go to reset all settings `Nvidia Control panel -> Manage 3D Settings -> Reset to defaults`



</details>
