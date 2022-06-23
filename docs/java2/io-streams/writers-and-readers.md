---
title: Schreiben und Lesen zeichenorientierter Daten
---

Für die Verarbeitung von zeichenorientierten Daten (z.B. Textdokumente) stehen die abstrakten Basisklassen `Reader` und `Writer` zur Verfügung.

| Datenstromklasse | Ein- und Ausgabe in... |
| ---------------- | ---------------------- |
| `BufferedReader` und `BufferedWriter` | ...einen Puffer |
| `FileReader` und `FileWriter` | ...eine Datei |
| `StringReader` und `StringWriter` | ...eine Zeichenkette |

## Schreiben zeichenorientierter Daten
1. Datei-Objekt erzeugen
2. FileWriter-Objekt erzeugen
3. BufferedWriter-Objekt erzeugen
4. Daten schreiben

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.txt");

        try (FileWriter fileWriter = new FileWriter(file);
             		BufferedWriter bufferedWriter = new BufferedWriter(fileWriter)) {
            bufferedWriter.write("Winter is Coming");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}
```

## Lesen zeichenorientierter Daten
1. Datei-Objekt erzeugen
2. FileReader-Objekt erzeugen
3. BufferedReader-Objekt erzeugen
4. Werte auslesen

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.txt");

        try (FileReader fileReader = new FileReader(file);
             		BufferedReader bufferedReader = new BufferedReader(fileReader)) {
            String line;
            while ((line = bufferedReader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } 
    }

}
```
