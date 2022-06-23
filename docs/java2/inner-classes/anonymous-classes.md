---
title: Anonyme Klassen
---

**Anonyme Klassen** besitzen im Gegensatz zu lokalen Klassen keinen Namen und werden innerhalb eines Ausdrucks definiert und instanziiert; Klassendeklaration und Objekterzeugung sind also in einem Sprachkonstrukt vereint. Wird als Datentyp eine Schnittstelle benötigt, implementiert die anonyme Klasse diese Schnittstelle, wird als Datentyp eine Klasse benötigt, so wird die anonyme Klasse daraus abgeleitet.

## Beispiel
Zunächst wird die Schnittstelle `Qux` samt der Methode `quux(String)`definiert.

```java
public interface Qux {

    void quux(String s);

}
```

Die Klasse `Foo` soll die Verwenderklasse der Schnittstelle `Qux` darstellen.

```java
public class Foo {

    public static void bar(String s, Qux q) {
        q.quux(s);
    }

}
```

In der main-Methode der Startklasse soll die Methode `bar(String, Qux)` der Klasse `Foo` aufgerufen werden, wofür eine konkrete Implementierung der Schnittstelle `Qux` benötigt wird. Die Implementierung erfolgt in Form einer anonymen Klasse.

```java
public class MainClass {

    public static void main(String[] args) {
        Foo.bar("Winter is Coming", new Qux() {
            @Override
            public void quux(String s) {
                System.out.println(s);
            } 
        });
    }

}
```
