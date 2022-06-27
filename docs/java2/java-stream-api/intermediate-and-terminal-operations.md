---
title: Intermediäre und Terminale Operationen
---

Die Methoden der Schnittstelle `Stream` werden in **intermediäre** und **terminale Operationen** unterteilt.

## Intermediäre Operationen
Intermediäre Operationen ermöglichen das Filtern, Sortieren, Mappen etc. von Strömen und liefern als Ergebnis wiederum einen Strom.

| Operation | Schnittstelle | Rückgabewert |
| --------- | ------------- | ------------ |
| filter | Predicate<T\> | Stream<T\> |
| map | Function<T, R\> | Stream<T\> |
| distinct | - | Stream<T\> |
| sorted | Comparator<T\> | Stream<T\> |
| limit | - | Stream<T\> |

## Terminale Operationen
Terminale Operationen werden z.B. zum Suchen, zum Aggregieren oder zum Ausgeben von Daten verwendet. Da terminale Operationen den Strom schließen, können auf ihnen keine keine weiteren Operationen mehr ausgeführt werden.

| Operation | Schnittstelle | Rückgabewert |
| --------- | ------------- | ------------ |
| reduce | BinaryOperator<T\> | T |
| forEach | Block<T\> | void |
| findFirst | - | Optional<T\> |
| anyMatch | Predicate<T\> | boolean |
