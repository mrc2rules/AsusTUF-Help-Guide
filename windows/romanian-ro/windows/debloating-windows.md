---
icon: broom-wide
cover: ../.gitbook/assets/10.png
coverY: 0
---

# Debloating pentru Windows

## What is bloatware?

"Bloatware" se referă la software preinstalat sau inutil, care oferă o valoare redusă și adesea încetinește sistemul.&#x20;

Producătorii includ aceste aplicații pentru a-și promova serviciile sau pentru a genera venituri, dar de obicei consumă memorie, spațiu de stocare și autonomia bateriei.

## De ce trebuie să șterg Bloatware?

1. Îmbunătățește performanța prin reducerea proceselor în fundal.
2. Eliberează spațiu de stocare.
3. Prelungește durata de viață a bateriei.
4. Reduce riscurile de securitate generate de aplicațiile învechite sau neutilizate.

## Pași de dezinstalare

{% stepper %}
{% step %}
### Instalare curată (opțiune alternativă)

Dacă este posibil, efectuează o reinstalare curată de Windows. Este cea mai eficientă metodă de a elimina fișierele nedorite preinstalate. Resetează sistemul și elimină toate fișierele preinstalate de la producător.

**FPentru instrucțiuni despre cum să efectuați o instalare curată, consultați ghidul pentru** [installing-windows-11.md](installing-windows-11.md "mention")
{% endstep %}

{% step %}
### Eliminarea aplicațiilor preinstalate

Acest ghid va folosi scriptul pentru debloat [Win11Debloat de Raphire](https://github.com/Raphire/Win11Debloat).

Poate elimina aplicațiile bloatware preinstalate, dezactiva telemetry, elimina elementele de interfață intruzive și multe altele. Pentru a vedea o listă cu fișierele eliminate în mod implicit,[faceți click aici](https://github.com/Raphire/Win11Debloat#default-settings).\


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
