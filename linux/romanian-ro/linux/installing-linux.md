---
description: scris de Zenith Zephyr, tradus de Scott
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
# Instalarea Linux

## Pasul 1: Configurare post-instalare

Dacă ai o placă grafică Nvidia dedicată, va trebui să instalezi driverele Nvidia pentru Linux.

Dacă ai o placă grafică AMD dedicată, nu este nevoie să instalezi drivere suplimentare deoarece driverele open-source Mesa sunt deja incluse în kernelul Linux.

**Notă:**  
Spre deosebire de Windows, în general nu este necesar să instalezi drivere suplimentare pentru majoritatea componentelor. Linux le gestionează, deobicei, automat.

## Pasul 2: Configurare software Asus și instalare drivere GPU

Instrucțiunile necesare se găsesc pe site-ul Asus Linux: https://asus-linux.org/guides/fedora-guide/. Poți sări peste pașii de instalare de acolo și să începi direct din secțiunea de configurare. Urmează acești pași:

1. Actualizează Fedora
2. Instalează driverele grafice Nvidia (sari peste dacă ai placă AMD)
3. Instalează asusctl și supergfxctl

După instalarea supergfxctl, deschide terminalul și rulează:

`sudo systemctl enable supergfxd.service`  

`sudo systemctl start supergfxd.service`

Poți ignora avertismentul „Asus kernel isn’t loaded” in _rog-control-center_.

# Comutarea modurilor de GPU cu o interfață grafică

*Dacă folosești GNOME, instalează extensia supergfxctl-gex: https://extensions.gnome.org/extension/5344/supergfxctl-gex/*

*Dacă folosești KDE, va trebui să instalezi supergfxctl-plasmoid: https://gitlab.com/Jhyub/supergfxctl-plasmoid*

Rulează următoarele comenzi pentru a-l instala:

`sudo dnf copr enable jhyub/supergfxctl-plasmoid`


`sudo dnf install supergfxctl-plasmoid`

Reîncarcă Plasma pentru ca modificările să aibă efect:

`plasmashell --replace &`


Apoi, în terminal, setează modul GPU pe Hybrid:

`supergfxctl --mode Hybrid`


După reîncărcarea shell-ului, o pictogramă cu un cip ar trebui să apară în bara de activități. Poți folosi această pictogramă pentru a comuta între modurile de GPU printr-o interfață grafică fără a mai folosi terminalul.  
Repornește sistemul și, voila! Modurile de GPU ar trebui să funcționeze perfect și să fie controlabile din interfață.

**Notă:**  
Comutarea modului GPU înspre sau dinspre *Hybrid* necesită delogare și logare din nou. Modul *Ultimate* funcționează similar cu Windows și necesită o repornire completă a sistemului.

## Pasul 3: Remedierea tastelor rapide

**Avertisment:**  
Unele funcții ale tastelor rapide sunt gestionate direct de BIOS, ceea ce înseamnă că input-ul nu poate ajunge la sistemul de operare și nu pot fi re-mapate.  
Pentru a verifica dacă o tastă poate fi re-mapată, apasă combinația dorită în timp ce creezi comanda rapidă.  
Dacă este înregistrată, re-maparea este posibilă; dacă nu, va trebui să alegi o altă combinație diferită.

În GNOME, mergi la Setări > Tastatură > Comenzi rapide, apoi apasă „+” pentru a adăuga o nouă comandă.

În KDE, mergi la Setări de sistem > Comenzi rapide > Comenzi personalizate, apoi creează o comandă globală → Comandă/URL.

Setează orice nume, apasă combinația dorită (ex: Fn+F4) și introdu comanda:

1. Pentru Armoury Crate: `rog-control-center`  
2. Pentru modul Aura: `asusctl aura -n`  
3. Pentru modul Performanță: `asusctl profile -n`
