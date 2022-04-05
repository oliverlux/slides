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

# SSH

<br> 




---
# Einleitung

- Verschlüsselte Fernsitzungen
- Verschlüsselte Datenübertragung
- SSH Tunnel

---

# SSH - Authentifizierung

- Anmeldung per Kennwort
- Anmeldung per Public-Key-Authentifizierung (zu bevorzugen)
    **Damit sind auch Scripte ohne Benutzereingriff möglich**

---
# SSH - Schlüssel erzeugen

1. Public und Private Key erzeugen mit `ssh-keygen`
1. Public Key auf das Zielsystem übertragen und umbenennen auf bswp. `id_rsa.pub-<Rechnername>`
1. Schlüssel nach `.ssh` verschieben
1. Prüfen, ob `authorized_keys` bereits besteht. Falls nicht, Schlüssel kopieren und unter dem Namen speichern. Ansonsten `cat id_rsa.pub-<Rechnername> >> authorized.keys`
1. Verbindung testen

---
# Anmeldung SSH

`ssh <Benutzer>@<Rechnername>`


---
# Aufbau SSH-Tunnel

`ssh -L<Port-Local>:<Rechner>:<Port> <Rechner>`

`ssh -L8080:netzbuch:80 netzbuch -p7167`







