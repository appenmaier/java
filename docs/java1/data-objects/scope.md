---
title: Gültigkeitsbereiche
---

Datenobjekte sind nur innerhalb eines Programmabschnitts (Unterprogramm[^1], Funktion[^2], Methode oder Anweisungsblock) gültig, d.h. man kann nur innerhalb dieses Programmabschnitts auf das Datenobjekt zugreifen.

```java
public class MainClass {

    public static void main(String[] args) {
        int a = 1, b;
        b = foo(a);
    }

    public static int foo(int c) {
        int d;
        d = a++; // Kompilierungsfehler
        d = c++;
        return d;
    }

}
```

[^1]: Die statischen Methoden einer Startklasse bezeichnet man als **Unterprogramme**
[^2]: Funktionen sind Methoden, die sowohl über Parameter als auch einen Rückgabewert verfügen
