---
title: Test Doubles
---

Oftmals werden zum Testen einer Methode andere Objekte bzw. Komponenten benötigt, die vom Test bereitgestellt werden müssen. Zum Testen können entweder die realen 
Komponenten, oder aber sogenannte **Test Doubles** verwendet werden:
- Eine **Fälschung** (Fake) imitiert eine reale Komponente
- Eine **Attrappe** (Dummy) ist ein Platzhalter für ein Objekt, welches im Test nicht benötigt wird
- Ein **Stummel** (Stub) gibt bei Aufruf einen festen Wert zurück; wird also für eingehende Aufrufe verwendet
- Eine **Nachahmung** (Mock) zeichnet die Methodenaufrufe an ihr auf und kann zurückgeben, welche Methode wie oft mit welchen Parametern aufgerufen wurde; wird also für 
ausgehende Aufrufe verwendet
- Ein **Spion** (Spy) kann ähnlich wie eine Nachahmung Methodenaufrufe aufzeichnen, kann diese aber auch die reale Komponente weiterleiten

Test Doubles sollen die Abhängigkeiten des **SUT**[^1] minimieren und für vorhersagbare Ergebnisse sorgen.

[^1]: System under Test
