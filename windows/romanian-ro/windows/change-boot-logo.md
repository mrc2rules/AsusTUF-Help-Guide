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

# Schimbarea Boot Logo

{% hint style="danger" %}
**Important:**\
Dacă greșiți instalarea, sistemul dvs. poate deveni imposibil de bootat! Acest software nu oferă garanție. Utilizați-l pe propriul risc.

* Asigurați-vă că computerul dvs. bootează cu UEFI (foarte probabil că da)
* Asigurați-vă că BitLocker este dezactivat sau găsiți cheia de recuperare.
* Creați o copie de rezervă completă sau un disc de salvare înainte de a face modificări la sigla de boot Windows. Copia de rezervă sau discul de salvare vă ajută să restaurați Windows dacă ceva nu merge bine și nu puteți boota.
{% endhint %}

## # Instalare pentru prima oară

### Pasul 1: Descarcă "HackBGRT"

Pentru a schimba boot logo-ul, vom folosi o aplicație open-source numită HackBGRT. Iată pașii de folosire.

1. Dute la [HackBGRT GitHub](https://github.com/Metabolix/HackBGRT/releases)
2. Descarcă **latest release ZIP file**.
3. Extract la desktop/folder de alegerea ta.

### Pasul 2: Folosirea HackBGRT

1. Deschide folder-ul extras, right-click pe **setup.exe** și selectează **Run as administrator**\
   \
   <img src="../.gitbook/assets/image (9).png" alt="" data-size="original">&#x20;
2. Va deschide aplicația în command-line. \
   \- **Apasă tasta i** pentru a intra în First Time Installation\
   \- **Apasă tasta B** pentru a boota în UEFI setup unde poți opri S ecure Boot\
   \
   Additional:\
   Dacă ai setat deja boot logo-ul și vrei să-l modifici, **apasă tasta F** pentru a modifica instalarea.\
   &#x20;\
   <img src="../.gitbook/assets/image (10).png" alt="" data-size="original">
3. După ce apeși orice tastă, va deschide Paint.

### Step 3: Setând logo-ul

{% hint style="info" %}
**Note:**

* Nu puteți seta GIF-uri sau imagini transparente ca noul logo de boot.
* Păstrați fundalul logo-ului negru, deoarece transparența nu este acceptată. Prin urmare, noul logo nu arată nelalocul său pe fundalul negru al ecranului de boot.
* Imaginea nu trebuie să fie mai mare de 300 x 300 pixeli. Deși dimensiunea nu este o cerință strictă, aceasta garantează că nu veți întâmpina probleme la setarea noului logo de boot.
{% endhint %}

1. În Paint, dă click pe **File** > **Import from Canvas** > **From file**. Apoi, găsește imaginea pe care o vrei sa o setezi ca noul Boot Logo. Selectează-l it și click pe butonul **Open**.
2. Dacă vrei, poți da click pe butonul **Resize**.
3. Odată ce ai terminat, click pe **File** > **Save** pentru a salva fișierul. După salvare, Închide Paint.
4. Apasă orice tastă pentru a ieși command line-ul.

### Step 4: Reboot / Instrucțiuni pentru Secure Boot

Fiindcă Secure Boot acceptă doar fișiere de încredere la boot, HackBGRT vine cu _shim_ boot loader, o unealtă ce te lasă să seletezi HackBGRT ca un program de încredere.&#x20;

După instalarea HackBGRT și reboot, **urmărește instrucțiunile de mai jos** pentru a completa procesul.



1. După reboot, vei vedea acest ecran.\
   \
   Select `OK`,  _Enter_.\
   ![](<../.gitbook/assets/image (11).png>)\

2.  Apasă orice tastă repede

    ```
    Shim UEFI key management
    Press any key to perform MOK management
    Booting in 5 seconds
    ```


3.  Selectează `Enroll hash from disk`, _Enter_.&#x20;

    ```
    Perform MOK management

    Continue to boot
    Enroll key from disk
    Enroll hash from disk
    ```


4.  Selectează primul disk, _Enter_. (**Nu selecta "MyAsus"!!**)

    ```
    Selectează Binary

    Binary-ul selectat va avea hash-ul lui Enrolled.
    Asta înseamnă ca nu se va da boot ulterior fară ca să dea prompt.
    Asigură-te mereu ca binary-ul este autentic înainte să dai Enroll.

    +----------------+
    | YOUR DISK NAME |
    +----------------+
    ```


5.  Selectează `EFI/`, _Enter_.

    ```
    +---------------+
    |     EFI/      |
    |    loader/    |
    | vmlinuz-linux |
    +---------------+
    ```


6.  Selectează `HackBGRT/`, _Enter_.

    ```
    +------------+
    |    ../     |
    |   Boot/    |
    | HackBGRT/  |
    | Microsoft/ |
    +------------+
    ```


7.  Selectează `grubx64.efi`, _Enter_.

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


8.  Selectează `Continue`, _Enter_.

    ```
    [Enroll MOK]

    +------------+
    | View key 0 |
    |  Continue  |
    +------------+
    ```


9.  Selectează `Yes`, _Enter_.

    ```
    Enroll the key(s)?

    +-----+
    | No  |
    | Yes |
    +-----+
    ```


10. Selectează `Reboot`, _Enter_.

    ```
    Perform MOK management

    +-----------------------+
    |        Reboot         |
    | Enroll key from disk  |
    | Enroll hash from disk |
    +-----------------------+
    ```



Acum ești gata să dai boot! Felicitări

## # Modificare Instalație

Dacă vrei să schimbi logo-ul, re-rulează **setup.exe** ca administrator și **apasă tasta F** pe tastatură ca să modifici instalația.

Ține aminte să salvezi fișierul in paint!

{% hint style="info" %}
**Pentru troubleshooting,** [**dă click aici.**](https://github.com/Metabolix/HackBGRT/tree/v2.5.2?tab=readme-ov-file#troubleshooting)
{% endhint %}

\
