---
title: Dateien und Verzeichnisse
---

Die Klasse `File` ermöglicht die Arbeit mit Dateien und Verzeichnissen. Mit Hilfe der Methode `exists()` kann beispielsweise geprüft werden, ob ein entsprechendes
Verzeichnis bzw. eine entsprechende Datei existiert oder nicht. Die Klasse bietet zudem Methoden zum Erstellen und Löschen von Verzeichnissen bzw. Dateien. Zum Erzeugen eines File-Objekts wird entweder ein Pfad zu einem Verzeichnis bzw. zu einer Datei oder ein URI[^1] benötigt.

[^1]: Unified Resource Identifier

## Lesen von Dateien mit Hilfe der Klasse Scanner
Zum Lesen einer Datei können entweder [Datenstromklassen](/java2/io-streams/io-streams.md) oder die Klasse `Scanner` verwendet werden.

```java
public class MainClass {

    public static void main(String[] args) throws FileNotFoundException {
        File file = new File("text.txt");
        Scanner scanner = new Scanner(file);

        while (scanner.hasNextLine()) {
            String line = scanner.nextLine();
            System.out.println(line);
        }

        scanner.close();
    }

}
```

> Nach der letzten Verwendung sollte die Methode `close()` der Klasse `Scanner` aufgerufen werden.

## Absolute und relative Pfadangaben
Beim Zugriff auf Verzeichnisse bzw. Dateien unterscheidet man zwischen absoluten und relativen Pfadangaben. Bei absoluten Pfadangaben wird der vollständige Pfad von der Wurzel des jeweiligen Verzeichnissystems bis zum Ziel angegeben, bei relativen der Weg von einem festgelegten Bezugspunkt bis zum Ziel.

![image](https://user-images.githubusercontent.com/47243617/170679603-aae95922-96a4-4e80-bdba-2a8b509115a8.png)

> Alle Klassen im Paket `java.io` verwenden als Bezugspunkt das Arbeitsverzeichnis des Benutzers (Systemeigenschaft `user.dir`).
