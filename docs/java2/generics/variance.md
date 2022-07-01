---
title: Varianz
---

Typparameter können gar nicht (**Bivarianz**), nach oben (**Kovarianz**), nach unten (**Kontravarianz**), oder sowohl nach oben als auch nach unten (**Invarianz**) 
eingeschränkt werden. Zusätzlich ermöglicht der Wildcard-Typ `?` bei parametrisierten Typen die Angabe eines unbestimmten Typs. 

## Beispiel
Die generische Klasse `GenericBox<T>` ermöglicht das Speichern einer beliebig typisierten Information.

```java
public class GenericBox<T> {

    private T content;
    public void set(T content) { this.content = content; }
    public T get() { return content; }

}
```

Die Drei Klassen `Above`, `Center` und `Below` bilden eine Generalisierungshierarchie ab, wobei die Klasse `Below` eine Unterklasse der Klasse `Center` und diese 
wiederum eine Unterklasse der Klasse `Above` darstellt.

```java
public class Above {}
public class Center extends Above {}
public class Below extends Center {}
```

In der main-methode der Startklasse werden verschiedene generische Boxen unterschiedlich deklariert und anschließend initialisiert.

```java
public class MainClass {

    public static void main(String[] args) {
        GenericBox<?> bivariant;
        bivariant = new GenericBox<Above>();
        bivariant = new GenericBox<Center>();
        bivariant = new GenericBox<Below>();

        GenericBox<? extends Center> covariant;
        covariant = new GenericBox<Above>(); // Kompilierungsfehler
        covariant = new GenericBox<Center>();
        covariant = new GenericBox<Below>();

        GenericBox<? super Center> contravariant;
        contravariant = new GenericBox<Above>();
        contravariant = new GenericBox<Center>();
        contravariant = new GenericBox<Below>(); // Kompilierungsfehler

        GenericBox<Center> invariant;
        invariant = new GenericBox<Above>(); // Kompilierungsfehler
        invariant = new GenericBox<Center>();
        invariant = new GenericBox<Below>(); // Kompilierungsfehler
    }

}
```
