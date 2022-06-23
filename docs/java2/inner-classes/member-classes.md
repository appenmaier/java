---
title: Elementklassen (Member Classes)
---

Objekte von **Elementklassen** sind immer mit einem Objekt der umgebenden Klasse verbunden. Dies ermöglicht die Umsetzung von Kompositionen (siehe [Klassendiagramme](../../java1/uml/class-diagrams.md) - Darstellung von Assoziationen). Sie haben Zugriff auf alle Variablen und Methoden der sie umgebenden Klasse und dürfen keine statischen Elemente enthalten.

## Beispiel
Zunächst wird die äußere Klasse `OuterClass` samt der Elementklasse `InnerClass` definiert. 

```java
public class OuterClass {

    public class InnerClass{ }
    
}
```

In der main-Methode der Startklasse kann ein Objekt der Klasse `InnerClass` nur auf ein bestehendes Objekt der Klasse `OuterClass` erzeugt werden.

```java
public class MainClass {

    public static void main(String[] args) {
        OuterClass o = new OuterClass();
        OuterClass.InnerClass i = new OuterClass.InnerClass(); // Kompilierungsfehler
        OuterClass.InnerClass i = o.new OuterClass.InnerClass();
    }

}
```
