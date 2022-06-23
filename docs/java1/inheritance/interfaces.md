---
title: Schnittstellen (Interfaces)
---

Schnittstellen (Interfaces) sind im Prinzip abstrakte Klassen, die ausschließlich abstrakte Methoden besitzen. Durch Schnittstellen wird sichergestellt, dass Klassen bestimmte Methoden bereitstellen und dass verschiedene Klassen miteinander kommunizieren können.

## Definition von Schnittstellen
Die Definition einer Schnittstelle erfolgt analog zur Definition von Klassen. Das Schlüsselwort für Schnittstellen lautet `interface`. Eine Schnittstelle kann nur öffentliche, abstrakte und öffentliche, statische Methoden beinhalten.

```java
public interface Foo {  

    void bar();
    void baz();  

}
```

> Die Angabe von `abstract` und `public` bei Methoden ist nicht erforderlich.

## Implementieren von Schnittstellen
Schnittstellen werden mit Hilfe des Schlüsselworts `implements` von einer Klasse implementiert. Durch die Implementierung der Schnittstelle verpflichtet sich die Klasse, alle Methoden der Schnittstelle zu implementieren.

```java
public class Qux implements Foo {

    public void bar() { }
    public void baz() { }

}
```

## Verwenden von Schnittstellen
Schnittstellen können ebenso wie Klassen als Datentypen verwendet werden. Die Typumwandlung von der implementierenden Klasse zur Schnittstelle bezeichnet man als **Upcast**, die Rückumwandlung als **Downcast**.

```java
public class MainClass {

    public static void main(String[] args) {
        Foo foo;
        Qux qux = new Qux();
        foo = qux; // Upcast
    }

}
```
