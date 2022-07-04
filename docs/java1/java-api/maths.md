---
title: Mathematische Berechnungen
---

Die Klasse `Math` stellt neben einigen Konstanten wie der Kreiszahl _Pi_ und der Eulerschen Zahl _E_ zahlreiche Methoden für mathematische Berechnungen zur Verfügung.

```java
public class MainClass {

    public static void main(String[] args) {
        int a = 5;
        int b = 3;
        double result;

        result = Math.pow(a, b);
        System.out.println(result);

        result = Math.sqrt(a);
        System.out.println(result);
    }

}
```
