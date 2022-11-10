---
marp: true
theme: gaia
paginate: true
_class: lead

backgroundImage: url('https://res.cloudinary.com/luggs/image/upload/v1634832661/GBS/bg1.png')
---

<!-- _backgroundImage: url('https://res.cloudinary.com/luggs/image/upload/v1622877578/GBS/gbs.jpg') 
_color: black;

_footer: ""
_paginate: false
-->

<style scoped>
h1 {
    background-color: #222;
    margin: 0;
    padding: 0 10px 0 20px;
    font-weight: 800;
    transform: rotate(-5deg);
    color: #fff;
    text-align: left;
}

h1::after {
    font-family: Arial, Helvetica, sans-serif;
    bottom: 0;
    color: #CCCC00;
    content: '.';
    position: absolute;
    margin-left: 25px;
    transform: translate(-100%, 0);
}

h3 {
    background-color: #222;
    margin: 0;
    padding: 0 10px 0 20px;
    font-weight: 400;
    transform: rotate(-5deg);
    color: #fff;
    text-align: left;
    width: 200px;
}

a {
    color: #fff;
    text-decoration: none;
}


</style>

### gbssg.ch

# cloud-init

<br> 






---

# Definition cloud-init 

> Cloud Images (AMI) sind Betriebssystemvorlagen und jede Instanz startet als identischer Klon. Jede Vorlage kann mittels `cloud-init` individuell angepasst werden und beim Start der Instanz können automatisiert Skripte abgearbeitet werden.

> Paket für die Initialisierung von Cloud Instanzen [Beschreibung von Canonical]

---
# Möglichkeiten mit cloud-init

- Automatisches Installieren und Konfigurieren von Software
- Anpassungen am Hostname
- Konfiguration von SSH-Keys
- Erstellen von Benutzern und Gruppen
- Abarbeiten von Skripten
- ...


---

# Weitere Informationen

- [Informationen cloud-init von IONOS](https://www.ionos.de/hilfe/server-cloud-infrastructure/serveradministration/serverkonfiguration-mit-cloud-init-allgemeine-informationen/)
- [Warum ist cloud-init so cool](https://contabo.com/blog/de/was-ist-cloud-init/)
- [cloud-init Dokumentation](https://cloudinit.readthedocs.io/en/latest/)





