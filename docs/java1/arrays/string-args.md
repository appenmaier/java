---
title:  Der Parameter String[] args
---

Der Parameter `String[] args` der main-Methode ermöglicht es dem Anwender, der ausführbaren Klasse beim Aufruf Informationen mitzugeben.

```java
public class MainClass {

    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.println("args[" + i + "]: " + args[i]);
        }
    }

}
```
