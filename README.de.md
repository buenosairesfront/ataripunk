[English](README.md) · [Español](README.es.md) · [Français](README.fr.md) · **Deutsch** · [日本語](README.ja.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md)

# U-MA Atari Punk

Eine Atari Punk Console zum Aufbauen am Bildschirm: zwei NE555, einer als Takt, einer als Impuls, der erst nach Ablauf wieder auslöst. Ändere jedes Bauteil außer den beiden 555, sieh sie auf einem Vierkanal-Oszilloskop und hör das Ergebnis live.

**▶ App öffnen:** https://buenosairesfront.github.io/ataripunk/

Keine Installation nötig. Die Oberfläche ist auf Spanisch.

## So funktioniert's

### Oszilloskop
Oben vier Spuren: Spannung an C1 (Pin 6 von IC1), Ausgang IC1, Spannung an C2 (Pin 6 von IC2) und das Lautsprechersignal. Anzeigen für Taktfrequenz, Impulsdauer, Teilung ÷n und Ausgangston.

### 01 · Die Schaltung
Der komplette Schaltplan. Tippe ein Bauteil an, um es zu ändern: Batterie (4,5–15 V), R1, R2, R3, Potis VR1 und VR2 (Wert, Stellung, Kennlinie A/B), C1, C2, C3 und Lautsprecher. Per Schieberegler, E12/E6-Normwerten oder Eingabe wie auf der Platine: `4k7`, `10n`, `100u`, `2M2`. Die beiden NE555 sind gesperrt. Fünf Presets.

### 02 · Spielen
Ein XY-Pad (X = VR1, Y = VR2), dessen Hintergrund eine Pixelkarte der Teilungen ist: jede Farbe ein ÷n, Helligkeit = Tonhöhe. Regler für VR1, VR2 und Lautstärke sowie ein Gate-Modus.

### 03 · Die Treppe
Ausgangsfrequenz über der Stellung von VR1. Gestrichelt: der Takt; dick: was man hört, unterbrochen, wo die Teilung springt. Das ist der Stufenklang der Atari Punk.

### 04 · Die Platine
Eine illustrative Platine mit realistischen Bauteilen: Farbringe, Keramik-Codes (103 = 10 nF) und Potiachsen folgen deinen Werten; ab 1 µF wird der Kondensator zum Elko.

### 05 · Stückliste
Alle Bauteile mit aktuellen Werten und Codes, zum Kopieren.

## Unter der Haube

Eine einzige `index.html` ohne Abhängigkeiten. Der Klang kommt aus einem ereignisgenauen Modell der beiden 555, Sample für Sample in einem AudioWorklet berechnet, mit dem Hochpass aus C3 und Last. Es ist eine Näherung: die Belastung des 555-Ausgangs wird ignoriert.

## Lokal starten

`index.html` herunterladen und öffnen oder den Ordner ausliefern:

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**Mehr von U-MA:** alle Instrumente und Werkzeuge an einem Ort → [U-MA-Übersicht](https://github.com/buenosairesfront/U-ma/blob/main/README.de.md)
<!-- /u-ma:more -->

## Credits

Atari Punk Console: Originalentwurf von Forrest M. Mims III (Stepped Tone Generator). App von U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/).
