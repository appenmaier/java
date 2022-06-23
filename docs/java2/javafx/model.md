---
title: Kommunikation zwischen Szenen
---

Da die verschiedenen Ereignisbehandler-Klassen in einer JavaFX-Anwendung nur lose miteiander gekoppelt sind, wird zur Kommunikation zwischen Szenen eine eindeutige Model-Klasse benötigt. Dies kann über das [Einzelstück-Entwurfsmuster (Singleton-Pattern)](../disgressions/design-patterns.md) erreicht werden.

## Beispiel
Die Klasse `Model` umfasst neben der Einzelstück-Implementierung das Attribut `input` sowie die dazugehörige set- und get-Methode.

```java
public class Model {

    private static Model instance;
    private String input;
  
    private Model() { }
  
    public static Model getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
    
    public void setInput(String input) {
        this.input = input;
    }
    
    public String getInput() {
        return input;
    }

}
```

In der Methode `initialize(URL, ResourceBundle)` der Klasse `InputController` wird das Attribut `model` initialisiert; in der Methode `goToOutput(ActionEvent)` wird zunächst die Eingabe in der Model-Klasse gespeichert und anschließend zur View `Output` gewechselt.

```java
public class InputController implements Initializable {

    @FXML
    private TextField inputTextField;
  
    private Model model;

    public void initialize(URL location, ResourceBundle resources) {
        model = Model.getInstance();    
    }

    public void goToOutput(ActionEvent actionEvent) { 
        String input = inputTextField.getText();
        model.setInput(input);
            
        Parent root = FXMLLoader.load(getClass().getResource("OutputView.fxml"));
        Scene scene = new Scene(root);
        Node node = (Node) actionEvent.getSource();
        Stage stage = (Stage) node.getScene().getWindow();
        stage.setScene(scene);
        stage.show();
    }

}
```

In der Methode `initialize(URL, ResourceBundle)` der Klasse `OuputController` wird zunächst das Attribut `model` initialisiert, anschließend die Eingabe aus dem Model ausgelesen und abschließend die Eingabe dem Ausgabefeld zugewiesen.

```java
public class OutputController implements Initializable {

    @FXML
    private Label inputLabel;
  
    private Model model;

    public void initialize(URL location, ResourceBundle resources) {
        model = Model.getInstance();    
        String input = model.getInput();
        inputLabel.setText(input);
    }

}
```
