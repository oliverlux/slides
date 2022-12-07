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

# TLS - Transport Layer Security

<br> 




---
# TLS-Zertifikat

- Das SSL-Zertifikat dient zur Verschlüsselung und Authentisierung des ganzen Datentransfers zwischen dem Computer des Seitenbesuchers und dem Server.
- Es wird von der Zertifizierungsstelle ausgestellt, welche für die Webbrowser vertrauenswürdig oder nicht vertrauenswürdig sein kann. 
- Die nicht vertrauenswürdigen Zertifikate können Sie kostenlos auch selbst ausstellen (das sog. self-signed Zertifikat), jedoch wird der Zugriff der Besucher auf ihre Webseiten verschlechtert.

---
# TLS Handshake
- Bei TLS-Handshakes handelt es sich um eine Reihe von Datagrammen oder Nachrichten, die von einem Client und einem Server ausgetauscht werden. 
- Ein TLS-Handshake umfasst mehrere Etappen, da Client und Server Informationen austauschen müssen, um den Handshake abzuschliessen und weitere Kommunikation ermöglichen zu können.

---

# Nicht vertrauenswürdiges TLS-Zertifikat

![Zertifikat](https://res.cloudinary.com/luggs/image/upload/w_600/v1670399419/Informatik/Modul%20117/selfsigned_certificate.png)

---
# Vertrauenswürdige TLS-Zertifikate

- Das vertrauenswürdige Zertifikat wird immer von einer bekannten Zertifizierungsstelle ausgestellt, dem Ihr System vertrauen kann. 
- In der Praxis bedeutet das, dass dieses Zertifikat mit allen heute verwendeten Browsern kompatibel ist. 
- In IE und Chrome ist das Zertifikat vertrauenswürdig dank der SSL-Zertifikate in Windows. Firefox hat seine eigenen vertrauenswürdigen Zertifikate.


---
# Zertifizierungsstellen

- Symantec
- Thawte
- RapidSSL
- GeoTrust
- Etc.



---
# Arbeitsauftrag

Analysieren Sie ein SSL Zertifikat und versuchen Sie Informationen zur Zertifizierungsstelle herauszufinden.
1. Welche Informationen finden Sie im Zertifikat?
1. Welche Informationen finden Sie über die Zertifizierungsstelle?
1. Recherchieren Sie, wie teuer ein SSL Zertifikat bei der jeweiligen Registrierungsstelle ist.
1. Was ist «Let’s encrypt»?

Erstellen Sie dazu ein kurzes Dokument mit Ihren Antworten.








