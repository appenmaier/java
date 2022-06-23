---
title: Initialisierung
---

In Java müssen Datenobjekte vor der ersten Verwendung explizit initialisiert werden, d.h. mit einem Wert belegt werden. Der Zuweisungsoperator `=` weist dem Datenobjekt auf der linken Seite den Wert des Ausdrucks auf der rechten Seite zu.

```java
public class MainClass {

    public static void main(String[] args) {
        int a = 42, b = a;
        boolean error = true;
        char char1;
        String text;
        
        char1 = 'M';
        text = "Winter is Coming";
    }

}
```
