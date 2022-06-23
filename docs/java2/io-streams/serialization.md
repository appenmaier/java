---
title: Schreiben und Lesen serialisierter Objekte
---

Um ein Objekt persistent zu machen (also zu sichern) und um ein Objekt durch das Netzwerk zu schicken (also für entfernte Methodenaufrufe) ist es notwendig, das Objekt in einen Byte-Strom umzuwandeln. Die Umwandlung eines Objektes in einen Byte-Strom bezeichnet man als **Serialisierung**, die Rückumwandlung als **Deserialisierung**. Die Serialisierung erfolgt über die writeObject-Methode der Klasse `ObjectOutputStream`, die Deserialisierung über die readObject-Methode der Klasse `ObjectInputStream`.

Damit Objekte einer Klasse serialisiert werden können, muss die entsprechende Klasse die Schnittstelle `Serializable` implementieren. Die Schnittstelle `Serializable` ist eine sogenannte Marker-Schnittstelle, d.h. sie besitzt keine zu implementierenden Methoden.

## Schreiben serialisierter Objekte
1. Datei-Objekt erzeugen
2. FileOutputStream-Objekt erzeugen
3. ObjectOutputStream-Objekt erzeugen
4. Objekte schreiben

```java
public class MainClass {

    public static void main(String[] args) {
        ArrayList<Foo> foos = new ArrayList();
        …
        File file = new File("foos.bin");

        try (FileOutputStream fileOutputStream = new FileOutputStream(file);
             		ObjectOutputStream objectOutputStream = new ObjectOutputStream(fileOutputStream)) {
            for (Foo f : foos) {
                objectOutputStream.writeObject(f);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}
```

## Lesen serialisierter Objekte
1. Datei-Objekt erzeugen
2. FileInputStream-Objekt erzeugen
3. ObjectInputStream-Objekt erzeugen
4. Objekte auslesen

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("foos.bin");

        try (FileInputStream fileInputStream = new FileInputStream(file);
             		ObjectInputStream objectInputStream = new ObjectInputStream(fileInputStream)) {
            while (true) {
                Foo foo = (Foo) objectInputStream.readObject();
                System.out.println(foo);
            }
        } catch (EOFException e) {
            /* End of File */
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }

}
```

## Versionierung bei der Serialisierung
Die Konstante `serialVersionUID` vom Datentyp `long` dient zur eindeutigen Identifikation der Version einer serialisierbaren Klasse. Durch die Konstante kann sichergestellt werden, dass Empfänger von serialisierten Objekten typkompatibel zum Sender sind, d.h. eine passende Klassenstruktur aufweisen.

```java
public class Foo implements Serializable {

    public static final long serialVersionUID = 1L;

}
```

> Obwohl jede serialisierbare Klasse automatisch eine ID erhält, wird die manuelle Zuweisung dringend empfohlen.
