---
title: Intermediäre und Terminale Operationen
---

Die Methoden der Schnittstelle `Stream` werden in **intermediäre** und **terminale Operationen** unterteilt.

## Intermediäre Operationen
Intermediäre Operationen ermöglichen unter anderem das Filtern, Abbilden sowie das Sortieren von Strömen und liefern als Ergebnis wiederum einen Strom.

| Operation     | Methode                                             | Schnittstellen-Methode     |
| ------------- | --------------------------------------------------- | -------------------------- |
| Filtern       | `filter(Predicate<T>): Stream<T>`                   | `test(T): boolean`         |
| Abbilden      | `map(Function<T, R>): Stream<T>`                    | `apply(T): R`              |
| Abbilden      | `mapToDouble(ToDoubleFunction<T, R>): DoubleStream` | `applyAsDouble(T): double` |
| Abbilden      | `mapToInt(ToIntFunction<T, R>): IntStream`          | `applyAsInt(T): int`       |
| Abbilden      | `mapToLong(ToLongFunction<T, R>): LongStream`       | `applyAsLong(T): long`     |
| Sortieren     | `sorted(Comparator<T>): Stream<T>`                  | `compare(T, T): int`       |
| Unterscheiden | `distinct(): Stream<T>`                             | -                          |
| Begrenzen     | `limit(): Stream<T>`                                | -                          |
| Überspringen  | `skip(): Stream<T>`                                 | -                          |

## Terminale Operationen
Terminale Operationen werden z.B. zum Prüfen, zum Aggregieren oder zum Sammeln verwendet. Da terminale Operationen den Strom schließen, können auf ihnen keine keine weiteren Operationen mehr ausgeführt werden.

| Operation   | Methode                            | Schnittstellen-Methode |
| ----------- | ---------------------------------- | ---------------------- |
| Finden      | `findAny(): Optional<T>`           | -                      |
| Finden      | `findFirst(): Optional<T>`         | -                      |
| Prüfen      | `allMatch(Predicate<T>): boolean`  | `test(T): boolean`     |
| Prüfen      | `anyMatch(Predicate<T>): boolean`  | `test(T): boolean`     |
| Prüfen      | `noneMatch(Predicate<T>): boolean` | `test(T): boolean`     |
| Aggregieren | `min(Comparator<T>: Optional<T>)`  | `compare(T, T): int`   |
| Aggregieren | `max(Comparator<T>): Optional<T>`  | `compare(T, T): int`   |
| Aggregieren | `count(): long`                    | -                      |
| Sammeln     | `collect(Collector<T, A, R>): R`   | -                      |
| Ausführen   | `forEach(Consumer<T>): void`       | `accept(T): void`      |

Zahlenströme (`IntStream`, `DoubleStream`, `LongStream`) besitzen die zusätzlichen terminale Operationen `sum()` und `average()`.
