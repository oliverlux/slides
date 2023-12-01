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

# Router und Routing

<br> 




---
# Aufgaben eines Routers

- Umpacken (Umladen) von Datenpaketen
- Ermitteln der verfügbaren Routen
- Auswahl der geeignetsten Route
- Pakete entsprechend weiterleiten
![Routing](https://res.cloudinary.com/luggs/image/upload/v1701420103/w_400/Informatik/Modul%20117/routing.png)


---

# Statisches Routing

Die Routen werden mit Hilfe der Routingtabelle statisch konfiguriert
- **Netzadresse**: Eintrag des Ziel-Netzes das erreicht werden soll
- **Next Hop**: IP-Adresse des nächsten Routers zum Ziel-Netz
- **Metric**: Ein Mass für die Güte eines Weges, häufig Hop Count
- **Interface**: Schnittstelle über die das Paket weitergeleitet wird

---
# Routing Tabelle

Destination Network | Next Hop | Metric (z.B. Hop Count) | Interface
-------- | -------- | -------- |-------- |
192.168.1.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
192.168.2.0/24   | 192.168.88.2 | 1 | s0 |

![Routingbeispiel](https://res.cloudinary.com/luggs/image/upload/c_scale,w_709/v1701422804/Informatik/Modul%20117/routingtabelle.png)

---
# Routing Tabelle

`route print`

![Routingtabelle](https://res.cloudinary.com/luggs/image/upload/c_scale,w_701/v1701423163/Informatik/Modul%20117/routingtabelle_cmd.png)


---
# Default Route (Roter Router)

Destination Network | Next Hop | Metric  | Interface
-------- | -------- | -------- |-------- |
192.168.1.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
0.0.0.0/0   | 192.168.88.2 | - | s0 |

![Default Route](https://res.cloudinary.com/luggs/image/upload/c_scale,w_548/v1701423452/Informatik/Modul%20117/default_route.png)

---
# Default Route (Blauer Router)

Destination Network | Next Hop | Metric  | Interface
-------- | -------- | -------- |-------- |
192.168.2.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
102.85.0.0/16   | -   | 0 | s1 |
192.168.1.0/24   | 192.168.88.1   | 1 | s0 |
0.0.0.0/0   | 102.85.1.1 | - | s1 |

Grafik auf nächster Folie

--- 
![Default Route](https://res.cloudinary.com/luggs/image/upload/c_scale,w_850/v1701424687/Informatik/Modul%20117/default_route_blau.png)

---
# Vorgehen

![Vorgehen Routing](https://res.cloudinary.com/luggs/image/upload/w_800/v1701424862/Informatik/Modul%20117/vorgehen_routing.png)

---
# Vorgehen

![Vorgehen Routing](https://res.cloudinary.com/luggs/image/upload/w_800/v1701425006/Informatik/Modul%20117/vorgehen_routing2.png)

---
# Routing Kommandos Windows

Aufgabe | Windows | 
-------- | -------- | 
Routingtabelle anzeigen   | `route print`   |
Statische Route eintragen   | `route add 157.3.0.0 mask 255.255.0.0 202.55.80.1 [metric 1]` |  
Default Route eintragen   | `route add 0.0.0.0 mask 0.0.0.0 161.99.1.1 [metric 1]` |  
Statische Route löschen | `route del ...` |

---
# Routing Kommandos Linux

Aufgabe | Linux | 
-------- | -------- | 
Routingtabelle anzeigen   | `route -n`   |
Statische Route eintragen   | `route add 157.3.0.0 mask 255.255.0.0 gw 202.55.80.1 [dev eth0][metric 1]` |  
Default Route eintragen   | `route add default gw 161.99.1.1 [metric 1]` |  
Statische Route löschen | `route del ...` |

---
# Routing Kommandos Cisco

Aufgabe | Cisco | 
-------- | -------- | 
Routingtabelle anzeigen   | `show ip route`   |
Statische Route eintragen   | `ip route 157.3.0.0 mask 255.255.0.0 202.55.80.1` |  
Default Route eintragen   | `ip route 0.0.0.0 0.0.0.0 161.99.1.1` |  
Statische Route löschen | `no ip route ...` |


---
# Routing Arten

- **Statisches Routing:** Die Routingtabelle wird manuell bearbeitet. Feste Vorgaben für den Router, dieser kann damit nicht auf Netzwerkprobleme reagieren.
- **Dynamisches Routing:** Die Routingtabelle wird von den Routern selbstständig aufgebaut. Über Routingprotokolle werden
Erreichbarkeitsdaten zwischen den Routern ausgetauscht.

---
# Routing Protokolle

- Interior Gateway Protocol (IGP) für grosse Unternehmensnetzwerke: 
    - OSPF (Open Shortest Path First)
    - RIP (Routing Information Protocol)
    - IS-IS (Intermediate System to Intermediate System)
- Exterior Gateway Protocol (EGP) für Router im Internet:
    - BGP (Border Gateway Protokoll)

---
# RIP

- Beim Start kennt der Router nur seine direkt angeschlossenen
Netzwerke, diese müssen unter RIP eingetragen werden
- Er sendet an alle seine Nachbarn eine Bitte um die Zusendung ihrer vollständigen Routingtabelle
- Mit den Antworten füllt der Router seine eigene Routingtabelle

---
# RIP

![RIP](https://res.cloudinary.com/luggs/image/upload/w_900/v1701425909/Informatik/Modul%20117/rip.png)





