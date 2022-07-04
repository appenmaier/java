---
title: Laufzeitmessungen
---

Neben den print-Methoden des Standard-Ausgabestroms `System.out` besitzt die Klasse `System` auch die Methode `currentTimeMillis()`, die die Differenz in Millisekunden
zwischen der aktuellen Systemzeit und dem Nullpunkt[^1] zurückgibt. Dies kann z.B. für einfache Laufzeitmessungen genutzt werden.

```java
public class MainClass {

    public static void main(String[] args) {
        long start = System.currentTimeMillis();    
        for (int i = 0; i < 1000; i++) {
            Foo.bar();
        }    
        long end = System.currentTimeMillis();

        System.out.println(end - start);
    }

}
```

[^1]: Der festgelegte Nullpunkt ist der 1. Januar 1970, 0 Uhr
