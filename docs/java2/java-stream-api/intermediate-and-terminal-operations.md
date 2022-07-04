---
title: Intermediäre und Terminale Operationen
---

Die Methoden der Schnittstelle `Stream` werden in **intermediäre** und **terminale Operationen** unterteilt.

## Intermediäre Operationen
Intermediäre Operationen ermöglichen das Filtern, Sortieren, Mappen etc. von Strömen und liefern als Ergebnis wiederum einen Strom.

| Operation     | Methode                             | Schnittstellen-Methode |
| ------------- | ----------------------------------- | ---------------------- |
| Filter        | `Stream<T> filter(Predicate<T>)`    | `boolean test(T)`      |
| Abbilden      | `Stream<T> flatMap(Function<T, R>)` | `R apply(T)`           |
| Abbilden      | `Stream<T> map(Function<T, R>)`     | `R apply(T)`           |
| Sortieren     | `Stream<T> sorted(Comparator<T>)`   | `int compare(T, T)`    |
| Unterscheiden | `Stream<T> distinct()`              | -                      |
| Begrenzen     | `Stream<T> limit()`                 | -                      |
| Überspringen  | `Stream<T> skip()`                  | -                      |

## Terminale Operationen
Terminale Operationen werden z.B. zum Suchen, zum Aggregieren oder zum Ausgeben von Daten verwendet. Da terminale Operationen den Strom schließen, können auf ihnen keine keine weiteren Operationen mehr ausgeführt werden.

| Operation  | Methode                           | Schnittstellen-Methode |
| -----------| --------------------------------- | ---------------------- |
| Finden     | `Optional<T> findAny()`          | -                      |
| Finden     | `Optional<T> findFirst()`         | -                      |
| Prüfen     | `boolean allMatch(Predicate<T>)`  | `boolean test(T)`      |
| Prüfen     | `boolean anyMatch(Predicate<T>)`  | `boolean test(T)`      |
| Prüfen     | `boolean noneMatch(Predicate<T>)` | `boolean test(T)`      |
| Reduzieren | `T reduce(BinaryOperator<T>)`     | `R apply(T, U)`        |
| Ausführen  | `void forEach(Consumer<T>)`       | `void accept(T)`       |
