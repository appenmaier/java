---
title: Überladene Methoden
---

Gleichnamige Methoden mit unterschiedlichen Parameterlisten einer Klasse werden in Java als überladene Methoden bezeichnet.

```java
public class Foo {

  public void bar() { }
  public void bar(Qux qux) { }
  public void bar(Qux qux, Quux quux) { }

}
```

> Überladene Methoden können keine unterschiedlichen Rückgabewerte besitzen.
