---
title: Aussehen einer Szene
---

Das Aussehen einer Szene erfolgt über Stylesheets. Stylesheets sind Dokumente zur Festlegung des Erscheinungsbildes von Dokumenten und grafischen Benutzeroberflächen. CSS[^1] stellt eine gängige Sprache für Stylesheets dar und zählt zusammen mit HTML und JavaScript zu den Kernsprachen des WWW[^2]. 

## Definition von Stylesheets
Die Festlegung des Erscheinungsbildes erfolgt über Formatierungsregeln. Formatierungsregeln bestehen aus einem Selektor, mehreren Attributen sowie den dazugehörigen Werten. Die Selektoren legen fest, welche Formatierungsregeln für welche Bildschirmelemente gelten. Als Selektoren können entweder die Namen der Bildschirmelement-Klassen (button, text-field etc.), die Ids der Bildschirmelemente oder sogenannte Pseudoklassen (focused, pressed,…) verwendet werden.

```css
.root {
   -fx-font-size: 10.0pt;
   -fx-font-family: 'Arial';
   -fx-background: 'dimgray';
}

.label {
   -fx-text-fill: 'white';
}

.button {
   -fx-background-color: 'darkgray';
   -fx-base: rgb(255.0,255.0,255.0);
}

:focused {
   -fx-border-color: 'red';
   -fx-border-width: 2;
   -fx-border-radius: 3;
}
```

## Verwenden von Stylesheets
Jeder Szene einer JavaFX-Anwendungen können über den verketteten Methodenaufruf `getStylesheets().add(String)` beliebig viele Stylesheets zugewiesen werden. Der 
Methode `add(String)` muss dabei eine URL[^3] auf ein Stylesheet mitgegeben werden.

```java
public class MainClass extends Application {

   public void start(Stage primaryStage) {
      Parent root = FXMLLoader.load(getClass().getResource("View.fxml"));
      Scene scene = new Scene(root);      
      scene.getStylesheets().add(getClass().getResource("View.css").toExternalForm());
      primaryStage.setTitle("Aussehen einer Szene");
      primaryStage.setScene(scene);
      primaryStage.show();  
   }

}
```

[^1]: Cascading Stylesheets
[^2]: World Wide Web
[^3]: Uniform Resoruce Locator
