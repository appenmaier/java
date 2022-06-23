---
title: Überschriebene Methoden
---

Wird in einer Unterklasse eine Methode definiert, die der Signatur einer Methode der Oberklasse entspricht, wird die Methode der Oberklasse "überschrieben", 
d.h. von der Unterklasse neu implementiert. Bei Bedarf kann die ursprüngliche Methodenimplementierung der Oberklasse mit Hilfe der Objektreferenz `super` aufgerufen werden.

```java
public class SuperClass {

    public void foo(){
        System.out.println("foo");
    }
    
}

public class SubClass extends SuperClass {

    @Override
    public void foo(){
        super.foo();
        System.out.println("bar");
    }
  
} 
```

> Die Annotation `@Override` sorgt bei fehlerhaftem Überschreiben der Methode für entsprechende Kompilierungsfehler.
