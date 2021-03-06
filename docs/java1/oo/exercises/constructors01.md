---
title: Übungsaufgabe Constructors01
---

- Passe die Klasse `Vehicle` aus Übungsaufgabe [ObjectsAndReferences01](objects-and-references01.md) mit Hilfe der abgebildeten Informationen an
- Passe die ausführbare Klasse aus Übungsaufgabe [ObjectsAndReferences01](objects-and-references01.md) so an, dass sie fehlerfrei ausgeführt werden kann

## Attribute der Klasse Vehicle

| Attribut | Datentyp | Sichtbarkeit |
| -------- | -------- | ------------ |
| make | String | private |
| model | String | private |
| speed | double | private |

## Methoden der Klasse Vehicle

| Methode | Rückgabewert | Sichtbarkeit | Beschreibung |
| ------- | ------------ | ------------ | ------------ |
| _~setMake(String)~_ | _~void~_ | _~public~_ | _~Festlegen des Herstellers~_ |
| _~setModel(String)~_ | _~void~_ | _~public~_ | _~Festlegen des Modells~_ |
| _Vehicle(String, String)_ | _void_ | _public_ | _Festlegen des Herstellers und des Modells_ |
| getMake() | String | public | Rückgabe des Herstellers |
| getModel() | String | public | Rückgabe des Modells |
| getSpeed() | double | public | Rückgabe der Geschwindigkeit |
| accelerate(int) | void | public | Erhöhung der Geschwindigkeit um den eingehenden Wert |
| brake(int) | void | public | Reduzierung der Geschwindigkeit um den eingehenden Wert |
| print() | void | public | Ausgabe: Hersteller Modell |
