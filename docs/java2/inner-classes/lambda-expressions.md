---
title: Lambda-Ausdrücke
---

**Lambda-Ausdrücke** sind anonyme Funktionen, die nur über ihre Referenz angesprochen werden können. Die Methodenparameter und der Methodenkörper werden getrennt vom 
Pfeiloperator `->` notiert. Voraussetzung für den Einsatz eines Lambda-Ausdrucks ist eine funktionale Schnittstelle[^1].

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

In der main-Methode der Startklasse soll die Methode `bar(String, Qux)` der Klasse `Foo` aufgerufen werden, wofür eine konkrete Implementierung der Schnittstelle `Qux` benötigt wird. Die Implementierung erfolgt in Form eines Lambda-Ausdrucks.

```java
public class MainClass {

    public static void main(String[] args) {
        Foo.bar("Winter is Coming", s -> System.out.println(s));
    }

}
```

## Syntaxvarianten
- Bei keinem oder mehreren Methodenparametern müssen diese in runden Klammern angegeben werden, bei genau einem Methodenparameter können die runden Klammern weggelassen werden
- Besteht der Methodenkörper aus mehreren Anweisungen, müssen diese in geschweiften Klammern angegeben werden, bei genau einer Anweisung können die geschweiften Klammern weggelassen werden
- Besteht der Methodenkörper aus genau einer Anweisung, kann das Semikolon am Anweisungsende weggelassen werden, ist die Anweisung eine return-Anweisung, kann auch das `return` weggelassen werden

## Methodenreferenzen
Lambda-Ausdrücke, bei denen die referenzierte Methode von den Parametertypen und vom Rückgabetyp genau auf die zu implementierende Methode passt, können als 
Methodenreferenz dargestellt werden. Bei einer Methodenreferenz wird die Klasse bzw. die Referenz auf der linken Seite mit Hilfe zweier Doppelpunkte vom Methodennamen 
auf der recht Seite getrennt.

```java
public class MainClass {

    public static void main(String[] args) {
        Foo.bar("Winter is Coming", s -> System.out.println(s)); // Lambda-Ausdruck
        Foo.bar("Winter is Coming", System.out::println); // Methodenreferenz
    }

}
```

[^1]: Eine funktionale Schnittstelle ist eine Schnittstelle, die über genau eine Methode verfügt
