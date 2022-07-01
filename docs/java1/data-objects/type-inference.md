---
title: Typinferenz bei Datenobjekten
---

Unter **Typinferenz** versteht man, dass bei der Deklaration eines Datenobjekts auf die Angabe eine Datentyps verzichtet werden kann, wenn der Compiler aufgrund der restlichen Angaben den Typ selbstständig ermitteln kann. Für die Typinferenz wird das Schlüsselwort `var` verwendet. 

```java
public class MainClass {

    public static void main(String[] args) {
        int i = 5;
        i = "Text"; // Kompilierungsfehler

        var j = 5;
        j = "Text"; // Kompilierungsfehler
    }

}
```

> Mit `var` deklarierte Datenobjekte sind weiterhin statisch typisiert. 
