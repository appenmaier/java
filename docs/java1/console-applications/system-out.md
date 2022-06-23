---
title: Konsolenausgaben
---

Der Standard-Ausgabestrom `System.out` bietet verschiedene Methoden, um Informationen auf der Konsole auszugeben:
- Bei den **print-Methoden** wird die Information unverändert und linksbündig ausgegeben
- Bei den **println-Methoden** wird die Information unverändert und linksbündig ausgegeben. Zusätzlich wird ein Zeilenumbruch ausgeführt
- Bei den **printf-Methoden** wird die Information formatiert ausgegeben. Die Formatierungsregeln sind nach dem Muster _[flags]\[width][.precision]conversion-character_ 
aufgebaut

```java
public class MainClass {

    public static void main(String[] args) {
        System.out.print("Winter is Coming");
        System.out.println("Winter is Coming");
        System.out.printf("%25S", "Winter is Coming");
    }

}
```
