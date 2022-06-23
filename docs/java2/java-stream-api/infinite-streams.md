---
title: Unendliche Ströme
---

Die Java Stream API stellt drei Methoden zur Verfügung, mit deren Hilfe (un)endliche Ströme erzeugt werden können:
- Die Methode `iterate(T, UnaryOperator<T>)` generiert einen unendlichen Strom aus einem Startwert und einer Funktion, welche das nächste Element erstellt
- Die Methode `iterate(T, Predicat <? Super T>, UnaryOperator<T>)` erweitert die "normale" iterate-Methode um eine Prädikatsfunktion zum Beenden des Stroms
- Die Methode `generate(Supplier<? Super T>)` kann zum Beispiel zum Erzeugen unendlich vieler zufälliger Elemente genutzt werden

## Beispiel
In der main-Methode der Startklasse werden drei (un)endliche Zahlenströme erzeugt.

```java
public class MainClass {

    public static void main(String[] args) {
        Stream.iterate(0, i -> ++i).limit(100).forEach(System.out::println);
        Stream.iterate(0, i -> i < 100, i -> ++i).forEach(System.out::println);
        Stream.generate(() -> new Random().nextInt(100)).limit(100).forEach(System.out::println);
    }

}
```

Die ersten beiden Zahlenströme geben die Zahlen von 0 bis 99 aus, der dritte Zahlenstrom 100 Pseudozufallszahlen von 0 bis 99. Der erste und dritte Zahlenstrom würden eigentlich unendliche viele (Pseudozufalls-)Zahlen erzeugen, werden aber durch die Methode `limit(long)` auf 100 (Pseudozufalls-)Zahlen begrenzt.
