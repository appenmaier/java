---
title: Mehrfachvererbung
---

Wird eine Klasse von mehreren Klassen abgeleitet, spricht man von Mehrfachvererbung. Das Prinzip der Mehrfachvererbung wird von vielen Programmiersprachen allerdings nicht (direkt) unterstützt. Der Hauptgrund hier sind mögliche Mehrdeutigkeiten. Diese Problem wird im **Diamantenproblem** ersichtlich: Erbt eine Klasse über mehrere mögliche Pfade von einer Basisklasse und werden dabei möglicherweise Methoden der Basisklasse unterschiedlich überschrieben, entstehen dadurch nicht eindeutige Varianten.

![image](https://user-images.githubusercontent.com/47243617/171616540-45e6b1c8-5869-43ba-a6ab-cd1287b1d961.png)

> Das Diamantenproblem trägt seinen Namen aufgrund der Rautenform des Klassendiagramms.
