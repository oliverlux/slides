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

# Boxmodell

<br> 






---

# "Klassisches" Boxmodell

- Mit CSS können Elementen (feste) Breiten, Höhen und Abstände gegeben und diese nebeneinander positioniert werden.
- Die rechteckigen Blöcke, die im Elementbaum erzeugt und auf dem Bildschirm dargestellt werden, folgen einem Schema, dem „Box-Modell“. Es ist somit Grundlage jeden Layouts.
- Jedes Block-Element wie Textabsätze (p), -Abschnitte (div, article, main, aside, …) und Überschriften (h1, h2, …) bildet eine rechteckige Box, die frei formatiert werden kann.

---
# Theorie Boxmodell (Teil 1)

![width:650px](https://wiki.selfhtml.org/images/f/f3/Box-Modell.svg)


---

# Theorie Boxmodell (Teil 2)

- Die Gesamthöhe einer Box wird berechnet durch `margin-left + border-left + padding-left + width + padding-right + border-right + margin-right`
- Interaktive Demo: http://codepen.io/carolineartz/full/ogVXZj

---

# Alternatives Boxmodell

- Mit CSS3 wurde das starre Konzept des Boxmodells angepasst. Mithilfe der Eigenschaft box-sizing lässt sich spezifizieren, worauf sich die Angaben von width bzw. height beziehen sollen.
- Durch `box-sizing: border-box` werden Innenabstand und Randlinie nun ohne weitere Berechnung von uns durch den Browser bei der Breitenberechnung berücksichtigt.

---

# Boxen nebeneinander

Die Eigenschaft float legt fest, in welche Richtung ein Element verschoben wird. Erlaubt sind dabei folgende Werte:
- `none`: Standardwert; das Element wird nicht verschoben.
- `left`: Das Element wird nach links verschoben.
- `right`: Das Element wird nach rechts verschoben.
- `inherit`: Der Wert der float-Eigenschaft des Elternelements wird geerbt.







