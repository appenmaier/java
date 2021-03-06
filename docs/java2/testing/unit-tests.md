---
title: Komponententests (Unit Tests)
---

**Komponententests** (Unit Tests) werden zum Testen einzelner, abgeschlossener Softwarebausteine verwendete. JUnit ist ein weit verbreitetes Framework zur Erstellung von Komponententests bzw. zum automatisierten Testen von Klassen und Methoden in Java. Die aktuelle Version **JUnit 5** stellt eine Kombination verschiedener Module der Projekte **JUnit Platform**, **JUnit Jupiter** sowie **JUnit Vintage** dar.

## Implementieren einer Testklasse
JUnit-Testklassen werden mit Hilfe entsprechender Annotationen implementiert:
- Die Annotationen `@Test` und `@ParameterizedTest` definieren einfache bzw. parametrisierte Testmethoden
- Die Annotationen `@BeforeAll` und `@AfterAll` definieren statische Methoden, die aufgerufen werden, wenn die Klasse für den Test initialisiert wird bzw. wenn alle Tests abgeschlossen sind
- Die Annotationen `@BeforeEach` und `@AfterEach` definieren Methoden, die vor bzw. nach jeder Testmethode aufgerufen werden
- Die Annotation `@Disabled` bewirkt, dass eine Testmethode beim Testen nicht ausgeführt wird
- Mit Hilfe der Annotation `@DisplayName` kann einer Testklasse bzw. einer Testmethode ein Anzeigename zugewiesen werden

## Zusicherungen (Assertions)
Die Klasse `Assertions` stellt verschiedene Methoden bereit, die immer dann eine Ausnahme vom Typ `AssertionError` auslösen, wenn das Ergebnis eines Methodenaufrufs nicht wie erwartet ausgefallen ist. Eine Ausnahme vom Typ `AssertionError` führt dazu, dass der Test als nicht erfolgreich gewertet wird.

| Assert-Methode | Bedeutung |
| -------------- | --------- |
| assertTrue, assertFalse | Prüft, ob etwas wahr ist bzw. falsch ist |
| assertNull, assertNotNull | Prüft, ob etwas null ist bzw. nicht null ist |
| assertSame, assertNotSame | Prüft, ob zwei Objekte identisch sind bzw. ob zwei Objekte nicht identisch sind |
| assertEquals, assertNotEquals | Prüft, ob zwei Elemente gleich sind bzw. ob zwei Element ungleich sind |
| assertThrows | Prüft, ob eine Ausnahme ausgelöst wird |
| assertTimeout | Prüft, ob eine Laufzeit eingehalten wird |

## Beispiel
Die Klasse `Calculator` stellt mehrere Methoden bereit, die getestet werden sollen.

```java
public class Calculator {
 
    public Calculator() { }
    
    public int abs(int a) {
        return a >= 0 ? a : a * -1;
    }
    
    public int divide(int a, int b) {
        return a / b;
    }
    
    public int multiply(int a, int b) {
        return a * b;
    }
    
}
```

Die statische Methode `setUp()` der Testklasse `CalculatorTest` stellt sicher, dass vor der Ausführung der Testmethoden ein Taschenrechner-Objekt erzeugt wird. In den Testmethoden werden verschiedene Testfälle wie z.B. die Division durch Null getestet.

```java
public class CalculatorTest {

    private static Calculator calculator;

    @BeforeAll
    static void setUp() {
        calculator = new Calculator();
    }

    @Test
    @DisplayName("Multiplication with Zero")
    void multiply_withZero_Zero() {
        assertEquals(0, calculator.multiply(0, 5));
        assertEquals(0, calculator.multiply(5, 0));
    }

    @ParameterizedTest
    @DisplayName("Absolute Values of positive and negative Values")
    @ValueSource(ints = { -1, 0, 1 })
    void abs_positiveAndNegativeValues_AbsoluteValues(int a) {
        assertTrue(calculator.abs(a) >= 0);
    }

    @Test
    @DisplayName("Division by Zero")
    void divide_byZero_ArithmeticException() {
        assertThrows(ArithmeticException.class, () -> calculator.divide(5, 0));
    }

}
``` 
