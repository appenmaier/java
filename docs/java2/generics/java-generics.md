---
title: Java Generics
---

Klassen und Methoden können in Java mit Typen parametrisiert werden. Diese werden durch spitze Klammern `<>` gekennzeichnet und stellen Platzhalter für 
konkrete Datentypen dar. Beim Kompilieren werden alle generischen Informationen vollständig entfernt und durch die konkreten Datentypen ersetzt. Durch die dadurch 
vorhandene statische Typsicherheit können Laufzeitfehler verhindert und Fehler bereits beim Kompilieren entdeckt werden.

## Beispiel für eine generische Klasse
Die generische Klasse `GenericBox<T>` ermöglicht das Speichern einer beliebig typisierten Information mit Hilfe der Typvariablen `T`.

```java
public class GenericBox<T> {

    private T content;
    public void set(T content) { this.content = content; }
    public T get() { return content; }

}
```

In der main-Methode der Startklasse wird zunächst eine ganze Zahl in einer generischen Box gespeichert und anschließend wieder ausgelesen.
Die Umwandlung der ganzen Zahl in eine Zeichenkette führt aufgrund der statischen Typsicherheit zu einem Kompilierungsfehler.

```java
public class MainClass {

    public static void main(String[] args) {
        GenericBox<Integer> genericBox = new GenericBox<>();
        genericBox.set(5);
        String i = genericBox.get(); // Kompilierungsfehler
    }

}
```

> Die Typisierung kann entweder explizit oder implizit über den Diamantenoperator `<>` erfolgen.

## Beispiel für eine generische Methode
Die generische Methode `getIndex(T, T[])` gibt den Index eines beliebig typisierten gesuchten Wertes innerhalb eines gleichtypisierten Feldes zurück.

```java
public class MainClass {

    public static void main(String[] args) {
        System.out.println(getIndex(5, new Integer[] { 3, 5, 2, 4, 1 }));
    }

    public static <T> int getIndex(T value, T[] values) {
        for (int i = 0; i < values.length; i++) {
            if (values[i].equals(value)) {
                return i;
            }
        }
        return -1;
    }

}
```

## Namensrichtlinien für Typvariablen
Um den Einsatzbereich von Typvariablen in generischen Klassen und Methoden kenntlich zu machen, sollte man festgelegte Zeichen verwenden.

| Typvariable | Einsatzbereich |
| ------- | -------------- |
| T, U, V, W... | Datentyp (Type) |
| E | Element einer Datensammlung (Element) |
| K | Schlüssel eines Assoziativspeichers (Key) |
| V | Wert eines Assoziativspeichers (Value) |
