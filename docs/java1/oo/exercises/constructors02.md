---
title: Übungsaufgabe Constructors02
---

- Erstelle die Klasse `Dice` mit Hilfe der abgebildeten Informationen
- Erstelle eine ausführbare Klasse, welche einen Würfel erzeugt. Es soll 5-mal hintereinander gewürfelt und das Ergebnis des Wurfes ausgegeben werden

## Attribute der Klasse Dice

| Attribut | Datentyp | Sichtbarkeit |
| -------- | -------- | ------------ |
| _id_ | _int_ | _private_ |
| _value_ | _int_ | _private_ |

## Methoden der Klasse Dice

| Methode | Rückgabewert | Sichtbarkeit | Beschreibung |
| ------- | ------------ | ------------ | ------------ |
| _Dice(int)_ | _void_ | _public_ | _Setzen der ID_ |
| _getId()_ | _int_ | _public_ | _Rückgabe der ID_ |
| _getValue_ | _int_ | _public_ | _Rückgabe des Wertes_ |
| _rollTheDice()_ | _void_ | _public_ | _Setzen des Wertes_ |

## Konsolenausgabe

```markdown
ID - Würfelwert
1 - 1
1 - 2
1 - 5
1 - 3
1 - 2
```
