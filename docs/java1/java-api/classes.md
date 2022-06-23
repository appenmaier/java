---
title: Wichtige Klassen
---

Um das Rad nicht jedesmal neu erfinden zu müssen, stellt die Java API eine Reiher hilfreicher Klassen bereit.

## Die Klasse Math
Die Klasse `Math` stellt neben einigen Konstanten wie der Kreiszahl Pi und der Eulerschen Zahl zahlreiche Methoden für mathematische Berechnungen zur Verfügung.

```java
public class MainClass {

    public static void main(String[] args) {
        int a = 5;
        int b = 3;
        double result;

        result = Math.pow(a, b);
        System.out.println(result);

        result = Math.sqrt(a);
        System.out.println(result);
    }

}
```

## Die Klasse Random
Die Klasse `Random` ermöglicht das Erzeugen von Pseudozufallszahlen[^1].

[^1]: Pseudozufallszahlen sind scheinbar zufällige Zahlen, die aber auf Grund einer Formel berechnet werden

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

## Die Klasse System
Neben den print-Methoden des Standard-Ausgabestroms `System.out` besitzt die Klasse `System` auch die Methode `currentTimeMillis()`, die die Differenz in Millisekunden zwischen der aktuellen Systemzeit und dem Nullpunkt[^2] zurückgibt. Dies kann z.B. für einfache Laufzeitmessungen genutzt werden.

[^2]: Der festgelegte Nullpunkt ist der 1. Januar 1970, 0 Uhr

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

## Die Klasse LocalDateTime
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

## Die Klasse Object
Alle Klassen in Java sind letztlich Unterklassen der Klasse `Object`. Daher wird diese auch als die Mutter aller Klassen bezeichnet. Die Klasse vererbt ihren Unterklassen wichtige Methoden, die jede Unterklasse überschreiben sollte (siehe [Vererbung](inheritance.md)):
- Die Methode `equals(Object)` prüft zwei Objekte auf Gleichheit[^3]
- Die Methode `hashCode()` liefert den Hashcode des aktuellen Objektes zurück
- Die Methode `toString()` liefert eine eindeutige Kennung des Objektes in der Form _[Vollständiger Klassenname]_@_[Adresse des Objektes im Hauptspeicher in hexadezimaler Notation]_[^4] zurück

[^3]: Zwei Objekte sind gleich, wenn all ihre Attribute gleich sind
[^4]: Der vollständige Klassennamen setzt sich aus den Paketen sowie dem eigentlichen Klassennamen zusammen

> Wird den print-Methoden des Ausgabestroms `System.out` eine Objektreferenz übergeben, wird implizit die Methode `toString()` des jeweiligen Objektes aufgerufen.

## Wrapper-Klassen
Wrapper-Klassen verpacken primitive Datentypen in vollwertigen Klassen und erweitern so die primitiven Datentypen um hilfreiche Methoden. Das Verpacken eines primitiven Datentyps bezeichnet man als **Boxing**, das Entpacken als **Unboxing**.

```java
public class MainClass {

    public static void main(String[] args) {
        Integer i = Integer.valueOf("631");
        Boolean b = Boolean.logicalXor(true, false);
        Character c = Character.toUpperCase('a');
    }

}
```
