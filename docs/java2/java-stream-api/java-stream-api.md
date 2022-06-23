---
title: Die Java Stream API
---

Die **Java Stream API** stellt Klassen zum [Erzeugen](streams.md) und Verarbeiten von **Strömen** (Streams) bereit. Ein Strom stellt eine Folge von Elementen dar, die das Ausführen verketteter, [intermediärer und terminaler Operationen](intermediate-and-terminal-operations.md) auf diesen Elementen nacheinander oder parallel ermöglicht. Die Daten, die durch die Elemente des Stromes repräsentiert werden, werden dabei durch den Strom selbst nicht verändert. Die Verarbeitung der Elemente erfolgt nach dem Prinzip der [Bedarfsauswertung (Lazy Evaluation)](lazy-evaluation.md). Neben endlichen Strömen stellt die Java Stream API auch Methoden zum Erzeugen [unendlicher Ströme](infinite-streams.md) bereit.

![image](https://user-images.githubusercontent.com/47243617/170433119-1c214acd-b1c7-4171-8cbc-1f259d824892.png)

> Ströme (Paket `java.util.stream`) haben nichts mit [Datenströmen (IO-Streams)](../../java2/io-streams/io-streams.md) (Paket `java.io`) zu tun.
