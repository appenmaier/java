---
title: Die try-with-resources-Anweisung
---

Bei einer "normalen" try-catch-Anweisung müssen die Datenstrom-Klassen manuell geschlossen werden, was sich als sehr aufwändig darstellt.

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.txt");
        FileWriter fileWriter = null;
        BufferedWriter bufferedWriter = null;

        try {
            fileWriter = new FileWriter(file);
            bufferedWriter = new BufferedWriter(fileWriter);
            bufferedWriter.write("Winter is Coming");
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (bufferedWriter != null) {
                try {
                    bufferedWriter.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }

}
```
> Der finally-Block einer try-Anweisung wird in jedem Fall durchlaufen.

Die try-with-resources-Anweisung ermöglicht die Deklaration von Ressourcen, die am Ende des try-Blockes automatisch geschlossen werden.

```java
public class MainClass {

    public static void main(String[] args) {
        File file = new File("stark.txt");

        try (FileWriter fileWriter = new FileWriter(file); BufferedWriter bufferedWriter = new BufferedWriter(fileWriter)) {
            bufferedWriter.write("Winter is Coming");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }

}
```

> Voraussetzung für den Einsatz der try-with-resources-Anweisung ist, dass die Ressourcen-Klassen die Schnittstelle `AutoCloseable` implementiert haben.
