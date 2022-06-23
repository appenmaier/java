---
title: Programmausführung
---

Programme auf einem Computer können auf unterschiedliche Arten ausgeführt werden:
- **Compiler** übersetzen den Quellcode in eine Datei, die vom jeweiligen Betriebssystem ausgeführt werden kann
- **Interpreter** übersetzen den Quellcode direkt in den Arbeitsspeicher und führt das Programm sofort aus
- **JIT-Compiler[^1]** vereinen die Vorteile von Compiler und Interpreter:
    - Der Compiler übersetzt den Quellcode in den sogenannten Bytecode
    - Der Interpreter überführt den Bytecode in Maschinencode

Compilersprachen wie z.B. C++ sind deutlich performanter und ermöglichen eine sicherere Entwicklung, Interpretersprachen wie z.B. PHP sind dagegen plattformunabhängig.

![image](https://user-images.githubusercontent.com/47243617/171617813-15f09fe9-e06c-4f1b-81cf-19c7c594ae6f.png)

> In Java wird der Interpreter als **Java Virtual Machine** bezeichnet.

[^1]: Just-In-Time-Compiler
