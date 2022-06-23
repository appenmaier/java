---
title: Datenströme (IO-Streams)
---

**Datenströme** (IO-Streams) sind unidirektionale Pipelines, die Schnittstellen eines Java-Programms nach außen darstellen. Daten können unabhängig von der Art der Quelle bzw. des Ziels vorne in einen Datenstrom geschrieben und hinten wieder ausgelesen werden. Ein Datenstrom kann dabei immer nur in eine Richtung verwendet werden (also entweder zur Ein- oder Ausgabe). Neben den [Standard-Datenströmen zur Ein- und Ausgabe](standard-io-streams.md) existieren verschiedene Klassen zum [Schreiben und Lesen zeichenorientierter Daten](writers-and-readers.md), zum [Schreiben und Lesen byteorientierter Daten](output-streams-and-input-streams.md) und zum [Schreiben und Lesen serialisierter Objekte](serialization.md). Das Arbeiten mit Datenstrom-Klassen kann dabei aufwändig über "normale" try-catch-Anweisungen oder mit Hilfe von [try-with-resources-Anweisungen](try-with-resources.md) realisiert werden.

![image](https://user-images.githubusercontent.com/47243617/170435801-cb897b17-2ebd-4b70-ad4f-330c4aca649b.png)
