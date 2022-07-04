---
title: Datums- und Zeitangaben
---

Die Klasse `LocalDateTime` liefert alle relevanten Informationen zum fast weltweit verwendeten Kalendersystem ISO-8601 (gregorianischer Kalender).

```java
public class MainClass {

    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();

        System.out.println("Jahr: " + now.getYear());
        System.out.println("Monat: " + now.getMonth());
        System.out.println("Tag: " + now.getDayOfMonth());
    }

}
```
