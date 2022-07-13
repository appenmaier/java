---
title: Gestaltungsrichtlinien (Design Principles)
---

Unter Gestaltungsprinzipien (Design Principles) versteht man Richtlinien, welche eine hohe Softwarequalität sicherstellen sollen. Neben einfachen Gestaltungsprinzipen
wie **DRY**[^1], **KISS**[^2] und **YAGNI**[^3], sind in der objektorientierten Programmierung vor allem die SOLID-Prinzipen sowie die Prinzipien **Separation of Concerns** und **Inversion of Control** von Bedeutung.

## Die SOLID-Prinzipien
Hinter dem Akronym SOLID verbergen sich 5 Gestaltungsprinzipien:
- Single Responsibility Principle: jede Klasse sollte genau eine Verantwortung besitzen
- Open Closed Principle: Software-Einheiten sollten offen für Erweiterungen, aber geschlossen für Modifikationen sein
- Liscov Substitution Principle: Objekte von Unterklassen sollten sich so Verhalten wie Objekte der dazugehörigen Oberklasse
- Interface Segregation Principle: Klassen sollten nur Methoden implementieren müssen, die sie auch verwenden
- Dependency Inversion Principle: Abhängigkeiten sollten immer von den konkreten zu den abstrakten Modulen verlaufen

> Das Akronym SOLID geht auf den Softwareentwickler Robert C. Martin zurück, der unter anderem auch an der Entwicklung des Agilen Manifests[^4] beteiligt war.

## Separation of Concerns
Unter dem Begriff **Separation of Concerns** versteht man in der Informatik das Gestaltungsprinzip, die verschiedenen Aufgaben einer Anwendung in verschiedene Bereiche aufzuteilen. Grafische Benutzeroberflächen werden zum Beispiel in der Regel in die Bereiche Aufbau, Aussehen und Verhalten aufgeteilt.

![image](https://user-images.githubusercontent.com/47243617/170881912-9a82825c-4f88-401c-adc1-369de09ccecf.png)

## Inversion of Control
Der Begriff **Inversion of Control** beschreibt die Arbeitsweise von Frameworks[^5]:
- Die Funktionen einer Anwendung werden beim Framework registriert, welches die Funktionen zu einem späteren Zeitpunkt aufruft
- Die Steuerung des Kontrollfluss obliegt nicht der Anwendung, sondern dem Framework

Die Umkehr der Steuerung kann auch als Anwendung des Hollywood-Prinzips[^6] verstanden werden.

[^1]: Don´t Repeat Yourself
[^2]: Keep It Simple, Stupid
[^3]: You Ain´t Gonna Need It
[^4]: Das Agile Manifest wurde 2001 verfasst und umfasst die vier wesentlichen Leitsätze der agilen Softwareentwicklung
[^5]: Unter einem Framework versteht man ein Programmiergerüst, welches die Architektur für die Anwendung vorgibt und den Kontrollfluss der Anwendung steuert
[^6]: Don´t call us, we´ll call you
