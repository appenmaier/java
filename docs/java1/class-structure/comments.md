---
title: Kommentare
---

Kommentare sollen die Lesbarkeit des Programms verbessern. Sie bewirken bei der Ausführung keine Aktion und werden vom Java-Compiler ignoriert. Java kennt einzeilige Kommentare mit `//`, Kommentarblöcke mit `/* */` und Dokumentationskommentare mit `/** */` (siehe [Die Java API](../java-api/java-api.md)).

```java
/**
  * Startklasse
  *
  * @author Daniel Appenmaier
  * @version 1.0
  */
public class MainClass {

    /**
      * Main-Methode
      *
      * @param args Argumente
      */
    public static void main(String[] args) { 
        /*
         * Ausgabe
         */
        System.out.println("Hallo Welt"); // Ausgabe
    }

}
```
