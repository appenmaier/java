---
title: Listen
---

Die Java API stellt eine Reihe von Klassen und Schnittstellen zur Verfügung, mit deren Hilfe Listen realisiert werden. Unter einer Liste versteht man eine geordnete Folge von Elementen, die auch doppelt enthalten sein können. Der Zugriff auf die Elemente erfolgt über den Index oder sequentiell.

## Die Schnittstelle List<E\>
Die Schnittstelle `List<E>` stellt verschiedene Fabrikmethoden[^1] zum Erzeugen unveränderlicher Listen zur Verfügung.

```java
public class MainClass {

    public static void main(String[] args) {
        List<String> list = List.of("Hans", "Peter", "Lisa");

        System.out.println(list.size());
        System.out.println(list.get(0));
        list.set(0, "Max"); // Laufzeitfehler
        list.add("Heidi"); // Laufzeitfehler
        list.remove(0); // Laufzeitfehler
    }

}
```

[^1]: Fabrikmethoden sind Methoden, die Objekte erzeugen

## Die Klasse Arrays
Die Klasse `Arrays` stellt neben Methoden zum Sortieren und Durchsuchen von Feldern auch eine Methode zum Erzeugen veränderbarer Listen fixer Größe zur Verfügung.

```java
public class MainClass {

    public static void main(String[] args) {
        List<String> list = Arrays.asList("Hans", "Peter", "Lisa");

        System.out.println(list.size());
        System.out.println(list.get(0));
        list.set(0, "Max");
        list.add("Heidi"); // Laufzeitfehler
        list.remove(0); // Laufzeitfehler
    }

}
```

## Die Klasse ArrayList<E\>
Die Klasse `ArrayList<E>` stellt eine veränderbare Liste dynamischer Größe auf Basis eine Feldes dar.

```java
public class MainClass {

    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Hans");
        list.add("Peter");
        list.add("Lisa");

        System.out.println(list.size());
        System.out.println(list.get(0));
        list.set(0, "Max");
        list.add("Heidi");
        list.remove(0);
   }

}
```
