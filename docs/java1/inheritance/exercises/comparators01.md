---
title: Übungsaufgabe Comparators01
---

- Erstelle die Klasse `Coordinate` anhand des abgebildeten Klassendiagramms
- Erstelle eine ausführbare Klasse, welche eine Koordinatenliste mit mehreren Koordinaten erzeugt, diese sortiert und anschließend auf der Konsole ausgibt

## Klassendiagramm
![image](https://user-images.githubusercontent.com/47243617/170883361-ce10024b-9dfe-4d83-8b73-3bd470208a13.png)

## Hinweise zur Klasse Coordinate
- Die Methode `getDistanceToOriginPoint()` soll die Distanz der Koordinate zum Nullpunkt zurückgeben
- Die Methode `compareTo(Coordinate)` soll die Koordinate mit der eingehenden Koordinate anhand ihrer jeweiligen Distanz zum Nullpunkt vergleichen. Ist die Distanz der Koordinate zum Nullpunkt kleiner als bzw. größer als bzw. gleich die der eingehenden Koordinate, soll der Wert 1 bzw. -1 bzw. 0 zurückgegeben werden 

## Hinweis
Die statische Methode `hypot(double, double)` der Klasse `Math` berechnet die Hypotenuse zum eingehenden X- und Y-Wert.
