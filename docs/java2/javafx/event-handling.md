---
title: Ereignisbehandlung
---

Ereignisse sind Nachrichten, die über das System weitergeleitet werden. Auf grafischen Benutzeroberflächen werden Ereignisse z.B. durch das Betätigen einer Drucktaste 
ausgelöst. In Java wird die Ereignisbehandlung durch das **Delegationsmodell** festgelegt:
1. Empfänger können sich beim Sender für ein Ereignis registrieren
2. Der Sender löst das Ereignis aus und übergibt das erzeugte Ereignis-Objekt an alle registrierten Empfänger
3. Die Empfänger nehmen das Ereignis-Objekt entgegen und haben dadurch die Möglichkeit, auf das Ereignis zu reagieren

![image](https://user-images.githubusercontent.com/47243617/170099750-69e5778c-d55c-4769-84cd-019f4b8b4e74.png)

## JavaFX Ereignisse
JavaFX stellt verschiedene Ereignisse bereit, die auf unterschiedliche Art und Weise ausgelöst werden:
- Ein `ActionEvent` wird bei verschiedenen Interaktionen mit den Controls ausgelöst, z.B. durch das Betätigen einer Drucktaste
- Ein `MouseEvent` wird bei verschiedenen Maus-Aktivitäten ausgelöst, z.B. durch das Betätigen einer Maustaste
- Ein `KeyEvent` wird durch Tastatureingaben ausgelöst
- Ein `WindowEvent` wird ausgelöst, wenn sich der Zustand eines Fensters ändert

## Ereignisbehandlung nach dem MVC-Entwurfsmuster
Die Ereignisbehandlung in JavaFX kann nach dem [MVC-Entwurfsmuster](../disgressions/design-patterns.md) umgesetzt werden. Hierbei übernimmt eine Klasse (Controller) die Ereignisbehandlung für ein konkretes FXML-Dokument (View). Im FXML-Dokument wird über die Eigenschaft `fx:controller` die verantwortliche Klasse für die Ereignisbehandlung festgelegt. Den zu behandelnden Ereignissen kann über die Eigenschaft `onAction` eine Behandlermethode der Ereignisbehandler-Klasse zugewiesen werden. Um in der Ereignisbehandler-Klasse auf die jeweiligen Elemente des FXML-Dokuments zugreifen zu können, müssen diesen über die Eigenschaft `fx:id` entsprechende Ids zugewiesen werden.

```xml
<?xml version="1.0" encoding="UTF-8"?>

<?import javafx.geometry.Insets?>
<?import javafx.scene.control.Button?>
<?import javafx.scene.control.TextField?>
<?import javafx.scene.layout.VBox?>

<VBox spacing="5.0" xmlns:fx="http://javafx.com/fxml/1" fx:controller="Controller">
  <children>
    <TextField fx:id="inputTextField" promptText="Eingabe" />
    <Button text="Eingabe ausgeben" onAction="printInput"/>
  </children>
  <padding>
    <Insets bottom="25.0" left="25.0" right="25.0" top="25.0" />
  </padding>
</VBox>
```

In der Ereignisbehandler-Klasse werden die Behandlermethoden implementiert. Diese müssen zwingend den Parameter `ActionEvent` besitzen, mit dessen Hilfe auf das ausgelöste Ereignis zugegriffen werden kann. Das Verknüpfen von Attributen der Ereignisbehandler-Klasse mit den Elementen des FXML-Dokuments erfolgt über die Annotation `@FXML` und der Namensgleichheit zwischen dem Attribut der Ereignisbehandler-Klasse und dem Wert der Eigenschaft `fx:id` des entsprechenden Elements des FXML-Dokuments.

```java
public class Controller {

    @FXML
    private TextField inputTextField;

    public void printInput(ActionEvent actionEvent) {
        String input = inputTextField.getText();
        System.out.println(input);
    }

}
```
