---
icon: microchip
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

# Ghidul pentru Display Driver Uninstaller (DDU)

Acest ghid vă arată cum să eliminați complet driverele pentru GPU și să îl reinstalați. Reinstalarea driverelor GPU va asigura instalarea și va rezolva eventualele probleme potențiale.

**Motivele pentru care ar putea fi nevoie să faceți acest lucru:**

* Dacă aveți accidente/ecran negru sau artefacte/glitch-uri pe ecran.\
  \
  Aceste probleme ar putea fi cauzate de un driver GPU defect/corupt. Laptopul tău are 2 GPU-uri.\
  — Un **iGPU** (integrat în procesor) _<mark style="color:blue;">ex: Intel UHD/Iris graphics, AMD Radeon xxxM graphics</mark>_\
  — A **dGPU** (placă grafică dedicată) _<mark style="color:green;">ex: Nvidia RTX/GTX series, AMD Radeon RX series</mark>_\

* Dacă aveți probleme în modurile **Standard/Eco/Optimized**, <mark style="color:yellow;">reinstalați driverele iGPU</mark>.\
  Dacă aveți probleme în modul **Ultimate** sau **când jucați**, <mark style="color:yellow;">reinstalați driverele dGPU</mark>.\


{% hint style="danger" %}
**ÎNAINTE DE A ÎNCEPE**

Dacă reinstalați **driverele dGPU, schimbați la modul Standard pe GHelper/Armoury Crate**\
Dacă reinstalați **driverele iGPU, schimbați la modul Ultimate pe GHelper/Armoury Crate**,

Dacă nu faceți asta, vei avea un ecran negru după ștergerea driverului, ar trebui să conectați un display/monitor extern la laptop prin portul care se conectează la celălalt GPU funcțional.
{% endhint %}

## Pasul 1: Descărcați drivere oficiale

Descărcați cele mai noi drivere pentru GPU-ul dvs. de pe site-ul producătorului.&#x20;

{% hint style="warning" %}
**NU le instalați sau le rulați încă!**
{% endhint %}

Nvidia: [https://www.nvidia.com/en-us/drivers/](https://www.nvidia.com/en-us/drivers/) \
AMD: [https://www.amd.com/en/support/download/drivers.html](https://www.amd.com/en/support/download/drivers.html)&#x20;

Păstrați installerul on your desktop pentru access ușor mai târziu. Este de preferat daca sunt de ultima versiune fiindca va funcționa mai bine, în special cu jocuri noi fiindca producătorii deobicei lanseaza patch-uri pentru ele.

## Pasul 2: Instalare DDU

Acest software va dezinstala complet tot ce este legat de drivere. fără a lăsa nicio urmă de ele, permițându-vă să instalați noi drivere noi.

&#x20;[https://www.wagnardsoft.com/forums/viewtopic.php?t=5092](https://www.wagnardsoft.com/forums/viewtopic.php?t=5092)&#x20;

Modul Portable este mai ușor, doar extrageți-l într-un folder gol de pe desktop.

## Pasul 3: Pregătire pentru DDU

1. Opriți complet conexiunea de la internet (WiFi sau ethernet). Acest lucru previne ca Windows să nu instaleze automat drivere din Windows Updates.
2. Deschide DDU, apoi pe stânga sus deschide meniul `Options`,&#x20;
3. Pornește opțiunea `Enable Safe Mode dialog`, este penultima opțiune.&#x20;
4. Redeschide DDU, ar trebui sa îți apară meniul `launch option`. Click pe el și selectează `Safe mode`
5. Laptopul tău iși va da restart în Safe Mode. Acest lucru este necesar pentru a nu cauza conflicte. 
6. DDU ar trebui să se deschidă automat după restart, dacă nu, rulează -l manual.

## Pasul 4: Folosind DDU

1. Odată ce ai intrat în DDU, Ar trebui să existe 2 meniuri pe partea dreaptă, \
   `-Select device type-` și `-Select device-`\
   \
   Sub primul meniu, **selectează opțiunea pentru GPU**\
   Sub al doilea, **select the GPU driver you want to uninstall.**&#x20;
2. Apoi apasă `clean and restart`, wait until it automatically restarts.&#x20;
3. După restart, instalează driverele GPU driver descărcate mai devreme, apoi ce termină de instalat, dă restart la laptop si repornește internetul.



_Tradus și adaptat de la ghidul lui @yamen76 's pe AsusTUF discord_



