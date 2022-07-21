---
title: Intermediäre und Terminale Operationen
---

Die Methoden der Schnittstelle `Stream` werden in **intermediäre** und **terminale Operationen** unterteilt.

## Intermediäre Operationen
Intermediäre Operationen ermöglichen unter anderem das Filtern, Abbilden sowie das Sortieren von Strömen und liefern als Ergebnis wiederum einen Strom.

| Operation     | Methode                                                           | Schnittstellen-Methode |
| ------------- | ----------------------------------------------------------------- | ---------------------- |
| Filtern       | `Stream<T> filter(Predicate<? super T>)`                          | `boolean test(T)`      |
| Abbilden      | `Stream<T> map(Function<? super T, ? extends R>)`                 | `R apply(T)`           |
| Abbilden      | `Stream<T> mapToDouble(ToDoubleFunction<? super T, ? extends R>)` | `R apply(T)`           |
| Abbilden      | `Stream<T> mapToInt(ToIntFunction<? super T, ? extends   R>)`     | `R apply(T)`           |
| Sortieren     | `Stream<T> sorted(Comparator<? superT>)`                          | `int compare(T, T)`    |
| Unterscheiden | `Stream<T> distinct()`                                            | -                      |
| Begrenzen     | `Stream<T> limit()`                                               | -                      |
| Überspringen  | `Stream<T> skip()`                                                | -                      |

## Terminale Operationen
Terminale Operationen werden z.B. zum Prüfen, zum Aggregieren oder zum Sammeln verwendet. Da terminale Operationen den Strom schließen, können auf ihnen keine keine weiteren Operationen mehr ausgeführt werden.

| Operation   | Methode                                        | Schnittstellen-Methode |
| ----------- | ---------------------------------------------- | ---------------------- |
| Finden      | `Optional<T> findAny()`                        | -                      |
| Finden      | `Optional<T> findFirst()`                      | -                      |
| Prüfen      | `boolean allMatch(Predicate<? super T>)`       | `boolean test(T)`      |
| Prüfen      | `boolean anyMatch(Predicate<? super T>)`       | `boolean test(T)`      |
| Prüfen      | `boolean noneMatch(Predicate<? siper T>)`      | `boolean test(T)`      |
| Aggregieren | `T reduce(BinaryOperator<T>)`                  | `R apply(T, U)`        |
| Aggregieren | `Optional<T> min(Comparator<? super T>)`       | `int compare(T, T)`    |
| Aggregieren | `Optional<T> max(Comparator<? super T>)`       | `int compare(T, T)`    |
| Aggregieren | `long count()`                                 | -                      |
| Sammeln     | `<R, A> R collect(Collector< ? super T, A, R>` | -                      |
| Ausführen   | `void forEach(Consumer<? super T>)`            | `void accept(T)`       |

Zahlenströme (`IntStream`, `DoubleStream`) besitzen die zusätzlichen terminale Operationen `sum()` und `average()`.
