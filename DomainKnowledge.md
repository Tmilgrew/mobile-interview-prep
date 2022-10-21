# Domain Knowledge

## Classes vs Structs vs Enum vs Protocol
<b>Classes:</b>

- Allocated on the heap
- Inheritance
- Type-casting
- Deinitializer
- Reference counting
- Reference types, i.e. not copied on assignment/passed as an argument
- Static dispatch on private and final methods

<b>Structs:</b>

- Allocated on the stack
- Automatically generated memberwise initializer with internal scope
- Value types, i.e. copied on assignment/passed as an argument
- Except for some standard library collections, copy occurs only on write
- Static dispatch on non-protocol conforming methods

Use classes if identity needs to be controlled, i.e. mutation of the class needs to be propagated to anything else that has a reference.

<b>Enum:</b>

- An enumeration defines a common type for a group of related values and enables you to work with those values in a type-safe way within your code.
- Whenever a procedure accepts a limited set of variables, consider using an enumeration.
- Raw values are compile time-set values directly assigned to every case within an enumeration.  You can explicityly assign a raw value: 

```
enum Character: Int {
	case letter = 6
	case digit
	case special
}
 
In this case the raw value for letter
is assigned as 6, while digit and 
special are implicitly assigned as 
2 and 3.
```

- Associated values allow you to store values of other types alongside case values:

```
enum Character: Int {
	case letter(Int)
	case digit
	case special(String)
}
```

<b>Protocol:</b>

## Design Patterns

### Structural Design Patterns
<b>MVC</b>


Model:

- Data specific to the application
- Defines logic and computation that manipulate process the data
- Contains persistent state
- No explicit connection to the view objects that present the data
- Not concerned with UI or presentation issues
- Is not aware of Controller or View and is not couple to either
- Should be reusable in related problem-domains

View:

- Objects user can see
- Enables viewing and editing of the data via user input (touches, clicks, keys)
- Is not aware of the Model or Controller
- Should be reconfigurable with different data
- View receives updates from the Controller
- View informs the Controller of user actions

Controller:

- Intermediary between view objects and one or more model objects
- Controller updates the Model, and is notified of any - changes to the Model
- Controller updates the View, and is informed of user actions from the View
- Can perform setup and coordinating tasks
- Manage life cycles of other objects


<b>MVVM</b>

<b>MVP</b>

<b>VIPER</b>

<b>MVI</b>


### Creational Design Patterns
<b>Abstract Factory</b>

Reference: [Refactor Guru: Abstract Factory](https://refactoring.guru/design-patterns/abstract-factory)

### Behavioral Design Patterns