# Object-Oriented Programming — Assignment (AITU)

![Java](https://img.shields.io/badge/Java-17-007396?logo=openjdk&logoColor=white)

## Overview

A small Java program demonstrating core OOP principles: abstract classes, interfaces, inheritance, method overriding, and polymorphism. Models a simple payroll scenario with employees and students sorted by payment amount.

## What it implements

- **`Payable` interface** — single-method contract `getPaymentAmount()`, applied to all payable entities.
- **`Person` abstract class** — implements `Payable` and `Comparable<Person>`. Holds `id` (auto-incremented), `name`, and `surname`. `compareTo` orders by `getPaymentAmount()`, enabling `Collections.sort`.
- **`Employee extends Person`** — concrete subclass with `position` and `salary` fields. `getPaymentAmount()` returns the salary directly.
- **`Student extends Person`** — concrete subclass with `gpa`. `getPaymentAmount()` returns a scholarship (36,660) if GPA > 2.67, else 0 — demonstrates conditional business logic via polymorphism.
- **Polymorphic collection** — `Main` stores both `Employee` and `Student` objects in an `ArrayList<Person>`, sorts them with `Collections.sort` (using the `Comparable` implementation), and prints each via the common `toString` / `getPaymentAmount` interface.

## Project structure

```
src/
├── Payable.java    # Interface: getPaymentAmount()
├── Person.java     # Abstract base: id, name, surname; Comparable by payment
├── Employee.java   # Concrete: position + salary
├── Student.java    # Concrete: GPA-based scholarship logic
└── Main.java       # Builds a mixed list, sorts, and prints results
```

## How to run

```bash
javac -d out src/*.java
java -cp out Main
```

Expected output (sorted ascending by payment amount):

```
Student: 3. Ringo Starr earns 0.00 tenge
Employee: 1. John Lennon earns 27045.78 tenge
Student: 4. Paul McCartney earns 36660.00 tenge
Employee: 2. George Harrison earns 50000.00 tenge
```

---

Adil Ormanov — [GitHub](https://github.com/Adilforest)
