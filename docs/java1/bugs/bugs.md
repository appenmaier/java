---
title: Programmfehler (Bugs)
---

**Programmfehler** (Bugs) führen dazu, dass Programme unerwartete Ergebnisse liefern oder abstürzen. Je komplexer das Programm, desto wichtiger wird eine durchdachte und konsequente Fehlerbehandlung.

**Kompilierungsfehler** sind Programmfehler, die verhindern, dass das Programm ausgeführt werden kann. Sie können relativ einfach behoben werden, da sie schon zur Designzeit auftreten und von den meisten Entwicklungsumgebungen direkt angezeigt werden.

Verhält sich das Programm nicht wie beabsichtigt, spricht man von **Logikfehlern**. Sie sind mit am schwersten zu entdecken und zu beheben. Zur Unterstüzung bei der Fehlersuche und -behandlung kann unter Anderem der [Debugger](debugging.md) verwendet werden.

**Laufzeitfehler** treten erst beim Ausführen des Programms auf. Sie entstehen meist dann, wenn das Programm versucht, eine Operation auszuführen, die nicht ausgeführt werden kann (z.B. die Division durch Null). Diese Situationen werden als [Ausnahmen (Exceptions)](exceptions.md).
