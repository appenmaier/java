---
title: Aufbau einer Szene
---

Der Aufbau einer Szene erfolgt deklarativ mit Hilfe von FXML-Dokumenten. FXML stellt eine auf XML[^1]-basierende Sprache dar und ermöglicht eine klare Trennung zwischen Layout und Code:
1. Die Main-Klasse ruft den FXML-Loader auf
2. Der FXML-Loader überführt das FXML-Dokument in einen Szenegraphen
3. Der FXML-Loader instanziiert den Controller und ruft die (optionale) initialize-Methode auf

![image](https://user-images.githubusercontent.com/47243617/170098136-eb627556-61e9-4b79-a942-26a9f1ee54e4.png)

## Definition von FXML-Dokumenten
Die einzelnen Bildschirmelemente der Szene werden in einem FXML-Dokument als geschachtelte Elemente dargestellt.

```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.geometry.Insets?>
<?import javafx.scene.control.Button?>
<?import javafx.scene.control.Label?>
<?import javafx.scene.control.TextField?>
<?import javafx.scene.layout.VBox?>

<VBox spacing="5.0" xmlns:fx="http://javafx.com/fxml/1">
   <children>
      <Button text="Drucktaste" />
      <Label text="Ausgabefeld" />
      <TextField promptText="Eingabefeld" />
   </children>
   <padding>
      <Insets bottom="25.0" left="25.0" right="25.0" top="25.0" />
   </padding>
</VBox>
```

## Verwenden von FXML-Dokumenten
Die statische Methode `load(URL)` der Klasse `FXMLLoader` überführt das angegebene FXML-Dokument in einen Szenegraphen und gibt den dazugehörigen Wurzelknoten vom Typ `Parent` zurück, mit dessen Hilfe anschließend die Szene erstellt werden kann.

```java
public class MainClass extends Application {

  public void start(Stage primaryStage) throws IOException {
    Parent root = FXMLLoader.load(getClass().getResource("View.fxml"));
    Scene scene = new Scene(root);
    primaryStage.setTitle("Aufbau einer Szene");
    primaryStage.setScene(scene);    
    primaryStage.show();
  }

}
```

[^1]: Die **Extensible Markup Language** (XML) ist eine Auszeichnungssprache zur Beschreibung strukturierter Daten
