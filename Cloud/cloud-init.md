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

> Aus einem generischen Image wird automatisch ein konfigurierter Server.

---

## Warum Cloud-Init?

| Ohne Cloud-Init | Mit Cloud-Init |
|---|---|
| Manuelles Login per SSH nach dem Start | Server ist nach dem Boot fertig eingerichtet |
| Fehleranfällig, nicht reproduzierbar | Gleiche Konfiguration = gleiches Ergebnis |
| Schlecht skalierbar | Beliebig viele Instanzen identisch |
| Dokumentation getrennt vom Setup | Konfiguration *ist* die Dokumentation |

> Grundlage für **Infrastructure as Code** und Automatisierung

---
# Möglichkeiten mit cloud-init

- Automatisches Installieren und Konfigurieren von Software
- Anpassungen am Hostname
- Konfiguration von SSH-Keys
- Erstellen von Benutzern und Gruppen
- Abarbeiten von Skripten
- ...

---

## Das `#cloud-config`-Format

- User-Data im **YAML**-Format
- Die **erste Zeile** muss exakt `#cloud-config` lauten
- Einrückung mit **Leerzeichen**, keine Tabs
- Jeder Schlüssel steuert ein Modul

```yaml
#cloud-config
hostname: web01
timezone: Europe/Zurich
package_update: true
```

---

## Wichtige Module

| Modul | Zweck |
|---|---|
| `users` / `groups` | Benutzer und Gruppen anlegen |
| `ssh_authorized_keys` | SSH-Schlüssel hinterlegen |
| `package_update` / `package_upgrade` | Paketquellen aktualisieren |
| `packages` | Software installieren |
| `write_files` | Dateien mit Inhalt anlegen |
| `runcmd` | Befehle beim ersten Boot ausführen |
| `hostname` / `timezone` | Systemeinstellungen |

---

## Beispiel: Benutzer anlegen

```yaml
#cloud-config
users:
  - name: oli
    groups: sudo
    shell: /bin/bash
    sudo: ALL=(ALL) NOPASSWD:ALL
    ssh_authorized_keys:
      - ssh-ed25519 AAAAC3Nza... oli@laptop
```

- Login nur per **SSH-Key**, kein Passwort
- `sudo`-Rechte ohne Passwortabfrage

---

## Praxisbeispiel: Webserver

```yaml
#cloud-config
package_update: true
packages:
  - nginx
write_files:
  - path: /var/www/html/index.html
    content: |
      <h1>Hallo aus Cloud-Init!</h1>
runcmd:
  - systemctl enable --now nginx
```

Nach dem Start: Webserver läuft und liefert die eigene Startseite aus.

---

## Cloud-Init verwenden

**AWS EC2** – User-Data beim Start angeben:

```bash
aws ec2 run-instances --image-id ami-xxxx \
  --instance-type t3.micro \
  --user-data file://cloud-config.yaml
```
---

# Weitere Informationen

- [Informationen cloud-init von IONOS](https://www.ionos.de/hilfe/server-cloud-infrastructure/serveradministration/serverkonfiguration-mit-cloud-init-allgemeine-informationen/)
- [Warum ist cloud-init so cool](https://contabo.com/blog/de/was-ist-cloud-init/)
- [cloud-init Dokumentation](https://cloudinit.readthedocs.io/en/latest/)
