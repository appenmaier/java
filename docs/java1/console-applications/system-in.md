---
title: Konsoleneingaben
---

Die Klasse `Scanner` im Paket `java.util` stellt Methoden zur Verfügung, um Werte bestimmter Datentypen von der Konsole einzulesen.

```java
public class MainClass {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int i = scanner.nextInt();
        System.out.println(i);
    }

}
```

> Dem Konstruktor muss der Standard-Eingabestrom `System.in` als Wert mitgegeben werden (siehe [Datenströme (IO-Streams)](../../java2/io-streams/io-streams.md)).
