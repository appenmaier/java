---
title: Übungsaufgabe ObjectsAndReferences01
---

- Erstelle die Klasse `Vehicle` mit Hilfe der abgebildeten Informationen
- Erstelle eine ausführbare Klasse, welches ein Fahrzeug erzeugt, lege Hersteller und Modell fest und lasse das Fahrzeug mehrmals beschleunigen und bremsen

## Attribute der Klasse Vehicle
| Attribut | Datentyp | Sichtbarkeit |
| -------- | -------- | ------------ |
| make     | String   | private      |
| model    | String   | private      |
| speed    | double   | private      |

## Methoden der Klasse Vehicle
| Methode          | Rückgabewert | Sichtbarkeit | Beschreibung                                            |
| ---------------- | ------------ | ------------ | ------------------------------------------------------- |
| setMake(String)  | void         | public       | Festlegen des Herstellers                               |
| setModel(String) | void         | public       | Festlegen des Modells                                   |
| getMake()        | String       | public       | Rückgabe des Herstellers                                |
| getModel()       | String       | public       | Rückgabe des Modells                                    |
| getSpeed()       | double       | public       | Rückgabe der Geschwindigkeit                            |
| accelerate(int)  | void         | public       | Erhöhung der Geschwindigkeit um den eingehenden Wert    |
| brake(int)       | void         | public       | Reduzierung der Geschwindigkeit um den eingehenden Wert |
| print()          | void         | public       | Ausgabe: Hersteller Modell                              |

## Konsolenausgabe
```markdown
Porsche 911 beschleunigt auf 30km/h
Porsche 911 beschleunigt auf 60km/h
Porsche 911 bremst auf 40km/h ab
Porsche 911 beschleunigt auf 80km/h
```
