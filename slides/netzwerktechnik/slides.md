---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://res.cloudinary.com/luggs/image/upload/v1765022012/Informatik/Allgemein/network.jpg
# some information about your slides (markdown enabled)
title: Netzwerktechnik
info: |
  ## Netzwerktechnik
  Folien zu Netzwerktechnik
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: fade-out
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 35min

---

# Netzwerktechnik

Folien zu verschiedenen Themen im Bereich Netzwerktechnik

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Weiter <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-sm">
  © Oliver Lux
</div>

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---


# Definition Netzwerk

> Ein Netzwerk stellt eine Infrastruktur dar, die Datenendgeräten die wahlfreie Kommunikation untereinander, den Datenaustausch und die Nutzung gemeinsamer Ressourcen und Dienste transparent ermöglicht.

<br><br>


# Netzwerkprotokolle

- Festlegen der Modalitäten für den Aufbau und das Trennen von Verbindungen
- Regeln zum Austausch der Daten und das Fehrhalten im Fehlerfall
<br><br>

> Netzwerkprotokolle stellen die Schicht zwischen der Hardware und der jeweiligen Anwendung, resp. dem Anwender dar, der mit ihnen kommuniziert.

---
transition: fade-out
---

# TCP/IP (Transmission Control Protocol/Internet Protocol)

- In den 60er Jahren erfunden
- Grundzüge von heute sind 1974 geschaffen worden (RFC 675)
- Grundlagenprotokolle der heutigen Netzwerkkommunikation

---
transition: fade-out
---

# Merkmale TCP/IP

- Architekturunabhängige Netzwerktechnologie
- Verbindungen von und zu allen Netzwerkteilnehmenden
- Anwendungsprotokolle nach allgemeinen Standards
- Vermittlungseben mit verbindungslosem Protokoll
- Paketvermittlungsrechner als Netzknoten
- Sicherungsfunktionen in Transportprotokollen

---
transition: fade-out
---

# OSI-Schichtenmodell
![OSI-Modell](https://res.cloudinary.com/luggs/image/upload/v1648542358/Informatik/Modul%20117/osi.png)

---
transition: fade-out
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
transition: fade-out
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
transition: fade-out
---

# Netzwerkplan

![Netzwerkplan](https://res.cloudinary.com/luggs/image/upload/w_500/v1648196997/Informatik/Modul%20117/netzwerkplan.png)

---
transition: fade-out
---

# Netzwerkplan - Wichtiges

- Korrekte Verbindungen
- Übersichtlichkeit
- Beschriftung der Geräte
- Titel, Autor, Version, etc.


---
transition: fade-out
layout: cover
---

# Netzwerkgeräte

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Hubs

- Leiten sämtliche Datenpakete an alle Ausgänge
- Arbeiten auf OSI-Layer 1
- Sind veraltet und sollten ersetzt werden

![Hub](https://res.cloudinary.com/luggs/image/upload/v1648643143/Informatik/Modul%20117/hub.gif)

---
transition: fade-out
---

# Switches

- Einfache Switches ➡ OSI-Layer 2
- Programmierbare Switches ➡ OSI-Layer 3
- Switches merken sich die MAC-Adressen

![Switch](https://res.cloudinary.com/luggs/image/upload/v1648643270/Informatik/Modul%20117/switch.gif)

---
transition: fade-out
---

# Switch - Schleifen

- Einfache Switches können mit einem Loop (oder Mehrfachverkabelung) und einem entsprechenden Broadcast-Paket ausser Gefecht gesetzt werden
- Abhilfe schafft STP (Spanning Tree Protocol)


---
transition: fade-out
---

# Virtuelle Netze (VLAN)

Programmierbare Swiches können 
- grosse Netzwerke unterteilen.
- betriebliche Organisationen mittels VLANs abbilden.
- das Netz nach Anwendungen einteilen (VoIP, Multimedia-Dienste, etc.).

---
transition: fade-out
---


# Angriffspunkte Switches

- Missbrauch STP
- Überlauf: Interne MAC-Tabelle wird sinnlos gefüllt, Switch wird zu einem Hub degradiert und Angreifer kann Netzwerkverkehr an einem Port mithören
- Gefälschte Frames

---
transition: fade-out
---

# Router

- Vermittelt Pakete an andere Netzwerke
- OSI-Layer 3
![Router](https://res.cloudinary.com/luggs/image/upload/v1648643939/Informatik/Modul%20117/router.png)


---
transition: fade-out
layout: cover
---

# Router

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Aufgaben eines Routers

- Umpacken (Umladen) von Datenpaketen
- Ermitteln der verfügbaren Routen
- Auswahl der geeignetsten Route
- Pakete entsprechend weiterleiten
![Routing](https://res.cloudinary.com/luggs/image/upload/v1701420103/w_400/Informatik/Modul%20117/routing.png)


---
transition: fade-out
---


# Statisches Routing

Die Routen werden mit Hilfe der Routingtabelle statisch konfiguriert
- **Netzadresse**: Eintrag des Ziel-Netzes das erreicht werden soll
- **Next Hop**: IP-Adresse des nächsten Routers zum Ziel-Netz
- **Metric**: Ein Mass für die Güte eines Weges, häufig Hop Count
- **Interface**: Schnittstelle über die das Paket weitergeleitet wird

---
transition: fade-out
---

# Routing Tabelle

Destination Network | Next Hop | Metric (z.B. Hop Count) | Interface
-- | -------- | -------- |-------- |
192.168.1.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
192.168.2.0/24   | 192.168.88.2 | 1 | s0 |

![Routingbeispiel](https://res.cloudinary.com/luggs/image/upload/c_scale,w_709/v1701422804/Informatik/Modul%20117/routingtabelle.png)

---
transition: fade-out
---

# Routing Tabelle

`route print`

![Routingtabelle](https://res.cloudinary.com/luggs/image/upload/c_scale,w_701/v1701423163/Informatik/Modul%20117/routingtabelle_cmd.png)

---
transition: fade-out
---

# Default Route (Roter Router)

Destination Network | Next Hop | Metric  | Interface
-- | -------- | -------- |-------- |
192.168.1.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
0.0.0.0/0   | 192.168.88.2 | - | s0 |

![Default Route](https://res.cloudinary.com/luggs/image/upload/c_scale,w_548/v1701423452/Informatik/Modul%20117/default_route.png)

---
transition: fade-out
---

# Default Route (Blauer Router)

Destination Network | Next Hop | Metric  | Interface
-- | -------- | -------- |-------- |
192.168.2.0/24   | -   | 0 | e0 |
192.168.88.0/24   | -   | 0 | s0 |
102.85.0.0/16   | -   | 0 | s1 |
192.168.1.0/24   | 192.168.88.1   | 1 | s0 |
0.0.0.0/0   | 102.85.1.1 | - | s1 |

Grafik auf nächster Folie

---
transition: fade-out
---

![Default Route](https://res.cloudinary.com/luggs/image/upload/c_scale,w_850/v1701424687/Informatik/Modul%20117/default_route_blau.png)

---
transition: fade-out
---

# Vorgehen

![Vorgehen Routing](https://res.cloudinary.com/luggs/image/upload/w_800/v1701424862/Informatik/Modul%20117/vorgehen_routing.png)

---
transition: fade-out
---

# Vorgehen

![Vorgehen Routing](https://res.cloudinary.com/luggs/image/upload/w_800/v1701425006/Informatik/Modul%20117/vorgehen_routing2.png)

---
transition: fade-out
---

# Routing Kommandos Windows

Aufgabe | Windows | 
-- | -------- | 
Routingtabelle anzeigen   | `route print`   |
Statische Route eintragen   | `route add 157.3.0.0 mask 255.255.0.0 202.55.80.1 [metric 1]` |  
Default Route eintragen   | `route add 0.0.0.0 mask 0.0.0.0 161.99.1.1 [metric 1]` |  
Statische Route löschen | `route del ...` |

---
transition: fade-out
---

# Routing Kommandos Linux

Aufgabe | Linux | 
-- | -------- | 
Routingtabelle anzeigen   | `route -n`   |
Statische Route eintragen   | `route add 157.3.0.0 mask 255.255.0.0 gw 202.55.80.1 [dev eth0][metric 1]` |  
Default Route eintragen   | `route add default gw 161.99.1.1 [metric 1]` |  
Statische Route löschen | `route del ...` |

---
transition: fade-out
---

# Routing Kommandos Cisco

Aufgabe | Cisco | 
-- | -------- | 
Routingtabelle anzeigen   | `show ip route`   |
Statische Route eintragen   | `ip route 157.3.0.0 mask 255.255.0.0 202.55.80.1` |  
Default Route eintragen   | `ip route 0.0.0.0 0.0.0.0 161.99.1.1` |  
Statische Route löschen | `no ip route ...` |


---
transition: fade-out
---

# Routing Arten

- **Statisches Routing:** Die Routingtabelle wird manuell bearbeitet. Feste Vorgaben für den Router, dieser kann damit nicht auf Netzwerkprobleme reagieren.
- **Dynamisches Routing:** Die Routingtabelle wird von den Routern selbstständig aufgebaut. Über Routingprotokolle werden
Erreichbarkeitsdaten zwischen den Routern ausgetauscht.

---
transition: fade-out
---

# Routing Protokolle

- Interior Gateway Protocol (IGP) für grosse Unternehmensnetzwerke: 
    - OSPF (Open Shortest Path First)
    - RIP (Routing Information Protocol)
    - IS-IS (Intermediate System to Intermediate System)
- Exterior Gateway Protocol (EGP) für Router im Internet:
    - BGP (Border Gateway Protokoll)

---
transition: fade-out
---

# RIP

- Beim Start kennt der Router nur seine direkt angeschlossenen
Netzwerke, diese müssen unter RIP eingetragen werden
- Er sendet an alle seine Nachbarn eine Bitte um die Zusendung ihrer vollständigen Routingtabelle
- Mit den Antworten füllt der Router seine eigene Routingtabelle

---
transition: fade-out
---

# RIP

![RIP](https://res.cloudinary.com/luggs/image/upload/w_900/v1701425909/Informatik/Modul%20117/rip.png)

---
transition: fade-out
layout: cover
---

# Kabeltypen

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Twisted-Pair-Kabel

- RJ45-Stecker
- Maximale Länge von 100 Metern

![RJ45](https://res.cloudinary.com/luggs/image/upload/w_500/v1648544118/Informatik/Modul%20117/rj45.webp)

---
transition: fade-out
---

<style scoped>
    table {
    font-size: 0.8em;
}
</style>
# Kabelkategorien 1/3

| Bezeichnung | Weitere Namen | Norm | Kabel | Hinweise |
|---|---|---|---|---|
| 10Base-T | Ethernet | IEEE 802.3j | Cat. 3-7 | Hubs oder Switches als Netzknoten |
| 100Base-TX | Fast Ethernet | IEEE 802.3, Clause 25 | Cat. 5-7 | Switches als Netzknoten |
| 100Base-T | Gigabit Ethernet | IEEE 802.3, Clause 40 | Cat. 5-7 | Switches als Netzknoten, Benutzung aller vier Doppeladern zur Unterdrückung von Signalechos  |

---
transition: fade-out
---

<style scoped>
    table {
    font-size: 0.8em;
}
</style>
# Kabelkategorien 2/3

| Bezeichnung | Weitere Namen | Norm | Kabel | Hinweise |
|---|---|---|---|---|
| 10GBase-T | 10 Gigabit Ethernet | IEEE 802.3an | Cat. 7 | Switches als Netzknoten, Benutzung aller vier Doppeladern zur Unterdrückung von Signalechos |
| 40GBase-T | 40 Gigabit Ethernet | IEEE 802.3bq | Cat. 8.1 | Switches als Netzknoten, für kurze Verbindungen zentraler EDV-Komponenten, RJ45-Stecker |

---
transition: fade-out
---

<style scoped>
    table {
    font-size: 0.8em;
}
</style>
# Kabelkategorien 3/3

| Bezeichnung | Weitere Namen | Norm | Kabel | Hinweise |
|---|---|---|---|---|
| 100GBase-T | 100 Gigabit Ethernet | IEEE 802.3bg | Cat. 8.2 | Switches als Netzknoten, für kurze Verbindungen zentraler EDV-Komponenten, ARJ45- bzw. GG45-Stecker  |

---
transition: fade-out
---

# Kabeltypen

`U` ungeschirmt
`F` Folienschirm
`S` Geflechtschirm
`SF`    Geflecht- und Folienschirm (nur bei Gesamtschirmung)
`TP`    Twisted Pair (verdrillte Adern)
`QP`    Quad Pair

![Kabeltypen](https://res.cloudinary.com/luggs/image/upload/h_200/v1648545187/Informatik/Modul%20117/kabeltypen.png)

---
transition: fade-out
---

# PoE (Power over Ethernet)

- Netzwerkfähige Geräte können über Strom versorgt werden
- Stromversorgungskabel kann eingespart werden

---
transition: fade-out
---

# Tipps

- Netzwerkkabel und -stecker können auch defekt sein
- Defekte Kabel **sofort** entsorgen
    - Stecker abschneiden, damit sofort ersichtlich ist, dass Netzwerkkabel defekt ist

---
transition: fade-out
---

# Lichtwellenleiter

- LWL ermöglichen schnellste Kommunikation
- Hohe Abhörsicherheit und geringer Platzbedarf
- Unempfindlichkeit gegenüber elektrischen Einflüssen
- Sehr aufwändige Montage
- Heikel im Umgang (Knicken), hohe Anschaffungspreise

---
transition: fade-out
---

# Unterschiedliche Arten LWL

![LWL](https://res.cloudinary.com/luggs/image/upload/v1648549247/Informatik/Modul%20117/lwl.png)

---
transition: fade-out
layout: cover
---

# IP-Adressen

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# IP-Adresse setzen

## Windows
`Systemeinstellungen` - `Netzwerk und Freigabecenter` - `Eigenschaften der LAN-Verbindung` - `Adapteroptionen`

## Linux
```
auto eth0
iface eth0 inet static
address 192.168.0.34
netmask 255.255.255.0
gateway 192.168.0.1
```

---
transition: fade-out
---

# Zeroconf

- Microsoft Windows ➡ APIPA (Automatic Private IP Adressing)
- Apple ➡ bonjour
- Linux ➡ avahi
<br><br>
> Zeroconf nur im Notfall verwenden. Meist ein Zeichen, dass etwas falsch konfiguriert ist.

---
transition: fade-out
---

# Physikalische Adresse (MAC)

- MAC (Media Access Control), eindeutig weltweite Identifizierung am Netzwerk
- Aufbau MAC-Adresse
    - `LL:LL:LL:XX:XX:XX` 
    - `LL`: Herstellercode
    - `XX`: Identifikationsteil
- Broadcast: `ff:ff:ff:ff:ff:ff`
- MAC-Adresse wird an OS weitergegeben, da besteht die Möglichkeit zur Veränderung

---
transition: fade-out
---

# Ethernet-Pakete (Frames)

- Daten werden mit Ethernet-Paketen transportiert
- Zerlegung der Daten in Einzelpakete, welche vom Sender zum Empfänger gesendet werden
![Aufbau Ethernet-Frame](https://res.cloudinary.com/luggs/image/upload/v1648625565/Informatik/Modul%20117/ethernet-frame.png)

- Typ: `0x800`: IPv4, `0x86DD`: IPv6
- Typ: `0x0806`: ARP, `0x0842`: Wake on LAN
- FCS: Frame Check Sequence

---
transition: fade-out
---

# ARP - Adress Resolution Protocol

- Ermittlung der zugehörigen IP-Adresse (v4) zu einer MAC-Adresse
- ARP fragt alle erreichbaren Teilnehmer, ob er die gesuchte IP besitzt (über `ff:ff:ff:ff:ff:ff`). Der Zielrechner mit der gewünschten IP antwortet mit der entsprechenden MAC-Adresse

```
Rechner 1 stellt Anfrage:
00:1e:33:0d:e9:f9 > ff:ff:ff:ff:ff:ff, ARP, length 42: arp who-has 192.168.0.1 tell 192.168.0.103

Rechner 1 erhält als Antwort von Rechner 2:
00:11:6b:62:93:2e > 00:1e:33:0d:e9:f9, ARP, length 60: arp reply 192.168.0.102 is-at 00:11:6b:62:93:2e
```
- ARP-Informationen werden gecached

---
transition: fade-out
---

# NDP - Neighbor Discovery Protocol

- Ermittlung der zugehörigen IP-Adresse (v6) zu einer MAC-Adresse
- Zur Fehlersuche helfen einige Fehlercodes

---
transition: fade-out
---

# IP-Adressen

- ab OSI-Schicht 3
- Analoge: IP-Adresse = Autokennzeichen, MAC-Adresse = Fahrgestellnummer
- IPv4 Adressen gehen aus, bei IPv6 sind 2^128 IP-Adressen vorhanden
- Regional Internet Registries: `AfriNIC` (Afrika), `APNIC` (Asien, Pazifik), `RIPE NCC` (Europa), `LACNIC` (Lateinamerika) und `ARIN` (Nordamerika)

---
transition: fade-out
---

# IPv4-Adressen

- Aufbau `NNN.NNN.NNN.NNN`
- Klassen
    - Klasse A: `0.0.0.0` - `127.255.255.255`
    - Klasse B: `128.0.0.0` - `191.255.255.255`
    - Klasse C: `192.0.0.0` - `223.255.255.255`
- Netz (N)- und Hostanteil (H) (Trennung anhand der Subnetzmaske)
    - Klasse A: `NNN.HHH.HHH.HHH`
    - Klasse B: `NNN.NNN.HHH.HHH`
    - Klasse C: `NNN.NNN.NNN.HHH`

---
transition: fade-out
---

# CIDR

- Classless Inter-Domain Routing (CIDR)
- Subnetzmaske nicht mehr dezimal (bspw. `255.255.255.0`), sondern binär (`11111111.11111111.11111111.00000000`)
- mehr Möglichkeiten zwischen Netz- und Hostanteil möglich, bspw. `11111111.11111111.11111111.11111000` = `255.255.255.248`
- Notation `192.168.1.36/29` (29x eine 1)
- CIDR-Berechnungen: https://www.ionos.de/digitalguide/server/knowhow/classless-inter-domain-routing/


---
transition: fade-out
---

# Zeroconf

- falls keine korrekte IP durch DHCP vergeben, wird Zeroconf (APIPA) verwendet
- Adressbereich `169.254.1.0` bis `169.254.254.255` wird vergeben
- Namensauflösung ohne DNS
- autom. Konfiguration greift tief ins OS ein. Vom Einsatz wird abgeraten

---
transition: fade-out
---

# IPv6-Adressen

- Integrierte Verschlüsselung von IP-Paketen (IPsec)
- Verwirklichung des Ende-zu-Ende-Prinzip, d.h. Wegfall von NAT (Network Address Translation)
- Hex. Schreibweise `fe80:0000:0000:0000:0223:54ff:fe5b:869d`
    - führende Blöcke mit `0` können weggelassen werden
    - aufeinanderfolgende Blöcke mit `0` dürfen ausgelassen  und mit einem `:` ersetzt werden
    - Bsp. von oben `fe80::223:54ff:fe5b:869d`
    - URL: `http://[fe80::223:54ff:fe5b:869d]:8080`

---
transition: fade-out
layout: cover
---

# DNS

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---
transition: fade-out
---

# Verwendung von Rechnernamen

- Datei hosts
- DNS (Domain Name Server)

![DNS Namensraum](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-namensraum.png)

---
transition: fade-out
---

# DNS - Wichtige Begriffe

- **autoritativ**: Der DNS-Server ist für eine Zone zuständig und die von ihm darüber ausgegebenen Informationen gelten als "sicher"
- **Primary Nameserver**: Der autoritative Server einer Zone
- **Secondary Nameserver**: zusätzlicher Nameserver für eine Zone mit den gleichen Informationen wie der autoritative Server (mittels Zonentransfer sichergestellt)
- **Nicht-autoritativ**: DNS-Server bezieht seine Informationen von anderen DNS-Servern
- **Caching-only-Nameserver**: Reiner Caching-Server

---
transition: fade-out
---

# DNS - Aufbau

![](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-aufbau.png)

---
transition: fade-out
---

# DNS - Resolver
![DNS-Resolver](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-resolver.png)

---
transition: fade-out
---

# Aufbau SOA-Record

```
$ORIGIN example.org.
$TTL 1750
@	IN	SOA	master.example.org admin\.master.example.org (
	2019040502	; serial
	86400		; refresh
	7200		; retry
	3600000	        ; expire
	1750		; minimum
)
	IN	NS	a.iana-servers.net.
www	IN	A	93.184.216.34
```
---
transition: fade-out
---

# Beschreibung SOA-Record

- **Zonenname**: kann durch `@` ersetzt werden, **Zonenklasse**: `IN`
- **Record-Type**: hier `SOA`
- **Primary Master**: primärer Nameserver
- **E-Mail Zonenbetreuer**: Kein @-Zeichen möglich
- **Seriennummer**: je höher, desto aktueller (normalerweise in der Form `YYYYMMDDlfd` (lfd = laufende Nummer))
- **Refresh** (Slave kontrolliert ob Änderungen), **Retry** (falls nicht erreichbar), **Expire** (Slave Zone läuft ab) und **TTL** (Vorhaltezeit von Anfragen mit negativer Antwort)

---
transition: fade-out
---

# Weitere Record-Typen

- `NS`: Nameserver (Zonendatei)
- `MX`: Mail-Server (Zonendatei)
- `A`: IPv4-Host (Zonendatei)
- `AAAA`: IPv6-Host (Zonendatei)
- `CNAME`: Verweis auf weiteren Host-Namen (Zonendatei)
- `PTR`: Zeiger (Revers-Zonendatei)

---
transition: fade-out
layout: cover
---

# Funktechnik

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# WLAN (Wireless LAN, Wi-Fi)

- WLAN
    - Normen wie IEEE 802.11a, 802.11ac, etc. https://de.wikipedia.org/wiki/IEEE_802.11
- GSM, UMTS etc.
    - GPRS, EDGE, UMTS, LTE, 5G, etc.

---
transition: fade-out
---

# WLAN - Betriebsarten

- Infrastrukturmodus
    Der Infrastruktur-Modus ähnelt im Aufbau dem Mobilfunknetz: Ein Wireless Access Point, oft in Form eines Routers, übernimmt die Koordination aller Clients und sendet in einstellbaren Intervallen (üblicherweise zehnmal pro Sekunde) kleine Datenpakete (füs SSID).
- Ad-hoc-Modus
    Kommunikation der Teilnehmenden untereinander, im Ad-hoc-Modus ist keine Station besonders ausgezeichnet, sondern alle sind gleichwertig.

---
transition: fade-out
---

# WLAN - Frequenzen und Kanäle

- 2.4 GHz
    Der Frequenzbereich im 2,4-GHz-Band wurde in 14 Kanäle aufgeteilt, es ist darauf zu achten, dass sich Frequenzbänder nicht überlappen (EU: 1, 5, 9, 13)
- 5 GHz

---
transition: fade-out
---

# WLAN - Sicherheit

- Offene Netze
- WEP
- WPA/WPA2
- WPA3 (aktuell)


---
transition: fade-out
layout: cover
---

# Protokolle

<style>
h1 {
  background-color: #ffffffff;
  background-image: linear-gradient(45deg, #ffffffff, #fcfcfcff);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
transition: fade-out
---

# Einleitung

- Verschlüsselte Fernsitzungen
- Verschlüsselte Datenübertragung
- SSH Tunnel

---
transition: fade-out
---

# SSH - Authentifizierung

- Anmeldung per Kennwort
- Anmeldung per Public-Key-Authentifizierung (zu bevorzugen)
    **Damit sind auch Scripte ohne Benutzereingriff möglich**

---
transition: fade-out
---

# SSH - Schlüssel erzeugen

1. Public und Private Key erzeugen mit `ssh-keygen`
1. Public Key auf das Zielsystem übertragen und umbenennen auf bswp. `id_rsa.pub-<Rechnername>`
1. Schlüssel nach `.ssh` verschieben
1. Prüfen, ob `authorized_keys` bereits besteht. Falls nicht, Schlüssel kopieren und unter dem Namen speichern. Ansonsten `cat id_rsa.pub-<Rechnername> >> authorized.keys`
1. Verbindung testen

---
transition: fade-out
---

# Anmeldung SSH

`ssh <Benutzer>@<Rechnername>`


---
transition: fade-out
---

# Aufbau SSH-Tunnel

`ssh -L<Port-Local>:<Rechner>:<Port> <Rechner>`

`ssh -L8080:netzbuch:80 netzbuch -p7167`


---
transition: fade-out
---

# TLS-Zertifikat

- Das SSL-Zertifikat dient zur Verschlüsselung und Authentisierung des ganzen Datentransfers zwischen dem Computer des Seitenbesuchers und dem Server.
- Es wird von der Zertifizierungsstelle ausgestellt, welche für die Webbrowser vertrauenswürdig oder nicht vertrauenswürdig sein kann. 
- Die nicht vertrauenswürdigen Zertifikate können Sie kostenlos auch selbst ausstellen (das sog. self-signed Zertifikat), jedoch wird der Zugriff der Besucher auf ihre Webseiten verschlechtert.

---
transition: fade-out
---

# TLS Handshake
- Bei TLS-Handshakes handelt es sich um eine Reihe von Datagrammen oder Nachrichten, die von einem Client und einem Server ausgetauscht werden. 
- Ein TLS-Handshake umfasst mehrere Etappen, da Client und Server Informationen austauschen müssen, um den Handshake abzuschliessen und weitere Kommunikation ermöglichen zu können.

---
transition: fade-out
---

# Nicht vertrauenswürdiges TLS-Zertifikat

![Zertifikat](https://res.cloudinary.com/luggs/image/upload/w_600/v1670399419/Informatik/Modul%20117/selfsigned_certificate.png)

---
transition: fade-out
---

# Vertrauenswürdige TLS-Zertifikate

- Das vertrauenswürdige Zertifikat wird immer von einer bekannten Zertifizierungsstelle ausgestellt, dem Ihr System vertrauen kann. 
- In der Praxis bedeutet das, dass dieses Zertifikat mit allen heute verwendeten Browsern kompatibel ist. 
- In IE und Chrome ist das Zertifikat vertrauenswürdig dank der SSL-Zertifikate in Windows. Firefox hat seine eigenen vertrauenswürdigen Zertifikate.

---
transition: fade-out
---

# Zertifizierungsstellen

- Symantec
- Thawte
- RapidSSL
- GeoTrust
- Etc.


