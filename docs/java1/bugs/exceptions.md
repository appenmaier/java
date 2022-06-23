---
title: Ausnahmen (Exceptions)
---

**Ausnahmen** (Exceptions) stellen Operationen dar, die zur Laufzeit nicht ausgeführt werden können (z.B. die Division durch Null). Sie gewährleisten eine klare Trennung zwischen funktionalem Code und Code zur Fehlerbehandlung. Die Fehlerbehandlung erfolgt gemäß dem Ausnahmenbehandlungsprozess: nachdem eine Ausnahme ausgelöst wurde, kann bzw. muss diese je nach Ausnahmenart vom Empfänger der Ausnahme entweder behandelt oder weitergeleitet werden (**Catch-or-Throw-Regel**). Man unterscheidet zwischen **geprüften** (checked) und **ungeprüften** (unchecked) Ausnahmen. Geprüfte Ausnahmen **müssen**, ungeprüfte Ausnahmen **können** behandelt bzw. weitergeleitet werden.

## Die Klassenhierarchie der Laufzeitfehler
Die Klasse `Throwable` stellt die Oberklasse aller Laufzeitfehler dar. Schwerwiegende Fehler (hauptsächlich Probleme in der JVM[^1]) werden durch Unterklassen der Klasse `Error` abgebildet, geprüfte Ausnahmen durch Unterklassen der Klasse `Exception` und ungeprüfte Ausnahmen durch Unterklassen der Klasse `RuntimeException`.

![image](https://user-images.githubusercontent.com/47243617/171613641-bfe294ad-7323-4865-a043-f77c751a8759.png)

## Definition von Ausnahmenklassen
Eigene Ausnahmenklassen werden durch einfaches Ableiten von einer bestehenden Ausnahmenklasse definiert. Ausnahmenklassen sollten dabei immer von der Klasse `Exception` oder einer ihrer Unterklassen abgeleitet werden, nicht von der Klasse `Error`.

```java
public class QuxException extends Exception {

    public QuxException() { }
    public QuxException(String message) { }

}
```

## Auslösen von Ausnahmen
Mit dem Schlüsselwort `throw` kann innerhalb einer Methode eine Ausnahme ausgelöst werden. Die Methode, in der die Ausnahme ausgelöst wird, muss mit dem Schlüsselwort `throws` die Ausnahmenklasse angeben, die ausgelöst werden kann.

```java
public class Foo {

    public void bar() throws QuxException {
        throw new QuxException();
    }

}
```

## Weiterleiten von Ausnahmen
Ausnahmen können weitergeleitet werden. Hierbei wird die Fehlerbehandlung an die nächsthöhere Ebene weitergegeben. Um eine Ausnahme weiterzuleiten, muss in der weiterleitenden Methode mit `throws` die Ausnahme angegeben werden, die ausgelöst werden kann.

```java
public class Foo {

    public void bar() throws QuxException {
        throw new QuxException();
    }
    
    public void baz() throws QuxException {
        bar();
    }

}
```

## Abfangen von Ausnahmen
Mit Hilfe der try-catch-Anweisung können Methoden, die eine Ausnahme auslösen können, überwacht werden; d.h. die Ausnahmen werden gegebenenfalls abgefangen. Der try-Block enthält die Anweisungen, die überwacht werden sollen, der catch-Block enthält die eigentliche Fehlerbehandlung. Als Parameter von `catch` muss angegeben werden, welche Ausnahme(n) abgefangen werden soll(en).

```java
public class MainClass {

    public static void main(String[] args) {
        try {
            Foo foo = new Foo();
            foo.bar();
        } catch (QuxException e) {
            /* Fehlerbehandlung */
        }
    }

}
```

[^1]: Java Virtual Machine
