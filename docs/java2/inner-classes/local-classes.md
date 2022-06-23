---
title: Lokale Klassen
---

**Lokale Klassen** werden innerhalb einer Methode definiert und können auch nur dort verwendet werden. Sie dürfen nicht als `public`, `protected`, `private` oder `static` definiert werden, dürfen keine statischen Elemente enthalten und können nur die mit `final` markierten Variablen und Parameter der umgebenden Methode verwenden.

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

In der main-Methode der Startklasse soll die Methode `bar(String, Qux)` der Klasse `Foo` aufgerufen werden, wofür eine konkrete Implementierung der Schnittstelle `Qux` benötigt wird. Die Implementierung erfolgt in Form der lokalen Klasse `LocalClass`.

```java
public class MainClass {

    public static void main(String[] args) {
        class LocalClass implements Qux {
            @Override
            public void quux(String s) {
                System.out.println(s);
            }
        }
        
        LocalClass l = new LocalClass();
        Foo.bar("Winter is Coming", l);
    }
  
}
```
