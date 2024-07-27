In Kotlin, a coroutine is a concurrency design pattern that you can use on Android to simplify code that executes asynchronously. Coroutines help manage long-running tasks that might otherwise block the main thread and lead to an unresponsive UI.

### Ways to Start a Coroutine

1. **`launch`**:
   - Starts a new coroutine without blocking the current thread.
   - Returns a `Job` that can be used to manage the coroutine (e.g., cancel it).
   ```kotlin
   GlobalScope.launch {
       // Your code here
   }
   ```

2. **`async`**:
   - Starts a new coroutine and returns a `Deferred`, which is a light-weight non-blocking future that represents a promise to provide a result later.
   - You can use `await()` on the `Deferred` to get the result.
   ```kotlin
   val deferred = GlobalScope.async {
       // Your code here
       "result"
   }
   runBlocking {
       val result = deferred.await()
   }
   ```

3. **`runBlocking`**:
   - Runs a new coroutine and blocks the current thread until its completion.
   - Typically used for testing or main functions.
   ```kotlin
   runBlocking {
       // Your code here
   }
   ```

4. **`CoroutineScope.launch`**:
   - Defines a scope for new coroutines.
   - Useful for structured concurrency.
   ```kotlin
   val scope = CoroutineScope(Dispatchers.Default)
   scope.launch {
       // Your code here
   }
   ```

### Example

```kotlin
import kotlinx.coroutines.*

fun main() {
   // launch example
   GlobalScope.launch {
       delay(1000L)
       println("World!")
   }
   println("Hello,")
   Thread.sleep(2000L) // Block the main thread to keep JVM alive

   // async example
   val deferred = GlobalScope.async {
       delay(1000L)
       "Result"
   }
   runBlocking {
       println("Result: ${deferred.await()}")
   }
}
```

In this example, the `launch` coroutine will print "World!" after a delay of 1 second. The `async` coroutine will also delay for 1 second and then return "Result", which is printed after awaiting.

Coroutines offer a robust way to handle asynchronous programming in Kotlin, making your code simpler and easier to read.