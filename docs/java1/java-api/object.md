---
title: Die Mutter aller Klassen
---

Alle Klassen in Java sind letztlich Unterklassen der Klasse `Object`. Daher wird diese auch als die Mutter aller Klassen bezeichnet. Die Klasse vererbt ihren 
Unterklassen wichtige Methoden, die jede Unterklasse überschreiben sollte:
- Die Methode `equals(Object)` prüft zwei Objekte auf Gleichheit[^1]
- Die Methode `hashCode()` liefert den Hashcode des aktuellen Objektes zurück
- Die Methode `toString()` liefert eine eindeutige Kennung des Objektes in der Form _[Vollständiger Klassenname]_@_[Adresse des Objektes im Hauptspeicher in 
hexadezimaler Notation]_[^2] zurück

> Wird den print-Methoden des Ausgabestroms `System.out` eine Objektreferenz übergeben, wird implizit die Methode `toString()` des jeweiligen Objektes aufgerufen.

[^1]: Zwei Objekte sind gleich, wenn all ihre Attribute gleich sind
[^2]: Der vollständige Klassennamen setzt sich aus den Paketen sowie dem eigentlichen Klassennamen zusammen
