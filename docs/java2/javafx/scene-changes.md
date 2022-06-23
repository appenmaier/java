---
title: Wechsel zwischen Szenen
---

Der Wechsel von Szenen erfolgt über die Methode `setScene(Scene)` der Klasse `Stage`. Die Methode `getSource()` der Klasse `ActionEvent` gibt das Bildschirmelement zurück, welches das Ereignis ausgelöst hat; die Methode `getWindow()` der Klasse `Scene` die Bühne, auf der die aktuelle Szene aufgeführt wird.

```java
public class Controller {

    public void goToOutput(ActionEvent actionEvent) throws IOException {  
        Parent root = FXMLLoader.load(getClass().getResource("View.fxml"));
        Scene scene = new Scene(root);
        Node node = (Node) actionEvent.getSource();
        Stage stage = (Stage) node.getScene().getWindow();
        stage.setScene(scene);
        stage.show();
    }

}
```
