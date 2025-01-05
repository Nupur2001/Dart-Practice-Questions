### Constructors in Dart:

- **Constructor**: A constructor is a special function inside a class that is used to initialize objects when they are created. It has the same name as the class and is called automatically when an object is instantiated.

### `this` keyword:
- The `this` keyword refers to the current instance of the class. It's used to refer to the instance variables (properties) of the class.
- In the constructor, we use `this` to assign the values passed as arguments (`shape` and `quantity`) to the corresponding instance variables (`this.shape` and `this.quantity`).

### Positional Arguments:
- Positional arguments are arguments passed to the constructor in a fixed order. Dart constructors can also have **positional** arguments, but this example uses **named arguments**.
- With **named arguments**, you can specify the argument names, which makes the code more readable and flexible.

### Named Arguments (with `required` keyword):
- In the code, we are using **named arguments** for the constructor (`shape` and `quantity`), which makes it clearer which value corresponds to which parameter when calling the constructor.
- The `required` keyword indicates that these arguments are mandatory when creating an object. Without providing these values, Dart will throw an error.

### Example of Constructor Behavior:
- In the example above, when we create the `cookie` object, the constructor is called automatically, which initializes the `shape` and `quantity` values. It also triggers the `baking` method immediately after the object is created.
- The constructor also prints a message: `"Cookie Constructor Called"`, allowing us to see that the constructor has executed.

### Using Constructors Effectively:
- Constructors are essential to initializing an object with specific data when it is created, and using named arguments with `required` ensures that the object is always initialized with necessary values.

### Private Variables:
- In Dart, **private variables** are defined by prefixing the variable name with an underscore (`_`). For example, `_height` and `_width` are private variables and cannot be accessed directly outside the `Cookie` class.
- These variables store data that is specific to the class and should not be modified directly from outside the class.

### Getters:
- A **getter** allows you to access a private variable outside the class. In this case, the getter `height` is used to access the private variable `_height`.
- The getter is defined with the `get` keyword: `int get height => _height;`.

### Setters:
- A **setter** allows you to modify a private variable outside the class. In this case, the setter `setHeight` is used to change the value of the private variable `_height`.
- The setter is defined with the `set` keyword: `set setHeight(int h) { _height = h; }`.

