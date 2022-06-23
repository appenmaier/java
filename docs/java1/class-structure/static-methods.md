---
title: Statische Methoden
---

**Statische Methoden** sind abgeschlossene Programmteile, die Parameter enthalten und einen Wert zurückgeben können. Sie müssen mit dem Schlüsselwort `static` gekennzeichnet werden (siehe [Statische Attribute und Methoden](../oo/static-attributes-and-methods.md)). Bei statischen Methoden, die einen Wert zurückgeben, muss der Datentyp des Rückgabewertes angegeben werden; bei statische Methoden, die keinen Wert zurückgeben, das Schlüsselwort `void`. Der Aufruf einer statischen Methode erfolgt über den Klassennamen gefolgt von einem Punkt.

```java
public class MainClass {

    public static void main(String[] args) {
        MainClass.printHelloWorld();
        MainClass.printText("Winter is Coming");
    }

    public static void printHelloWorld() {
        System.out.println("Winter is Coming");
    }

    public static void printText(String text) {
        System.out.println(text);
    }

}
```

> Die statischen Methoden einer Startklasse werden auch als **Unterprogramme** bezeichnet.
