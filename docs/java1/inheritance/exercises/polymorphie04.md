---
title: Übungsaufgabe Polymorphie04
---

- Passe die Klasse `Dice` aus Übungsaufgabe [ClassDiagrams02](../../uml/exercises/class-diagrams02.md) anhand des abgebildeten Klassendiagramms an und erstelle die Klassen `HighValueDice` und `LowValueDice`
- Passe die Klasse `Player` aus Übungsaufgabe [ClassDiagrams02](../../uml/exercises/class-diagrams02.md) anhand des abgebildeten Klassendiagramms an
- Passe die Methode `move(Player)` der Klasse `DiceGame` aus Übungsaufgabe [ClassDiagrams02](../../uml/exercises/class-diagrams02.md) so an, dass jeder Spieler während des Spiels einmal die Möglichkeit hat, entweder nur mit 4-5-6-Würfeln oder 1-2-3-Würfeln zu würfeln

## Klassendiagramm
![image](https://user-images.githubusercontent.com/47243617/170884123-4f6ae3ad-612d-490c-94f3-1f9882b38002.png)

## Hinweis zur Klasse HighValueDice
Die rollTheDice-Methode soll nur 4er, 5er und 6er würfeln.

## Hinweis zur Klasse LowValueDice
Die rollTheDice-Methode soll nur 1er, 2er und 3er würfeln.

## Konsolenausgabe
```markdown
Hans hat aktuell 0 Punkte
Hans, möchtest Du einmalig Spezialwürfel verwenden (true, false)?: true
Hans, welche Spezialwürfel möchtest Du verwenden (1=4-5-6-Würfel, 2=1-2-3-Würfel)?: 1
Hans, möchtest Du würfeln (true, false)?: true
Hans hat 12 Punkte
Hans hat insgesamt 12 Punkte
…
Lisa hat aktuell 46 Punkte
Lisa, möchtest Du würfeln (true, false)?: true
Lisa hat 12 Punkte
Lisa hat insgesamt 58 Punkte
Lisa hat verloren
Der Sieger heißt Hans und hat 49 Punkte
```
