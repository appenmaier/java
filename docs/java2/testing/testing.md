---
title: Softwaretests
---

Softwaretests sollen sicherstellen, dass bei der Entwicklung oder Änderung einer Software der Quellcode in allen festgelegten Anwendungsfällen korrekt funktioniert. Mit
Hilfe von Softwaretests können Softwareentwickler im Idealfall schon während des Entwicklungsprozesses mögliche Fehler identifizieren und beheben.

Man unterscheidet bei Softwaretests zwischen verschiedenen Testarten, die in der Testpyramide dargestellt werden:
- Akzeptanztests: Testen des gesamten Systems unter realitätsgetreuen Bedingungen
- Systemtests: Testen des gesamten Systems
- Integrationstests: Testen mehrerer, voneinander abhängiger Komponenten
- Komponententests: Testen einzelner, abgeschlossener Softwarebausteine

![image](https://user-images.githubusercontent.com/47243617/171476574-eebee507-6ab3-4b57-9130-ac097785c4cc.png)

[Komponententests (Unit Tests)](unit-tests.md) spielen vor allem bei der [testgetriebenen Entwicklung (Test Driven Development)](tdd.md) eine große Rolle. Da gerade bei Komponententests die zu testenden Klassen teilweise viele Abhängigkeiten besitzen, kommen hierfür oftmals [Test Doubles](test-doubles.md) zum Einsatz. 
