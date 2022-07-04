---
title: Pseudozufallszahlen
---

Die Klasse `Random` ermöglicht das Erzeugen von Pseudozufallszahlen[^1].

```java
public class MainClass {

    public static void main(String[] args) {
        Random random = new Random();
        int randomNumber;

        for (int i = 0; i < 100; i++) {
            randomNumber = random.nextInt(100) + 1;
            System.out.println(randomNumber);
        }
    }

}
```

[^1]: Pseudozufallszahlen sind scheinbar zufällige Zahlen, die aber auf Grund einer Formel berechnet werden
