---
title: Schreiben und Lesen byteorientierter Daten
---

Für die Verarbeitung von byteorientierten Daten (z.B. Bild- und Video-Dateien) stehen die abstrakten Basisklassen `InputStream` und `OutputStream` zur Verfügung.

| Datenstromklasse | Ein- und Ausgabe in... |
| ---------------- | ---------------------- |
| `BufferedInputStream` und `BufferedOutputStream` | ...einen Puffer |
| `FileInputStream` und `FileOutputStream` | ...eine Datei |
| `StringInputStream` und `StringOutputStream` | ...eine Zeichenkette |

## Schreiben byteorientierter Daten
1. Datei-Objekt erzeugen
2. FileOutputStream-Objekt erzeugen
3. BufferedOutputStream-Objekt erzeugen
4. Daten schreiben

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.bin");

        try (FileOutputStream fileOutputStream = new FileOutputStream(file);
             		BufferedOutputStream bufferedOutputStream = new BufferedOutputStream(fileOutputStream)) {
            bufferedOutputStream.write("Winter is Coming".toBytes());
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}
```

## Lesen byteorientierter Daten
1. Datei-Objekt erzeugen
2. FileInputStream-Objekt erzeugen
3. BufferedInputStream-Objekt erzeugen
4. Werte auslesen

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.bin");

        try (FileInputStream fileInputStream = new FileInputStream(file);
             		BufferedInputStream bufferedInputStream = new BufferedInputStream(fileInputStream)) {
             	byte[] input = bufferedInputStream.readAllBytes();
             	System.out.println(new String(input));
        } catch (IOException e) {
            e.printStackTrace();
        } 
    }

}
```