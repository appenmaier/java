---
title: Übungsaufgabe StaticAttributesAndMethods01
---

- Passe die Klasse `Vehicle` aus Übungsaufgabe [Constructors01](constructors01.md) mit Hilfe der abgebildeten Informationen an
- Passe die Klasse `Vehicle` so an, dass beim Erzeugen von Objekten das Attribut `numberOfVehicles` inkrementiert wird
- Passe die ausführbare Klasse aus Übungsaufgabe [Constructors01](constructors01.md) so an, dass mehrere Fahrzeuge erstellt werden und dass die Anzahl Fahrzeuge einmal vor und einmal nach den Objekterzeugungen ausgegeben wird

## Attribute der Klasse Vehicle

| Attribut | Datentyp | Sichtbarkeit | Level |
| -------- | -------- | ------------ | ----- |
| make | String | private | nicht-statisch |
| model | String | private | nicht-statisch |
| speed | double | private | nicht-statisch |
| _numberOfVehicles_ | _int_ | _private_ | _statisch_ |

## Methoden der Klasse Vehicle

| Methode | Rückgabewert | Sichtbarkeit | Level | Beschreibung |
| ------- | ------------ | ------------ | ----- | ------------ |
| Vehicle(String, String) | void | public | nicht-statisch | Festlegen des Herstellers und des Modells |
| getMake() | String | public | nicht-statisch | Rückgabe des Herstellers |
| getModel() | String | public | nicht-statisch | Rückgabe des Modells |
| getSpeed() | double | public | nicht-statisch | Rückgabe der Geschwindigkeit |
| accelerate(int) | void | public | nicht-statisch | Erhöhung der Geschwindigkeit um den eingehenden Wert |
| brake(int) | void | public | nicht-statisch | Reduzierung der Geschwindigkeit um den eingehenden Wert |
| print() | void | public | nicht-statisch | Ausgabe: Hersteller Modell |
| _getNumberOfVehicles()_ | _int_ | _public_ | _statisch_ | _Rückgabe der Anzahl Fahrzeuge_ |

## Konsolenausgabe

```markdown
Anzahl Fahrzeuge: 0
Anzahl Fahrzeuge: 3
Porsche 911
MAN TGX
Opel Zafira Life
```
