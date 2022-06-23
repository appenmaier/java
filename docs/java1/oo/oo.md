---
title: Grundlagen der Objektorientierung
---

Die reale Welt besteht aus Objekten mit individuellen Eigenschaften und individuellem Verhalten. Für ein einfacheres Verständnis werden Objekte kategorisiert, also zu 
sinnhaften Einheiten verbunden. In der objektorientierten Programmierung werden Beobachtungen aus der realen Welt zum Konzept der **Objektorientierung** zusammengefasst:
- Eine Kategorie von ähnlichen Objekten bezeichnet man als **Klasse**
- Konkrete Ausprägungen bzw. Instanzen einer Klasse werden wiederum als **Objekte** bezeichnet
- Die Eigenschaften von Objekten werden als **Attribute**, das Verhalten als **Methoden** bezeichnet

![image](https://user-images.githubusercontent.com/47243617/170762507-dc3f4d1f-0730-44c1-acbf-3b9090832c9b.png)

> Jedes Objekt ist eindeutig identifizierbar.

## Datenkapselung
Ein wesentlicher Grundsatz der Objektorientierung ist, dass Attribute durch Methoden gekapselt werden. Datenkapselung bedeutet, dass Attribute nicht direkt geändert 
werden können, sondern nur durch den indirekten Zugriff über Methoden. Typische Methoden zum Lesen und Schreiben von Attributen sind die sogenannten Getter bzw. 
Setter.

![image](https://user-images.githubusercontent.com/47243617/170760689-edc2460c-b661-4c90-b93d-da03b2d8acd3.png)

## Sichtbarkeit von Attributen und Methoden
Um die Sichtbarkeit von Attributen und Methoden zu definieren, existieren verschiedene Zugriffsrechte. Die Sichtbarkeit bestimmt, von welchem Ort aus Attribute und
Methoden verwendet bzw. aufgerufen werden dürfen.

| Zugriffsrecht | Zugriff aus gleicher Klasse | Zugriff von einer Klasse aus dem gleichen Paket | Zugriff von einer Unterklasse | Zugriff von einer beliebigen Klasse |
| ------------- | --------------------------- | ----------------------------------------------- | ----------------------------- | ----------------------------------- |
| public | ja | ja | ja | ja |
| protected | ja | ja | ja | nein |
| package | ja | ja | nein | nein |
| private | ja | nein | nein | nein |
