---
title: Generische Programmierung
---

Quellcode sollte generell so allgemein bzw. generisch geschrieben werden, dass er für unterschiedliche Datenstrukturen und Datentypen verwendet werden kann. Das Ziel der generischen Programmierung ist die Entwicklung von wiederverwendbarem Code. In Java verwendet man das Konzept der generischen Datentypen (**[Java Generics](java-generics.md)**), also Klassen, die mit verschiedene Datentypen verwendet werden können.

Auch ohne Java Generics kann in Java mit Hilfe der Klasse `Object` generisch programmiert werden. Der Nachteil besteht darin, dass durch den Upcast einer beliebigen Klasse auf die Klasse `Object` die spezifischen Methoden der Klasse nicht mehr verwendet werden können und der dadurch notwendige Downcast zu Laufzeitfehlern führen kann. 

## Beispiel
Die Klasse `Box` ermöglicht das Speichern einer beliebig typisierten Information.

```java
public class Box {

    private Object content;
    public void set(Object content) { this.content = content; }
    public Object get() { return content; }

}
```

In der main-Methode der Startklasse wird zunächst eine ganze Zahl in einer Box gespeichert und anschließend wieder ausgelesen. Die Umwandlung der ganzen Zahl in eine Zeichenkette führt erst zur Laufzeit zu einem Fehler.

```java
public class MainClass {

    public static void main(String[] args) {
        Box box = new Box();
        box.set(5);
        String i = (String) box.get(); // Laufzeitfehler
    }

}
```
