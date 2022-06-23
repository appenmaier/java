---
title: Statische Attribute und Methoden
---

Neben "normalen" Attributen und Methoden kann eine Klasse auch statische Attribute und statische Methoden besitzen. Im Gegensatz zu "normalen" Attributen existieren statische Attribute nur einmal pro Klasse und besitzen daher für alle Objekte dieser Klasse dieselben Werte. Innerhalb einer statischen Methode kann nur auf die statischen Attribute der Klasse zugegriffen werden.

Bei der Deklaration von statischen Attributen und statischen Methoden kommt das Schlüsselwort `static` zum Einsatz. Für den Zugriff auf ein statisches Attribut bzw. 
den Aufruf einer statischen Methode wird keine Instanziierung benötigt, d.h. der der Zugriff bzw. Aufruf erfolgt über den Klassennamen.

```java
public class Foo {

  public static String bar;
  public static void baz() { }

}

public class MainClass {

  public static void main(String[] args) {
    Foo.bar = "Fubar";
    Foo.baz();
  }

}
```

> "Normale" Attribute und Methoden werden auch als Instanzattribute bzw. Instanzmethoden bezeichnet, statische Attribute und Methoden auch Klassenattribute bzw. Klassenmethoden
