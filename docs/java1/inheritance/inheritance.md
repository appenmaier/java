---
title: Vererbung
---

Bei der Modellierung von Klassen stellt man häufig fest, dass sich einige Klassen der Struktur und dem Verhalten nach ähneln. In solchen Fällen hat man 
die Möglichkeit, die gemeinsamen Strukturen und Verhaltensweisen aus den speziellen Klassen zu extrahieren und in einer allgemeineren Klasse unterzubringen. Dies wird 
als **Generalisierung** bezeichnet. Umgekehrt gibt es oftmals auch Bedarf, eine bestehende Klasse um zusätzliche Attribute und/oder Methoden zu erweitern. Dies bezeichnet man als **Spezialisierung**. Die Beziehung zwischen einer speziellen Klasse und einer allgemeinen Klasse wird **Vererbung** bezeichnet.

> Die speziellen Klasse werden als **Unterklassen** (Sub Classes), die allgemeinen Klassen als **Oberklassen** (Super Classes) bezeichnet.

## Implementieren von Vererbung
Die Vererbung wird mit dem Schlüsselwort `extends` realisiert. In der Oberklasse können Attribute und Methoden mit dem Schlüsselwort `protected` als geschützt festlegt werden. Unterklassen können auf alle öffentlichen und geschützten Attribute und Methoden der Oberklasse zugreifen.

```java
public class SuperClass {

    public Foo foo;
    protected Bar bar;
    private Baz baz;
  
    public SuperClass(Foo foo) {
        this.foo = foo;
    }
    
}

public class SubClass extends SuperClass {

    public SubClass(Foo foo) {
        super(foo);
    }
  
    public void foobar() {
        System.out.println(foo);
        System.out.println(bar);
        System.out.println(baz); // Kompilierungsfehler
    }
  
}
```

> In den Konstruktoren der Unterklasse muss ein Konstruktor der Oberklasse mit Hilfe von `super` aufgerufen werden.
