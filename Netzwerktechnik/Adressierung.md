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

# Adressierung im Netzwerk

<br> 




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

# Ethernet-Pakete (Frames)

- Daten werden mit Ethernet-Paketen transportiert
- Zerlegung der Daten in Einzelpakete, welche vom Sender zum Empfänger gesendet werden
![Aufbau Ethernet-Frame](https://res.cloudinary.com/luggs/image/upload/v1648625565/Informatik/Modul%20117/ethernet-frame.png)

- Typ: `0x800`: IPv4, `0x86DD`: IPv6
- Typ: `0x0806`: ARP, `0x0842`: Wake on LAN
- FCS: Frame Check Sequence
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
# NDP - Neighbor Discovery Protocol

- Ermittlung der zugehörigen IP-Adresse (v6) zu einer MAC-Adresse
- Zur Fehlersuche helfen einige Fehlercodes


---
# IP-Adressen

- ab OSI-Schicht 3
- Analoge: IP-Adresse = Autokennzeichen, MAC-Adresse = Fahrgestellnummer
- IPv4 Adressen gehen aus, bei IPv6 sind 2^128 IP-Adressen vorhanden
- Regional Internet Registries: `AfriNIC` (Afrika), `APNIC` (Asien, Pazifik), `RIPE NCC` (Europa), `LACNIC` (Lateinamerika) und `ARIN` (Nordamerika)

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
# CIDR

- Classless Inter-Domain Routing (CIDR)
- Subnetzmaske nicht mehr dezimal (bspw. `255.255.255.0`), sondern binär (`11111111.11111111.11111111.00000000`)
- mehr Möglichkeiten zwischen Netz- und Hostanteil möglich, bspw. `11111111.11111111.11111111.11111000` = `255.255.255.248`
- Notation `192.168.1.36/29` (29x eine 1)
- CIDR-Berechnungen: https://www.ionos.de/digitalguide/server/knowhow/classless-inter-domain-routing/

---
# Zeroconf

- falls keine korrekte IP durch DHCP vergeben, wird Zeroconf (APIPA) verwendet
- Adressbereich `169.254.1.0` bis `169.254.254.255` wird vergeben
- Namensauflösung ohne DNS
- autom. Konfiguration greift tief ins OS ein. Vom Einsatz wird abgeraten

---
# IPv6-Adressen

- Integrierte Verschlüsselung von IP-Paketen (IPsec)
- Verwirklichung des Ende-zu-Ende-Prinzip, d.h. Wegfall von NAT (Network Address Translation)
- Hex. Schreibweise `fe80:0000:0000:0000:0223:54ff:fe5b:869d`
    - führende Blöcke mit `0` können weggelassen werden
    - aufeinanderfolgende Blöcke mit `0` dürfen ausgelassen  und mit einem `:` ersetzt werden
    - Bsp. von oben `fe80::223:54ff:fe5b:869d`
    - URL: `http://[fe80::223:54ff:fe5b:869d]:8080`






