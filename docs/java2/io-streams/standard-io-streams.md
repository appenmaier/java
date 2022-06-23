---
title: Standard-Datenströme zur Ein- und Ausgabe
---

Java stellt Standard-Datenströme für die Eingabe (`System.in`), die Ausgabe (`System.out`), sowie die Fehlerausgabe (`System.err`) zur Verfügung.

```java
public class MainClass {

    public static void main(String[] args) {
        byte input[] = new byte[256];
        int noBytes = 0;
        String output = "";

        try {
            noBytes = System.in.read(input);
        } catch (IOException e) {
            System.err.println(e.getMessage());
        }

        if (noBytes > 0) {
            output = new String(input, 0, noBytes);
        System.out.println(output);
        }
    }

}

```
> Die Klasse `Scanner`, die ebenfalls auf dem Datenstrom-Konzept basiert, ermöglicht eine einfache Möglichkeit der Eingabe.
