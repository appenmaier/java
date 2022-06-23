---
title: Konstruktoren
---

Bei Konstruktoren handelt es sich um spezielle Methoden, die zur Initialisierung eines Objekts verwendet werden. Konstruktoren heißen wie ihre Klasse und können eine 
beliebige Anzahl an Parametern haben. Allerdings kann für Konstruktoren kein Rückgabewert festgelegt werden, da diese implizit die Referenz auf das Objekt 
zurückgeben.

Im Gegensatz zu z.B. C++ existieren in Java keine Destruktoren, die nicht mehr benötigte Objekte aus dem Speicher entfernen. Stattdessen läuft im Hintergrund der 
sogenannte Garbage Collector, der nicht mehr benötigte Objekte (also Objekte, die nicht mehr über eine Referenzvariable angesprochen werden können) löscht.

```java
public class Foo {

  public Foo() { }
  public Foo(Qux qux) { }
  public Foo(Qux qux, Quux quux) { }

}
```

> Auch Konstruktoren können überladen werden.


