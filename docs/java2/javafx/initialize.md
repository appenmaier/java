---
title: Initialisierung einer Szene
---

Die Methode `initialize(URL, ResourceBundle)` der Schnittstelle `Initializable` wird vom FXML-Loader vor Anzeige der dazugehörigen Szene aufgerufen und ermöglicht es, 
die Szene dynamisch anzupassen.

```java
public class Controller implements Initializable {

    @FXML
    private Label label;

    public void initialize(URL location, ResourceBundle resources) {
        Random random = new Random();
        int randomNumber = random.nextInt(100);
        label.setText(String.valueOf(randomNumber));
    }

}
```
