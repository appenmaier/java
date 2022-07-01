---
title: Typumwandlung (Type Casting)
---

Der Cast-Operator `()` erlaubt die explizite Umwandlung eines Datentyps in einen anderen. Bei Wertzuweisungen findet eine implizite Typumwandlung vom niederwertigen zum höherwertigen Datentyp statt. Zu beachten ist, dass bei einer Typumwandlung ein Genauigkeitsverlust stattfinden kann.

```java
public class MainClass {

    public static void main(String[] args) {
        int a = 14;
        int b = 3;
        double result;
 
        // implizite Typumwandlung
        result = a / b;
        System.out.println(result); 

        // explizite Typumwandlung
        result = (double) a / b;
        System.out.println(result); 
    }

}
```

Die Wertigkeit von Datentypen entscheidet darüber, welche Typumwandlungen möglich sind.

![image](https://user-images.githubusercontent.com/47243617/170633184-e5f0e9c3-0d17-4f46-b718-4b12657aa53c.png)

> Für den Datentyp `boolean` ist keine Typumwandlung möglich
