---
title: Erzeugen von Feldern
---

Da es sich bei Feldern um Objekte handelt, müssen diese vor Verwendung erzeugt werden. Bei der Erzeugung muss immer die Länge des Feldes (d.h. die Anzahl der Elemente) 
angegeben werden. Jedes Feld verfügt über das Attribut `length`, welches die Länge des Feldes enthält.

```java
public class MainClass {

    public static void main(String[] args) {
        int[] ids = new int[5];
        int[] ids2 = { 4, 8, 15, 16, 23, 42 };
    }

}
```

> Felder werden zwar mit Hilfe des new-Operators erzeugt, besitzen aber keinen Konstruktor.
