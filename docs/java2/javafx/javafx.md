---
title: JavaFX-Anwendungen
---

JavaFX stellt ein Framework[^1] zur Entwicklung plattformübergreifender grafischer Benutzeroberflächen dar. Eine grafische Benutzeroberfläche oder auch Graphical User Interface (GUI)[^2] hat die Aufgabe, Programme mittels grafischer Bildschirmelemente bedienbar zu machen:
- **Controls** wie Eingabefelder, Drucktasten und Ausgabefelder ermöglichen die Interaktion mit der Anwendung
- **Container** wie Horizontalboxen und Bereichscontainer ermöglichen die strukturierte Darstellung und Verwaltung anderer Bildschirmelemente:
- **Dialoge** wie Nachrichtendialoge und Dateiauswahl-Dialoge stellen vordefinierte Oberflächen dar, mit deren Hilfe wiederkehrende Anwendungsfälle abgedeckt werden können

![image](https://user-images.githubusercontent.com/47243617/170096955-acb2be70-1dea-40a8-820a-b66792c45460.png)

## Aufbau einer JavaFX-Anwendung
Eine JavaFX-Anwendung besteht aus einer oder mehreren **Bühnen** (Stages), die beliebig vielen **Szenen** (Scenes) enthalten können, wobei jede Szene wiederum beliebig viele **Bildschirmelemente** (Nodes) enthalten kann:
- Die Bühne stellt den Rahmen für den tatsächlichen Inhalt bereit
- Eine Szene verwaltet den sogenannten **Szenegraphen**, der den sichtbaren Teil einer grafischen Benutzeroberfläche repräsentiert
- Ein Bildschirmelement ist Teil des Szenegraphen und kann entweder zur Strukturierung (Container) oder zur Interaktion (Control) genutzt werden

![image](https://user-images.githubusercontent.com/47243617/170097082-91fb3635-d5a6-46c4-aaa5-a082abe42bad.png)

## Der Szenegraph
Der Szenegraph verwaltet die einzelnen Bildschirmelemente einer Szene. Die Elemente eines Graphen werden als Knoten, der Ursprung des Graphen als Wurzel-Knoten 
bezeichnet.

![image](https://user-images.githubusercontent.com/47243617/170097162-be77b953-e445-4e7a-bbdf-2fedf2295e6f.png)

> Beim Szenegraphen ist der Wurzel-Knoten vom Typ `Parent`.

## Lebenszyklus einer JavaFX-Anwendung
JavaFX-Anwendungen sind Unterklassen der Klasse `Application`, die die verschiedenen Lebenszyklus-Methoden bereitstellt:
- Die Methode `launch(String[])` speichert die Parameter, erzeugt ein Objekt der eigenen Klasse und ruft die weiteren Lebenszyklus-Methoden auf
- Die Methode `init()` kann genutzt werden, um z.B. die Aufrufparameter auszulesen
- Die Methode `start(Stage)` bekommt eine Bühne übergeben und wird dazu verwendet, die Bühne zu gestalten und die erste Szene aufzurufen
- Die Methode `stop()` wird aufgerufen, bevor der Prozess gestoppt wird und kann genutzt werden, um Aufräumarbeiten durchzuführen

[^1]: Unter einem Framework versteht man ein Programmiergerüst, welches die Architektur für die Anwendung vorgibt und den Kontrollfluss der Anwendung steuert
[^2]: Graphical User Interface