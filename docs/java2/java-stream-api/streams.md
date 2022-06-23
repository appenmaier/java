---
title: Erzeugen von Strömen
---

Ströme können unter anderem aus Feldern, Datensammlungen wie z.B. Listen und Mengen sowie Einzelobjekten erzeugt werden. 

```java
public class MainClass {

    public static void main(String[] args) {        
        int[] array = {4, 8, 15, 16, 23, 42};
        IntStream integerStream = Arrays.stream(array);

        List<Integer> list = List.of(4, 8, 15, 16, 23, 42);
        Stream<Integer> integerStream2 = list.stream();

        Stream<Integer> integerStream3 = Stream.of(4, 8, 15, 16, 23, 42);
    }

}
```

> Die Zahlenfolge 4-8-15-16-23-42 spielt eine große Rolle in der Fernsehserie **Lost**

Im Gegensatz zu "normalen" Strömen besitzen Objekte der Klassen `IntStreams`, `DoubleStreams` und `LongStreams` Methoden zur Weiterverarbeitung ihrer primitiver Werte.

```java
public class MainClass {

    public static void main(String[] args) {
        int[] array = {4, 8, 15, 16, 23, 42};
        IntStream integerStream = Arrays.stream(array);
        int sum = integerStream.sum();
    }
    
}
```
