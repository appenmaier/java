---
title: Zugriff auf Feldelemente
---

Der Zugriff auf die Elemente eines Feldes erfolgt über die Angabe des entsprechenden Index.

```java
public class MainClass {

    public static void main(String[] args) {
        int[] ids = { 4, 8, 15, 16, 23, 42 };

        for (int i = 0; i < ids.length; i++) {
            System.out.println(ids[i]);
        }
    }

}
```

> Der Index beginnt bei Java bei 0.
