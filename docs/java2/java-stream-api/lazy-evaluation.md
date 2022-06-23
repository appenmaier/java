---
title: Bedarfsauswertung (Lazy Evaluation)
---

Die Elemente in Strömen werden nur bei Bedarf ausgewertet. Intermediäre Operationen werden also nur dann ausgeführt, wenn eine terminale Operation vorhanden ist und bei verketteten Operationen werden für jedes Element die einzelnen Operationen nacheinander ausgeführt.

## Beispiel
In der main-Methode der Startklasse wird auf den Zahlenstrom 4-8-15-16-23-42 zunächst der Filter _Zahl > 15_ angewendet, anschließend der Filter _Zahl = ganze Zahl_ und abschließend werden die verbliebenen Zahlen auf der Konsole ausgegeben. Zum Nachvollziehen werden die Zahlen auch bei den beiden Filtern auf der Konsole ausgegeben.

```java
public class MainClass {

    public static void main(String[] args) {
        Stream.of(4, 8, 15, 16, 23, 42).filter(i -> {
            System.out.println(i + ": filter 1");
            return i % 2 == 0;;
        }).filter(i -> {
            System.out.println(i + ": filter 2");
            return > 15;
        }).forEach(i -> System.out.println(i + ": forEach"));
    }

}
```

Ohne Bedarfsauswertung würden die verschiedenen Operationen für die jeweils verbliebenen Elemente ausgeführt nacheinander werden. Die Ausgabe sähe wie folgt aus:

```
 4: filter 1
 8: filter 1
 15: filter 1
 16: filter 1
 23: filter 1
 42: filter 1
 4: filter 2
 8: filter 2
 16: filter 2
 42: filter 2
 16: forEach
 42: forEach
 ```
 
Aufgrund der Bedarfsauswertung werden die verschiedenen Operationen aber für jedes Element einzeln nacheinander ausgeführt. Dadurch ergibt sich folgende Ausgabe:

```
4: filter 1
4: filter 2
8: filter 1
8: filter 2
15: filter 1
16: filter 1
16: filter 2
16: forEach
23: filter 1
42: filter 1
42: filter 2
42: forEach
```
