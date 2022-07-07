---
title: Übungsaufgabe ElementAccess03
---

Erstelle eine ausführbare Klasse zum Berechnen von ISBN-Prüfziffern[^1].

## Konsolenausgabe

```markdown
Gib bitte eine ISBN ohne Prüfziffer ein: 978376572781
Ergebnis: Die Prüfziffer lautet 8
```

## Formel

```
z13 = (10 - ((z1 + z3 + z5 + z7 + z9 + z11 + 3*(z2 + z4 + z6 + z8 + z10 + z12))mod10))mod10
```

>	Die Methode `charAt(int)` der Klasse `String` gibt das Zeichen mit dem Index der eingehenden Zahl zurück, die statische Methode `getNumericalValue(char)` der Klasse 
`Character` den ganzzahligen Wert des eingehenden Zeichens.

[^1]: Eine ISBN besteht aus 13 Ziffern (die 13. Ziffer stellt die Prüfziffer dar)
