---
title: Datenklassen (Records)
---

Datenklassen sind Klassen die lediglich der Kapselung unveränderlicher Daten dienen. Daher bestehen Datenklassen häufig aus Boilerplate-Code[^1].

[^1]: Unter Boilerplate-Code versteht man Anweisungblöcke, die an verschiedenen Stellen mehr oder weniger identisch verwendet werden

```java
public final class Student {

    public int id;
    public String name;

    public Student (int id, String name) {
        this.id = id;
        this.name = name;
    }
  
    public int getId() {
        return id;
    }
  
    public String getName() {
        return name;
    }
  
    public final boolean equals(Object o) { }
    public final int hashCode() { }
    public final String toString() { }

}
```

Seit Java 16 bieten Records die Möglichkeiten, Datenklassen einfach umzusetzen. Records sind spezielle Klassen, die anhand der festgelegten Parameter entsprechende
Konstruktoren, Getter sowie Implementierungen für die Methoden `equals(Object)`, `hashCode()` und `toString()` erzeugen. Das Schlüsselwort für Records lautet `record`.

```java
public record(int id, String name ) { }
```

> Da Records von der Klasse `Record` abgeleitet sind, können Records nicht von einer weiteren Klasse abgeleitet werden. Allerdings können Records, wie andere Klassen auch, beliebig viele [Schnittstellen](../../java1/inheritance/interfaces.md) implementieren.
