---
title: Geschachtelte Klassen (Nested Classes)
---

**Geschachtelte Klassen** sind Top-Level-Klassen, die zur Strukturierung des Namensraumes[^1] in anderen Top-Level-Klassen definiert sind. Geschachtelte Klassen müssen statisch definiert werden und sind im eigentlich Sinne keine "richtigen" inneren Klassen.

## Beispiel
Zunächst wird die äußere Klasse `OuterClass` samt der geschachtelten Klasse `InnerClass` definiert.

```java
public class OuterClass {

    public static class InnerClass{ }
    
}
```
In der main-Methode der Startklasse kann die innere Klasse `InnerClass` nur durch Angabe des vollständigen Namensraumes verwendet werden, was die Angabe der äußerer Klasse `OuterClass` miteinschließt.

```java
public class MainClass {

    public static void main(String[] args) {
        OuterClass o = new OuterClass;
        OuterClass.InnerClass i = new OuterClass.InnerClass();
    }

}
```

[^1]: Die vollständige Pfadangabe zur Klasse (z.B. `java.lang`)
