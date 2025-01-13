# Understanding the `implements` Keyword in Dart

## Overview
The `implements` keyword in Dart allows a class to define its behavior by adopting the structure of another class or interface. Unlike inheritance, where a subclass inherits both the implementation and the structure of a superclass, `implements` enforces the implementing class to provide its own definition for all the members of the implemented class.

This document explains the use of the `implements` keyword and related concepts with examples and best practices.

---

## Key Concepts

### 1. **Definition and Use of `implements`**
- A class uses the `implements` keyword to promise that it will implement all the properties and methods defined in another class or interface.
- The implementing class **does not inherit** the implementation from the implemented class but only adopts its structure.

### Example:
```dart
class Vehicle {
  int noOfWheels = 4;

  void accelerate() {
    print("Vehicle is accelerating");
  }
}

class Car implements Vehicle {
  @override
  int noOfWheels = 4;

  @override
  void accelerate() {
    print("Car is accelerating with $noOfWheels wheels.");
  }
}

void main() {
  final car = Car();
  car.accelerate();
}
```

### 2. **The `@override` Annotation**
- The `@override` annotation is optional but highly recommended. It ensures that:
  - You explicitly intend to override a member.
  - Dart will validate whether the member being overridden actually exists in the implemented class or interface.

#### Why Use `@override`?
- Avoids errors due to typos or misnamed methods.
- Improves code readability and maintainability by signaling overridden methods clearly.

### Example:
```dart
class Automobile {
  void startEngine() {
    print("Starting engine");
  }
}

class Truck implements Automobile {
  @override
  void startEngine() {
    print("Truck engine started");
  }
}
```

---

## `implements` vs. `extends`
| Feature             | `implements`                                  | `extends`                           |
|---------------------|-----------------------------------------------|-------------------------------------|
| **Inheritance**     | No implementation is inherited.               | Inherits both implementation and structure. |
| **Override Required** | All members must be explicitly overridden.   | Overriding is optional.             |
| **Flexibility**      | Multiple classes can be implemented.          | Only one class can be extended.     |

---

## Example with Multiple Interfaces

A class can implement multiple interfaces by separating them with commas.

### Example:
```dart
class Automobile {
  void start() {
    print("Automobile started");
  }
}

class Machine {
  void operate() {
    print("Machine operating");
  }
}

class Hybrid implements Automobile, Machine {
  @override
  void start() {
    print("Hybrid automobile started");
  }

  @override
  void operate() {
    print("Hybrid machine operating");
  }
}

void main() {
  final hybrid = Hybrid();
  hybrid.start();
  hybrid.operate();
}
```

---

## Best Practices for Using `implements`
1. **Define Clear Interfaces:** If you only need to define a structure (properties and methods), use abstract classes instead of concrete classes.

   ```dart
   abstract class Drivable {
     void drive();
   }

   class Bike implements Drivable {
     @override
     void drive() {
       print("Driving a bike");
     }
   }
   ```

2. **Use `@override` Annotation:** Always use `@override` to avoid accidental mismatches or missing methods.

3. **Favor Composition Over `implements` in Complex Hierarchies:** For more complex behavior sharing, consider composition instead of implementing multiple interfaces.

---

## Key Takeaways
- The `implements` keyword is a powerful way to define strict contracts for classes.
- It enforces the implementing class to provide its own logic for all members, ensuring a clear structure.
- Use `@override` to make your intent explicit and prevent errors.
- Dart allows implementing multiple classes or interfaces, making it flexible for various scenarios.

---

