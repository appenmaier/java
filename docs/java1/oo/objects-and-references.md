---
title: Objekte und Referenzvariablen
---

## Deklaration von Referenzvariablen
Technisch gesehen handelt es sich bei einer Klasse um einen komplexen Datentyp. Analog zu den primitiven Datentypen können auch für Klassen Variablen – 
sogenannte Referenzvariablen – definiert werden. 

Im Gegensatz zu "normalen" Variablen werden bei Referenzvariablen nicht die eigentlichen Werte in den Variablen gespeichert, sondern die Speicheradressen der 
erzeugten Objekte. Die Selbstreferenz `this` verweist innerhalb einer Klasse auf das eigene Objekt.

![image](https://user-images.githubusercontent.com/47243617/170764624-4e55faa5-179f-4100-b444-f197619fb671.png)

> Der Standarwert von Referenzvariablen ist `null`

## Erzeugen von Objekten
Beim Erzeugen eines Objekts mit Hilfe des Operators `new` wird der bei der Deklaration reservierte Speicherplatz durch das Objekt belegt.

```java
public class Foo { }

public class MainClass {

  public static void main(String[] args) {
    Foo foo = new Foo();
  }

}
```

> Nach dem new-Operator muss immer ein Konstruktor der Klasse stehen.

## Zugriff auf Attribute und Aufruf von Methoden
Erlauben die Zugriffsrechte den Zugriff auf ein Attribut, kann über die deklarierte Referenzvariable und einem nachgestellten Punkt auf das Attribut zugegriffen werden. Auch sichtbare Methoden werden über diese Syntax aufgerufen.

```java
public class Foo {

  public String bar;
  public void baz(Qux qux) { }

}

public class MainClass {

  public static void main(String[] args) {
    Foo foo = new Foo();
    foo.bar = "Hallo Welt";
    foo.baz(new Qux());
  }

}
```

> Beim Aufruf einer Methode müssen alle Parameter in der richtigen Reihenfolge[^1] versorgt werden.

[^1]: Parameter, die diesem Prinzip folgen, bezeichnet man als Positionsparameter
