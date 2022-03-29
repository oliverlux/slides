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

# Grundlagen Netzwerktechnik

<br> 




---
# Definition Netzwerk

> Ein Netzwerk stellt eine Infrastruktur dar, die Datenendgeräten die wahlfreie Kommunikation untereinander, den Datenaustausch und die Nutzung gemeinsamer Ressourcen und Dienste transparent ermöglicht.


---
# Netzwerkprotokolle

- Festlegen der Modalitäten für den Aufbau und das Trennen von Verbindungen
- Regeln zum Austausch der Daten und das Fehrhalten im Fehlerfall

> Netzwerkprotokolle stellen die Schicht zwischen der Hardware und der jeweiligen Anwendung, resp. dem Anwender dar, der mit ihnen kommuniziert.

---
# TCP/IP (Transmission Control Protocol/Internet Protocol)

- In den 60er Jahren erfunden
- Grundzüge von heute sind 1974 geschaffen worden (RFC 675)
- Grundlagenprotokolle der heutigen Netzwerkkommunikation

---
# Merkmale TCP/IP

- Architekturunabhängige Netzwerktechnologie
- Verbindungen von und zu allen Netzwerkteilnehmenden
- Anwendungsprotokolle nach allgemeinen Standards
- Vermittlungseben mit verbindungslosem Protokoll
- Paketvermittlungsrechner als Netzknoten
- Sicherungsfunktionen in Transportprotokollen

---
# OSI-Schichtenmodell
![OSI-Modell](https://res.cloudinary.com/luggs/image/upload/v1648542358/Informatik/Modul%20117/osi.png)

---

# Netzwerktopologien 

- Sterntopologie
- Baumtopologie
- Ringtopologie
- Bustopologie
- Vermaschte Topologie

Weitere Informationen: 
🌎 https://www.elektronik-kompendium.de/sites/net/0503281.htm


---
# Reichweite von Netzwerken 

<style>
    table {
        font-size:85%;
    }
</style>

| Name | Beschreibung |
|------|-------------|
| PAN | Personal Area Network, Reichweite ca. 5-10 Meter |
| LAN | Local Area Network, Reichweite typischerweise in einem Gebäude| 
| CAN | Campus Area Network, Reichweite über einen Firmenkomplex / Universität |
| MAN | Metropolian Area Network, Reichweite über ein Stadtgebiet |
| WAN | Wide Area Network, Reichweite über grössere geografische Distanz, mehrere LANs zusammen |
| GAN | Global Area Network, weltweite Verbindung von mehreren WANs |

---

# Netzwerkplan

![Netzwerkplan](https://res.cloudinary.com/luggs/image/upload/w_500/v1648196997/Informatik/Modul%20117/netzwerkplan.png)

---

# Netzwerkplan - Wichtiges

- Korrekte Verbindungen
- Übersichtlichkeit
- Beschriftung der Geräte
- Titel, Autor, Version, etc.



