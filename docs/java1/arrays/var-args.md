---
title:  Variable Arugmentlisten (VarArgs)
---

**Variable Argumentlisten** (VarArgs) ermöglichen die Definition von Methoden, denen beliebig viele Werte eines Datentyps mitgegeben werden können. Die Parameterliste einer Methode kann allerdings nur eine variable Argumentliste beinhalten und diese muss immer am Ende der Parameterliste stehen.

```java
public class MainClass {

    public static void main(String[] args) {
        printAll("Peter", "Lisa");
        printAll("Heidi", "Franz", "Fritz");
    }

    public static void printAll(String... texts) {
        for (int i = 0; i < texts.length; i++) {
            System.out.println(texts[i]);
        }
    }

}
```

> Technisch gesehen handelt es sich bei einer variablen Argumentliste um ein Feld.
