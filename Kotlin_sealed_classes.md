In Kotlin, a `sealed class` is a special kind of class that is used to represent restricted class hierarchies. When a value can have one of a limited set of types, a sealed class is a good choice. Here are the main uses and features of sealed classes:

### Features of Sealed Classes

1. **Restricted Hierarchy:** Sealed classes allow you to define a fixed set of subclasses. This means that all subclasses must be known at compile-time.
2. **Enum-like Classes with State:** Sealed classes are often used when you need to represent a finite set of distinct types but with different properties and methods.
3. **Exhaustive When Expressions:** When expressions involving sealed classes can be exhaustive, meaning the compiler can check if all possible cases are covered.

### Syntax

A sealed class is declared using the `sealed` keyword. All subclasses of a sealed class must be declared within the same file.

```kotlin
sealed class Shape {
    class Circle(val radius: Double) : Shape()
    class Rectangle(val width: Double, val height: Double) : Shape()
    object NotAShape : Shape()
}

fun describeShape(shape: Shape): String {
    return when (shape) {
        is Shape.Circle -> "A circle with radius ${shape.radius}"
        is Shape.Rectangle -> "A rectangle with width ${shape.width} and height ${shape.height}"
        Shape.NotAShape -> "Not a shape"
    }
}
```

### Example Use Cases

#### Representing Different States

Sealed classes are useful for representing different states in state machines or UI states.

```kotlin
sealed class UiState {
    object Loading : UiState()
    class Success(val data: String) : UiState()
    class Error(val message: String) : UiState()
}

fun handleUiState(state: UiState) {
    when (state) {
        is UiState.Loading -> println("Loading...")
        is UiState.Success -> println("Success with data: ${state.data}")
        is UiState.Error -> println("Error: ${state.message}")
    }
}
```

#### Handling Network Responses

Sealed classes can be used to handle different types of network responses.

```kotlin
sealed class NetworkResult {
    data class Success(val data: String) : NetworkResult()
    data class Failure(val error: Throwable) : NetworkResult()
    object Loading : NetworkResult()
}

fun handleNetworkResult(result: NetworkResult) {
    when (result) {
        is NetworkResult.Success -> println("Data: ${result.data}")
        is NetworkResult.Failure -> println("Error: ${result.error.message}")
        NetworkResult.Loading -> println("Loading...")
    }
}
```

### Benefits

1. **Exhaustive When Expressions:** When you use sealed classes in a `when` expression, the compiler ensures that all possible subclasses are handled, providing compile-time safety.
2. **Better Modeling:** Sealed classes allow for better modeling of data structures and states by restricting the type hierarchy.
3. **Readability:** Code becomes more readable and maintainable as the possible types are known and limited.

### Conclusion

Sealed classes in Kotlin provide a powerful way to define and work with restricted hierarchies, making them ideal for modeling situations where a type can have a limited set of possible subclasses. They improve safety and readability by ensuring that all cases are handled, and they are particularly useful in scenarios like state representation and handling different types of responses.