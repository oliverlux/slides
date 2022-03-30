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

# IP-Adressen in der Praxis

<br> 




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

# Zeroconf

- Microsoft Windows ➡ APIPA (Automatic Private IP Adressing)
- Apple ➡ bonjour
- Linux ➡ avahi

> Zeroconf nur im Notfall verwenden. Meist ein Zeichen, dass etwas falsch konfiguriert ist.

---
# Verwendung von Rechnernamen

- Datei hosts
- DNS (Domain Name Server)

![DNS Namensraum](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-namensraum.png)

---
# DNS - Wichtige Begriffe

- **autoritativ**: Der DNS-Server ist für eine Zone zuständig und die von ihm darüber ausgegebenen Informationen gelten als "sicher"
- **Primary Nameserver**: Der autoritative Server einer Zone
- **Secondary Nameserver**: zusätzlicher Nameserver für eine Zone mit den gleichen Informationen wie der autoritative Server (mittels Zonentransfer sichergestellt)
- **Nicht-autoritativ**: DNS-Server bezieht seine Informationen von anderen DNS-Servern
- **Caching-only-Nameserver**: Reiner Caching-Server

---

# DNS - Aufbau

![](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-aufbau.png)

---

# DNS - Resolver
![DNS-Resolver](https://res.cloudinary.com/luggs/image/upload/v1648640975/Informatik/Modul%20117/dns-resolver.png)

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

# Beschreibung SOA-Record

- **Zonenname**: kann durch `@` ersetzt werden, **Zonenklasse**: `IN`
- **Record-Type**: hier `SOA`
- **Primary Master**: primärer Nameserver
- **E-Mail Zonenbetreuer**: Kein @-Zeichen möglich
- **Seriennummer**: je höher, desto aktueller (normalerweise in der Form `YYYYMMDDlfd` (lfd = laufende Nummer))
- **Refresh** (Slave kontrolliert ob Änderungen), **Retry** (falls nicht erreichbar), **Expire** (Slave Zone läuft ab) und **TTL** (Vorhaltezeit von Anfragen mit negativer Antwort)

---

# Weitere Record-Typen

- `NS`: Nameserver (Zonendatei)
- `MX`: Mail-Server (Zonendatei)
- `A`: IPv4-Host (Zonendatei)
- `AAAA`: IPv6-Host (Zonendatei)
- `CNAME`: Verweis auf weiteren Host-Namen (Zonendatei)
- `PTR`: Zeiger (Revers-Zonendatei)




