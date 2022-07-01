---
title: Übungsaufgabe Exceptions01
---

- Passe die Klasse `Vehicle` aus Übungsaufgabe [Interfaces01](../inheritance/exercises/interfaces01.md) anhand des abgebildeten Klassendiagramms an und erstelle die Ausnahmenklasse 
`InvalidValueException`
- Passe die ausführbare Klasse aus Übungsaufgabe [Interfaces01](../inheritance/exercises/interfaces01.md) so an, dass sie fehlerfrei ausgeführt werden kann

## Klassendiagramm
![image](https://user-images.githubusercontent.com/47243617/176827972-1ad44ba0-46ec-4f21-933b-1a6b1f042e87.png)

## Hinweise zur Klasse Vehicle
- In der Methode `accelerate(int)` soll bei einem Wert kleiner gleich Null die Ausnahme `InvalidValueException` ausgelöst werden
- In der Methode `brake(int)` soll bei einem Wert kleiner gleich Null die Ausnahme `InvalidValueException` ausgelöst werden
