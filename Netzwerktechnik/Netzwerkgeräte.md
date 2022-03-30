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

# Netzwerkgeräte

<br> 




---
# Hubs

- Leiten sämtliche Datenpakete an alle Ausgänge
- Arbeiten auf OSI-Layer 1
- Sind veraltet und sollten ersetzt werden

![Hub](https://res.cloudinary.com/luggs/image/upload/v1648643143/Informatik/Modul%20117/hub.gif)

---

# Switches

- Einfache Switches ➡ OSI-Layer 2
- Programmierbare Switches ➡ OSI-Layer 3
- Switches merken sich die MAC-Adressen

![Switch](https://res.cloudinary.com/luggs/image/upload/v1648643270/Informatik/Modul%20117/switch.gif)

---
# Switch - Schleifen

- Einfache Switches können mit einem Loop (oder Mehrfachverkabelung) und einem entsprechenden Broadcast-Paket ausser Gefecht gesetzt werden
- Abhilfe schafft STP (Spanning Tree Protocol)

---
# Virtuelle Netze (VLAN)

Programmierbare Swiches können 
- grosse Netzwerke unterteilen.
- betriebliche Organisationen mittels VLANs abbilden.
- das Netz nach Anwendungen einteilen (VoIP, Multimedia-Dienste, etc.).

---
# Angriffspunkte Switches

- Missbrauch STP
- Überlauf: Interne MAC-Tabelle wird sinnlos gefüllt, Switch wird zu einem Hub degradiert und Angreifer kann Netzwerkverkehr an einem Port mithören
- Gefälschte Frames

---
# Router

- Vermittelt Pakete an andere Netzwerke
- OSI-Layer 3
![Router](https://res.cloudinary.com/luggs/image/upload/v1648643939/Informatik/Modul%20117/router.png)





