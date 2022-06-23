---
title: Klassen, Attribute und Methoden
---

## Definition von Klassen
Klassen werden in Java mit dem Schlüsselwort `class` definiert. Die Angabe des Zugriffsrechts legt die Sichtbarkeit der Klasse fest.

```java
public class Foo { }
```

## Definition von Attributen
Die Attribute einer Klasse sind Datenobjekte und werdern daher analog zu Variablen und Konstanten definiert. Die Angabe des Zugriffsrechts legt die Sichtbarkeit des 
Attributs fest.

```java
public class Foo {

  public String bar;
  public int baz;

}
```

## Definition von Methoden
Methoden sind in der Programmierung eine Verallgemeinerung von mathematischen Funktionen. Eine Methode besteht aus einem Methodennamen, einer Liste von Eingabeparameter (optional), einem Rückgabewert (optional) sowie dem Methodenrumpf.

Methoden können entweder genau einen Rückgabewert oder keinen Rückgabewert besitzen. Methoden mit genau einem Rückgabewert müssen vor dem Methodennamen den Datentyp 
des Rückgabewerts angeben und am Ende des Methodenrumpfes immer die Anweisung `return` besitzen, Methoden ohne Rückgabewert müssen dies mit dem Schlüsselwort `void` 
kenntlich machen.


```java
public class Foo {

  public void bar(Qux qux);
  public int baz();

}
```

> Die **Signatur einer Methode** setzt sich aus Methodenname und den Datentypen der Parameterliste zusammen.
